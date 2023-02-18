# Ethereum Nedir? 🔵 💙

⏲️ **38dk** 


Ethereum genellikle "dünya bilgisayarı" olarak tanımlanır. Ama bu ne anlama geliyor? Bilgisayar
bilimi bakış açısıyla açıklama ile başlayalım ve ardından bunu, Ethereum'un kapasitesi ve 
özelliklerinin daha pratik bir analiziyle, Bitcoin ve diğer merkeziyetsiz, bilgi alışverişi platformlarıyla 
(veya kısaca "blok zincirler")ile karşılaştırarak çözmeye çalışalım.


Bilgisayar bilimi açısından bakıldığında, _Ethereum_, küresel olarak erişilebilir bir tekil durumdan ve 
bu duruma değişiklikleri uygulayan bir sanal makineden oluşan deterministik bir makinedir ancak pratikte sınırsız bir durum makinesidir.
(**state machine:sonlu otomat veya basitçe durum makinesi, matematiksel bir hesaplama modelidir. Herhangi bir zamanda tam olarak sonlu sayıdaki durumlardan birinde olabilen soyut bir makinedir. FSM(Finite State machine), bazı girdilere yanıt olarak bir durumdan diğerine geçebilir; bir durumdan başka bir duruma geçişe transition<geçiş>denir.**)


Daha Pratiksel(Uygulamaya yönelik) bir bakış açısıyla Ethereum, akıllı sözleşmeler adı verilen
programları çaıştıran açık kaynaklı, global olarak merkezi olmayan bir bilgi-işlem altyapısıdır. 
Sistemin durum değişikliklerini senkronize etmek ,depolamak için bir blok zinciri ve yürütme(çalıştırma) kaynak maliyetlerini ölçmek ve kısıtlamak için _ether_(bununda alt birimleri mevucttur) adı verilen bir kripto para birimi kullanır.

Ethereum platformu, geliştiricilerin; hazır,ekonomik işlevlere sahip ve 
güçlü merkeziyetsiz uygulamalar oluşturmasını sağlar.Yüksek kullanılabilirlik, denetlenebilirlik,
şeffaflık ve tarafsızlık sağlarken sansürü azaltır veya ortadan kaldırır ve belirli karşı taraf risklerini azaltır.


## Bitcoin ile kıyaslandığında


Birçok kişi, özellikle _Bitcoin_ olmak üzere, önceden kripto para birimleri deneyimiyle Ethereum'a gelecektir. Ethereum, diğer açık blok zincirlerle birçok ortak unsuru paylaşır: katılımcıları birbirine bağlayan bir eşler arası ağ, durum güncellemelerinin senkronizasyonu için Bizans Genaralleri --hataya dayanıklı bir konsensüs algoritması-- (bir İş kanıtı(PoW) :pencil: **Bu çeviriyi yaparken Ethereum PoS geçmiş yani Merge edilmiş olabilir Unutmayın** <2022 Eylul>), dijital gibi kriptografik ilkellerin kullanımı imzalar ve hash(benzersiz farklı uzunluklta girdiler sonucu sabit uzunlukta benzersiz çıktılar veren _özet değer algoritaması_) ve bir dijital para birimi kullanır. (Ether)

Yine de birçok yönden, Ethereum'un hem amacı hem de yapısı, Bitcoin de dahil olmak üzere, kendisinden önce gelen açık blok zincirlerinden çarpıcı biçimde farklıdır.

Ethereum'un amacı, öncelikle bir dijital para birimi ödeme ağı olmak değildir. Dijital para birimi ether, **Ethereum'un çalışması için hem ayrılmaz hem de gerekli olsa da, ether, Ethereum platformunun dünya bilgisayarı olarak kullanımı için** ödeme yapmak için bir 
_yardımcı para birimi_ olarak tasarlanmıştır. 💻 :moneybag:


Çok sınırlı bir Betik diline sahip olan Bitcoin'den farklı olarak, Ethereum, keyfi ve 
sınırsız karmaşıklıkta kod yürütebilen ve sanal bir makine çalıştıran genel amaçlı programlanabilir bir blok zinciri olarak tasarlanmıştır. 
Bitcoin'in Komut Dosyası dili, kasıtlı olarak,  basitçe  doğru/yanlış değerlendirmesiyle sınırlandırıldığında Ethereum'un dili Turing bütünlüğüdür.
Yani Ethereum'un doğrudan genel amaçlı bir bilgisayar olarak işlev görebileceği anlamına gelir.
'[Alan Turing Bütünlüğü Wiki](https://en.wikipedia.org/wiki/Turing_completeness)'
:pencil: Wikiden şimdi kim okuyacak yaaağ :smile: derseniz kısaca: 
_Sistemin diğer veri işleme kural kümelerini tanıyabileceği veya karar verebileceği anlamına gelir._

## Blokzincirin Bileşenleri: ⛓️ 
-Open ve Public bir blok zincirinin bileşenleri (genel Olarak):

