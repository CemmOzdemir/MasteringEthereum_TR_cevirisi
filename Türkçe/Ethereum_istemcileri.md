
# ETHEREUM İSTEMCİLERİ(Clients) 🔌

Ethereum istemcisi, _Ethereum spesifikasyonunu uygulayan ve eşler arası ağ üzerinden diğer Ethereum istemcileriyle iletişim kuran bir yazılım uygulamasıdır._ Farklı Ethereum istemcileri, referans belirtimine ve standartlaştırılmış iletişim protokollerine **uyuyorlarsa birlikte çalışırlar.** Bu farklı istemciler farklı ekipler tarafından ve _farklı programlama dillerinde uygulanırken_, hepsi aynı **protokolü "konuşur" ve aynı kuralları takip eder.** Bu nedenle, hepsi aynı Ethereum ağıyla çalışmak ve etkileşim kurmak için kullanılabilir.

Ethereum _açık kaynaklı_ bir projedir ve tüm büyük istemciler için kaynak kodu, açık kaynak lisansları (örneğin, LGPL v3.0) altında mevcuttur.İndirmek ve herhangi bir amaç için kullanmak ücretsizdir. Açık kaynak, kullanımı ücretsiz olmaktan çok daha fazlasını ifade eder. Ayrıca Ethereum'un gönüllüler topluluğu(foundation) tarafından geliştirildiği ve herkes tarafından değiştirilebileceği anlamına gelir. _Daha fazla bakış açısı, daha güvenilir kod anlamına gelir._ 🛡️

Ethereum, "Sarı Kağıt"(Yellow Paper) 🟨 adı verilen resmi bir spesifikasyonla( 🇹🇷 TDK:Teknik özelliklerini anlatan şartnameye verilen ad) tanımlanır.

Ethereum'un spesifikasyonu -İngilizce ve matematiksel (resmi)- olarak birleştiren bir kağıtta belgelenmiştir. Bu resmi belirtim, çeşitli Ethereum İyileştirme Önerilerine ek olarak, bir _Ethereum istemcisinin standart davranışını tanımlar_. Sarı Kitap(yellow paper), Ethereum'da büyük değişiklikler yapıldıkça periyodik olarak güncellenir.

Ethereum'un açık ve resmi spesifikasyonunun bir sonucu olarak, bir _Ethereum istemcisi bağımsız olarak geliştirilmiş_ , ve bununla  **birlikte çalışabilir yazılım uygulamaları** vardır. Ethereum, ağ üzerinde çalışan diğer tüm blok zincirlerinden daha **fazla çeşitliliğe sahiptir** ve bu genellikle **iyi bir şey olarak kabul edilir.** (Gerçek merkeziyetsizliğe her şekilde ulaşabilmek) Gerçekten de, örnek olarak; **belirli bir istemcinin uygulama stratejisinden yararlanılması, geliştiricileri açıkları düzeltirken yaşadıkları güçlükleri halletmeye çalışırken, diğer istemciler ağın neredeyse etkilenmeden çalışmasını sağladığından, ağ üzerindeki saldırılara karşı mükemmel bir savunma** yolu olduğunu kanıtlamıştır.

-------------------
## Ethereum Ağları

Ethereum Yellow Paper'da tanımlanan resmi spesifikasyona büyük ölçüde uyan, ancak birbirleriyle birlikte çalışabilen veya çalışamayan çeşitli Ethereum tabanlı ağlar vardır.

Bu Ethereum tabanlı ağlar arasında Ethereum, Ethereum Classic, Ella, Expanse, Ubiq, Musicoin ve diğerleri bulunur. Çoğunlukla protokol düzeyinde uyumlu olsa da, bu ağlar genellikle her bir ağı desteklemek için Ethereum istemci yazılımının geliştiricilerinin, küçük değişiklikler yapmasını gerektiren özelliklere veya özniteliklere sahiptir. Bu nedenle, Ethereum istemci yazılımının her sürümü, her Ethereum tabanlı blok zincirini çalıştırmaz.

Şu anda, altı farklı dilde yazılmış **Ethereum protokolünün altı ana uygulaması vardır**:

* parity ---> Rust ile yazılmış 

* Geth ------> Go ile yazılmış

