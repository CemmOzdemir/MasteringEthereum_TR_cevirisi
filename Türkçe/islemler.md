# İŞLEMLER ➡️📖⬅️

_İşlemler_, Ethereum ağı tarafından iletilen ve Ethereum blok zincirine **kaydedilen**, harici olarak sahip olunan bir hesaptan (EOA'dan) kaynaklanan _imzalı mesajlardır_. Bu temel tanım, birçok **şaşırtıcı ve büyüleyici ayrıntıyı gizler**👻. İşlemlere  başka bir perspektiften bakınca, **bir durum değişikliğini tetikleyebilecek veya EVM'de bir sözleşmenin yürütülmesine(çalışmasına) neden olabilecek TEK şey olmalarıdır**.  Ethereum, global 🌎 bir tekil(singleton) durum makinesidir ve bu durum makinesinin durumunu değiştirerek "tik-tok⏰" olan  şeyler _işlemlerdir_.(Buradaki cümlede yazar Ethereum'u bir saate ⏰ benzeterek,geçen her saniyeyi işlemlere benzetmiştir.Saat sürekli ilerliyorsa işlemler sayesinde yani) 

**Sözleşmeler kendi başlarına çalışamazlar. Ethereum otonom olarak çalışmaz. Her şey bir işlemle başlar.** 💥🌍

Bu bölümde işlemleri inceleyeceğiz, nasıl çalıştıklarını göstereceğiz ve detayları inceleyeceğiz. Bu bölümde çoğu kişinin, **belki de bir cüzdan uygulaması yazdıkları için kendi işlemlerini düşük düzeyde yönetmekle ilgilenenlere yönelik olduğunu unutmayın**; Buradaki detayları ilginç bulacak olsanız da, mevcut cüzdan uygulamalarını kullanmaktan memnunsanız bunun için panik yapmanıza gerek yok!☕

--------------

## Bir İşlemin Yapısı
Öncelikle, Ethereum ağında [seri hale](https://en.wikipedia.org/wiki/Serialization)[kısaca serileştirme işleminin Yönteminde:veriyi bir yere depolama kullanılır.] getirilip iletildiği için, bir işlemin temel yapısına bir göz atalım. Serileştirilmiş bir işlem alan her istemci ve uygulama, kendi **dahili veri yapısını kullanarak**, belki de ağ serileştirme işleminde mevcut olmayan meta verilerle birlite bunu bellekte saklayacaktır. **Ağ serileştirmesi, bir _işlemin tek standart biçimidir_**.

İşlem, **aşağıdaki verileri içeren** _serileştirilmiş bir ikili-sistemde(binary0️⃣1️⃣) mesajdır_ ⏬

* Nonce :

Mesajın tekrarını önlemek için kullanılan 🔄 ,EOA tarafından kaynaklanan,bir sıra numarasıdır

* Gaz fiyatı (price) ⛽

Oluşturucunun her bir gaz birimi için ödemeye hazır olduğu ether miktarı (wei cinsinden)

* Gaz sınırı (limit) 🚗

Oluşturucunun bu işlem için satın almak istediği maksimum gaz miktarı

* alıcı (recepient) 👱‍♂️👱‍♀️

Hedef Ethereum adresi

* Değer (value) 💰

Hedefe gönderilecek ether miktarı (wei cinsinden)

* Veri(data) 💻

Değişken-uzunluklu binary veri yükü

* v,r,s ✒️

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
