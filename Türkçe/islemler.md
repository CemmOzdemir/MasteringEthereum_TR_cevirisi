# İŞLEMLER ➡️📖⬅️

_İşlemler_, Ethereum ağı tarafından iletilen ve Ethereum blok zincirine **kaydedilen**, harici olarak sahip olunan bir hesaptan (EOA'dan) kaynaklanan _imzalı mesajlardır_. Bu temel tanım, birçok **şaşırtıcı ve büyüleyici ayrıntıyı gizler**👻. İşlemlere  başka bir perspektiften bakınca, **bir durum değişikliğini tetikleyebilecek veya EVM'de bir sözleşmenin yürütülmesine(çalışmasına) neden olabilecek TEK şey olmalarıdır**.  Ethereum, global 🌎 bir tekil(singleton) durum makinesidir ve bu durum makinesinin durumunu değiştirerek "tik-tok⏰" olan  şeyler _işlemlerdir_.(Buradaki cümlede yazar Ethereum'u bir saate ⏰ benzeterek,geçen her saniyeyi işlemlere benzetmiştir.Saat sürekli ilerliyorsa işlemler sayesinde yani) 

**Sözleşmeler kendi başlarına çalışamazlar. Ethereum otonom olarak çalışmaz. Her şey bir işlemle başlar.** 💥🌍

Bu bölümde işlemleri inceleyeceğiz, nasıl çalıştıklarını göstereceğiz ve detayları inceleyeceğiz. Bu bölümde çoğu kişinin, **belki de bir cüzdan uygulaması yazdıkları için kendi işlemlerini düşük düzeyde yönetmekle ilgilenenlere yönelik olduğunu unutmayın**; Buradaki detayları ilginç bulacak olsanız da, mevcut cüzdan uygulamalarını kullanmaktan memnunsanız bunun için panik yapmanıza gerek yok!☕

--------------

## Bir İşlemin Yapısı
Öncelikle, Ethereum ağında [seri hale](https://en.wikipedia.org/wiki/Serialization)[kısaca serileştirme işlemi Yönteminde:veriyi bir yere istediğimiz formatta depolama/kaydetme vardır.] getirilip iletildiği için, bir işlemin temel yapısına bir göz atalım. Serileştirilmiş bir işlem alan her istemci ve uygulama, kendi **dahili veri yapısını kullanarak**, belki de ağ serileştirme işleminde mevcut olmayan meta verilerle birlite bunu bellekte saklayacaktır. **Ağ serileştirmesi, bir _işlemin tek standart biçimidir_**.

İşlem, **aşağıdaki verileri içeren** _serileştirilmiş bir ikili-sistemde(binary0️⃣1️⃣) mesajdır_ ⏬

* Nonce :

Mesajın tekrarını önlemek için kullanılan 🔄 ,EOA tarafından kaynaklanan,bir sıra numarasıdır

* Gaz fiyatı (price): ⛽

Oluşturucunun her bir gaz birimi için ödemeye hazır olduğu ether miktarı (wei cinsinden)

* Gaz sınırı (limit): 🚗

Oluşturucunun bu işlem için satın almak istediği maksimum gaz miktarı

* alıcı (Recipient): 👱‍♂️👱‍♀️

Hedef Ethereum adresi

* Değer (value): 💰

Hedefe gönderilecek ether miktarı (wei cinsinden)

* Veri(data): 💻

Değişken-uzunluklu binary veri yükü

* v,r,s :✒️

EOA'dan Kaynaklanan bir ECDSA dijital imzasının üç bileşenidir.


İşlem mesajının yapısı, özellikle Ethereum'da basit şekilde, baytları mükemmel bir şekilde veri serileştirme için oluşturulan Özyinelemeli Uzunluk Öneki(RLP-Recursive Length Prefix) kodlama şeması kullanılarak serileştirilir. 
Ethereum'daki tüm sayılar, uzunlukları _8 bitin katları olan_ [big-endian](https://en.wikipedia.org/wiki/Endianness) tamsayılar olarak kodlanmıştır.

aşağıdaki görseli Big-endian size yardımcı olması için bırakıyorum ⤵️:  

<img title="Big-endian"  src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/54/Big-Endian.svg/800px-Big-Endian.svg.png">


Alan etiketlerinin (alıcı, gaz limiti vb.) burada netlik amacıyla gösterildiğine, ancak RLP kodlu alan değerlerini içeren işlemin serileştirilmiş verilerin parçası olmadığına dikkat edin. **Genel olarak, RLP herhangi bir alan sınırlayıcı veya etiket içermez**. RLP'nin uzunluk öneki, her alanın uzunluğunu tanımlamak için kullanılır. Tanımlanan uzunluğun ötesindeki herhangi bir şey, yapıdaki bir sonraki alana aittir.

Bu iletilen gerçek **işlem yapısı olsa da**, çoğu dahili temsil ve kullanıcı arayüzü görselleştirme uygulamaları, bunu işlemden veya blok zincirinden türetilen _ek bilgilerle_ sunar.

Örneğin, adreste gönderen EOA'yı tanımlayan ➡️ "gönderen(from)" verisi olmadığını 🔴 fark edebilirsiniz. Bunun nedeni, EOA'nın genel anahtarının, ECDSA imzasının v,r,s bileşenlerinden türetilebilmesidir. Adres, sırayla, genel anahtardan türetilebilir. 
**"Kimden/from"** alanını **gösteren** bir işlem gördüğünüzde, bu, işlemi görselleştirmek için kullanılan **yazılım tarafından eklenmiştir**. İstemci yazılımı tarafından işleme sıklıkla eklenen diğer meta veriler, blok numarasını (bir kez çıkarıldıktan ve blok zincirine dahil edildikten sonra) ve bir işlem kimliğini (hesaplanan hash) içerir. Yine, bu veriler işlemden türetilir ve işlem mesajının kendisinin bir parçasını oluşturmaz.

-------------

## İşlemde Nonce

Nonce, bir işlemin en önemli ve en az anlaşılan bileşenlerinden biridir. Sarı Kağıttaki tanımı ise şöyledir: 

|
▶️nonce: Bir adresten gönderilen _işlem sayısına_ veya ilişkili koda sahip hesaplarda bu hesap tarafından yapılan _sözleşme oluşturma sayısına_ **eşit** bir skaler değerdir. 
|

Kesin bir ifadeyle, **nonce, kaynak adresin bir özelliğidir(attribute); yani, yalnızca gönderen adres bağlamında bir anlamı vardır**. Ancak nonce, bir hesabın blok zincirindeki durumunun bir parçası olarak **açıkça saklanmaz**. Bunun yerine, bir adresten kaynaklanan **onaylanmış işlemlerin sayısı sayılarak dinamik olarak hesaplanır.**

İşlem sayma nonce'sinin varlığının önemli olduğu _iki senaryo vardır_: 1️⃣ işlemlerin kullanılabilirlik özelliğini yaratma sırasına dahil edilmesi ve 2️⃣ işlem çoğaltma durumuna karşı Koruma 🛡️ sağlayan hayati özelliğidir. 
Bunların her biri için örnek bir senaryoya bakalım:⌨️

_1.senaryo_:

İki işlem yapmak istediğinizi düşünün. _6 etherlik_ önemli bir ödemeniz ve ayrıca _8 etherlik_ bir ödemeniz daha var. Önce 6 ether işlemini imzalar ve yayınlarsınız, çünkü bu daha _önemlidir_ ve ardından ikinci, 8 ether işlemini imzalar ve yayınlarsınız. Ne yazık ki, hesabınızın yalnızca _10 ether_ içerdiği gerçeğini gözden kaçırdınız, bu nedenle ağ her iki işlemi de kabul edemez: bunlardan biri başarısız 🔴 olur. Önce daha önemli olan 6 ether olanı gönderdiğiniz için, anlaşılır bir şekilde bunun geçmesini ve 8 etherin reddedilmesini beklersiniz. 

Ancak, Ethereum gibi merkezi olmayan bir sistemde düğümler(nodes), işlemleri her iki sırayla da alabilir; _belirli bir düğümde bir işlemin diğerinden önce kendisine yayılacağının garantisi yoktur_. Bu nedenle, bazı düğümlerin önce 6 ether işlemini, diğerlerinin ise önce 8 ether işlemini alması neredeyse **kesin olacaktır**. **Nonce olmadan,** hangisinin kabul edilip hangilerinin reddedileceği **rastgele olurdu**. 

Ancak, nonce dahil edildiğinde, gönderdiğiniz **ilk işlemin nonce değeri 3 diyelim,** 
8-ether işlemi sonraki nonce değerine sahip olacaktır (**yani 4**).
Bu nedenle, ilk alınsa(8 etherlik işlem) bile 0'dan 3'e kadar olmayan işlemler işlenene kadar bu işlem yok sayılır.Wow ucuz atlattık😸

----------------
_2.senaryo_ :

Şimdi 100 eterli bir hesabınız olduğunu hayal edin. Hoş değil mi! 🤑 

Gerçekten satın almak istediğiniz bir laptop 💻 olsun laptop  için ether ile ödeme kabul edecek birini çevrimiçi bulduğunuzu hayal edin. O kişiye 2 ether gönderirsiniz ve size yeni Laptopunuzu gönderirler.Hoooş🥳 . Bu 2-ether ödemesini yapmak için, hesabınızdan -----> hesabına(ether göndereceğimiz kişi) 2 ether gönderen bir işlem imzaladınız ve ardından doğrulanması ve blok zincirine dahil edilmesi için Ethereum ağına yayınladınız.🟢 

Şimdiii, **işlemde nonce değeri olmadan**, aynı adrese ikinci kez 2 ether gönderen ikinci bir işlem, _ilk işlemle tamamen aynı görünecektir_. Bu, Ethereum ağında işleminizi gören herkesin (yani alıcı veya hackerlar dahil herkes anlamına gelir), **orijinal işleminizi kopyalayıp yapıştırarak tüm etheriniz bitene kadar işlemi tekrar tekrar yaparak sömürmesi  anlamına gelir**. Ağa yeniden gönderiyor ve bununla birlikte, işlem verilerinde bulunan nonce değeri ile, aynı miktarda etheri aynı alıcı adresine birden çok kez gönderirken bile, her bir işlem aynı olmuyor.Kısaca benzersizdir(unique). Bu nedenle, işlemin bir parçası olarak artan ➕  **nonce'a sahip olduğunuzda, hiç kimsenin yaptığınız bir ödemeyi "kopyalaması" mümkün değildir.**

⭐Özetle, Bitcoin protokolünün “Harcanmamış İşlem Çıktısı” (UTXO) mekanizmasının aksine, hesap-tabanlı(account-based) bir protokol için nonce kullanımının gerçekten hayati olduğunu belirtmek önemlidir.


## Nonce'ları Takip Etme

Uygulama açısıdan nonce, bir hesaptan kaynaklanan onaylanmış (yani [On-chain](https://www.icrypex.com/tr/blog/on-chain-ve-off-chain-nedir-calisma-prensibi-nasildir)) **işlemlerin sayısının güncel bir sayısıdır.** Nonce'ın ne olduğunu bulmak için, örneğin web3 arayüzü aracılığıyla blok zincirini sorgulayabilirsiniz. Ropsten testnet'te ve Geth'te (veya tercih ettiğiniz web3 arayüzünde) bir JavaScript konsolu açın, ardından şunu yazın:

`web3.eth.getTransactionCount("0x9e713963a92c02317a681b9bb3065a8249de124f")`

`40`

🔍İPUCU :Nonce, sıfır tabanlı bir sayaçtır, yani ilk işlemin nonce değeri 0'dır. Bu örnekte, **40'lık bir işlem sayımız var**, yani 0'dan 39'a kadar nonces görüldü. Bir sonraki işlemin nonce'sinin 40 olması gerekecek.Bir Programlama diline hakimseniz anlamış olmalısnız.Anlamadıysanız benden size gelsin:[TIKLAYINIZ](https://www.bilgigunlugum.net/prog/cprog/2c_dizi)🔍 

Cüzdanınız, önettiği her adres için nonce'ların kaydını tutacaktır. _İşlemleri yalnızca tek bir noktadan başlattığınız sürece bunu yapmak oldukça basittir_. Diyelim ki kendi cüzdan yazılımınızı veya işlemleri başlatan başka bir uygulamayı yazıyorsunuz. Nonces'i nasıl takip edersiniz?🧐

**Yeni bir işlem oluşturduğunuzda, sıradakini bir sonraki nonce'a atarsınız.Ancak ONAYLAYANA kadar getTransactionCount toplamına dahil edilmeyecektir.
Programcı dostlarımızın anlıyacağı yoldan nonce++; ☣️ Ama Onaylamadan önce yapma**

⚠️ 
UYARI :Bekleyen işlemleri saymak için getTransactionCount() işlevini kullanırken dikkatli olun, çünkü arka arkaya birkaç işlem gönderirseniz bazı sorunlarla karşılaşabilirsiniz.⚠️

Aşağıdaki örnek koda birlikte bakalım: 

```
> web3.eth.getTransactionCount("0x9e713963a92c02317a681b9bb3065a8249de124f", \
"pending")
40
> web3.eth.sendTransaction({from: web3.eth.accounts[0], to: \
"0xB0920c523d582040f2BCB1bD7FB1c7C1ECEbdB34", value: web3.utils.toWei(0.01, "ether")});
> web3.eth.getTransactionCount("0x9e713963a92c02317a681b9bb3065a8249de124f", \
"pending")
41
> web3.eth.sendTransaction({from: web3.eth.accounts[0], to: \
"0xB0920c523d582040f2BCB1bD7FB1c7C1ECEbdB34", value: web3.utils.toWei(0.01, "ether")});
> web3.eth.getTransactionCount("0x9e713963a92c02317a681b9bb3065a8249de124f", \
"pending")
41
> web3.eth.sendTransaction({from: web3.eth.accounts[0], to: \
"0xB0920c523d582040f2BCB1bD7FB1c7C1ECEbdB34", value: web3.utils.toWei(0.01, "ether")});
> web3.eth.getTransactionCount("0x9e713963a92c02317a681b9bb3065a8249de124f", \
"pending")
41

```
🔍İPUCU :Bu kod örneklerini _Geth'in javascript konsolunda yeniden oluşturmaya çalışıyorsanız_, _web3.utils.toWei() yerine web3.toWei()_ kullanmalısınız. Bunun nedeni Geth'in web3 kütüphanesinin daha eski bir sürümünü kullanmasıdır.🔍(Şuan ne durumda bilmiyorum)


Gördüğünüz gibi, gönderdiğimiz ilk işlem, işlem sayısını 41'e çıkardı ve bekleyen işlemi gösterdi. Ancak art arda üç işlem daha gönderdiğimizde, `getTransactionCount` çağrısı onları saymadı. Mempool'da bekleyen üç tane olmasını bekleseniz bile, yalnızca 1️⃣ bir tane sayılır. Ağ iletişiminin yerleşmesine izin vermek için birkaç saniye beklersek, `getTransactionCount` çağrısı beklenen sayıyı döndürür. Ama arada sırada bekleyen birden fazla işlem varken bize faydası olmayabilir.


İşlemler oluşturan bir uygulama oluşturduğunuzda, bekleyen işlemler için `getTransactionCount`'a _güvenemez_. Yalnızca bekleyen ve onaylanan sayılar eşit olduğunda (tüm bekleyen işlemler onaylanırsa), nonce sayacınızı başlatmak için `getTransactionCount` çıktısına güvenebilirsiniz. Bundan sonra, her işlem onaylanana kadar işleminizdeki nonce'ı takip edin.

_Parity'nin JSON RPC arabirimi_, bir işlemde kullanılması gereken sonraki nonce değerini döndüren `parity_nextNonce `fonksiyonunu sunar. parity_nextNonce fonksiyonunu, birkaç işlemi onaylamadan hızlı bir şekilde art arda oluştursanız bile, nonce'ları doğru şekilde sayar:

```
$ curl --data '{"method":"parity_nextNonce", \
  "params":["0x9e713963a92c02317a681b9bb3065a8249de124f"],\
  "id":1,"jsonrpc":"2.0"}' -H "Content-Type: application/json" -X POST \
  localhost:8545

{"jsonrpc":"2.0","result":"0x32","id":1}

```
📝 NOT: Parity, JSON RPC arayüzüne erişmek için bir web konsoluna sahiptir, ancak burada ona erişmek için bir komut satırı HTTP istemcisi kullanıyoruz. 📝 

## Nonce'daki *Boşluk*, *Tekrarlama* ve *Onaylama*

İşlemleri programlı olarak oluşturuyorsanız, özellikle aynı anda birden fazla bağımsız işlemden yapıyorsanız, nonce'leri takip etmek önemlidir.

Ethereum ağı, işlemleri nonce'ye dayalı olarak sırayla işler. Bu, bir işlemi 0 olmayan ile iletir ve ardışık bir işlem  olmayan 2 ile (indeks[2] gibi düşünün)  iletirseniz, ikinci işlemin hiçbir bloğa dahil edilmeyeceği görürsünüz. Ethereum ağı eksik nonce'nin görünmesini beklerken(yani indeks[1] gibi düşünün), **mempool'da saklanacaktır.** _Tüm düğümler, eksik nonce'ın basitçe ertelendiğini ve nonce 2 ile yapılan işlemin sıranın dışından alındığını varsayacaktır_.

Daha sonra 1 no'lu eksik bir işlem iletirseniz, her iki işlem de (1 ve 2 no'lu) işlenir ve dahil edilir.(Tabii geçerliyse). 
Boşluğu doldurduğunuzda: **Ağ, mempool'da tuttuğu sıranın dışındaki işlemin madenciliğini  yapabilir**.

Bunun anlamı, sırayla birkaç işlem oluşturursanız ve _bunlardan biri resmi olarak herhangi bir bloğa dahil edilmezse_, sonraki tüm işlemler **"sıkışıp(stuck)" eksik nonce'yi bekler**. Bir işlem, geçersiz olduğundan veya yetersiz gaza sahip olduğundan, nonce dizisinde yanlışlıkla bir "_boşluk(gap)_" oluşturabilir. Tekrar harekete geçirmek için, **eksik nonce ile geçerli bir işlem iletmeniz gerekir**. "_Eksik(missing)_" nonce'a sahip bir işlem ağ tarafından doğrulandığında, **sonraki nonce'lara sahip tüm yayınlanmış işlemlerinin aşamalı olarak geçerli hale geleceğine dikkat etmelisiniz; bir işlemi "Tekrar Çağırmak 🔴" mümkün değildir !**

Öte yandan, örneğin **aynı nonce'ye sahip** ancak **farklı alıcılara veya değerlere sahip** iki işlemi ileterek bir nonce'yi yanlışlıkla çoğaltırsanız, bunlardan biri onaylanır 🟢 ve biri reddedilir🔴. Hangisinin onaylanacağı, onları alan ilk doğrulama düğümüne 🎛️ ulaşma sırasına göre belirlenecektir - yani, oldukça rastgele- olacaktır.

Gördüğünüz gibi, _nonce'ları takip etmek gereklidir ve uygulamanız bu süreci doğru yönetmezse sorunlarla karşılaşırsınız_. Ne yazık ki 🥶 , bir sonraki bölümde göreceğimiz gibi, bunu eş zamanlı yapmaya çalışıyorsak işler daha da zorlaşıyor.[Galiba 🍿[Taxi Driver-1976](https://www.imdb.com/title/tt0075314/) Travis'in uyku problemi çökecek gibi üzerimize 😄⏬ Yine sizlere kült bir filmi bıraktım.🚕]

<img title="Taxi Driver-1976"  src="https://static1.srcdn.com/wordpress/wp-content/uploads/2020/02/Travis-in-Taxi-Driver-3.jpg?q=50&fit=contain&w=1500&h=&dpr=1.5">

## Eşzamanlılık, İşlem Başlangıcı ve Nonce'lar

Eşzamanlılık, bilgisayar biliminin karmaşık  yönlerinden biridir ve özellikle Ethereum gibi merkezi olmayan ve dağıtılmış gerçek zamanlı sistemlerde bazen beklenmedik bir şekilde ortaya çıkar.

Basit bir ifadeyle, eşzamanlılık: _Birden fazla bağımsız sistem tarafından eşzamanlı hesaplamaya sahip olduğunuz zamandır_. Bunlar aynı programda (örneğin çoklu kullanım), aynı CPU'da (örneğin çoklu işlem) veya farklı bilgisayarlarda (örneğin dağıtılmış sistemler) olabilir. Ethereum, tanımı gereği, işlemlerin (örneğin düğümler, istemciler, DApp'ler) eşzamanlılığına izin veren ancak fikir birliği(consensus) yoluyla tek bir durumu dayatan bir sistemdir.

Şimdiii, _aynı adres veya adreslerden_ işlem üreten birden fazla _bağımsız cüzdan uygulamanız_ olduğunu hayal edin.

Böyle bir duruma bir örnek, borsanın 🔥sıcak cüzdanından (anahtarları çevrimiçi olarak saklayan bir cüzdan) **para çekme işlemleri** olabilir. 

İdeal olarak, bir darboğaz veya tek bir başarısızlık noktası haline gelmemesi için _birden fazla bilgisayarla, para çekme işlemine(withdraw()) sahip olmak istersiniz._ Bununla birlikte, para çekme üreten birden fazla bilgisayara sahip olmak, en azından nonce'ların seçimi olmak üzere bazı zorlu eşzamanlılık sorunlarına yol açacağından, bu hızla sorunlu🙀 bir hal alır. Aynı sıcak cüzdan hesabından işlem oluşturan, ❓imzalayan ve yayınlayan birden fazla bilgisayar nasıl koordine(sekron) olur? 

İşlemleri imzalayan bilgisayarlara ilk gelen-alır(first-come first-served) esasına göre nonce atamak için tek bir bilgisayar kullanabilirsiniz. Ancak, bu bilgisayar artık _tek bir başarısızlık noktasıdır._ Daha da kötüsü, 🙀 birden fazla nonce atanırsa ve bunlardan biri **hiç kullanılmazsa** (yani bilgisayarın o nonce ile işlemi işlemesinde bir hata olması nedeniyle), sonraki tüm işlemler takılıp(sıkışır/stuck) kalır.


Başka bir yaklaşım: işlemleri oluşturmak, onlara bir nonce atamakla mümkün (ve bu nedenle onları imzasız bırakmak  *⭐ ⚠️nonce'nin işlem verilerinin ayrılmaz bir parçası olduğunu ve bu nedenle işlemi doğrulayan **dijital imzaya dahil edilmesi gerektiğini** unutmayın*) olacaktır. Daha sonra bunları imzalayan ve aynı zamanda nonce'ların kaydını tutan **tek bir düğümde sıralayabilirsiniz**. Yine de, bu süreçte bir **tıkanıklık noktası** olacaktır: nonces'ların imzalanması ve izlenmesi, işleminizin veri yığını altında sıkışık(stuck) hale gelmesi muhtemel olan kısmıdır, oysa imzasız işlemin oluşturulması, gerçekten yapmadığınız kısımdır..Biraz eşzamanlı olurdu, ancak sürecin kritik bir bölümünde eksiklik olurdu.

Sonuç olarak, bu eşzamanlılık sorunları, bağımsız süreçlerde hesap bakiyelerini ve işlem onaylarını **takip etmenin zorluğuna ek olarak**, çoğu uygulamayı eşzamanlılıktan kaçınmaya ve bir borsadaki tüm para çekme işlemlerini **tek bir işlemle işlemek** veya birden fazla işlem kurmak gibi **darboğazlar yaratmaya** ya da para çekme işlemleri için tamamen bağımsız çalışabilen ve yalnızca aralıklı olarak yeniden dengelenmesi gereken birden fazla sıcak cüzdan kurmaya zorlar.🤯

----------

## İşlemde Gaz ⛽💸

Daha önceki bölümlerde gaz hakkında biraz konuşmuştuk ve şimdi bu bölümünde daha ayrıntılı olarak tartışıyoruz. Ancak, bir işlemin `gasPrice`  ve `gasLimit` bileşenlerinin rolüyle ilgili bazı temel bilgileri ele alalım.

Gaz, Ethereum'un yakıtıdır.⛽ Gaz ether demek değildir - _Ethere karşı kendi döviz kuruna sahip ayrı bir sanal para birimidir_. 
Ethereum, **bir işlemin kullanabileceği kaynak miktarını kontrol etmek için gaz kullanır**, çünkü dünya çapında binlerce bilgisayarda işlenecektir. Açık uçlu (Turing-complete) hesaplama modeli, DoS saldırılarından veya yanlışlıkla kaynak tüketen işlemlerden kaçınmak için bir tür ölçüm gerektirir.Bu yüzden gaz kullanırız.

Bu, ether değerindeki hızlı değişimlerle birlikte ortaya çıkabilecek dengesizliği korumak ve ayrıca gazın ödediği çeşitli kaynakların maliyetleri arasındaki önemli ve hassas oranları yönetmenin bir yolu olarak _etherden ayrıdır_. (yani, hesaplama, bellek ve depolama).

Bir işlemdeki `gasPrice` alanı, **işlemi oluşturanın gaz karşılığında ödemeye hazır oldukları fiyatı belirlemesine olanak tanır**. Fiyat, gaz birimi başına _wei_ cinsinden ölçülür.(Geçmiş bölümlerde bunu görmüştük.)

🔍İPUCU---> Popüler olan [ETH Gas Station](https://ethgasstation.info/) web sitesi,size Ethereum ana ağı için mevcut gaz fiyatları ve diğer ilgili gaz ölçümleri hakkında bilgi sağlar. 🤓 Benden sizlere küçük bir ipucu daha artık yazmış olduğunuz akıllı sözleşmelerde ne kadar gas tükettiğini bizzat yazmış olduğunuz özelliklerin yanında görüyorsunuz. 

Cüzdanlar, işlemlerin daha hızlı onaylanmasını sağlamak için oluşturdukları işlemlerde _gasPrice'ı ayarlayabilir_. gasPrice ne kadar ⬆️yüksek olursa, işlemin onaylanması o kadar hızlı olur🦅.Tersine, daha düşük öncelikli işlemler daha düşük bir fiyat taşıyabilir ve bu da daha _yavaş onaya_ neden olabilir. gasPrice'ın ayarlanabileceği minimum değer **sıfırdır**, bu da ücretsiz bir işlem anlamına gelir.🤥 Bir blokta yer talebinin düşük olduğu dönemlerde, bu tür işlemler çok iyi madenciliğe maruz kalabilir.

📝 NOT----> Kabul edilebilir minimum gasPrice sıfırdır. Bu, cüzdanların tamamen ücretsiz işlemler oluşturabileceği anlamına gelir. Kapasiteye bağlı olarak, bunlar hiçbir zaman onaylanmayabilir, ancak protokolde ücretsiz işlemleri yasaklayan hiçbir şey yoktur. Ethereum blok zincirine başarıyla dahil edilen bu tür işlemlerin birkaç örneğini bulabilirsiniz. 📝

Web3 arayüzü, birkaç blokta bir ortalama fiyat hesaplayarak bir gasPrice önerisi sunar (bunu yapmak için truffle konsolunu veya herhangi bir JavaScript web3 konsolunu kullanabiliriz):

```
> web3.eth.getGasPrice(console.log)
> null BigNumber { s: 1, e: 10, c: [ 10000000000 ] }
```

Gazla ilgili ikinci önemli alan `gasLimit` 'tir. Basit bir ifadeyle, _gasLimit, işlemi yapanın işlemi tamamlamak için satın almak istediği maksimum gaz birimi sayısını verir_. Basit ödemeler için, yani bir EOA'dan başka bir EOA'ya ether aktaran işlemler için, gereken gaz miktarı **21.000 (wei) gaz birimi** olarak sabitlenmiştir. Bunun ne kadar ethere mal olacağını hesaplamak için, ödemeye hazır olduğunuz `gasPrice` ile 21.000'i çarparsınız(✖️).Daha fazla detay için [bakınız](https://ethereum.org/en/developers/docs/gas/#what-is-gas-limit) 

Örneğin:

```
> web3.eth.getGasPrice(function(err, res) {console.log(res*21000)} )
> 210000000000000
```

İşleminizin gönderim(alıcı) yeri sözleşme adresi(address account) ise, ihtiyaç duyulan gaz miktarı _tahmin edilebilir_ ancak _kesin olarak belirlenemez_.Bunun nedeni, bir sözleşmenin, farklı toplam gaz maliyetleriyle, farklı yürütme yollarına yol açan **farklı koşulları değerlendirebilmesidir**. Sözleşme, kontrolünüz dışındaki ve tahmin edilemeyen koşullara bağlı olarak yalnızca basit bir hesaplama veya daha karmaşık bir hesaplama yürütebilir. Bunu göstermek için bir örneğe bakalım:⬇️ 

Her çağrıldığında bir sayacı artıran (++) ve çağrı sayısına eşit sayıda belirli bir döngüyü yürüten bir akıllı sözleşme yazabiliriz. Belki 100. çağrımda piyango🐦 gibi özel bir ödül veren bir sözleşme olsun🤑, ancak ödülü hesaplamak için **ek hesaplama yapması gerekir**. Sözleşmeyi 99 kez çağrırsanız **bir şey olur**, ancak 100. çağrıda **çok FARKLI bir şey olur**. Bunun için _ödeyeceğiniz gaz miktarı, işleminiz bir bloğa dahil edilmeden önce bu işlevi kaç işlemin çağırdığına bağlıdır_. Belki de tahmininiz 9️⃣9️⃣. işlem olmasına dayanıyor, ancak işleminiz onaylanmadan hemen önce başkası 99. kez işlemi çağrıyor. Artık çağrıyı yapan 1️⃣0️⃣0️⃣.işlemin sahibsiniz ve hesaplama gücünüz(ve gaz maliyeti) çok daha yüksek bir orana geldi.

Ethereum'da kullanılan yaygın bir benzetmeyi kullanarak daha rahat anlayabiliriz: 

`gasLimit`'i arabanızdaki _yakıt deposunun kapasitesi_ 🧴(60 litre olsun) olarak düşünebilirsiniz.Arabayı _işlem_ olarak düşünün🚙. Depoyu yolculuk için ihtiyaç duyacağını düşündüğünüz kadar gazla doldurursunuz.⛽(Bu da işleminizi doğrulamak için _gereken hesaplamayı temsil eder_).

Miktarı bir dereceye kadar _tahmin edebilirsiniz_, ancak yolculuğunuzda yakıt tüketimini artıran bir yönlendirme (daha karmaşık bir yürütme yolu)🛣️ gibi beklenmeyen değişiklikler olabilir.

Bununla birlikte, bir _yakıt deposuna benzetme_ biraz yanıltıcıdır☹️. 

Aslında,  ne kadar **gaz kullandığınıza bağlı olarak**, _yolculuk TAMAMLANDIKTAN SONRA_ gazı aldığınız bir Benzinilik şirketinin hesabına  ödemek gibidir.(Opet kartınız 💳 ile depoyu doldurdunuz ama ödeme yapmadınız.Gittiğiniz yere Ulaştıktan sonra ne kadar yaktıysanız şirkete ödediğiniz miktar gibi düşünün.Belki trafikte kalacaksınız, 🚥 belkide çok hızlı bir şekilde motorcu 🏍️ dostlarımız gibi hızlıca ulaşım sağlayacaksınız.)

İşleminizi ilettiğinizde, ilk doğrulama adımlarından biri, kaynaklandığı hesabın `gasPrice * gasLimit`'i ödemek için _yeterli ethere sahip olup olmadığını kontrol etmektir_ . Ancak, _işlem tamamlanana kadar tutar hesabınızdan gerçekten düşülmez._ Yalnızca işleminiz tarafından tüketilen gaz için _faturalandırılırsınız_ 📑, ancak işleminizi göndermeden önce ödemek istediğiniz **maksimum miktar** için yeterli bakiyeniz olmalıdır.

## İşlemde Alıcı(recipient) 👳‍♂️

Bir işlemin alıcısı, alıcı alanında belirtilir. Bu, **20 baytlık bir Ethereum adresi içerir**. Adres, bir _EOA_ veya bir _sözleşme adresi_ olabilir.

Ethereum bu alanın daha fazla doğrulamasını yapmaz. _Herhangi bir 20 baytlık değer geçerli kabul edilir_. 20 baytlık değer, karşılık gelen bir özel anahtarı _olmayan_ 🔴 veya karşılık gelen bir sözleşme _olmayan_ bir adrese 🔴 karşılık Geliyorsa, **İŞLEM HALA GEÇERLİDİR 🟢**. 
⭐Ethereum'un bir adresin var olan bir genel anahtardan (ve dolayısıyla özel bir anahtardan) doğru bir şekilde türetilmiş olup olmadığını bilmesinin bir yolu yoktur.

⚠️UYARII--->Ethereum protokolü, işlemlerde alıcı adreslerini doğrulamaz. Karşılık gelen özel anahtarı veya sözleşmesi olmayan bir adrese gönderebilir, böylece etheri "yakarak" sonsuza kadar harcanamaz hale getirebilirsiniz. Doğrulama, kullanıcı arayüzü seviyesinde yapılmalıdır.⚠️

Bir işlemin yanlış adrese gönderilmesi muhtemelen gönderilen etheri yakacak ve onu sonsuza kadar erişilemez (harcanamaz) hale getirecektir, çünkü çoğu adresin bilinen bir özel anahtarı yoktur ve bu nedenle onu harcamak için hiçbir imza üretilemez. _Adres doğrulamasının kullanıcı arayüzü seviyesinde gerçekleştiği varsayılır_ (bkz. Bu linki size ben bırakıyorum EIP'lere buradan bakabilirsiniz ▶️ [EIP55](https://eips.ethereum.org/EIPS/eip-55). 

Aslında, ether yakmak 🔥 için bir takım geçerli nedenler vardır : Örneğin, ödeme kanallarında ve diğer akıllı sözleşmelerde hile yapılmasını caydırıcı hale getirme gibi.

## İşlem Değeri & Verisi (Value & Data) :
Bir işlemin ana "[payload(yük)](https://tr.wikipedia.org/wiki/Payload_(bilgisayar))" iki alanda bulunur: **1️⃣ DEĞER(VALUE) ve 2️⃣VERİ(DATA)**. 

İşlemler: 
* hem değere hem de veriye 
* yalnızca değere, 
* yalnızca veriye 
* veya ne değere ne de veriye sahip olabilir. 

Dört kombinasyonun tümü geçerlidir.✔️

Yalnızca **değeri olan bir işlem bir ödemedir**. Yalnızca **veri içeren bir işlem bir çağrıdır**. Hem değeri hem de verisi olan bir işlem hem bir ödeme hem de bir çağrıdır. Ne değeri ne de verisi olan bir işlem ise  muhtemelen sadece bir _gaz israfıdır_! Ama yine de mümkün.

0️⃣Bu kombinasyonların hepsini deneyelim. Denememizin(Demo) daha kolay okunmasını sağlamak için öncelikle cüzdanımızdan kaynak(gönderen) ve hedef(alıcı) adresleri ayarlayacağız:

```
src = web3.eth.accounts[0];
dst = web3.eth.accounts[1];
```

1️⃣ İlk işlemimiz yalnızca bir değer (ödeme) içerir ve veri yükü içermez:

```
web3.eth.sendTransaction({from: src, to: dst, \
  value: web3.utils.toWei(0.01, "ether"), data: ""}); // data kısmı bakınız boş
```

Cüzdanımız, değeri olan ancak veri içermeyen bir işlemi gösteren Parity cüzdanında gösterildiği gibi gönderilecek değeri belirten bir onay ekranı gösterir.

<img title="sadeceDeger"  src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/parity_txdemo_value_nodata.png">

2️⃣ Sonraki örnek hem bir değeri hem de bir veri yükünü belirtir:

```
web3.eth.sendTransaction({from: src, to: dst, \
  value: web3.utils.toWei(0.01, "ether"), data: "0x1234"});
```
<img title="hemDegerHemVeri"  src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/parity_txdemo_value_data.png">

3️⃣ Sadece Veriyi içeren örneğimiz ise(ayrıca değer 0) :

`web3.eth.sendTransaction({from: src, to: dst, value: 0, data: "0x1234"});`

Cüzdanımız, Parity cüzdanında gösterildiği gibi sıfır değeri ve veri yükünü gösteren bir onay ekranı gösterir, değeri olmayan bir işlemi gösterir, sadece veriyi gösterir.

<img title="sadeceVeri"  src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/parity_txdemo_novalue_data.png">

4️⃣ Son olarak işlem ne gönderilecek bir değer ne de bir veri yükü içerir:

`web3.eth.sendTransaction({from: src, to: dst, value: 0, data: ""}));`

<img title="Herikisideyok"  src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/parity_txdemo_novalue_nodata.png">

## Sözleşmelere ve EOA'lara Değer Aktarımı 💸

Bir değer içeren bir Ethereum işlemi oluşturduğunuzda, bu bir ödemeye eşdeğerdir. Bu tür işlemler, varış adresinin bir sözleşme olup olmamasına bağlı olarak farklı davranır.

EOA adresleri için veya daha doğrusu blok zincirinde bir sözleşme olarak işaretlenmemiş herhangi bir adres için, Ethereum, gönderdiğiniz değeri adresin bakiyesine ekleyerek bir durum değişikliği kaydedecektir. Adres daha önce görülmediyse, istemcinin durumunun içine eklenir ve bakiyesi, ödemenizin değerine göre başlatılır.

Hedef adres (to)-----> bir sözleşme ise, EVM sözleşmeyi çalıştıracak ve işleminizin veri yükünde belirtilen fonksiyonu çağırmaya çalışacaktır. İşleminizde veri yoksa, EVM bir **fallback fonksiyonu** çağıracak ve bu fonksiyon ödenebilirse, daha sonra ne yapılacağını belirlemek için bunu çalışıracaktır.fallback funct'da _kod yoksa, işlemin durumu_, tıpkı bir cüzdana yapılan ödeme gibi, **sözleşmenin bakiyesini artırmak olacaktır**. fallback fonsiyonu veya non-payable fallback fonksiyonu yoksa, işlem geri alınır.

Bir sözleşme, bir fonksiyon çağrıldığında veya bir fonksiyonda kodlanmış koşullar tarafından belirlendiği şekilde hemen bir (istisna döndürerek) gelen ödemeleri reddedebilir.🔴 

fonksyion başarılı bir şekilde sona ererse (istisnasız,hepsinde geçerli), sözleşmenin durumu, sözleşmenin ether bakiyesindeki bir artışı yansıtacak şekilde güncellenir. 📈


## EOA veya Sözleşmeye Veri Yükü(payload) Aktarma ➡️

İşleminiz veri içerdiğinde, _büyük olasılıkla bir sözleşme adresine yönlendirilir_. Bu, bir EOA'ya veri yükü _gönderemeyeceğiniz anlamına gelmez_.Bu, Ethereum protokolünde tamamen geçerlidir. Ancak bu durumda, verilerin yorumlanması **EOA'ya erişmek için kullandığınız cüzdana bağlıdır**. 

Ethereum protokolü tarafından görmezden gelinir ve **Çoğu cüzdan, kontrol ettikleri bir EOA'ya yapılan bir işlemde alınan verileri de yok sayar**. Gelecekte, cüzdanların verileri sözleşmeler gibi yorumlamasına izin veren ve böylece işlemlerin kullanıcı cüzdanlarında çalışan işlevleri başlatmasına izin veren standartların ortaya çıkması olasıdır. _Kritik fark, bir EOA tarafından veri yükünün herhangi bir yorumunun, bir sözleşme yürütmesinin aksine Ethereum'un fikir birliği(consensus) kurallarına tabi olmamasıdır._

Şimdilik, işleminizin bir sözleşme adresine veri teslim ettiğini varsayalım. 👍 Bu durumda, veriler **EVM tarafından bir sözleşme çağrısı** olarak yorumlanacaktır. Çoğu sözleşme, bu verileri daha spesifik olarak bir fonksiyon çağrısı olarak kullanır, adlandırılmış fonksiyonlar çağırır ve kodlanmış argümanları fonksiyona iletir.

ABI uyumlu bir sözleşmeye gönderilen _veri yükü_ (tüm sözleşmelerin öyle olduğunu varsayabilirsiniz), aşağıdakilerin hexadecimal şekilde serileştirilmiş haliyle kodlamasıdır:

* A function selector(Bir Fonksiyon Seçicisi)

Fonksiyonun prototipinin Keccak-256 hash fonksiyonun ilk 4 baytını temsil eder. Bu, sözleşmenin hangi işlevi çağırmak istediğinizi açık bir şekilde tanımlamasını sağlar.

* The function arguments(Fonksiyonun argümanları)

ABI belirtiminde tanımlanan, çeşitli temel türlerin kurallarına göre kodlanmış fonksiyonun bağımsız değişkenlerini ifade eder.

💳 Geçmiş bölümlerdeki faucet(musluk) sözleşmemizdeki withdraw() fonksiyonunu nasıl tanımladığımızı hatırlayalım:

`function withdraw(uint withdraw_amount) public {`

**Bir fonksiyonun prototipi, parantez içine alınmış ve virgülle ayrılmış olarak, fonksiyonun adını, ardından argümanlarının her birinin veri türlerini içeren dize olarak tanımlanır**. Buradaki fonksiyon adı withdraw'dur ve bir uint olan (uint256 için kısa gösterimidir) _tek bir argüman alır_, bu nedenle withdraw()'un prototipi şöyle olur:

`withdraw(uint256)`

Bu dizenin Keccak-256 hash değerini (karmasını) hesaplayalım:

```
> web3.utils.sha3("withdraw(uint256)");
'0x2e1a7d4d13322e7b96f9a57413e1525c250fb7a9021cf91d1540d5b69f16a49f'
```
Hash'ın ilk 4 baytı `0x2e1a7d4d`'dir. Bu, sözleşmeye hangi işlevi çağırmak istediğimizi söyleyen "fonksiyon seçici(selector)" değerimizdir.

Ardından, `withdraw_amaount `argümanı olarak iletilecek bir değer hesaplayalım. 0.01 ether çekmek istiyoruz. Bunu, wei cinsinden onaltılık seri hale getirilmiş big-endian uint256-bit tamsayıyla kodlayalım:

```
> withdraw_amount = web3.utils.toWei(0.01, "ether");
'10000000000000000'
> withdraw_amount_hex = web3.utils.toHex(withdraw_amount);
'0x2386f26fc10000'
```
Şimdi, fonksiyon seçiciyi miktara ekliyoruz :

`2e1a7d4d000000000000000000000000000000000000000000000000002386f26fc10000`

Bu, işlemimizin _veri yüküdür(data payload)_, `withdraw`'u çağırır ve `withdraw_amaount` olarak 0,01 ether talep eder.


## Özel İşlem: Sözleşme Oluşturma 📋🖋️

Bahsetmemiz gereken özel bir durum, blok zinciri üzerinde _yeni bir sözleşme oluşturan ve onu gelecekte kullanmak üzere dağıtan bir işlemdir_. Sözleşme oluşturma işlemleri,**0️⃣sıfır adres adı verilen özel bir varış(alıcı) adresine gönderilir**; bir _sözleşme kayıt işlemindeki alıcı(to) alanı_ **0x0** adresini içerir. Bu adres ne bir EOA'yı 🔴(karşılık gelen özel-genel anahtar çifti yoktur ✖️) ne de bir sözleşmeyi temsil🔴 eder. Asla _ether harcayamaz veya bir işlem başlatamaz_. Yalnızca "bu sözleşmeyi oluştur" özel anlamı ile bir varış noktası olarak kullanılır.

Sıfır adres sadece sözleşme oluşturmaya yönelik olsa da bazen çeşitli adreslerden ödemeler alır. Bunun iki açıklaması vardır: 1️⃣ ya kaza eseridir ve bu eter kaybına neden olur. 💸 
2️⃣ ya da kasıtlı bir ether 🔥 yakma işlemidir.(eter'i asla harcanamayacak bir adrese göndererek kasıtlı olarak yok etme durumudur. Aklınıza kim geldi? Tabiiki de büyük adam [JOKER](https://www.youtube.com/watch?v=JVL3Kz_x2MA) 🤡).

<img title="HLedger_abim_enİyisiydi"  src="https://twinfinite.net/wp-content/uploads/2016/01/burningmoney.jpg">

Ancak, kasıtlı bir ether yakma işlemi yapmak istiyorsanız, niyetinizi ağa belirtip , bunun yerine özel olarak tasarlanmış yakma 🔥 adresini kullanmalısınız:

`0x000000000000000000000000000000000000dEaD`

⚠️UYARI---> Belirlenen yanma adresine gönderilen herhangi bir ether harcanamaz hale gelecek ve sonsuza kadar kaybolacaktır.

Bir sözleşme oluşturma işleminin yalnızca, _sözleşmeyi oluşturacak derlenmiş bayt kodunu(compiled bytecode)_ içeren bir _veri yükü_ içermesi gerekir. Bu işlemin tek etkisi sözleşmeyi oluşturmaktır. Yeni sözleşmeyi, bir başlangıç bakiyesi ile ayarlamak istiyorsanız, _değer alanına bir eter tutarı ekleyebilirsiniz, ancak bu tamamen isteğe bağlıdır_. Sözleşme oluşturma adresine **veri yükü olmadan  bir değer (ether) gönderirseniz**, etkisi bir yanma adresine göndermeyle aynı sonuçaları doğurur.🙀 

Örnek olarak Giriş bölümünde  kullanılan **Faucet.sol** sözleşmesini data payload'undaki sözleşme ile sıfır adresine manuel olarak bir işlem oluşturabiliriz. Sözleşmenin bir  _derlenmiş baytkodu_ ile temsil edilmesi gerekir. Bu, _Solidity derleyicisi_ ile yapılabilir:

```
$ solc --bin Faucet.sol

Binary:
6060604052341561000f57600080fd5b60e58061001d6000396000f30060606040526004361060...
```
Aynı bilgiler Remix çevrimiçi derleyicisinden de elde edilebilir.

Şimdi işlemi oluşturabiliriz:

```
> src = web3.eth.accounts[0];
> faucet_code = \
  "0x6060604052341561000f57600080fd5b60e58061001d6000396000f300606...f0029";
> web3.eth.sendTransaction({from: src, to: 0, data: faucet_code, \
  gas: 113558, gasPrice: 200000000000});

"0x7bcc327ae5d369f75b98c0d59037eec41d44dfae75447fd753d9f2db9439124b"
```
Sıfır adresli sözleşme oluşturma durumunda bile her zaman bir (to)🚩 parametresi belirtmek _iyi_ bir uygulamadır, çünkü ether'inizi yanlışlıkla 0x0'a göndermenin ve sonsuza kadar kaybetmenin maliyeti çok yüksektir. Ayrıca bir _gasPrice ve gasLimit_ belirtmelisiniz.

Sözleşmeyi mining ettikten sonra, sözleşmenin başarıyla çıkarıldığını gösteren Etherscan blok gezgininde görebiliriz. ⤵️


<img title="0x0adressEtherscan"  src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/contract_published.png">

Sözleşme hakkında bilgi almak için işlemin **makbuzuna(receipt)**📋 bakabiliriz** ⏬

```
> web3.eth.getTransactionReceipt( \
  "0x7bcc327ae5d369f75b98c0d59037eec41d44dfae75447fd753d9f2db9439124b");

{
  blockHash: "0x6fa7d8bf982490de6246875deb2c21e5f3665b4422089c060138fc3907a95bb2",
  blockNumber: 3105256,
  contractAddress: "0xb226270965b43373e98ffc6e2c7693c17e2cf40b",
  cumulativeGasUsed: 113558,
  from: "0x2a966a87db5913c1b22a59b0d8a11cc51c167a89",
  gasUsed: 113558,
  logs: [],
  logsBloom: \
    "0x00000000000000000000000000000000000000000000000000...00000",
  status: "0x1",
  to: null,
  transactionHash: \
    "0x7bcc327ae5d369f75b98c0d59037eec41d44dfae75447fd753d9f2db9439124b",
  transactionIndex: 0
}


```

Bu, önceki bölümde gösterildiği gibi, sözleşmeye para göndermek ve sözleşmeden para almak için kullanabileceğimiz sözleşmenin adresini içerir:

```
> contract_address = "0xb226270965b43373e98ffc6e2c7693c17e2cf40b"
> web3.eth.sendTransaction({from: src, to: contract_address, \
  value: web3.utils.toWei(0.1, "ether"), data: ""});

"0x6ebf2e1fe95cc9c1fe2e1a0dc45678ccd127d374fdf145c5c8e6cd4ea2e6ca9f"

> web3.eth.sendTransaction({from: src, to: contract_address, value: 0, data: \
  "0x2e1a7d4d000000000000000000000000000000000000000000000000002386f26fc10000"});

"0x59836029e7ce43e92daf84313816ca31420a76a9a571b69e31ec4bf4b37cd16e"

```
Bir süre sonra, para gönderme ve alma işlemlerinin gösterimi(her iki işlem de) Etherscan'da görünür.

<img title="etherscan_confirmed"  src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/published_contract_transactions.png">

---------------------------------------------------

# Dijital imzalar 🔏
Şimdiye kadar, dijital imzalar hakkında herhangi bir ayrıntıya girmedik. Bu bölümde, dijital imzaların nasıl çalıştığına ve özel anahtarı açıklamadan(yani ifşa etmeden) bir özel anahtarın sahipliğinin kanıtını ⚖️ sunmak için nasıl kullanılabileceğine bakacağız.

## Eliptik Eğri Dijital İmza Algoritması (ECDSA)
Ethereum'da kullanılan dijital imza algoritması, Eliptik Eğri Dijital İmza Algoritmasıdır(ECDSA). 

📌[Kriptografi](https://github.com/CemmOzdemir/MasteringEthereum_TR_cevirisi/blob/develop/Türkçe/Kriptografi.md#eliptik-eğri-kriptografisinin-açıklaması) bölümünde açıklandığı gibi, eliptik eğri özel-genel anahtar çiftlerine dayanır.

Dijital imza, Ethereum'da üç amaca hizmet eder: 

1️⃣.---> Dijital imza, bir Ethereum hesabının sahibi olan _özel anahtarın sahibinin_, ether harcamasına veya bir sözleşmenin çalıştırılmasına izin verdiğini kanıtlar.

2️⃣.---> İnkar-edilememezliği garanti eder: Yetkinin kanıtı su götürmez bir gerçektir. 

3️⃣.---> Dijital imza, işlem verilerinin işlem imzalandıktan sonra hiç kimse tarafından değiştirilmediğini ve değiştirilemeyeceğini kanıtlar.

**Wikipedia'nın Dijital İmza Tanımı**:

Dijital imza; dijital mesajların veya belgelerin gerçekliğini sunmak için _matematiksel bir şemadır_. Geçerli bir dijital imza, alıcıya mesajın bilinen bir gönderici tarafından yaratıldığına **(kimlik doğrulama)** 🗃️ , gönderenin mesajı gönderdiğini inkar edemeyeceğine **(reddedemezlik👴)** ve mesajın aktarım sırasında değiştirilmediğine **(bütünlük)** inanması için neden verir.[Wikiyi sizin için buraya bırakıyorum.](https://en.wikipedia.org/wiki/Digital_signature)


## Dijital İmzalar Nasıl Çalışır?
Dijital imza, **iki bölümden** oluşan matematiksel bir şemadır. 1️⃣ _İlk kısım_, bir **mesajdan (bizim durumumuzda _işlem_ yani) özel(private) bir anahtar(imza anahtarı 🔑) kullanarak** bir imza oluşturmak için bir algoritmadır. 2️⃣_İkinci kısım_, herkesin imzayı, **yalnızca mesaj ve bir genel(public) 🔐 anahtar kullanarak** doğrulamasını sağlayan bir algoritmadır.

## Dijital imza oluşturma
Ethereum'un ECDSA uygulamasında, **imzalanan "mesaj"---->işlemdir** veya daha doğrusu işlemden _RLP kodlu verilerin Keccak-256 hash değeridir_. **İmza anahtarı, EOA'nın özel anahtarıdır**.----> Sonuç imzadır:

S i g = F sig ( F keccak256 ( m ) , k ) ---> Buradaki ifadeler şunlardır :
  
  * k ➡️ özel anahtarı yani imza anahtarını temsil eder.
  * m ➡️ RLP kodlu işlemdir.
  * F<sub>keccak256</sub> ➡️ Keccak-256 karma işlevidir.
  * F<sub>sig</sub> ➡️ imzalama algoritmasıdır.
  * Sig ➡️ ,elde edilen imzadır.
  
F<sub>sig</sub> fonksiyonu, genellikle **r** ve **s** olarak adlandırılan iki değerden oluşan bir Sig imzası üretir:

`S i g = ( r , s )`

## İmzanın Doğrulanması ✔️

İmzayı doğrulamak için imza (`r ve s`), serileştirilmiş işlem ve imzayı oluşturmak için kullanılan özel anahtara karşılık gelen genel(public) bir anahtar olmalıdır. Esasen, bir imzanın doğrulanması "yalnızca bu genel(public) anahtarı oluşturan özel anahtarın sahibinin bu işlemde bu imzayı üretmiş olabileceği" anlamına gelir.

İmza doğrulama algoritması mesajı, (yani, işlemin bir karmasını(hash değerini)) imzalayanın genel(public) anahtarını ve imzayı (r ve s değerlerini) alır ve imza bu mesaj ve genel anahtar için geçerliyse `True`🟢 değerini döndürür.

## ECDSA Matematiği 🤓
Daha önce bahsedildiği gibi, imzalar, r ve s olmak üzere iki değerden oluşan bir imza üreten F<sub>sig</sub> matematiksel işlevi tarafından oluşturulur. Bu bölümde F<sub>sig</sub> fonksiyonuna daha detaylı bakacağız.

İmza algoritması önce kriptografik olarak güvenli bir şekilde kısa ömürlü **(geçici) bir özel anahtar üretir**. Bu geçici anahtar, gönderenin gerçek özel anahtarının Ethereum ağındaki imzalı işlemleri izleyen saldırganlar tarafından **hesaplanmamasını** sağlamak için r ve s değerlerinin hesaplanmasında kullanılır.

Kriptoloji bölümünden de bildiğimiz gibi, geçici özel anahtar, karşılık gelen (geçici) genel anahtarı türetmek için kullanılır, bu nedenle:

+ Geçici özel anahtar olarak kullanılan, kriptografik olarak güvenli bir rastgele sayı `q` dur

+ `q` ve eliptik eğri oluşturucu noktası `G`'den oluşturularak ona  karşılık gelen geçici ortak anahtar `Q`dur

📝NOT----> Dijital imzanın `r` değeri daha sonra geçici genel anahtar `Q`'nun **x koordinatıdır.**


Buradan, algoritma imzanın `s` değerini şu şekilde hesaplar:

**s ≡ q-1 (Keccak256(m) + r * k)  (mod p)** Burada:
  
  * q ➡️ geçici özel anahtardır.
  * r ➡️geçici genel anahtarın x koordinatıdır.
  * k ➡️imzalayan (EOA sahibinin) özel anahtarıdır.
  * m ➡️işlem verileridir.
  * p ➡️eliptik eğrinin asal mertebesidir.(Egeye sor???)


Doğrulama, eliptik eğri üzerinde bir nokta olan bir Q değerini (imza oluşturmada kullanılan geçici genel anahtar) hesaplamak için r ve s değerlerini ve gönderenin genel anahtarını kullananarak imza oluşturma işlevinin tersidir. Adımlar aşağıdaki gibidir:

1️⃣ Tüm  girdilerin doğru şekilde oluşturulduğunu kontrol edin.

2️⃣ w = s<sup>-1</sup> (mod p) hesaplanır.  

3️⃣ u<sub>1</sub> = Keccak256(m) * w (mod p) hesaplanır.                    

4️⃣ u<sub>2</sub> = r * w (mod p) hesaplanır.

5️⃣  Son olarakta Eliptik eğrideki noktayı hesaplarız:  Q ≡ u<sub>1</sub> * G + u<sub>2</sub> * K  (mod p)

  Yani burada da:
  * r ve s➡️ imza değerleridir.

  * K,➡️ imzalayanın (EOA sahibinin) genel anahtarıdır.

  * m, ➡️imzalanan işlem verileridir.

  * G,➡️ eliptik eğri oluşturucu noktasıdır.
  
  * p,➡️ eliptik eğrinin asal mertebesidir.
  
  
Hesaplanan `Q noktasının x koordinatı r'ye **eşitse**`, doğrulayıcı imzanın geçerli olduğu sonucuna varabilir.
**İmzayı doğrularken özel anahtarın ne bilindiğini ne de ifşa edildiğini unutmayın*.  
  
   
📝NOT---> ECDSA, zorunlu olarak oldukça karmaşık bir matematik parçasıdır; Derin bir açıklama bu kitabın kapsamı dışındadır. Burada belittiğimiz link ➡️ size yol gösterecektir: 🕳️[ECDSA zıkkımının daha derinine inmek için tıklayınız](https://www.instructables.com/Understanding-how-ECDSA-protects-your-data/). 

Yalnız şunu söylemeden edemeyeceğim.Bu konu üzerinde geçirdiğiniz her _1 saat, dünyada 7 yıla_ eşit oluyor.🌽🚀 

Anlamayan dostlarımıza özel: 🍿 [Interstellar](https://www.imdb.com/title/tt0816692/) 
  
<img title="Abime_O_gezegeni_VERMEYEYİM"  src="https://i.redd.it/gevxp9dvk7b11.jpg">

😠"Ulan Film önerisi alacak olsam Onedio,Mubi gibi paltformlara giderdim,sen bana İşlemleri anlat!" diyen değerli okuyucu, çok haklısın.🤕   

--------------

## Uygulamada İşlemi İmzalama  
  
Geçerli bir işlem üretmek için, _gönderen_, Eliptik Eğri Dijital İmza Algoritmasını(ECDSA) kullanarak **mesajı dijital olarak imzalamalıdır**. 

"İşlemi imzala"🔏 dediğimizde aslında **"RPP serileştirilmiş işlem verilerinin Keccak-256 hash'ini imzala"** demek istiyoruz. _İmza, işlemin kendisine değil🔴, işlem verilerinin karma(hash) değerine 🟢 uygulanır_.

Ethereum'da bir işlemi imzalamak için, gönderici şunları yapmalıdır:

* Dokuz alan içeren bir işlem veri yapısı oluşturun: _nonce, gasPrice, gasLimit, to, value, data, chainID, 0, 0_.

* İşlem veri yapısının RLP-şifrelenmiş serileştirilmiş bir mesajını üretin.

* Bu serileştirilmiş mesajın Keccak-256 karmasını(hash) hesaplayın.

* ECDSA imzasını hesaplayın, hash'i kaynak EOA'nın özel anahtarıyla imzalayın.

* ECDSA imzasının hesaplanan v, r ve s değerlerini işleme ekleyin.

Özel imza değişkeni **v** iki şeyi belirtir: 1️⃣ zincir kimliği ve 2️⃣ECDSare_cover fonksiyonunun imzayı denetlemesine yardımcı olacak _kurtarma Tanımlayıcısı(recovery identifier)_. 
Daha fazla bilgi için ⬇️

EIP-155 ile Saf İşlem Oluşturma(Raw Transaction Creation) bölümünde ele alacağız. 

🛡️Kurtarma tanımlayıcısı (_"eski tarz"_ imzalarda 27-28  veya tam `Spurious Dragon` tarzı işlemlerde 35-36), public anahtarın _y bileşeninin_ 🔑Parity'e belirtmek için kullanılır.Daha fazla Bilgi için bakınız: [EIP-155](https://eips.ethereum.org/EIPS/eip-155) 


📝NOT----> #2.675.000 numaralı blokta Ethereum, diğer değişikliklerin yanı sıra işlem tekrarından korumayı içeren (bir ağ için yapılan işlemlerin, diğerlerinde tekrar çalışmasını engelleyen) yeni bir _imzalama şeması_ sunan 🐉"Spurious Dragon" hard fork'u uyguladı. Bu yeni imzalama şeması **EIP-155'te belirtilmiştir**. Bu değişiklik, _işlemin biçimini ve imzasını etkiler_, bu nedenle, **iki biçimden birini alan ve hashing uygulanmakta olan işlem mesajında yer alan veri alanlarını gösteren üç imza değişkeninden ilkine (yani v) 🔍 dikkat edilmelidir**. 

## Ham(Raw?) İşlem Oluşturma ve İmzalama

Bu bölümde npm ile kurulabilen _ethereumjs-tx kütüphanesini_ kullanarak ham/saf(raw) bir işlem oluşturup imzalayacağız. Bu, normalde bir cüzdanda veya bir kullanıcı adına işlemleri imzalayan bir uygulamada kullanılacak fonksiyonları gösterir. Bu örneğin kaynak kodu, [kitabın GitHub reposundaki](https://github.com/ethereumbook/ethereumbook/blob/develop/code/web3js/raw_tx/raw_tx_demo.js) ⬅️ _raw_tx_demo.js_ dosyasındadır:

`link:code/web3js/raw_tx/raw_tx_demo.js[]`

Örnek kodu çalıştırırsak aşağıdaki sonuçları verir:
  
```
$ node raw_tx_demo.js
RLP-Encoded Tx: 0xe6808609184e72a0008303000094b0920c523d582040f2bcb1bd7fb1c7c1...
Tx Hash: 0xaa7f03f9f4e52fcf69f836a6d2bbc7706580adce0a068ff6525ba337218e6992
Signed Raw Transaction: 0xf866808609184e72a0008303000094b0920c523d582040f2bcb1...

```  

## EIP-155 ile Ham İşlem Oluşturma

EIP-155 _"Basit Tekrarlama Saldırısı Koruması"_ standardı, **imzalamadan önce işlem verilerinin içinde bir zincir tanımlayıcı içeren tekrar oynatmaya karşı korumalı bir işlem kodlamasını belirtir**. Bu, bir blok zinciri (örneğin, Ethereum ana-ağı) için oluşturulan işlemlerin 🟢 başka bir blok zincirinde (örneğin, Ethereum Classic veya Ropsten test ağı) geçersiz 🔴 olmasını sağlar. 

🎯**Bu nedenle, bir ağda yayınlanan işlemler başka bir ağda tekrarlanamaz**, Kısaca budur.
  
EIP-155, _işlem veri yapısının_ **ana altı6️⃣ Unsuruna** , (+)üç unsur daha ekler-----> 7️⃣zincir tanımlayıcısı(chain Identifier ⛓️) , 8️⃣0 ve 9️⃣0 
  
Bu üç alan, işlem _verilerine kodlanmadan ve hash edilmeden önce eklenir_. Bu nedenle, **imzanın daha sonra uygulanacağı işlemin karmasını değiştirirler**. Zincir tanımlayıcısını _imzalanan verilere dahil edereriz_. 
Zincir tanımlayıcı değiştirilirse imza geçersiz kılınacağından _işlem imzası herhangi bir değişikliği önler_. 

Bu nedenle EIP-155, **imzanın geçerliliği zincir tanımlayıcıya bağlı olduğundan**, bu bir işlemin başka bir zincirde tekrar çalışmasını imkansız hale getirir.😎

 Zincir tanımlayıcıları belirtildiği gibi, işlemin amaçlandığı ağa göre bir değer alır.

Tablo1(zincir Tanımlayıcıları) 📊

|Zincir Adı |Zincir ID|
------------|----------|
|Ethereum mainnet |1 |
|Morden (obsolete), Expanse | 2|
|Ropsten | 3|
|Rinkeby(Şuan artık işlem görmüyor) |4 |
|Rootstock mainnet | 30|
|Rootstock testnet |31 |
|Kovan |2 |
|Ethereum Classic mainnet | 61|
| Ethereum Classic testnet| 62|
|Geth private testnets | 1337|

Ortaya çıkan işlem yapısı RLP kodlu, karma#️⃣ ve imzalıdır. İmza algoritması, **zincir tanımlayıcıyı**  ve  **v** önekinde de şifreleme için biraz değiştirilir.

🐱 Daha fazla bilgi için [EIP-155 Github reposuna](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-155.md) bakınız.

-----------
## İmza Öneki Değeri (v) ve Genel Anahtarı Kurtarma

[Bir İşlemin Yapısı](https://github.com/CemmOzdemir/MasteringEthereum_TR_cevirisi/edit/develop/Türkçe/islemler.md#bir-i̇şlemin-yapısı) kısmında ⤴️ belirtildiği gibi, işlem mesajı bir "gönderen(from)" alanı içermez. **Bunun nedeni, yaratıcının genel anahtarının doğrudan ECDSA imzasından hesaplanabilmesidir**. Genel anahtara sahip olduğunuzda, adresi kolayca hesaplayabilirsiniz.


[ECDSA Matematiği kısmında](https://github.com/CemmOzdemir/MasteringEthereum_TR_cevirisi/edit/develop/Türkçe/islemler.md#ecdsa-matematiği-) hesaplanan r ve s değerleri göz önüne alındığında, iki muhtemel genel anahtarı hesaplayabiliriz.

İlk olarak, imzadaki x koordinat r değerinden iki eliptik eğri noktası, R ve R' hesaplıyoruz. İki nokta vardır, çünkü eliptik eğri x ekseni boyunca simetriktir, böylece herhangi bir x değeri için eğriye uyan iki olası değer vardır, x ekseninin her iki tarafında birer tane bulunur.

r'den r'nin tersi olan r<sup>-1</sup>'i de hesaplarız.

Son olarak, mesaj hash'inin en düşük _n_ bit'i olan z'yi hesaplıyoruz, burada n, eliptik eğrinin sırasıdır.

Muhtemelen iki genel anahtar şunlardır ve sonrası:

* K<sub>1</sub> = r<sup>-1</sup>(sR – zG) 
 
 VE
 
* K<sub>2</sub> = r<sup>-1</sup>(sR' – zG)

Burada anlatılmak istenen şey:

* K<sub>1</sub> ve K<sub>2</sub>, imzalayanın genel anahtarı için iki olasılıktır.

* r<sup>-1</sup>, imzanın r değerinin çarpımsal tersidir.

* s, imzanın değeridir.

* R ve R', geçici üretilmiş genel anahtarın Q için iki olasılığıdır.

* z, mesaj hashindeki(karmasındaki ) n'nin en düşük bitidir.

* G, eliptik eğri oluşturucu noktasıdır.


Bu durumu daha verimli hale getirmek için, **işlemin imzası , bize iki olası R değerinden hangisinin geçici ortak anahtar olduğunu söyleyen bir önek değeri** içerir.
**v çift ise, R doğru değerdir. Eğer v tek ise, o zaman R' dir**. Bu şekilde, R için yalnızca bir değer ve K için yalnızca bir değer hesaplamamız gerekir.

-------------------------

## İmzanın ve İletimin  Ayrılması(Çevrim-dışı imzalama)

Bir işlem imzalandıktan sonra Ethereum ağına iletilmeye hazırdır.📖Bir işlemin 1️⃣ oluşturulması(creation), 2️⃣imzalanması(singing) ve 3️⃣yayınlanmasının(broadcasting) üç adımı normalde tek bir işlem olarak gerçekleşir, örneğin `web3.eth.sendTransaction ` kullanımı gibi. 

Ancak (Raw) İşlem Oluşturma ve İmzalama bölümünde gördüğünüz gibi işlemi 🏋️ iki ayrı adımda oluşturup imzalayabilirsiniz. **İmzalanmış bir işleminiz olduğunda, bunu hex- kodlu- imzalı bir işlem alan ve Ethereum ağında ileten** ` web3.eth.sendSignedTransaction `kullanarak iletebilirsiniz.

İşlemlerin _imzalanmasını ✏️ ve  📮 iletilmesini_ neden ayırmak istiyoruz? En yaygın neden **güvenliktir**. Bir işlemi imzalayan bilgisayarın, memory(hafızaya) yüklenmiş ve kilidi açılmış özel anahtarlara sahip olması gerekir. İletimi yapan bilgisayar ❣️ internete bağlı olmalıdır.(Unutmadan bir ethereum istemciside çalışıyor olmak durumunda 🎛️)

Bu iki işlev bir bilgisayardaysa 💻, çevrimiçi bir sistemde **özel anahtarlarınız** vardır ve bu oldukça tehlikelidir. İmzalama ve iletme işlevlerinin ayrılması ve farklı makinelerde (sırasıyla _çevrimdışı ve _çevrimiçi_ bir cihazda) gerçekleştirilmesi **çevrimdışı imzalama olarak adlandırılır** ve yaygın bir güvenlik uygulamasıdır 🛡️.

💠Ethereum işlemlerinin **çevrimdışı imzalanması(offline)** süreci şöyledir:

1️⃣ Çevrimiçi bilgisayarda hesabın mevcut durumunun, özellikle de mevcut nonce ve mevcut fonların alınabileceği(işlem yapılabileceği) imzaya ihtiyaç duymayan bir işlem oluşturun.

2️⃣İmzasız işlemi, işlem imzalaması için, örneğin bir QR code veya USB flash aracılığıyla "[Air-gapped](https://en.wikipedia.org/wiki/Air_gap_(networking)) ( 📝 Buna değinmiştik,yine söyleyelim bir Ağ güvenliğini sağlayan bir sistem)" olan çevrimdışı bir cihaza aktarın.

3️⃣İmzalanmış işlemi, Ethereum blok zincirinde yayınlamak için, örneğin QR code veya USB flash aracılığıyla çevrimiçi olan bir cihaza iletin.


<img title="OfflineSigning"  src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/offline_signing.png">

Yukarıdaki görselde de göreceğimiz gibi; ⤴️
ihtiyacınız olan güvenlik düzeyine bağlı olarak, "çevrimdışı imzalama" bilgisayarınız, izole edilmiş ve güvenlik duvarı 🛡️ ile korunan bir alt ağdan (çevrimiçi ancak hepsinden ayrı) air-gapped sistem olarakta bilinen, _tamamen çevrimdışı bir sisteme_ kadar değişen farklı seviyelere, çevrimiçi bilgisayardan farklı seviyelerde ayrılabilir. 

Air-gapped bir sistemde _ağ bağlantısı hiç yoktur; bilgisayar çevrimiçi ortamdan_ tabiri caizse bir "**hava boşluğu**(adını oradan alıyor)" ile ayrılır.

İşlemleri imzalamak için bunları, veri depolama ortamı veya  bir web kamerası ve QR kodu kullanarak(bu daha iyi) Air-gapped bir bilgisayara aktarırsınız. Elbette bu, imzalanmasını istediğiniz her işlemi _manuel olarak_ 🚜 aktarmanız gerektiği anlamına gelir ve bu _ölçeklenmez_.

Pek çok ortam tamamen Air-Gapped bir sistem kullanamazken, küçük bir izolasyon seviyesi bile önemli güvenlik avantajlarına sahiptir. Örneğin, yalnızca bir `message-queue(ileti sırası)` protokolüne izin veren bir güvenlik duvarına sahip korunmuş bir alt ağ, çevrimiçi sistemde oturum açmaktan çok daha düşük bir saldırı oranı 📉 ve çok daha yüksek 📈 güvenlik 🛡️sağlayabilir. ➕

📝BENDEN SİZLERE📝
Şimdi anlatacak olduğum konuda size `QUEUE` 'yu biraz anlatmam gerekecek.Bu bilgiyi biliyorsanız geçin.Zaten Data Structure dersini seviyorum 🖕 birde burada okuyayım derseniz Geçmeyin😄 🟠[Patika.dev](https://app.patika.dev/paths) üzerinden almış olduğum Veri Yapıları kursundan yararlanarak güzel ve kısa bir şekilde anlatmam gerekirse; Queue bir veri yapısıdır. FIFO(First in First out) yani ilk giren ilk çıkar prensibiyle hareket eder.Bunu şöyle düşünün:Bir 🚌otobüs kuyruğunda en erken gelmiş ve durakta duran bireyin otobüse binmesi gibi düşünebilirsiniz. Türkçesini 🔈 "Sıra"  olarak çevirebiliriz. Daha fazla bilgi için 🖱️[Tıklayınız(Youtube)](https://www.youtube.com/watch?v=G6LCgUlgE8I)💯    

* Enquene--------> Yeni elemanı Sıra'ya eklenmesi demektir.

* Dequeue--------> Elemanın Sıradan çıkarılması demektir.

Bu görsel anlamanıza yardımcı olacaktır. ⤵️

<img title="Queue(sıra)"  src="https://upload.wikimedia.org/wikipedia/commons/5/52/Data_Queue.svg">

➕ Birçok şirket bu amaçla [ZeroMQ (0MQ)](https://zeromq.org) gibi bir protokol kullanır. Böyle bir sistemle **işlemler serileştirilir** ve imza için sıraya(queue) alınır. Sıra protokolü, **serileştirilmiş mesajı** bir TCP soketine benzer şekilde imzayı bilgisayarına iletir. _İmzalayan bilgisayar_, serileştirilmiş işlemleri sıradan dikkatlice okur, **uygun anahtarla bir imza uygular ve bunları giden bir başka sıraya(queue) yerleştirir.** Giden Sıra, imzalanmış işlemleri, onları sıraya alan ve ileten bir **Ethereum istemcisine sahip bir bilgisayara** iletir.

## İşlem Yayılımı (Transaction Propagation)

Ethereum ağı bir **"Flood-routing"** protokolü kullanır. Her Ethereum istemcisi, (ideal olarak) bir ağ oluşturan eşler arası (P2P) ağda bir düğüm görevi görür🎛️. Hiçbir ağ düğümü _özel değildir_: hepsi aynı eşler gibi davranır. P2P ağına bağlı ve buna katılan bir Ethereum istemcisine atıfta bulunmak için **"düğüm(Node)"** ⚫ terimini kullanacağız.

İşlem yayılımı, **kaynak Ethereum düğümünün** imzalı bir işlem oluşturması (veya çevrimdışı olarak alması) ile başlar. İşlem doğrulanır ✔️ ve ardından doğrudan _kaynak düğüme bağlı olan diğer tüm Ethereum düğümlerine iletilir._ Ortalamaya göre her Ethereum düğümü, _komşuları_ 🤗 olarak adlandırılan en az 13 diğer düğümle bağlantı kurar.
 **Her komşu düğüm, işlemi alır almaz doğrular**. _Geçerli olduğunu kabul ederlerse, bir kopyasını saklarlar_ ve (geldiği node hariç) tüm komşularına yayarlar_. Sonuç olarak, işlem, ağdaki tüm düğümler işlemin bir kopyasına sahip olana kadar, kaynak düğümden dışarı doğru yayılır ve ağ boyunca devam eder. _Düğümler, yaydıkları mesajları filtreleyebilirler, ancak varsayılan(default) olarak ayarlı kaldıklarında, aldıkları tüm geçerli işlem mesajlarını yaymaktadırlar._

Sadece birkaç saniye içinde, bir Ethereum işlemi dünyadaki tüm Ethereum düğümlerine yayılır. Her düğümün bakış açısından, **işlemin kaynağını ayırt etmek mümkün değildir**. _Onu düğüme gönderen komşu işlemin yaratıcısı olabilir veya işlemi komşularından birinden almış olabilir_ 🐵 . Bir saldırganın işlemlerin kökenini takip edebilmek veya yayılıma müdahale edebilmesi için tüm düğümlerin önemli bir yüzdesini kontrol etmesi gerekir. Bu, özellikle blok zinciri ağlarına uygulandığında, P2P ağlarının güvenlik ve gizlilik tasarımının bir parçasıdır.🛡️

--------------

## Blok Zinciri üzerinde Kayıt Alma ⛓️📖
 
Ethereum'daki tüm düğümler eşit eşler olsa da, bazıları madenciler tarafından işletiliyor ve yüksek performanslı grafik işleme birimlerine(GPU'lar) sahip bilgisayarlar ile madencilik çiftliklerine işlemler ve bloklar yapıyorlar.(Ethereum'un Eylül 2022 de artık PoS geçtiğini unutmayın.Artık GPU fiyatlarının düşeceğini söyleyebiliriz.Çünkü ETHEREUM büyük bir değişikliğe gitti PoW---->PoS geçti 🐼)
Madencilik bilgisayarları, sıradaki bloğa işlemler ekler ve sıradaki bloğu geçerli kılan bir çalışma kanıtı(PoW) bulmaya çalışır. Bunu Consensus♟️ bölümünde daha ayrıntılı olarak tartışacağız.

Çok fazla ayrıntıya girmeden, **geçerli işlemler sonunda bir işlem bloğuna dahil edilecek** ve böylece Ethereum blok zincirine kaydedilecektir. Bir bloğa işlendiğinde, işlemler aynı zamanda bir hesabın bakiyesini değiştirerek (basit bir ödeme durumu gibi) veya dahili durumlarını değiştiren sözleşmeleri başlatarak Ethereum Tekil durmunu(singleton) da değiştirir. Bu değişiklikler, bir işlem makbuzu/fişi 🔖 biçiminde, işlemin yanında kaydedilir. Bütün bunları _EVM_ 🎰 bölümünde çok daha detaylı inceleyeceğiz.

----------

## Çoklu İmza (MultiSig) İşlemleri

Bitcoin'in komut dosyası oluşturmayı biliyorsanız, yalnızca birden fazla taraf işlemi imzaladığında para harcayabilen bir Bitcoin çoklu imza hesabı oluşturmanın mümkün olduğunu bilirsiniz. (örneğin, 2'de 2 veya 4 imzadan 3'ü).
Ethereum'un _temel EOA değeri_ işlemlerinde çoklu imzalar için bir karşılık yoktur; bununla birlikte, ether ve token transferini işlemek için aklınıza gelebilecek herhangi bir koşulla akıllı sözleşmeler tarafından _keyfi imzalama kısıtlamaları_ uygulanabilir.

Bu avantajdan yararlanmak için ether, çoklu imza gereksinimleri veya harcama limitleri gibi istenen harcama kurallarıyla programlanmış bir **"cüzdan sözleşmesine"** aktarılmalıdır. 🔄

**Cüzdan sözleşmesi**, Fon şartlarını karşıladıktan sonra yetkili bir EOA tarafından istendiğinde fonları gönderir. Örneğin, **etherinizi çok imzalı bir koşulda korumak için, etherinizi çok imzalı bir sözleşmeye aktarın**. Başka bir hesaba para göndermek istediğinizde, gerekli tüm kullanıcıların normal bir cüzdan uygulaması kullanarak sözleşmeye işlem göndermesi gerekecek ve sözleşmeyi son işlemi gerçekleştirmek için etkin bir şekilde yetkilendirecektir.👮

Çoklu İmza cüzdanı, birden fazla özel anahtarla güvence altına alınan bir kripto cüzdanıdır.Normal bir cüzdanı yedeklemek ve kurtarmak için genellikle yalnızca bir tohum yeterlidir.(Cüzdanlar bölümünde anlatmıştık.) Bunun yerine, **çok imzalı bir cüzdanı yedeklemek ve kurtarmak için birden çok anahtar gerekir**.

Çoklu imza işlemlerini **akıllı bir sözleşme** olarak uygulama yeteneği, Ethereum'un esnekliğini🦋 gösterir. Bununla birlikte, ekstra esneklik, çoklu-imza yapılarının güvenliğini baltalayan hatalara yol açabileceğinden, iki ucu keskin bir kılıçtır. ⚔️(Güncel olarak ne durumda bilmiyorum Lütfen araştırın)

sizlere benden bazı kaynaklar 📚

* [GNOSIS varlık yönetim cüzdanı ](https://gnosis-safe.io)

* [Linen Cüzdan yapısı](https://linen.app/assets/best-multisig-wallet-for-ethereum-polygon/)

* 🐱 [BitGo Github](https://github.com/BitGo/eth-multisig-v4)

* 📘[Blog Yazısı/Inominds](https://www.innominds.com/blog/securing-ethereum-wallet-with-multisig)

---------------------------
## Sonuç olarak bu Bölümde:

İşlemler, Ethereum sistemindeki her hareketin başlangıç 🏳️ noktasıdır. İşlemler, Ethereum Sanal Makinesinin sözleşmeleri değerlendirmesine, bakiyeleri güncellemesine ve daha genel olarak Ethereum blok zincirinin durumunu değiştirmesine neden olan **"girdiler(inputs)"** dir. Ardından, akıllı sözleşmelerle çok daha detaylı şekilde bakacağız 📜 ve Solidity💻 programlama dilinde nasıl kodlama yapılır, öğreneceğiz.

--------------------

_Bölüm Sonu_ 🏁

--------------------

**"Tutkularınızı küçümseyen insanlardan uzak durun.Küçük insanlar bunu her zaman yaparlar,ama hakikaten büyük olanlar sizinde harika olabileceğinizi kendinize hisettirirler. 🗣️ Mark Twain"**
