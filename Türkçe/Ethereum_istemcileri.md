
# ETHEREUM İSTEMCİLERİ(Clients) 🔌

Ethereum istemcisi, _Ethereum spesifikasyonunu uygulayan ve eşler arası ağ üzerinden diğer Ethereum istemcileriyle iletişim kuran bir yazılım uygulamasıdır._ Farklı Ethereum istemcileri, referans belirtimine ve standartlaştırılmış iletişim protokollerine **uyuyorlarsa birlikte çalışırlar.** Bu farklı istemciler farklı ekipler tarafından ve _farklı programlama dillerinde uygulanırken_, hepsi aynı **protokolü "konuşur" ve aynı kuralları takip eder.** Bu nedenle, hepsi aynı Ethereum ağıyla çalışmak ve etkileşim kurmak için kullanılabilir.

Ethereum _açık kaynaklı_ bir projedir ve tüm büyük istemciler için kaynak kodu, açık kaynak lisansları (örneğin, LGPL v3.0) altında mevcuttur.İndirmek ve herhangi bir amaç için kullanmak ücretsizdir. Açık kaynak, kullanımı ücretsiz olmaktan çok daha fazlasını ifade eder. Ayrıca Ethereum'un gönüllüler topluluğu(foundation) tarafından geliştirildiği ve herkes tarafından değiştirilebileceği anlamına gelir. _Daha fazla bakış açısı, daha güvenilir kod anlamına gelir._ 🛡️

Ethereum, "Sarı Kağıt"(Yellow Paper) 🟨 adı verilen resmi bir spesifikasyonla( 🇹🇷 TDK:Teknik özelliklerini anlatan şartnameye verilen ad) tanımlanır.

Ethereum'un spesifikasyonu -İngilizce ve matematiksel (resmi)- olarak birleştiren bir kağıtta belgelenmiştir. Bu resmi belirtim, çeşitli Ethereum İyileştirme Önerilerine ek olarak, bir _Ethereum istemcisinin standart davranışını tanımlar_. Sarı Kitap(yellow paper), Ethereum'da büyük değişiklikler yapıldıkça periyodik olarak güncellenir.

Ethereum'un açık ve resmi spesifikasyonunun bir sonucu olarak, bir _Ethereum istemcisi bağımsız olarak geliştirilmiş_ , ve bununla  **birlikte çalışabilir yazılım uygulamaları** vardır. Ethereum, ağ üzerinde çalışan diğer tüm blok zincirlerinden daha **fazla çeşitliliğe sahiptir** ve bu genellikle **iyi bir şey olarak kabul edilir.** (Gerçek merkeziyetsizliğe her şekilde ulaşabilmek) Gerçekten de, örnek olarak; **belirli bir istemcinin uygulama stratejisinden yararlanılması, geliştiricileri açıkları düzeltirken yaşadıkları güçlükleri halletmeye çalışırken, diğer istemciler ağın neredeyse etkilenmeden çalışmasını sağladığından, ağ üzerindeki saldırılara karşı mükemmel bir savunma** yolu olduğunu kanıtlamıştır.

-------------------
## Ethereum Ağları

Ethereum Yellow Paper'da tanımlanan resmi spesifikasyona büyük ölçüde uyan, ancak birbirleriyle birlikte çalışabilen veya çalışamayan çeşitli Ethereum tabanlı ağlar vardır.

Bu Ethereum tabanlı ağlar arasında Ethereum, Ethereum Classic, Ella, Expanse, Ubiq, Musicoin ve diğerleri bulunur. Çoğunlukla protokol düzeyinde uyumlu olsa da, bu ağlar genellikle her bir ağı desteklemek için Ethereum istemci yazılımının bakımcılarının küçük değişiklikler yapmasını gerektiren özelliklere veya özniteliklere sahiptir. Bu nedenle, Ethereum istemci yazılımının her sürümü, her Ethereum tabanlı blok zincirini çalıştırmaz.

Şu anda, altı farklı dilde yazılmış **Ethereum protokolünün altı ana uygulaması vardır**:

* parite ---> Rust ile yazılmış 

* Geth ------> Go ile yazılmış

* cpp-ethereum ----> C++ ile yazılmış

* pyethereum ------->Python ile yazılmış 

* Mantis ------> Scala ile yazılmış

