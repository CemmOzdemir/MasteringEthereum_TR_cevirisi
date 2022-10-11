# İŞLEMLER ➡️📖⬅️

_İşlemler_, Ethereum ağı tarafından iletilen ve Ethereum blok zincirine **kaydedilen**, harici olarak sahip olunan bir hesaptan (EOA'dan) kaynaklanan _imzalı mesajlardır_. Bu temel tanım, birçok **şaşırtıcı ve büyüleyici ayrıntıyı gizler**👻. İşlemlere  başka bir perspektiften bakınca, **bir durum değişikliğini tetikleyebilecek veya EVM'de bir sözleşmenin yürütülmesine(çalışmasına) neden olabilecek TEK şey olmalarıdır**.  Ethereum, global 🌎 bir tekil(singleton) durum makinesidir ve bu durum makinesinin durumunu değiştirerek "tik-tok⏰" olan  şeyler _işlemlerdir_.(Buradaki cümlede yazar Ethereum'u bir saate ⏰ benzeterek,geçen her saniyeyi işlemlere benzetmiştir.Saat sürekli ilerliyorsa işlemler sayesinde yani) 

**Sözleşmeler kendi başlarına çalışamazlar. Ethereum otonom olarak çalışmaz. Her şey bir işlemle başlar.** 💥🌍

Bu bölümde işlemleri inceleyeceğiz, nasıl çalıştıklarını göstereceğiz ve detayları inceleyeceğiz. Bu bölümde çoğu kişinin, **belki de bir cüzdan uygulaması yazdıkları için kendi işlemlerini düşük düzeyde yönetmekle ilgilenenlere yönelik olduğunu unutmayın**; Buradaki detayları ilginç bulacak olsanız da, mevcut cüzdan uygulamalarını kullanmaktan memnunsanız bunun için panik yapmanıza gerek yok!☕

--------------

## Bir İşlemin Yapısı
Öncelikle, Ethereum ağında [seri hale](https://en.wikipedia.org/wiki/Serialization)[kısaca serileştirme işleminin Yönteminde:veriyi bir yere depolama/kaydetme vardır.] getirilip iletildiği için, bir işlemin temel yapısına bir göz atalım. Serileştirilmiş bir işlem alan her istemci ve uygulama, kendi **dahili veri yapısını kullanarak**, belki de ağ serileştirme işleminde mevcut olmayan meta verilerle birlite bunu bellekte saklayacaktır. **Ağ serileştirmesi, bir _işlemin tek standart biçimidir_**.

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


Başka bir yaklaşım: işlemleri oluşturmak, onlara bir nonce atamakla mümkün (ve bu nedenle onları imzasız bırakmak  *⭐ ⚠️nonce'nin işlem verilerinin ayrılmaz bir parçası olduğunu ve bu nedenle işlemi doğrulayan **dijital imzaya dahil edilmesi gerektiğini** unutmayın*) olacaktır. . Daha sonra bunları imzalayan ve aynı zamanda nonce'ların kaydını tutan **tek bir düğümde sıralayabilirsiniz**. Yine de, bu süreçte bir **tıkanıklık noktası** olacaktır: nonces'ların imzalanması ve izlenmesi, işleminizin veri yığını altında sıkışık(stuck) hale gelmesi muhtemel olan kısmıdır, oysa imzasız işlemin oluşturulması, gerçekten yapmadığınız kısımdır..Biraz eşzamanlı olurdu, ancak sürecin kritik bir bölümünde eksiklik olurdu.

Sonuç olarak, bu eşzamanlılık sorunları, bağımsız süreçlerde hesap bakiyelerini ve işlem onaylarını **takip etmenin zorluğuna ek olarak**, çoğu uygulamayı eşzamanlılıktan kaçınmaya ve bir borsadaki tüm para çekme işlemlerini **tek bir işlemle işlemek** veya birden fazla işlem kurmak gibi **darboğazlar yaratmaya** ya da para çekme işlemleri için tamamen bağımsız çalışabilen ve yalnızca aralıklı olarak yeniden dengelenmesi gereken birden fazla sıcak cüzdan kurmaya zorlar.🤯

----------

## İşlemde Gaz ⛽💸