* Standartlaştırılmış bir **Gossip** protokolüne dayalı olarak, katılımcıları birbirine bağlayan,işlemleri ve doğrulanmış işlem bloklarını yayan bir eşler arası (P2P) ağ.(Gossip Protokolü :Bir iletişim protokolüdür, bilginin sosyal ağlarda nasıl paylaşıldığı ile aynı prensipte çalışan bilgisayardan bilgisayara iletişim sürecidir. daha fazla bilgi için GeeksforGeeks ziyaret edebilirsiniz 😻[Gossip Protocol](https://www.geeksforgeeks.org/the-gossip-protocol-in-cloud-computing/)
* Durum geçişlerini temsil eden işlemler şeklinde mesajlar.
* Neyin bir işlemi oluşturduğunu ve neyin geçerli bir durum geçişini sağladığını yöneten bir dizi fikir birliği kuralı.
* Konsensüs kurallarına göre işlemleri işleyen bir [durum makinesi](https://www.techopedia.com/definition/16447/state-machine)---> Ben şimdi bunu okuyamam derseniz **kısaca: Durum makinesi, bilgisayar programları veya dijital mantık tasarlamada kullanılan bir kavramdır. İki tür durum makinesi vardır: sonlu ve sonsuz durum makineleri. İlki, koşullar karşılandığında mantık yolunun tespit edilebildiği,akış grafikleriyle modellenebilen sınırlı sayıda durum, geçiş ve eylemden oluşur. İkincisi pratik olarak kullanılmaz(?).Yani belirli bir zamanda bir şeyin durumunu depolayan herhangi bir cihazdır. Durum, girdilere dayalı olarak değişir ve uygulanan değişiklikler için sonuç çıktısını sağlar.** 
* Doğrulanmış ve kabul edilmiş 🟢 tüm durum geçişlerinin bir günlüğü(Distr. Ledger'a atıf) :book: gibi davranan, kriptografik olarak güvenli bir blokzincir.
* Katılımcıları konsensüs kurallarının uygulanmasında işbirliği yapmaya zorlayarak,blok zinciri üzerindeki kontrolü merkezsizyetsiz hale getiren bir konsensüs algoritması.
* Durum makinesini açık bir ortamda(open) ekonomik olarak güvenceye almak için [Oyun Teorisine](https://tr.wikipedia.org/wiki/Oyun_teorisi) dayalı olarak sağlam bir teşvik planı (örneğin, çalışma kanıtı maliyetleri-- blok ödülleri) [Buradaki yazıdanda okuyabilirsiniz](https://www.oyunlastirma.co/metaverse/blockchain-ve-oyun-teorisi-iliskisi-binanca-akademisi/) ---> Oyun Teorisi wikiyi kim okyacak yaaa 😄diyorsanız **kısaca : Oyun teorisi, bireyin başarısının diğerlerinin seçimlerine dayalı olduğu seçimler yapması olan, bazı stratejik durumların matematiksel olarak davranış biçimlerini yakalamaya çalışır.**

Bu bileşenlerin tümü veya çoğu genellikle tek bir yazılım istemcisinde(client) birleştirilir. Örneğin, Bitcoin'de referans uygulaması, Bitcoin Core açık kaynak projesi tarafından geliştirilir ve bitcoind istemcisi olarak uygulanır. Ethereum'da, bir _referans uygulaması_ yerine bir _referans spesifikasyonu_, vardır.sistemin Yellow Pepper'ında matematiksel bir açıklaması vardır.Referans spesifikasyonuna göre oluşturulmuş bir dizi istemci vardır.

Geçmişte, açıklanan tüm özellikleri kapsayan teknolojilerin kombinasyonuna ,kısaca (referans olarak), az önce listelenen tüm bileşenleri temsil etmek için "blockchain" terimini kullandık. Ancak bugün, farklı özelliklere sahip çok çeşitli blok zincirleri var. Açık, genel, küresel, merkezi olmayan, tarafsız ve sansüre dayanıklı gibi. Söz konusu blok zincirinin özelliklerini anlamamıza yardımcı olacak kavramlara ihtiyacımız var ve bunun için bileşenlerin izin verdiği bir "blok zinciri" sisteminin ortaya çıkardiğı önemli özelliklerini tanımlamamız lazım. 

Tüm blok zincirleri eşit yaratılmamıştır. Birisi size bir şeyin blok zinciri olduğunu söylediğinde, bir yanıt almamışsınızdır 🔴; bunun yerine, "blockchain" kelimesini kullandıklarında ne anlama geldiklerini netleştirmek için birçok soru sormaya başlamalısınız. 🤔: Önceki listedeki bileşenlerin tanımını sorarak başlayın, ardından bu "blok zincirinin" açık(open), genel(public),Özel(private) vb. özellikler gösterip göstermediğini sorun.

## Ethereum'un Doğuşu(başlangıcı):

Tüm büyük yenilikler gerçek sorunları çözer ve Ethereum bir istisna değildir. Ethereum, insanların Bitcoin modelinin gücünü fark ettiği ve kripto para uygulamalarının ötesine geçmeye çalıştığı bir zamanda tasarlandı. Ancak geliştiriciler bir bilmeceyle karşı karşıya kaldılar: Ya Bitcoin'in üzerine inşa etmeleri(yeni ürünler ortaya koymak) ya da **yeni bir blokzinciri** başlatmaları(kurmak) gerekiyordu. Bitcoin üzerine inşa etmek(chainin yani), ağın kesin kısıtlamaları içinde yaşamak ve geçici çözümler bulmaya çalışmak anlamına geliyordu. Sınırlı işlem türleri, veri türleri ve veri depolama boyutları, doğrudan Bitcoin üzerinde çalışabilecek uygulama türlerini sınırlandırıyor gibiydi; başka herhangi bir şey ek zincir dışı katmanlara ihtiyaç duyuyordu ve bu, halka açık bir blok zinciri kullanmanın birçok avantajını hemen ortadan kaldırdı. Zincirde daha fazla serbestliğe ve esnekliğe ihtiyaç duyan projeler için tek seçenek yeni bir blok zincirdi. Ancak bu çok fazla iş anlamına geliyordu: tüm altyapı öğelerini yeniden başlatmak, kapsamlı testler vb.

2013'ün sonlarına doğru, genç bir programcı ve Bitcoin meraklısı olan **Vitalik Buterin**💙, Bitcoin ve _Mastercoin'in (Bitcoin'i basit akıllı sözleşmeler sunacak şekilde genişleten bir bindirme protokolü)_ özelliklerini daha da genişletmeyi düşünmeye başladı. Aynı yılın Ekim ayında Vitalik, Mastercoin ekibine, Mastercoin'in özel sözleşme dilinin yerine esnek ve yazılabilir (ancak Turing-tamamlanmamış) sözleşmelere izin veren daha genel bir yaklaşım önerdi. Mastercoin ekibi etkilenmiş olsa da, bu teklif kendi yol haritalarında  çok radikal bir değişikliğe sebep olurdu.

Aralık 2013'te Vitalik, Ethereum'un arkasındaki fikri özetleyen bir teknik incelemeyi(**whitepaper**) paylaşmaya başladı: _Turing-complete halde , genel amaçlı bir blokzincir_. Birkaç düzine insan bu ilk taslağı gördü ve geri bildirimde bulundu ve Vitalik'in teklifi geliştirmesine yardımcı oldular.

Bu kitabın her iki yazarı da teknik incelemenin erken bir taslağını aldı ve üzerinde yorum yaptı. Andreas M. Antonopoulos bu fikirden etkilendi ve Vitalik'e akıllı sözleşme yürütme konusunda fikir birliği kurallarını uygulamak için ayrı bir blok zincirinin kullanımı ve ↗️ [Turing-complete](https://en.wikipedia.org/wiki/Turing_completeness) ,diline etkileri hakkında birçok soru sordu. Andreas, Ethereum'un ilerlemesini büyük bir ilgiyle takip etmeye devam etti, ancak Mastering Bitcoin adlı kitabını yazmanın ilk aşamalarındaydı ve çok sonrasına kadar doğrudan Ethereum'a katılmadı. Ancak Dr. Gavin Wood, Vitalik'e ulaşan ve C++ programlama becerileri konusunda yardım teklif eden ilk kişilerden biriydi. Gavin, Ethereum'un kurucu ortağı, ortak tasarımcısı ve CTO'su oldu.

Vitalik'in ["Ethereum Prehistory"](https://vitalik.ca/general/2017/09/14/prehistory.html) yazısında anlattığı gibi:

____
Bu, Ethereum protokolünün tamamen benim eserim olduğu zamandı. Ancak bu andan itibaren gruba yeni katılımcılar katılmaya başladı. Protokol tarafında açık ara en öne çıkan isim Gavin Wood'du…

Gavin ayrıca, Ethereum'u dijital varlıkları tutabilen ve önceden belirlenmiş kurallara göre bunları genel amaçlı bir bilgi işlem platformuna aktarabilen blok zincir tabanlı sözleşmelerle programlanabilir para oluşturmak için bir platform olarak görmekten tutun ,vizyondaki ince değişiklik için büyük ölçüde kredilendirilebilir(değerlendirilebilmek)... 
Bu, vurgu ve terminolojideki ince değişikliklerle başladı ve daha sonra bu etki, Ethereum'u merkezi olmayan teknolojilerin bir parçası, diğer ikisi Whisper ve Swarm olarak gören “Web 3” topluluğuna artan vurgu ile daha da güçlendi.
____

Aralık 2013'ten itibaren Vitalik ve Gavin, Ethereum olan protokol katmanını birlikte oluşturarak fikri yeniledi ve geliştirdi.

Ethereum'un kurucuları, programlanarak çok çeşitli uygulamaları destekleyebilecek belirli bir amacı olmayan bir blok zinciri düşünüyorlardı. Fikir, Ethereum gibi genel amaçlı bir blok zinciri kullanarak, bir geliştiricinin, eşler arası ağların, blok zincirlerin, konsensüs algoritmalarının vb. temel mekanizmalarını uygulamak zorunda kalmadan kendi özel uygulamalarını programlayabilmesiydi. Ethereum platformu soyutlamak için tasarlandı. bu ayrıntılar ve merkezi olmayan blok zinciri uygulamaları için belirleyici ve güvenli bir programlama ortamı sağlayacaktı.

💝**Satoshi gibi, Vitalik ve Gavin da yeni bir teknoloji icat etmediler**; yeni buluşları mevcut teknolojilerle özgün bir şekilde birleştirdiler ve fikirlerini dünyaya kanıtlamak için prototip kodunu yaydılar.
Kurucular yıllarca çalıştılar, vizyonu inşa ettiler ve geliştirdier ve nihayet 30 Temmuz 2015'te ilk Ethereum bloğu çıkarıldı. _Dünyanın bilgisayarı_, dünyaya hizmet etmeye başladı.

📝NOT: Vitalik Buterin'in "A Prehistory of Ethereum" adlı makalesi Eylül 2017'de yayınlandı ve Ethereum'un ilk zamanlarının büyüleyici bir birinci-şahıs bakış açısıyla sunuyor.
➡️[buradan](https://vitalik.ca/general/2017/09/14/prehistory.html) okuyabilirsiniz.

## Ethereum'un Dört Gelişim Aşaması

Ethereum'un gelişimi, her aşamada meydana gelen büyük değişikliklerle birlikte dört farklı aşamada planlandı. Bir aşama, işlevselliği geriye dönük uyumlu _olmayacak_ şekilde değiştiren "sert çatallama(Hard Forks)" olarak bilinen alt sürümler içerebilir.

Dört ana geliştirme aşamasının kod adları: 
* Frontier 
* Homestead 
* Metropolis  
* Serenity

Bugüne kadar ortaya çıkan ara sert çatallar(intermediate hard forks); _Ice Age, DAO, Tangerine Whistle, Spurious Dragon, Byzantium, Constantinople/St. Petersburg, İstanbul ve Muir Glacier_. Hem geliştirme aşamaları hem de ara sert çatallar, blok numarasına göre "tarihli" olan aşağıdaki zaman çizelgesinde gösterilmektedir:
_____
* Blok #0
Frontier —> Ethereum'un 30 Temmuz 2015'ten Mart 2016'ya kadar süren ilk aşaması. 🔢
_____

* Blok #200.000
Ice Age—>Hazır olduğunda PoS'a geçişi motive etmek için üstel bir zorluk artışı getiren bir hard fork.

_____
* Blok #1,150.000
Homestead—>Ethereum'un ikinci aşaması, Mart 2016'da piyasaya sürüldü. 🔢
_____
* Blok #1,192.000
DAO—Saldırıya uğramış DAO sözleşmesinin kurbanlarını geri ödeyen ve Ethereum ile Ethereum Classic'in iki rakip sisteme bölünmesine neden olan bir hard fork.

* Blok #2,463,000
Tangerine Whistle—>Belirli I/O ağırlıklı operasyonlar için gaz hesaplamasını değiştirmek ve bu operasyonların düşük gaz maliyetinden yararlanan bir hizmet reddi (DoS) saldırısından birikmiş durumu temizlemek için bir hard fork.

* Blok #2,675,000
Spurious Dragon—>Daha fazla DoS saldırı vektörüne yönelik bir hard fork ve başka bir durum temizleme. Ayrıca, bir tekrar saldırı koruma mekanizması.
_______
* Blok #4.370.000
Metropolis Byzantium—Metropolis,---> Ethereum'un üçüncü aşamasıdır. Ekim 2017'de piyasaya sürülen Byzantium, Metropolis'in ilk bölümüdür ve düşük seviyeli işlevler ekler ve blok ödülünü ve zorluğunu ayarlar. 🔢
_______
* Blok #7.280.000
Konstantinopolis / St. Petersburg—Konstantinopolis, Metropolis'in benzer iyileştirmelerle ikinci kısmı olarak planlandı. Etkinleştirilmesinden birkaç saat önce kritik bir hata keşfedildi. Bu nedenle hard fork ertelendi ve St. Petersburg olarak yeniden adlandırıldı.

* Blok #9.069.000
İstanbul—Önceki ikisiyle aynı yaklaşıma ve adlandırma kuralına sahip ek bir hard fork.

* Blok #9,200,000
Muir Glacier—Buz Devri'nin getirdiği üstel artış nedeniyle tek amacı zorluğu yeniden ayarlamak olan bir hard fork.
______
⚠️Güncel UYARI: Şimdi kitapta Serenity(ETH 2.0)aşamasına yani 4.aşamaya 🔢 geçeceğini söylemiş buna çok yaklaştık değerli arkadaşlar hatta siz bunu okurken ETH merging(Yani PoS geçmiş) olabilir(oldu bile.Ethereum merge edildi😸).Bundan sonra Merging kısmında yapılacak gelişmeler ise şöyle olacak :

* Merge 
* Surge  
* Verge 
* Purge 
* Splurge.

↪️[daha fazla bilgi için](https://news.t-rex.exchange/en/ethereum-after-merge/)

---------

## Ethereum: Genel Amaçlı Bir Blok Zincir ⛓️

Orijinal blok zincir, yani Bitcoin'in blok zinciri, bitcoin birimlerinin durumunu ve sahipliklerini izler. Bitcoin'i, işlemlerin küresel bir durum geçişine neden olarak bitcoinlerin sahipliğini değiştiren, dağıtık bir konsensüs durum makinesi olarak düşünebilirsiniz. Durum geçişleri, konsensüs kuralları tarafından sınırlandırılır ve tüm katılımcıların (sonunda) birkaç blok çıkarıldıktan sonra sistemin ortak bir (konsensüs) durumu üzerinde birleşmesine izin verir.

Ethereum ayrıca dağıtılmış bir durum makinesidir. Ancak, yalnızca para birimi sahipliği durumunu izlemek yerine, Ethereum genel amaçlı bir veri deposunun, yani bir anahtar-değer(key-value) demeti(tuple ---> Python bilginiz varsa eğer **kısaca içine veri depolamak için kullanılan veri türüdür.List yapısını andırır.
KAFANIZI KARIŞTIRMAK İSTEMEM 🤯 AMA BURADA TIPKI BİR SOLIDITY MAPPING GİBİ DÜŞÜNMENİZİ İSTİYORUM.[MAPPING HAKKINDA DAHA FAZLA BİLGİ İÇİN 🇹🇷](https://veliuysal.medium.com/solidity-veri-tipi-mapping-bcf39d8b0ef9)**) olarak ifade edilebilen herhangi bir veriyi tutabilen bir deponun durum geçişlerini izler. Bir anahtar-değer veri deposu, her biri bir anahtar tarafından başvurulan rastgele değerleri tutar; örneğin, "Victor Hugo" anahtarı(key) 🔑 tarafından başvurulan "Sefiller" kitabı değeri(value)🔐.Bazı yönlerden bu, çoğu genel amaçlı bilgisayar tarafından kullanılan Rastgele Erişim Belleğinin **(RAM)** veri depolama modeliyle aynı amaca hizmet eder. Ethereum, hem kodu hem de verileri depolayan belleğe sahiptir ve bu belleğin zaman içinde nasıl değiştiğini izlemek için Ethereum blok zincirini kullanır. Genel amaçlı depolanmış programlı bir bilgisayar gibi, Ethereum durum makinesine kod yükleyebilir ve bu kodu çalıştırabilir ve sonuçta ortaya çıkan durum değişikliklerini blok zincirinde saklayabilir.Çoğu genel amaçlı bilgisayardan kritik farklılıklardan ikisi, Ethereum durum değişikliklerinin fikir birliği kurallarına göre yönetilmesi ve durumun küresel olarak dağıtılmasıdır. _Ethereum şu soruyu yanıtlıyor: "Herhangi bir rastgele durumları izleyebilir ve durum makinesini fikir birliği altında çalışan, dünya çapında bir bilgisayar oluşturmak için programlayabilirsek ne olur?"_

## Ethereum Bileşenleri(Parçaları)
Ethereum'da, Bir Blok Zincirinin Bileşenleri bölümünde açıklanan bir blok zinciri sisteminin bileşenleri, daha spesifik(özel olarak,derinlemesine) olarak açıklayacak olursak:


* P2P ağı / P2P network
Ethereum, 30303 numaralı TCP bağlantı noktasında adreslenebilen Ethereum ana ağı üzerinde çalışır ve ÐΞVp2p adlı bir protokol çalıştırır.

* fikir birliği kuralları /Consensus rules
Ethereum'un konsensüs kuralları, referans spesifikasyonu olan Sarı Kitapta tanımlanmıştır (bkz. Daha Fazla Okuma).

* işlemler /Transactions
Ethereum işlemleri (diğer şeylerin yanı sıra) bir gönderici, alıcı, değer ve veri yükünü içeren ağ mesajlarıdır.

* durum makinesi /state Machine

Ethereum durum geçişleri, bayt kodunu (makine dili talimatları) yürüten, yığın tabanlı bir sanal makine olan _Ethereum Sanal Makinesi (EVM)_ tarafından işlenir. "Akıllı sözleşmeler" olarak adlandırılan EVM programları, yüksek seviyeli dillerde (örneğin, Solidity) yazılır ve EVM'de yürütülmek üzere bayt koduna derlenir.

* Veri yapıları /Data Structures

Ethereum'un durumu, Merkle Patricia Ağacı adı verilen serileştirilmiş bir karma veri yapısında işlemleri ve sistem durumunu içeren bir veritabanı (genellikle Google'ın LevelDB'si) olarak her düğümde yerel olarak depolanır.

* fikir birliği algoritması / Consensus algorithm
Ethereum, en uzun zinciri ve dolayısıyla mevcut durumu belirlemek için önemi PoW tarafından belirlenen sıralı tek imza bloklarını kullanan Bitcoin'in fikir birliği modeli Nakamoto Consensus'u kullanır. Ancak, yakın gelecekte kod adı Casper olan PoS ağırlıklı oylama sistemine geçme planları var.(?)

* Ekonomik güvenlik / Economic security
Ethereum şu anda _Ethash_ adlı bir PoW algoritması kullanıyor, ancak gelecekte bir noktada PoS'a geçişle bu algoritmadan vazgeçilecek.

* İstemciler /Clients
Ethereum, en belirginleri Go-Ethereum (Geth) ve Parity olan istemci yazılımının birlikte çalışabilir birkaç uygulamasına sahiptir.

**Daha fazla bu konular hakkında okuma yapmak isterseniz 🇬🇧**
Aşağıdaki referanslar, burada bahsedilen teknolojiler hakkında ek bilgi sağlar: ⬇️

* Ethereum Sarı Kağıdı(yellow Paper): https://ethereum.github.io/yellowpaper/paper.pdf

* Bej Kağıt(beige), Sarı Kağıdın daha geniş bir kitle için _daha az resmi_ bir dilde yeniden yazılmış hali: https://github.com/chronaeon/beigepaper

* ÐΞVp2p ağ protokolü: https://github.com/ethereum/devp2p/blob/master/rlpx.md

* Ethereum Sanal Makinesi kaynak listesi: https://eth.wiki/en/concepts/evm/ethereum-virtual-machine-(evm)-awesome-list

* LevelDB veritabanı (en sık blok zincirinin yerel kopyasını saklamak için kullanılır): https://github.com/google/leveldb

* Merkle-Patricia ağaçları: https://eth.wiki/en/fundamentals/patricia-tree

* Ethash PoW algoritması: https://eth.wiki/en/concepts/ethash/ethash

* Casper PoS v1 Uygulama Kılavuzu: http://bit.ly/2DyPr3l

* Go-Ethereum (Geth) istemcisi: https://geth.ethereum.org/

* Parite Ethereum istemcisi: https://parity.io/

<img title="Alan_Turing" alt="Imitation_Game" src="https://upload.wikimedia.org/wikipedia/commons/a/a1/Alan_Turing_Aged_16.jpg">


## Ethereum ve Turing Bütünlüğü 🤖

Ethereum hakkında okumaya başlar başlamaz, hemen "Turing complete" terimiyle karşılaşacaksınız. Ethereum, Bitcoin'in aksine "Turing complete" olduğunu söylüyorlar. Bu tam olarak ne anlama geliyor?

Terim, bilgisayar biliminin babası olarak kabul edilen İngiliz matematikçi [Alan Turing](https://tr.wikipedia.org/wiki/Alan_Turing)'i ifade eder. **🎥EKstra Bilgi: Ayrıca Alan Turing'in hayatını konu alan Başrolünde Benedict Cumberbatch'ın oynadığı [Imitation Game-Enigma](https://www.imdb.com/title/tt2084970/) izlemenizi tavsiye ederim**.🍿 1936'da sembolleri sıralı belleğe(sonsuz uzunlukta bir kağıt bandı andıran), okuyarak ve yazarak manipüle(yönlendiren) eden bir durum makinesinden oluşan bir bilgisayarın matematiksel bir modelini yarattı. Bu yapı ile Turing,**evrensel hesaplanabilirlik,** yani tüm problemlerin çözülebilir olup olmadığı ile ilgili soruları (olumsuz) yanıtlamak için matematiksel bir temel sağlamaya devam etti. Hesaplanamayan problem sınıfları olduğunu kanıtladı. Spesifik olarak, **Durma sorununun(halting problem)** (rastgele bir  girdi verildiğinde, programın sonunda çalışmayı durdurup durmayacağını belirlemenin mümkün olup olmadığı) çözülebilir _olmadığını_ kanıtladı. Alan Turing ayrıca, herhangi bir Turing makinesi simüle etmek(taklit etmek) için kullanılabiliyorsa, Turing'in eksiksiz olduğu bir sistemi tanımladı<Turing complete>. Böyle bir sisteme Evrensel Turing makinesi (UTM) denir.
  
  Ethereum'un, verileri belleğe okurken ve yazarken, Ethereum Sanal Makinesi adı verilen bir durum makinesinde; barındırılan bir programı yürütme yeteneği, onu Turing-bütün(turing complete) bir sistem ve dolayısıyla bir UTM(Evrensel Turing makinesi) yapar. Ethereum, sonlu belleğin sınırlamaları göz önüne alındığında, herhangi bir Turing makinesi tarafından hesaplanabilen herhangi bir algoritmayı hesaplayabilir.

Ethereum'un çığır açan yeniliği, depolanmış programlı bir bilgisayarın genel amaçlı bilgi işlem mimarisini merkezi olmayan bir blokzinciri ile birleştirmek ve böylece dağıtık,tek durumlu (singleton) dünya bilgisayarı oluşturmaktır. Ethereum programları "her yerde" çalışır, ancak fikir birliği(consensus) kurallarıyla güvence altına alınmış ortak bir durum gerekir.

## Bir "Özellik" Olarak Turing Bütünlüğü:
  
Ethereum'un _Turing-complete_ olduğunu duyduğunuzda, bunun _Turing-incomplete_ bir sistemde, bir şekilde eksik olan bir özellik olduğu sonucuna varabilirsiniz. Aksine, **tam tersi.** _Turing-complete_'e ulaşmak çok kolaydır; aslında, bilinen [en basit Turing-complete durum makinesinin](https://www.sciencedirect.com/science/article/pii/S0304397596000771) 4 durumu vardır ve sadece 22 komut uzunluğunda bir durum tanımıyla 6 sembol kullanır. Gerçekten de, bazen sistemlerin "yanlışlıkla Turing tamamlandı(accidentally Turing complete)" olduğu tespit edilir. Bu tür sistemlerin eğlenceli bir referansı: http://bit.ly/2Og1VgX adresinde bulunabilir.

Bununla birlikte, daha önce değindiğimiz durma sorunu ⤴️ nedeniyle, özellikle genel blok zincirleri gibi açık erişim sistemlerinde Turing bütünlüğü çok tehlikelidir. Örneğin, modern yazıcılar(Printers) Turing complete'dir(tamamlanmış) ve onları durağan bir duruma göndererek yazdırılacak dosyalar verilebilir. Ethereum'un Turing'i tamamlaması, herhangi bir karmaşıklıktaki herhangi bir programın Ethereum tarafından hesaplanabileceği anlamına gelir. Ancak bu _esneklik, bazı zorlu güvenlik ve kaynak yönetimi sorunlarını_ da beraberinde getiriyor. Yanıt vermeyen bir yazıcı(printer) kapatılıp tekrar açılabilir. Bu, halka açık bir blok zinciri ile mümkün değildir.

 ## Turing Bütünlüğünün Etkileri
  
 Turing, bir programı bilgisayarda simüle ederek sonlandırılıp sonlandırılmayacağını tahmin edemeyeceğinizi kanıtladı.Basit bir ifadeyle, bir programı çalıştırmadan yolunu tahmin edemeyiz. Turing-complete sistemleri, sonlanmayan bir programı tanımlamak için kullanılan (aşırı basitleştirmede) bir terim olan "sonsuz döngülerde" 🔄 çalışabilir. Hiç bitmeyen bir döngü çalıştıran bir program oluşturmak önemsizdir. Ancak, başlangıç koşulları ve kod arasındaki karmaşık etkileşimler nedeniyle, istenmeyen, hiç bitmeyen döngüler uyarı vermeden ortaya çıkabilir. Ethereum'da bu bir zorluk teşkil eder: katılan her düğüm (istemci), çağırdığı akıllı sözleşmeleri çalıştırarak her işlemi doğrulamalıdır. Ancak Turing'in kanıtladığı gibi, Ethereum akıllı bir sözleşmenin sona erip sonlanmayacağını veya gerçekte çalıştırmadan (muhtemelen sonsuza kadar devam edecek) ne kadar süreceğini tahmin edemez. Kazara veya bilerek, bir düğüm onu doğrulamaya çalıştığında sonsuza kadar çalışacak şekilde akıllı bir sözleşme oluşturulabilir. Bu etkili bir şekilde bir DoS saldırısıdır. Ve elbette, doğrulaması bir milisaniye süren bir program ile sonsuza kadar çalışan bir program arasında, kaynakları boşa harcayan sonsuz sayıda kötü, kaynak tüketen, belleği şişiren, CPU'yu aşırı ısıtan programlar vardır. 
⭐
_Bir dünya bilgisayarında, kaynakları kötüye kullanan bir program, dünyanın kaynaklarını kötüye kullanır. Ethereum, kaynak kullanımını önceden tahmin edemiyorsa, akıllı bir sözleşme tarafından kullanılan kaynakları nasıl kısıtlar?_

+ Bu zorluğa cevap vermek için Ethereum, gaz(gas) ⛽ adı verilen bir ölçüm mekanizması sunar. EVM akıllı bir sözleşme yürütürken, her talimatı (hesaplama, veri erişimi vb.) dikkatle hesaba katar. Her talimatın gaz birimlerinde önceden belirlenmiş bir maliyeti vardır. Bir işlem bir akıllı sözleşmenin yürütülmesini tetiklediğinde, akıllı sözleşmeyi çalıştırırken tüketilebileceklerin üst sınırını belirleyen bir miktar gaz içermelidir. Hesaplama tarafından tüketilen gaz miktarı işlemde mevcut olan gazı aşarsa EVM yürütmeyi sonlandıracaktır. **Gaz, Ethereum'un herhangi bir programın tüketebileceği kaynakları sınırlarken Turing-tam hesaplamaya izin vermek için kullandığı mekanizmadır.**

Sıradaki soru, ⭐ _"Ethereum Dünya Bilgisayarında hesaplama için nasıl gaz alınır?"_ 

 + Yalnızca bir işlemin parçası olarak satın alınabilir ve yalnızca ether(işlem yaparken altbirimleride vardır.Ancak hespi birer etherin parçasıdır.) ile satın alınabilir. Eter'in bir işlemle birlikte gönderilmesi ve kabul edilebilir bir gaz fiyatı ile birlikte gaz alımı için açıkça tahsis edilmesi gerekir. Tıpkı benzinikte olduğu gibi, gazın fiyatı sabit değildir.(Umarız Merge den sonra Gaz fiyatlarında azda olsa düşüş olur.Gözlerimizdeki ışıltı sönmesin!💸 🕴️) 😸 İşlem için gaz satın alınır, hesaplama yapılır ve kullanılmayan gaz işlemi gönderene iade edilir.🔄
  
## Genel Amaçlı Blok Zincirlerden ----> Merkezi Olmayan Uygulamalara (DApps) 🎛️

Ethereum, çeşitli kullanımlar için programlanabilen genel amaçlı bir blok zinciri yapmanın bir yolu olarak başlamıştı. Ancak çok hızlı bir şekilde, Ethereum'un vizyonu, DApp'leri programlamak için bir platform haline geldi. DApp'ler, akıllı sözleşmelerden daha geniş bir perspektifi temsil eder. Bir DApp, en kısa tanımıyla akıllı bir sözleşme ve bir web kullanıcı arayüzüdür. Daha geniş anlamda, bir DApp, açık, merkezi olmayan, eşler arası altyapı hizmetleri üzerine inşa edilmiş bir web uygulamasıdır.

Bir DApp en az şunlardan oluşur:
  + Blok zincir üzerinde bir akıllı kontrakt
  + Bir web frontend kullanıcı arayüzü

  Ek olarak, birçok DApp, aşağıdakiler gibi diğer merkezi olmayan bileşenleri içerir:
  
  + Merkezi olmayan (P2P) bir depolama protokolü ve platformu
  + Merkezi olmayan (P2P) bir mesajlaşma protokolü ve platformu
  
🔍İPUCU : DApp'lerin ÐApps olarak yazıldığını görebilirsiniz. Ð karakteri, Ethereum'a atıfta bulunan "ETH" adı verilen Latince karakterdir. Bu karakteri görüntülemek için Unicode 0xD0 kod noktasını veya gerekirse HTML karakter varlığı eth'i (veya ondalık varlık #208) kullanın.
  
  ## İnternetin Üçüncü çağı (web3.0) 🌑
  
2004'te "Web 2.0" terimi, 🤓 web'in _kullanıcı tarafından oluşturulan içeriğe, duyarlı arayüzlere ve etkileşimi_, evrimini tanımlayarak ön plana çıktı. Web 2.0 teknik bir özellik değil,❎ web uygulamalarının yeni odağını tanımlayan bir terimdir.

DApps kavramı, bir web uygulamasının her yönüne eşler arası protokollerle merkeziyetsizlik prensibini benimseyen; World Wide Web'i(www) bir sonraki doğal evrim aşamasına taşımayı amaçlamaktadır. **Bu evrimi tanımlamak için kullanılan terim, web'in üçüncü "versiyonu" anlamına gelen web3'tür.** İlk olarak Dr. Gavin Wood tarafından önerilen web3, merkezi olarak sahip olunan ve yönetilen uygulamalardan merkezi olmayan protokoller üzerine kurulu uygulamalara kadar web uygulamaları için yeni bir vizyonu ve odağı temsil ediyor.

Sonraki bölümlerde, tarayıcınızda çalışan _JavaScript_ uygulamaları ile Ethereum blokzinciri arasında köprü kuran **Ethereum web3.js JavaScript kitaplığını** 📖 keşfedeceğiz. web3.js kitaplığı ayrıca _Swarm adlı bir P2P depolama ağına_ ve _Whisper adlı bir P2P mesajlaşma servisine_ bir arayüz içerir. Web tarayıcınızda çalışan bir JavaScript kitaplığında bulunan bu üç bileşenle geliştiriciler, web3 DApp'leri oluşturmalarına olanak tanıyan eksiksiz bir uygulama geliştirme paketine sahip olur.

📝 Not: Eğer Web3 geliştiriçiliğini merak ediyorsanız 32saatlik Patrick Collins'in [Eğitim videosuna](https://www.youtube.com/watch?v=gyMwXuJrbJQ) bakınız. ---> zero to HERO 💪 Bu ingilizce bana türkçe bir şeyler ateşlee derseniz -----> 🇹🇷 
  💙 [Chainlink Türkiye Kanalı](https://linktr.ee/ChainlinkTurkey)-----> Türkiye'nin en iyi Eğitimlerini sunan kanal olarak sizlerle.Hemde Bedavaa 🤑
  
  [ITU Blockchain Klubünün Youtube kanalı ve Eğitimleri](https://www.youtube.com/c/ITUBlockchain) --->Değerli dostlarımızın eğitimleride bedava 🤑
  
## Ethereum'un Geliştirme Kültürü(Geleneği) 💚
  
Şimdiye kadar, Ethereum'un hedeflerinin ve teknolojisinin, Bitcoin gibi kendisinden önce gelen diğer blok zincirlerinden nasıl farklı olduğundan bahsettik. Ethereum da çok farklı bir geliştirme kültürüne sahip.

Bitcoin'de geliştirme, korumacı ilkeler tarafından yönlendirilir: mevcut sistemlerden hiçbirinin bozulmamasını sağlamak için tüm değişiklikler dikkatlice incelenir. Çoğunlukla, değişiklikler yalnızca geriye dönük uyumluysa uygulanır. Mevcut müşterilerin kaydolmalarına izin verilir, ancak yükseltme yapmamaya karar verirlerse çalışmaya devam edeceklerdir. 
  
Ethereum'da, karşılaştırmalı olarak, topluluğun geliştirme kültürü geçmişten ziyade geleceğe odaklanır.
 🏯 [Mantra felsefesi](https://www.ruhsalyasam.com/mantra-nedir/) "hızlı hareket et ve bir şeyleri hallet" demektir. Bir değişiklik gerekirse, önceki varsayımları geçersiz kılmak, uyumluluğu bozmak veya istemcileri güncellemeye zorlamak anlamına gelse bile uygulanır. Ethereum'un geliştirme kültürü, hızlı inovasyon, hızlı evrim ve geriye dönük uyumluluk pahasına olsa bile ileriye dönük iyileştirmeler yapma istekliliği ile öne çıkar.
  
 Bunun bir geliştirici olarak sizin için anlamı,**esnek kalmanız ve temel varsayımlardan bazıları değiştikçe altyapınızı yeniden oluşturmaya hazır olmanız gerektiğidir**. Ethereum'daki geliştiricilerin karşılaştığı en büyük zorluklardan biri, değişmez bir sisteme kod dağıtmak ile hala gelişmekte olan bir geliştirme platformu arasındaki doğal çelişkidir. Akıllı sözleşmelerinizi basitçe "yükseltemezsiniz".( ✏️ Not:Bazı akıllı sözleşmlerin upgradeable olanlarıda vardır ama bazı büyük sorunlarıda peşinde getirirler.Çoğu projede Akıllı Sözleşmeler upgradeable değildir.) Yenilerini dağıtmaya, kullanıcıları, uygulamaları ve fonları taşımaya ve **baştan başlamaya** hazır olmalısınız. 
  
İronik olarak, bu aynı zamanda daha fazla özerkliğe ve daha az merkezi kontrole sahip sistemler oluşturma hedefinin hala tam olarak gerçekleştirilmediği anlamına gelir. Özerklik ve merkeziyetsizlik, platformda önümüzdeki birkaç yıl içinde Ethereum'da elde edebileceğinizden biraz daha fazla istikrar gerektirir. Platformu "geliştirmek" için akıllı sözleşmelerinizi hurdaya çıkarmaya 🥡 ve yeniden başlatmaya hazır olmalısınız, bu da onlar üzerinde belirli bir derecede kontrol sahibi olmanız gerektiği anlamına gelir.
  
 🤩Ancak olumlu tarafı, Ethereum çok hızlı ilerliyor. Bir nükleer santralin arkasına bisiklet kulübesinin 🚴 nasıl inşa edileceği gibi küçük ayrıntılar üzerinde tartışarak gelişmeyi durdurmak anlamına gelen bir ifade olan "bisikletten kurtulma" için çok az süre var. Bisikletten kurtulmayı kafanıza takarsanız, aniden dikkatiniz dağılmış ve geliştirme ekibinin geri kalanının planı değiştirdiğini ve bisikletleri otonom hovercraft lehine çevirdiğini keşfedebilirsiniz. 😃 Sonunda, Ethereum platformunun gelişimi yavaşlayacak ve arayüzleri sabit hale gelecektir. Ancak bu arada **inovasyon, itici ilkedir**. Devam etsen iyi olur, çünkü kimse senin için yol vermeyecek,durmayacak.🙄.
  
  
## Neden Ethereum Öğrenmelisiniz ?
  
 Blokzincirler çok dik bir öğrenme eğrisine sahiptirler, çünkü birden fazla disiplini tek bir etki alanında birleştirirler: _programlama, bilgi güvenliği, kriptografi, ekonomi, dağıtılmış sistemler, eşler arası ağlar, vb_. Ethereum bu **öğrenme eğrisini çok daha az dik hale getirir**, bu yüzden sizler hızlı bir şekilde başlayabilirsiniz.Şunuda unutmamak gerekir ki aldatıcı derecede basit bir ortamın yüzeyinin hemen altında çok daha fazlası yatıyor. Öğrendikçe ve daha derine bakmaya başladıkça, her zaman başka bir karmaşıklık ve merak katmanı vardır.

Ethereum, blokzincirler hakkında bilgi edinmek için harika bir platformdur ve diğer blok zincir platformlarından daha hızlı, büyük bir geliştirici topluluğu oluşturur. **Ethereum, geliştiriciler tarafından geliştiriciler için oluşturulmuş bir geliştiricinin blok zinciridir**. JavaScript uygulamalarına aşina bir geliştirici, Ethereum'a adapte olabilir ve çok hızlı bir şekilde çalışabilir kodlar üretmeye başlayabilir. Ethereum'un ilk birkaç yılında, yalnızca beş satır kodla bir (token)jeton oluşturabileceğinizi gösteren tişörtler 👕 görmek yaygındı. Tabii ki, bu iki ucu keskin bir kılıç.⚔️ **KOD YAZMAK KOLAYDIR, ANCAK İYİ VE GÜVENLİ KOD YAZMAK ÇOK ZORDUR.** 💻
  
 ## Bu Kitap Size Ne Öğretecek?

  Bu kitap Ethereum'a derinlemesine iniyor ve her bileşeni inceliyor. Basit bir işlemle başlayacak, nasıl çalıştığını inceleyecek, basit bir sözleşme oluşturacak, daha iyi hale getirecek ve Ethereum sistemindeki yolculuğunu takip edeceksiniz.

Sadece Ethereum'u nasıl kullanacağınızı değil, nasıl çalıştığını da öğreneceksiniz, aynı zamanda neden olduğu gibi tasarlandığını da öğreneceksiniz. Parçaların her birinin nasıl çalıştığını ve nasıl bir araya geldiklerini ve nedenini anlayabileceksiniz.

Bölüm SONU 🏁

**"Hiç kimse bir zamanlar sevdiğiniz kişiden daha yabancı hale gelemez."🗣️ Erich Maria Remarque**