* cpp-ethereum ----> C++ ile yazılmış

* pyethereum ------->Python ile yazılmış 

* Mantis ------> Scala ile yazılmış

* Harmony -------> Java ile yazılmış

 ⭐ Bu bölümde, en yaygın iki istemciye, _Parity ve Geth'e bakacağız._ Her istemciyi kullanarak bir düğümün nasıl kurulacağını göstereceğiz ve bazı komut satırı seçeneklerini ve uygulama programlama arabirimlerini (API'ler) keşfedeceğiz.
 
 ----------------------
 
 ## Tam Düğüm(full Node) Çalıştırmalı mıyım? 🎛️
 
 Blok zincirlerinin **kullanımı,esnekliği ve sansür direnci gibi önemli unsurları, bağımsız olarak işletilen ve coğrafi olarak dağılmış birçok tam düğüme sahip olmalarına bağlıdır. Her bir tam düğüm, diğer yeni düğümlerin operasyonlarını başlatmak için blok verilerini almasına yardımcı olabilir ve ayrıca operatöre tüm işlemlerin ve sözleşmelerin yetkili ve bağımsız bir doğrulamasını sunar.**
 
 Ancak, tam bir düğüm çalıştırmak, donanım kaynaklarında ve bant genişliğinde bir maliyete neden olacaktır. Tam bir düğüm 300 GB'a kadar veri indirebilir (istemci yapılandırmasına bağlı olarak Mart 2021'den itibaren) ---->[🗒️NOT: güncel olarak şuanlık EYLÜL2022----> ~730 GB ] ve yerel bir sabit sürücüde depolayabilir. Bu veri yükü, her geçen gün yeni işlemler ve bloklar eklendikçe oldukça hızlı bir şekilde artmaktadır. Bu konuyu Tam Düğüm için Donanım Gereksinimlerinde daha ayrıntılı olarak anlatacağız.
 Main net ağında çalışan tam bir düğüm, Ethereum geliştirmesi için gerekli değildir. Bir testnet düğümü (sizi daha küçük genel test blok zincirlerinden birine bağlar), **Ganache gibi yerel bir özel blok zincir** veya **Infura gibi bir hizmet sağlayıcı tarafından sunulan bulut tabanlı bir Ethereum istemcisi** ile yapmanız gereken hemen hemen her şeyi yapabilirsiniz. 
 
 Ayrıca blok zincirinin yerel bir kopyasını **saklamayan veya blokları ve işlemleri doğrulamayan** bir uzak istemci(remote clients) çalıştırma seçeneğiniz de vardır. Bu istemciler bir _cüzdanın işlevselliğini_ sunar ve işlemler oluşturabilir ve yayınlayabilir. Uzak istemciler, kendi tam düğümünüz, public blok zinciri, genel veya izin verilen (PoA) test ağı veya özel-yerel blok zinciri gibi mevcut ağlara bağlanmak için kullanılabilir. Pratikte, **tüm farklı düğüm seçenekleri arasında geçiş yapmanın uygun bir yolu olarak MetaMask, Emerald Wallet, MyEtherWallet veya MyCrypto gibi uzak bir istemci** kullanırsınız.

Bazı farklılıklar olsa da "uzaktan istemci(remote clients)" ve "cüzdan"(wallet) terimleri _birbirinin yerine kullanılır._  _Genellikle bir uzak istemci, bir cüzdanın işlem fonksiyonlarına ek olarak bir **API (web3.js API gibi)** sunar._
 
 ⚠️