* Harmony -------> Java ile yazılmış

 ⭐ Bu bölümde, en yaygın iki istemciye,_Parity ve Geth'e bakacağız._ Her istemciyi kullanarak bir düğümün nasıl kurulacağını göstereceğiz ve bazı komut satırı seçeneklerini ve uygulama programlama arabirimlerini (API'ler) keşfedeceğiz.
 
 ----------------------
 
 ## Tam Düğüm(full Node) Çalıştırmalı mıyım? 🎛️
 
 Blok zincirlerinin **kullanımı,esnekliği ve sansür direnci gibi önemli unsurları, bağımsız olarak işletilen ve coğrafi olarak dağılmış birçok tam düğüme sahip olmalarına bağlıdır. Her bir tam düğüm, diğer yeni düğümlerin operasyonlarını başlatmak için blok verilerini almasına yardımcı olabilir ve ayrıca operatöre tüm işlemlerin ve sözleşmelerin yetkili ve bağımsız bir doğrulamasını sunar.**
 
 Ancak, tam bir düğüm çalıştırmak, donanım kaynaklarında ve bant genişliğinde bir maliyete neden olacaktır. Tam bir düğüm 300 GB'a kadar veri indirebilir (istemci yapılandırmasına bağlı olarak Mart 2021'den itibaren) ---->[🗒️NOT: güncel olarak şuanlık EYLÜL2022---->730 GB ] ve yerel bir sabit sürücüde depolayabilir. Bu veri yükü, her geçen gün yeni işlemler ve bloklar eklendikçe oldukça hızlı bir şekilde artmaktadır. Bu konuyu Tam Düğüm için Donanım Gereksinimlerinde daha ayrıntılı olarak anlatacağız.
 Main net ağında çalışan tam bir düğüm, Ethereum geliştirmesi için gerekli değildir. Bir testnet düğümü (sizi daha küçük genel test blok zincirlerinden birine bağlar), **Ganache gibi yerel bir özel blok zincir** veya **Infura gibi bir hizmet sağlayıcı tarafından sunulan bulut tabanlı bir Ethereum istemcisi** ile yapmanız gereken hemen hemen her şeyi yapabilirsiniz. 
 
 Ayrıca blok zincirinin yerel bir kopyasını **saklamayan veya blokları ve işlemleri doğrulamayan** bir uzak istemci(remote clients) çalıştırma seçeneğiniz de vardır. Bu istemciler bir _cüzdanın işlevselliğini_ sunar ve işlemler oluşturabilir ve yayınlayabilir. Uzak istemciler, kendi tam düğümünüz, public blok zinciri, genel veya izin verilen (PoA) test ağı veya özel-yerel blok zinciri gibi mevcut ağlara bağlanmak için kullanılabilir. Pratikte, **tüm farklı düğüm seçenekleri arasında geçiş yapmanın uygun bir yolu olarak MetaMask, Emerald Wallet, MyEtherWallet veya MyCrypto gibi uzak bir istemci** kullanırsınız.

Bazı farklılıklar olsa da "uzaktan istemci(remote clients)" ve "cüzdan"(wallet) terimleri _birbirinin yerine kullanılır._  _Genellikle bir uzak istemci, bir cüzdanın işlem fonksiyonlarına ek olarak bir **API (web3.js API gibi)** sunar._
 
 ⚠️
Ethereum'daki uzak cüzdan kavramını _light clients_ ile(Bitcoin'deki Basitleştirilmiş Ödeme Doğrulama istemcisine benzer) karıştırmayın. light istemciler, blok _başlıklarını doğrular ve işlemlerin blok zincirine dahil edilmesini doğrulamak ve etkilerini belirlemek için Merkle kanıtlarını kullanır.Onlara tam bir düğüme benzer bir güvenlik düzeyi verir._ Oysa, **Ethereum remote clients blok başlıklarını veya işlemlerini doğrulamaz.** Blok zincirine erişim sağlamak için tam bir itemciye(full_node) tamamen güvenirler ve bu nedenle önemli güvenlik ve anonimlik garantilerini kaybederler. Kendi çalıştırdığınız tam bir istemci kullanarak bu sorunları azaltabilirsiniz.("Node KURUN " Dr.tobbyKitty 🐱") 

📝NOT+Ekleme :Nodelar hakkında daha fazla bilgi almak için [tobby'nin web sitesini](https://tobbykitty.com/2022/05/28/node-nedir-nodelar-hakkinda-her-sey/)
ziyaret edebilirsiniz.



 
 
 
 
