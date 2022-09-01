# Ethereum Nedir?

Ethereum genellikle "dünya bilgisayarı" olarak tanımlanır. Ama bu ne anlama geliyor? Bilgisayar
bilimi bakış açısıyla açıklama ile başlayalım ve ardından bunu, Ethereum'un kapasitesi ve 
özelliklerinin daha pratik bir analiziyle, Bitcoin ve diğer merkeziyetsiz, bilgi alışverişi platformlarıyla 
(veya kısaca "blok zincirler")ile karşılaştırarak çözmeye çalışalım.


Bilgisayar bilimi açısından bakıldığında, _Ethereum_, küresel olarak erişilebilir bir tekil durumdan ve 
bu duruma değişiklikleri uygulayan bir sanal makineden oluşan deterministik bir makinedir ancak pratikte sınırsız bir durum makinesidir.
(**state machine: önceki durumuna ve girişlerinin mevcut değerlerine bağlı olarak belirli sayıda koşullardan birinde olabilen makinelere verilen addır.**)


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
_yardımcı para birimi_ olarak tasarlanmıştır. 💻: :moneybag:


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
* Konsensüs kurallarına göre işlemleri işleyen bir [durum makinesi](https://www.techopedia.com/definition/16447/state-machine)---> Ben şimdi bunu okuyamam derseniz **kısaca: Durum makinesi, bilgisayar programları veya dijital mantık tasarlamada kullanılan bir kavramdır. İki tür durum makinesi vardır: sonlu ve sonsuz durum makineleri. İlki, koşullar karşılandığında mantık yolunun tespit edilebildiği,akış grafikleriyle modellenebilen sınırlı sayıda durum, geçiş ve eylemden oluşur. İkincisi pratik olarak kullanılmaz.Belirli bir zamanda bir şeyin durumunu depolayan herhangi bir cihazdır. Durum, girdilere dayalı olarak değişir ve uygulanan değişiklikler için sonuç çıktısını sağlar.** 
* Doğrulanmış ve kabul edilmiş 🟢 tüm durum geçişlerinin bir günlüğü(Distr. Ledger'a atıf) :book: gibi davranan, kriptografik olarak güvenli bir blokzincir.
* Katılımcıları konsensüs kurallarının uygulanmasında işbirliği yapmaya zorlayarak,blok zinciri üzerindeki kontrolü merkezsizyetsiz hale getiren bir konsensüs algoritması.
* Durum makinesini açık bir ortamda(open) ekonomik olarak güvenceye almak için [Oyun Teorisine](https://tr.wikipedia.org/wiki/Oyun_teorisi) dayalı olarak sağlam bir teşvik planı (örneğin, çalışma kanıtı maliyetleri-- blok ödülleri) ---> Oyun Teorisi wikiyi kim okyacak yaağ 😄diyorsanız **kısaca : Oyun teorisi, bireyin başarısının diğerlerinin seçimlerine dayalı olduğu seçimler yapması olan bazı stratejik durumların matematiksel olarak davranış biçimlerini yakalamaya çalışır.**

Bu bileşenlerin tümü veya çoğu genellikle tek bir yazılım istemcisinde(client) birleştirilir. Örneğin, Bitcoin'de referans uygulaması, Bitcoin Core açık kaynak projesi tarafından geliştirilir ve bitcoind istemcisi olarak uygulanır. Ethereum'da, bir _referans uygulaması_ yerine bir _referans spesifikasyonu_, vardır.sistemin Yellow Pepper'ında matematiksel bir açıklaması vardır.Referans spesifikasyonuna göre oluşturulmuş bir dizi istemci vardır.

Geçmişte, açıklanan tüm özellikleri kapsayan teknolojilerin kombinasyonuna ,kısaca (referans olarak), az önce listelenen tüm bileşenleri temsil etmek için "blockchain" terimini kullandık. Ancak bugün, farklı özelliklere sahip çok çeşitli blok zincirleri var. Açık, genel, küresel, merkezi olmayan, tarafsız ve sansüre dayanıklı gibi. Söz konusu blok zincirinin özelliklerini anlamamıza yardımcı olacak kavramlara ihtiyacımız var ve bunun için bileşenlerin izin verdiği bir "blok zinciri" sisteminin ortaya çıkardiğı önemli özelliklerini tanımlamamız lazım. 

Tüm blok zincirleri eşit yaratılmamıştır. Birisi size bir şeyin blok zinciri olduğunu söylediğinde, bir yanıt almamışsınızdır 🔴; bunun yerine, "blockchain" kelimesini kullandıklarında ne anlama geldiklerini netleştirmek için birçok soru sormaya başlamalısınız. 🤔: Önceki listedeki bileşenlerin tanımını sorarak başlayın, ardından bu "blok zincirinin" açık(open), genel(public),Özel(private) vb. özellikler gösterip göstermediğini sorun.

## Ethereum'un Doğuşu(başlangıcı):