Ethereum'daki uzak cüzdan kavramını _light clients_ ile(Bitcoin'deki Basitleştirilmiş Ödeme Doğrulama istemcisine benzer) karıştırmayın. light istemciler, blok _başlıklarını doğrular ve işlemlerin blok zincirine dahil edilmesini doğrulamak ve etkilerini belirlemek için Merkle kanıtlarını kullanır.Onlara tam bir düğüme benzer bir güvenlik düzeyi verir._ Oysa, **Ethereum remote clients blok başlıklarını veya işlemlerini doğrulamaz.** Blok zincirine erişim sağlamak için tam bir itemciye(full_node) tamamen güvenirler ve bu nedenle önemli güvenlik ve anonimlik garantilerini kaybederler. Kendi çalıştırdığınız tam bir istemci kullanarak bu sorunları azaltabilirsiniz.("Node KURUN " Dr.tobbyKitty 🐱") 

📝NOT+Ekleme :Nodelar hakkında daha fazla bilgi almak için [tobby'nin web sitesini](https://tobbykitty.com/2022/05/28/node-nedir-nodelar-hakkinda-her-sey/)
ziyaret edebilirsiniz.

## Tam Düğüm Avantajları ve Dezavantajları

Tam bir düğüm çalıştırmayı seçmek,_onu bağladığınız ağların çalışmasına yardımcı olur_, ancak aynı zamanda sizin için düşük ile orta düzeyde maliyetler gerektirir. Bazı avantajlara ve dezavantajlara bakalım:

-------------------
Avantajlar: 🟢
-------------------
* Ethereum tabanlı ağların esnekliğini ve sansür direncini destekler.

* Tüm işlemleri yetkili bir şekilde doğrular.

* Herhangi bir aracı olmadan halka açık blok zincirindeki herhangi bir sözleşmeyle etkileşime girebilir.

* Sözleşmeleri bir aracı olmadan doğrudan halka açık blok zincirine dağıtabilir.

* Blok zinciri durumunu (hesaplar, sözleşmeler vb.) çevrimdışı olarak sorgulayabilir. (salt okunur)

* Okuduğunuz bilgileri üçüncü bir tarafa bildirmeden blok zincirini sorgulayabilir.

----------------
Dezavantajları: 🔴
----------------
* Önemli ve büyüyen donanım ve bant genişliği kaynakları gerektirir.

* İlk başlatıldığında tam senkronizasyon için birkaç gün gerekebilir.

* Senkronize kalmak için bakımı yapılmalı, yükseltilmeli ve çevrimiçi tutulmalıdır.


## Public(Herkese Açık) Testnet'in Avantajları ve Dezavantajları

Tam bir düğüm(full Node) çalıştırmayı seçseniz de seçmeseniz de, muhtemelen bir public test ağı düğümü çalıştırmak isteyeceksiniz. Herkese açık bir test ağı kullanmanın bazı avantaj ve dezavantajlarına bakalım:

------------
Avantajlar: 🟢
------------
* Bir test ağı düğümünün, ana ağa kıyasla önemli ölçüde daha az veriyi senkronize etmesi ve depolaması gerekir.

* Bir testnet düğümü, çok daha kısa sürede tamamen eşitlenebilir.

* Sözleşmeleri dağıtmak veya işlem yapmak, hiçbir değeri olmayan ve birkaç "musluktan"(faucet)🚰 *ücretsiz olarak edinilebilen test etherini gerektirir.*

* Test ağları, diğer birçok kullanıcı ve sözleşmeyle birlikte "canlı" çalışan halka açık blok zincirlerdir.

----------
Dezavantajları: 🔴
------------
* Bir test ağında **gerçek** parayı kullanamazsınız; test etherinde çalışır. Sonuç olarak, tehlikede hiçbir şey olmadığı için güvenliği gerçek hackerlara karşı test edemezsiniz.

* Bir test ağında _gerçekçi bir şekilde test edemeyeceğiniz_ bir genel blok zincirinin bazı yönleri vardır. Örneğin, **işlem ücretleri, işlem göndermek için gerekli olmasına rağmen, gaz ücretsiz olduğu için bir test ağında dikkate alınmaz.** Ayrıca, test ağları, genel ana ağın bazen yaptığı gibi ağ tıkanıklığı yaşamaz.

## LOCAL Blok Zinciri Simülasyonu Avantajları ve Dezavantajları: 🍬
Birçok test amacı için en iyi seçenek, **tek örnekli bir özel blok zinciri başlatmaktır**. _Ganache (eski adıyla testrpc),_ başka hiçbir katılımcı olmadan etkileşime girebileceğiniz en popüler _Local blok zinciri simülasyonlarından biridir._ Genel test ağının birçok avantaj ve dezavantajını paylaşır, ancak bazı farklılıkları da vardır.

-------
Avantajlar: 🟢
--------
* Senkronizasyon yok ve depolamada neredeyse hiç veri tutmaz. 

* Test eteri almaya gerek yok; Ganache,test için zaten ether tutan hesaplarla başlatılır.

* Başka kullanıcı yok,sadece siz varsınız. 🚕

Başka sözleşme yok, yalnızca mevcut bir Ethereum düğümünü devre dışı bırakma seçeneğini **kullanmadığınız** sürece, başlattıktan sonra ağa dağıttığınız sözleşmelerle tek başına çalışır. 

---------
Dezavantajları: 🔴
-----------
* Başka kullanıcıya sahip olmamak,  açık(public) bir blok zinciri gibi davranmadığı anlamına gelir. İşlem alanı veya işlemlerin sıralanması için rekabet yoktur.

* Sizden başka madenci olmaması, madenciliğin daha öngörülebilir olduğu anlamına gelir; bu nedenle, halka açık bir blok zincirinde meydana gelen bazı senaryoları test edemezsiniz.

* Mevcut bir Ethereum düğümünü çatallıyorsanız(fork), aksi söz konusu olduğunda **budanmış olabilecek(Prune) bloklardan** durumla etkileşime girebilmeniz için bir arşiv düğümü(archive) olması gerekir. [Daha fazla bilgi için TobbyKitty web sitesinden Node Nedir? yazısı okuyalım.](https://tobbykitty.com/2022/05/28/node-nedir-nodelar-hakkinda-her-sey/) 🐱

 <img title="budama(pruning)" src="https://pbs.twimg.com/media/E8rdzAMWEAUh4ry.png">
 
 ## Ethereum İstemcisi Çalıştırma

_Zamanınız ve kaynaklarınız varsa_, yalnızca süreç hakkında daha fazla bilgi edinmek için bile olsa **tam bir düğüm(full node) çalıştırmayı denemelisiniz**. Bu bölümde, Ethereum istemcileri Parity ve Geth'in nasıl indirileceğini, derleneceğini ve çalıştırılacağını ele alıyoruz. Bu, işletim sisteminizde komut satırı arabirimini(**Cmd-Terminal** ) kullanma konusunda biraz bilgi sahibi olmayı gerektirir. İster tam düğümler olarak, ister test ağı düğümleri olarak veya yerel(local) bir özel blok zincirinin istemcileri olarak çalıştırmayı seçseniz de, bu istemcileri yüklemeye değer bulacaksınız.✊
 
-------------- 
 ⚠️ UYARI: Kitabın basımı ve yazılmış olan gereksinimlere baktığımızda güncel OLMADIĞINA karar verdim. Bu yüzden sizlerin güncel bilgilerden yararlanmanızı sağlamak için bu bölümü link olarak size bırakıyorum: 
-------------
⏬ _SİSTEM GEREKSİNİMLERİ_ :

[QuickNode üzerinden(Eylül 2022) Ferhat Kochan'ın yazısını inceleyeblirsiniz.](https://www.quicknode.com/guides/infrastructure/ethereum-full-node-vs-archive-node) 
 
---------------
⚠️UYARI 1: GO-ethereum'un Github reposu üzerinden _GETH_ güncel kuruluma erişebilirsiniz. 📎[Github reposu](https://github.com/ethereum/go-ethereum)
 --------------

-------------
⚠️UYARI 2: _PARITY_'i(Rust dili ile yazılmıştı unutmayın) güncel kurulumu için ise openethereum github reposuna gidiniz: 📎[Github reposu](https://github.com/openethereum/parity-ethereum)  
-------------

## Ethereum Tabanlı Blok Zincirlerinin İlk Senkronizasyonu ➿

Geleneksel olarak, bir Ethereum blok zincirini senkronize ederken, istemciniz en başından beri, yani genesis bloğundan her bloğu ve her işlemi indirir ve doğrular.

Blok zincirini bu şekilde **tam olarak senkronize etmek mümkün olsa da,** bu tür senkronizasyon **çok uzun zaman alacak** ve **yüksek kaynak gereksinimlerine sahip olacaktır.** (çok daha fazla RAM'e ihtiyaç duyacaktır ve eğer hızlı bir donanımınız yoksa gerçekten çok uzun zaman alacaktır). 

Birçok Ethereum tabanlı blok zinciri, 2016'nın sonunda DoS saldırılarının kurbanı oldu. Etkilenen blok zincirleri, tam bir senkronizasyon yaparken yavaş yavaş senkronize olma durumnda olacaktırlar.

Örneğin, Ethereum'da yeni bir müşteri 2.283.397 bloğa ulaşana kadar hızlı ilerleme kaydedecektir. Bu blok 18 Eylül 2016'da çıkarıldı ve DoS saldırılarının başlangıcını işaret ediyor. Bu bloktan 2.700.031 bloğa (26 Kasım 2016), işlemlerin doğrulanması son derece yavaş, bellek yoğun ve I/O yoğun hale geliyor. Bu, blok başına 1 dakikayı aşan doğrulama süreleriyle sonuçlanır. Ethereum, DoS saldırılarında kullanılan **temel güvenlik açıklarını gidermek için hard fork🍴 kullanarak bir dizi yükseltme gerçekleştirdi**. Bu yükseltmeler, spam işlemleri tarafından oluşturulan yaklaşık 20 milyon boş hesabı kaldırarak blok zincirini de temizledi.

_Tam doğrulama ile eşitleme yapıyorsanız_, istemciniz yavaşlar ve DoS saldırılarından etkilenen blokları doğrulamak birkaç gün, hatta daha uzun sürebilir.

Neyse ki, çoğu Ethereum istemcisi **varsayılan olarak**  işlemlerin tam doğrulamasını, blok zincirinin ucuyla senkronize olana kadar geçen(atlama yoluyla) ve ardından tam doğrulamaya devam eden **"hızlı"** bir senkronizasyon gerçekleştirir.

Geth, Ethereum için varsayılan olarak hızlı senkronizasyon gerçekleştirir. Seçilen diğer Ethereum zinciri için özel talimatlara başvurmanız gerekebilir.

Parity ayrıca varsayılan olarak hızlı senkronizasyon yapar.

📝NOT :_Geth_, yalnızca **boş bir blok veritabanıyla başlatıldığında hızlı senkronizasyonu çalıştırabilir**. Hızlı mod olmadan zaten senkronizasyona başladıysanız, Geth geçiş yapamaz. Blok zinciri veri dizinini silmek ve baştan hızlı senkronizasyona başlamak, tam doğrulama ile senkronizasyona devam etmekten daha hızlıdır. Blok zinciri verilerini silerken herhangi bir cüzdanı silmemeye dikkat edin!

## Geth veya Parity Çalıştırmak
Artık "ilk senkronizasyon"un zorluklarını anladığınıza göre, bir Ethereum istemcisi başlatmaya ve blok zincirini senkronize etmeye hazırsınız. Hem Geth hem de Parity için, tüm yapılandırma parametrelerini görmek için **--help** seçeneğini kullanabilirsiniz. Varsayılan ayarlar genellikle mantıklıdır ve çoğu kullanım için uygundur. İsteğe bağlı parametreleri ihtiyaçlarınıza uyacak şekilde nasıl yapılandıracağınızı seçin, ardından **zinciri senkronize etmek için Geth veya Parity'yi başlatın.** Sonra bekleyin…

🔍İPUCU:Ethereum blok zincirini senkronize etmek, çok fazla RAM içeren çok hızlı bir sistemde yarım gün, daha yavaş bir sistemde birkaç gün sürer.

## JSON-RPC Arayüzü 🖤

Ethereum istemcileri, bir uygulama programlama arabirimi ve _JavaScript Nesne Gösterimi (JSON)_ olarak kodlanmış bir dizi _Uzaktan Yordam Çağrısı (RPC)_ komutu sunar. Bunun **JSON-RPC API olarak anıldığını göreceksiniz.** Esasen, **JSON-RPC API, bir Ethereum istemcisini bir Ethereum ağına ve blok zincirine ağ geçidi olarak kullanan programlar yazmamıza izin veren bir arayüzdür.**

Genellikle, RPC arabirimi 8545 numaralı bağlantı noktasında bir HTTP hizmeti olarak sunulur. _Güvenlik nedenleriyle_, varsayılan olarak yalnızca yerel(LOCAL) ana bilgisayardan (127.0.0.1 olan kendi bilgisayarınızın IP adresi) gelen bağlantıları kabul etmesi nedeniyle **kısıtlanmıştır.**

JSON-RPC API'sine erişmek için, mevcut her RPC komutuna karşılık gelen "stub" işlev çağrıları sağlayan özel bir kitaplık (seçtiğiniz programlama dilinde yazılmış) kullanabilir veya manuel olarak HTTP istekleri oluşturabilir ve JSON gönderip/alabilirsiniz.(kodlanmış istekler). RPC arabirimini çağırmak için _curl_ gibi genel bir komut satırı HTTP istemcisi bile kullanabilirsiniz. Bunu deneyelim. Öncelikle Geth'in çalışır durumda olduğundan, --rpc ile RPC arabirimine HTTP erişimine izin vermek için yapılandırıldığından emin olun, ardından yeni bir terminal penceresine geçin (örneğin, mevcut bir pencerede Ctrl-Shift-N veya Ctrl-Shift-T ile). terminal penceresi) burada gösterildiği gibi:

`$ curl -X POST -H "Content-Type: application/json" --data \
'{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":1}' \
http://localhost:8545
{"jsonrpc":"2.0","id":1,
"result":"Geth/v1.9.11-unstable-0b284f6c-20200123/linux-amd64/go1.13.4"}`

Bu örnekte, http://localhost:8545 adresine bir HTTP bağlantısı kurmak için _curl_ kullanıyoruz. 8545 numaralı bağlantı noktasında bir HTTP hizmeti olarak JSON-RPC API'sini sunan geth'i zaten çalıştırıyoruz. CURL'a HTTP POST komutunu kullanması ve içeriği application/json türü olarak tanımlaması talimatını veriyoruz. Son olarak, HTTP isteğimizin veri bileşeni olarak JSON kodlu bir istek iletiyoruz. Komut satırımızın çoğunu, HTTP bağlantısını doğru yapmak için Curl tarafından ayarlıyor. dikkat  çeken kısım, yayınladığımız gerçek JSON-RPC komutudur:

`{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":1}`

JSON-RPC isteği, JSON-RPC 2.0 belirtimine göre biçimlendirilir. Her istek dört öğe içerir: 🔢

* jsonrpc:
JSON-RPC protokolünün sürümü. Bu tam olarak "2.0" OLMALIDIR.

* method:
Çağrılacak yöntemin adı.

* params:
Yöntemin çağrılması sırasında kullanılacak parametre değerlerini tutan yapılandırılmış bir değer. Bu üye EKLENEBİLİR.

* id
İstemci tarafından oluşturulmuş ve dahil edilmişse; bir dize, Sayı veya NULL değeri içermesi ZORUNLU olan bir tanımlayıcıdır. Sunucu, dahil edilmişse, yanıt nesnesindeki aynı değerle yanıt vermelidir( ZORUNLU.) Bu üye, iki nesne arasındaki bağlamı ilişkilendirmek için kullanılır.

🔍İPUCU :id parametresi, öncelikle tek bir JSON-RPC çağrısında birden çok istekte bulunduğunuzda kullanılır; bu, **toplu işlem(Batching)** adı verilen bir uygulamadır. Her istek için yeni bir HTTP ve TCP bağlantısının **ek yükünü önlemek** için toplu işlem kullanılır. Örneğin, Ethereum bağlamında, tek bir HTTP bağlantısı üzerinden binlerce işlemi almak istiyorsak toplu işleme kullanırdık. Toplu oluştururken, **her istek için farklı bir kimlik belirlersiniz** ve ardından bunu JSON-RPC sunucusundan gelen her yanıttaki kimlikle eşleştirirsiniz. Bunu uygulamanın en kolay yolu, bir **sayaç tutmak ve her istek için değeri artırmaktır**.


Aldığımız yanıt şu:

`{"jsonrpc":"2.0","id":1,
"result":"Geth/v1.9.11-unstable-0b284f6c-20200123/linux-amd64/go1.13.4"}
`
Bu bize JSON-RPC API'sinin Geth istemci sürümü 1.9.11 tarafından sunulduğunu söyler.

Biraz daha ilginç bir şey deneyelim. Bir sonraki örnekte, gazın wei'deki mevcut fiyatını JSON-RPC API'sine soruyoruz: ⏬

`$ curl -X POST -H "Content-Type: application/json" --data \
  '{"jsonrpc":"2.0","method":"eth_gasPrice","params":[],"id":4213}' \
  http://localhost:8545
{"jsonrpc":"2.0","id":4213,"result":"0x430e23400"}`

0x430e23400 yanıtı, bize mevcut gaz fiyatının **18 gwei** (gigawei veya milyar wei) olduğunu söylüyor.

Hexadecimal olarak düşünmüyorsanız, komut satırında _bash-fu_ ile ondalık sayıya dönüştürebilirsiniz:

`$ echo $((0x430e23400))`

`18000000000`(output) 

Tam JSON-RPC API'si [Ethereum wikiden](https://github.com/ethereum/wiki/wiki/JSON-RPC) araştırılabilir.🔷

## Parity'nin Geth uyumluluk modu
Parity, Geth tarafından sunulanla aynı olan bir JSON-RPC API sunduğu özel bir "Geth uyumluluk modu"na sahiptir. Parity'yi bu modda çalıştırmak için --geth anahtarını kullanın:

`$ parity --geth`

## Uzak Ethereum İstemcileri(Remote) 🤓
Uzak istemciler, tam bir(full) istemcinin _işlevlerinin bir alt kümesini sunar_. Tam Ethereum blok zincirini saklamazlar, bu nedenle kurulumları daha hızlıdır ve çok **daha az veri depolama** gerektirir.

Bu istemciler genellikle aşağıdakilerden birini veya birkaçını yapma olanağı sağlar ⬇️ 

* Bir cüzdanda özel anahtarları ve Ethereum adreslerini yönetin.

* İşlemler oluşturun, imzalayın ve yayınlayın.

* Veri yükünü kullanarak akıllı sözleşmelerle etkileşim kurun.

* DApp'lere göz atın ve etkileşim kurun.

* Blok gezgini(explorer) gibi harici hizmetlere bağlantılar sunun.

* Ehter birimlerini dönüştürün ve harici kaynaklardan döviz kurlarını alın.

* Web tarayıcısına bir JavaScript nesnesi olarak bir web3 örneği enjekte edin.

* Başka bir istemci tarafından tarayıcıya sağlanan/enjekte edilen bir web3 örneğini kullanın.

* Yerel veya uzak bir Ethereum düğümünde RPC hizmetlerine erişin.

Bazı uzak istemciler, örneğin mobil (akıllı telefon) cüzdanlar, yalnızca **temel cüzdan işlevselliği sunar.** Diğer uzak istemciler, **tam gelişmiş DApp tarayıcılarıdır**. Uzak istemciler, başka bir yerde, örneğin yerel olarak sizin tarafınızdan makinenizde veya bir web sunucusunda çalıştırılan bir **tam düğüme bağlanarak, Ethereum blok zincirinin yerel bir kopyasını senkronize etmeden,** genellikle _tam düğümlü bir Ethereum istemcisinin bazı işlevlerini_ sunar.

En popüler uzak istemcilerden bazılarına ve sundukları işlevlere bakalım.

## Mobil (Akıllı Telefon) Cüzdanlar
Tüm mobil cüzdanlar uzak istemcilerdir, çünkü akıllı telefonlar tam bir Ethereum istemcisini çalıştırmak için yeterli _kaynağa sahip değildir_. Hafif istemciler(light clients) geliştirme aşamasındadır ve Ethereum için **genel kullanımda değildir**. Parity, hafif istemci "experimental(deneysel)" olarak işaretlenir ve --light seçeneğiyle, Parity çalıştırılarak kullanılabilir.

Popüler mobil cüzdanlar aşağıdakileri içerir: ( ⚠️bunları yalnızca örnek olarak listeliyoruz; bu, bu cüzdanların güvenliğinin veya işlevselliğinin bir onayı veya göstergesi değildir.)

* [Jaxx](https://jaxx.io/)

Bitcoin, Litecoin, Ethereum, Ethereum Classic, ZCash, çeşitli ERC20 jetonları ve diğer birçok para birimini destekleyen, BIP-39 anımsatıcı tohumlarına dayalı çok para birimli bir mobil cüzdan. Jaxx, Android ve iOS'ta, tarayıcı eklenti cüzdanı ve çeşitli işletim sistemleri için masaüstü cüzdanı olarak mevcuttur.

* [Status](https://status.im/)

Çeşitli jetonları ve popüler DApp'leri destekleyen bir mobil cüzdan ve DApp tarayıcısı. iOS ve Android için kullanılabilir.

* [Trust Wallet](https://trustwalletapp.com/)

Ethereum ve Ethereum Classic'in yanı sıra ERC20 ve ERC223 belirteçlerini destekleyen mobil çoklu para birimi cüzdanı. Trust Wallet, iOS ve Android için kullanılabilir.

* [cipher Browser](https://www.cipherbrowser.com/)

Ethereum uygulamaları ve belirteçleri ile entegrasyona izin veren tam özellikli bir Ethereum özellikli mobil DApp tarayıcısı ve cüzdanı. iOS ve Android için kullanılabilir.

## Tarayıcı Cüzdanları

Chrome ,Firefox,Brave gibi web tarayıcılarının eklentileri veya uzantıları olarak çeşitli cüzdanlar ve DApp tarayıcıları mevcuttur. Bunlar, tarayıcınızın içinde çalışan uzak istemcilerdir.

Daha popüler olanlardan bazıları MetaMask, Jaxx, MyEtherWallet ve MyCrypto'dur.

* Metamask 🦊

Önceki bölümlerde de tanıtılan MetaMask, **çok yönlü bir tarayıcı tabanlı cüzdan**, RPC istemcisi ve temel sözleşme gezginidir. Chrome, Firefox, Opera ve Brave Browser'da mevcuttur.(güncel olarak mobil içinde uygun)

Diğer tarayıcı cüzdanlarından farklı olarak MetaMask, **çeşitli Ethereum blok zincirlerine (mainnet, Ropsten testnet, Kovan testnet, yerel RPC düğümü, vb.) bağlanan bir RPC istemcisi olarak hareket ederek tarayıcı JavaScript bağlamına bir web3 örneği enjekte eder.** Bir web3 örneği enjekte etme ve harici RPC hizmetlerine bir ağ geçidi görevi görme yeteneği, MetaMask'ı hem geliştiriciler hem de kullanıcılar için çok güçlü bir araç haline getirir. Örneğin, bu araçlar için bir web3 sağlayıcısı ve RPC ağ geçidi görevi gören MyEtherWallet veya MyCrypto ile birleştirilebilir.

* Jaxx
Bir önceki bölümde mobil cüzdan olarak tanıtılan Jaxx, Chrome ve Firefox eklentisi ve masaüstü cüzdan olarak da mevcut.

* MyEtherWallet (MEW)
MyEtherWallet, aşağıdakileri sunan tarayıcı tabanlı bir JavaScript uzaktan(remote) istemcisidir:

* Trezor ve Ledger gibi popüler donanım cüzdanlarına bir köprü hizmeti sunar
* Başka bir istemci tarafından enjekte edilen bir web3 örneğine bağlanabilen bir web3 arayüzüdür (ör. MetaMask)
* Bir Ethereum tam istemcisine bağlanabilen bir RPC istemcisidir
* Bir sözleşmenin adresi ve uygulama ikili arayüzü (ABI) verildiğinde akıllı sözleşmelerle etkileşime girebilen temel bir arayüz sunar
* Bir donanım cüzdanına benzer şekilde, birinin uyumlu bir Android veya iOS cihazı kullanmasını sağlayan bir mobil uygulama olan MEWConnect.
* JavaScript'te çalışan bir yazılım cüzdanıdır.

⚠️UYARI: MyEtherWallet ve diğer tarayıcı tabanlı JavaScript cüzdanlarına erişirken çok dikkatli olmalısınız, çünkü bunlar kimlik avı için sık hedeflerdir. Doğru web URL'sine erişmek için her zaman bir _arama motoru veya bağlantı_ değil,🔴 bir yer imi(favoriler-sık kullanılanlar gibi) 🟢 kullanın.📌







