# KRİPTOGRAFİ  🔡 🧮

Ethereum'un temel teknolojilerinden biri, **bilgisayar güvenliğinde yaygın olarak kullanılan bir matematik dalı olan kriptografidir**. Kriptografi, Latince _"gizli yazı"_ anlamına gelir, ancak **kriptografi çalışmaları, şifreleme olarak adlandırılan _gizli yazıdan_ daha fazlasını kapsar**. Örneğin kriptografi, bir gizliliği ifşa etmeden bir gizli bilgiyi kanıtlamak için (örneğin _dijital bir imza_ 🖋️ ile) veya verilerin gerçekliğini kanıtlamak için (örneğin, dijital parmak izleriyle,💻 🖐️ aynı zamanda _"hash"_ olarak da bilinir) kullanılabilir. Bu tür kriptografik kanıtlar, Ethereum platformunun (gerçek anlamda tüm blok zinciri sistemlerinin) çalışması için kritik olan **matematiksel araçlardır ve ayrıca Ethereum uygulamalarında yaygın olarak kullanılmaktadırlar.**

Ağ dağıtımı sırasında, Ethereum protokolünün hiçbir parçasının **şifreleme içermediğini** unutmayın; yani, Ethereum platformuyla ve düğümler arasındaki (işlem verileri dahil) _tüm iletişimler şifrelenmez_ 🔴 ve (zorunlu olarak) herkes tarafından görülebilir. Bu, herkesin durum güncellemelerinin doğruluğunu doğrulayabilmesi ve fikir birliğine varılabilmesi içindir. Gelecekte, sıfır bilgi kanıtı(Zero Knowledge Proof 0️⃣ ------>Bu ne demek yaaa 😸 diyorsanız: 👩‍💻[Chainlink'in Türkiye ve Avrupa sorumlusu Elif Hilal Umucu'nun yazısını bırakıyorum](https://medium.com/chainlink-community/zero-knowledge-proof-sıfır-bilgi-kanıtı-nedir-b810be4e1b29) 🔷) ve( homomorfik şifreleme [bunun içinde opsiyonel olarak buraya bırakıyorum 🌼](https://learn.microsoft.com/tr-tr/azure/architecture/solution-ideas/articles/homomorphic-encryption-seal) ) gibi gelişmiş kriptografik araçlar, bazı şifreli hesaplamaların blok zincirine kaydedilmesine izin verirken aynı şekilde consensus'u mümkün kılacaktır; bununla birlikte, Bu teknolojiler ile ilgili çalışmalar sürmektedir.

Bu bölümde, Ethereum'da kullanılan bazı kriptografik unsurları tanıtacağız: 
Yani, **özel anahtarlar** 🔐 ve **adresler biçiminde fon(bakiye) sahipliğini kontrol etmek için kullanılan açık anahtar kriptografisi** 🔑(PKC).----->(Public Key Crptography)

----------

## Anahtarlar ve Adresler
Kitapta daha önce gördüğümüz gibi, Ethereum'un iki farklı hesap türü vardır: 1- _harici olarak sahip olunan hesaplar (EOA'lar) ve 2-sözleşmeler._ EOA'ların ether sahipliği, dijital **özel anahtarlar**, **Ethereum adresleri** ve **dijital imzalar** aracılığıyla kurulur. Özel anahtarlar(kapalı anahtar olarakta geçer (Private Key) 🔐 ), Ethereum ile tüm kullanıcı etkileşiminin **merkezinde yer alır**. Aslında, _hesap adresleri doğrudan özel anahtarlardan türetilir_ ----> özel anahtar, hesap olarak da bilinen(account) tek bir Ethereum adresini eşsiz(unique) bir şekilde belirler.📰

Özel anahtarlar hiçbir şekilde **doğrudan** Ethereum sisteminde kullanılmaz; asla iletilmez veya Ethereum'da **depolanmaz**. 🔴  Başka bir deyişle, özel anahtarlar gizli kalmalı ve ağa iletilen iletilerde asla **görünmemeli ve zincir üzerinde depolanmamalıdır**; Ethereum sisteminde yalnızca _hesap adresleri ve dijital imzalar iletilir ve saklanır._ 🟢İlerleyen bölümlerde derince anlatılacak.

Fonlara erişim ve kontrol, yine **özel anahtar kullanılarak oluşturulan dijital imzalarla sağlanır**. 
Ethereum işlemleri, blokzincire dahil edilmek için geçerli bir _dijital imza gerektirir_. Özel anahtarın bir kopyasına sahip olan herkes, ilgili hesabın ve sahip olduğu herhangi bir etherin kontrolüne sahiptir. Bir kullanıcının özel anahtarını güvende tuttuğunu varsayarsak, Ethereum işlemlerindeki dijital imzalar, özel anahtarın sahipliğini kanıtladıkları için fonların gerçek sahibini kanıtlar.

Ethereum tarafından kullanılanlar gibi, _1️⃣ açık(public) anahtar şifreleme tabanlı sistemlerde, anahtarlar 2️⃣ özel (gizli/kapalı) bir anahtar ve bir genel anahtardan oluşan çiftler halinde gelir_ .Açık(genel) anahtarı bir 🏦 banka hesap numarasına(IBAN) ve özel anahtarı da bankacılık şifrenize benzer olarak düşünün; **hesap üzerinde kontrol sağlayan ikincisidir** ve onu diğerlerine **tanımlayan ilkidir.** Özel anahtarlar, Ethereum kullanıcıları tarafından çok nadiren görülür; çoğunlukla özel dosyalarda (şifreli biçimde) saklanırlar ve Ethereum cüzdan yazılımı tarafından yönetilirler.

Bir Ethereum işleminin _ödeme kısmında_, **hedeflenen alıcı(gönderilmek istenen kişi)**, bir banka havalesinde ,hak sahibi olan kişinin _hesap ayrıntılarıyla aynı şekilde kullanılan bir adet Ethereum adresiyle temsil edilir_. Birazdan daha detaylı olarak göreceğimiz gibi, bir *EOA(Externally Owned Accounts -----> Geçtiğimiz kısımlarda anlatıldı.Ama ben sadece bu bölümü okuyorum.Beni bilgilendirmek durumundasın.Pijjjlik 🐱 yapma derseniz. ▶️ [Bakınız](https://ethereum.stackexchange.com/questions/5828/what-is-an-eoa-account#5829) )* için bir Ethereum adresi, bir **anahtar çiftinin public anahtar kısmından üretilir**. Ancak, tüm Ethereum adresleri _genel-özel anahtar çiftlerini temsil etmez_. Akıllı sözleşme bölümünde göreceğimiz gibi, özel anahtarlarla desteklenmeyen sözleşmeleri de temsil edebilirler.

Bu bölümün geri kalanında, önce temel kriptografiyi biraz daha detaylı inceleyeceğiz ve Ethereum'da kullanılan matematiği açıklayacağız. Ardından anahtarların nasıl oluşturulduğuna, saklandığına ve yönetildiğine bakacağız. Son olarak, özel anahtarları, genel anahtarları ve adresleri temsil etmek için kullanılan çeşitli kodlama biçimlerini gözden geçireceğiz. 👨‍💻 👩‍💻

-----------------
## Açık Anahtar Kriptografisi ve Kripto Para Birimi 🔑 🤑
Açık anahtar şifrelemesi ("asimetrik şifreleme" olarak da adlandırılır.📝[Türkçe-kısa medium yazısı](https://medium.com/@muhammedkaralar/simetrik-ve-asimetrik-şifreleme-d57673284646)), günümüz _bilgi güvenliğinin temel bir parçasıdır_. İlk olarak 1970'lerde _Martin Hellman, Whitfield Diffie ve Ralph Merkle_ tarafından yayınlanan anahtar değişim protokolü, kriptografi alanında ilk büyük halka açık bir şekilde ve ilgisini cezbeden bir atılımdı. 1970'lerden önce, güçlü kriptografik bilgi hükümetler tarafından _gizli_ tutuluyordu.(Büyük bir ihtimal ile soğuk savaş döneminden kaynaklı💣 🚀)

Açık anahtar şifrelemesi, bilgilerin güvenliğini sağlamak için _benzersiz anahtarlar_ kullanır. Bunlar, özel bir özelliği olan _matematiksel fonksiyonlara_ dayanmaktadırlar: bunları **hesaplamak kolaydır, ancak tersini hesaplamak zordur.🤕** Bu işlevlere dayalı olarak kriptografi, _matematik yasalarıyla güvence altına alınan dijital sırların ve kırılmaz(hacking anlamında --->Ancak teknoloji sürekli gelişiyor.Bu yüzden ileride ne olacağını kestirmek kolay değil 🧐) dijital imzaların oluşturulmasını sağlar._

Örneğin, iki büyük asal sayıyı birbiriyle çarpmak önemsizdir. Ancak iki büyük asal sayının çarpımı verildiğinde, asal çarpanları bulmak çok zordur (asal çarpanlara ayırma denilen bir problem). Diyelim ki _8,018,009 sayısını_ sunalım ve bunun iki asal sayının çarpımı olduğunu söyleyelim. Bu iki asal sayıyı bulmak sizin için onları çarparak 8,018,009 elde etmekten çok daha zor. ✏️
_Bazı gizli bilgileri biliyorsanız, bu matematiksel işlevlerden bazıları kolayca tersine_ çevrilebilir. Yukarıdaki örnekte, size asal çarpanlardan birinin _2.003_ olduğunu söylersem, diğerini basit bir bölme ile önemsiz bir şekilde bulabilirsiniz: 8,018,009 ÷ 2,003 = _4,003_ Bu tür işlevlere genellikle 🚪**gizli-kapı(trapdoor) işlevleri/fonksiyonları denir**, çünkü işlevi tersine çevirmek için _kısayol olarak_ kullanılabilecek bir parça gizli bilgi verilmedikçe, tersine çevrilmeleri çok zordur.

------------------------ 

Kriptografide, daha kullanışlı ve gelişmiş bir _matematiksel fonksiyon kategorisi_ ⛓️ **eliptik bir eğri üzerindeki aritmetik işlemlere dayanır**. Eliptik eğri aritmetiğinde, çarpma modulü _a asaldır_,  ⚠️**ancak bölmek(ters) pratik olarak imkansızdır.(YUKARIDAKİ İŞLEMDEKİ GİBİ BÖLEREK BULAMAYIZ.)** Buna 
🌟 _AYRIK LOGARİTMA PROBLEMİ_ denir ve şu anda bilinen bir gizli kapısı 🚪 yoktur. Eliptik eğri kriptografisi modern bilgisayar sistemlerinde yaygın olarak kullanılmaktadır ve Ethereum'un (ve diğer kripto para birimlerinin) **özel anahtarları ve dijital imzaları** kullanmasının temelidir.

📝NOT:Modern kriptografide kullanılan kriptografi ve matematiksel fonksiyonlar hakkında daha fazla bilgi edinmek istiyorsanız aşağıdaki kaynaklara göz atın: 🇬🇧 (İNGİLİZCE)
  
  + [kriptografi-cryptography](http://bit.ly/2DcwNhn)
  + [Gizli-kapı Fonksiyonları-trapdoor Func.](http://bit.ly/2zeZV3c)
  + [asal çarpanlara ayırma-Prime factorization](http://bit.ly/2ACJjnV)
  + [Ayrık logaritma-dicrete Logarithm](http://bit.ly/2Q7mZYI)
  + [Eliptik eğri kriptografisi-Elliptic curve cryptography](http://bit.ly/2zfeKCP)
  
--------------------

Ethereum'da, bu bölümde bahsettiğimiz genel-özel(public-private) anahtar çiftini oluşturmak için açık anahtar şifrelemesini (asimetrik şifreleme olarak da bilinir) kullanırız. _Açık anahtar özel anahtardan türetildiği için "çift" olarak kabul edilirler._ Birlikte, sırasıyla herkese açık bir _hesap gösterimi(adres)_ ve hesaptaki herhangi bir _ethere erişim üzerinde özel kontrolü_ ve  _akıllı sözleşmeleri kullanırken hesabın ihtiyaç duyduğu herhangi bir kimlik doğrulaması_ sağlayarak bir Ethereum hesabını temsil ederler. _Özel anahtar, hesaptaki herhangi bir parayı harcamak için işlemleri imzalamak için gerekli olan dijital imzalar oluşturmak için gereken benzersiz bilgi parçası olarak erişimi kontrol eder._ **Dijital imzalar**, Akıllı sözleşmlere bölümünde göreceğimiz gibi, **sözleşme sahiplerinin veya kullanıcılarının kimliğini doğrulamak için de kullanılır.**

| 
🔍İPUCU: Çoğu cüzdan uygulamasında, özel ve genel anahtarlar, kolaylık sağlamak için bir anahtar çifti olarak birlikte saklanır. Ancak, genel(açık) anahtar özel anahtarın yardımıyla zor olmayacak şekilde hesaplanabilir, bu nedenle _yalnızca özel anahtarı saklamak da mümkündür._ 
🔐 🔑 ( 🤓BİR ÖRNEK İLE PEKİŞTİRELİM: Örneğin Bisikletinizi( 1️⃣ **HESABINIZ**) kitlediniz.( 2️⃣**KİLİT----> PUBLIC(AÇIK) KEY**, 3️⃣ **ANAHTAR--->ÖZEL ANAHATARINIZ**). Bir süre başka bir yerde işiniz vardı ve bisikletinizi kitlediğiniz yerden ayrıldınız.Geri döndüğünüzde ise yan taraflarına sizin bisikletinizle ve aynı kilitle bağlamış başka bisikletler gördünüz.(renk-boyut olarak falan).Burada sahip olduğunuz kendi anahtarınız(_özel anahtarınız_) sayesinde kilite ulaşabilirsiniz ve bisikletinizi bulabilrsiniz.🚴 UNUTMAYIN!! Kriptografide her kilitin farklı anahtarı vardır.benzeri diye bir durum yoktur._Unique_ )

|

Herhangi bir mesajı imzalamak için dijital bir imza oluşturulabilir. _Ethereum işlemleri için, **işlemin detayları mesaj olarak** kullanılır._ Kriptografinin matematiği // ⭐ bu durumda eliptik eğri kriptografisi // **mesajın (yani işlem detaylarının) 🧷 özel anahtarla 🔑 +birleştirilmesi ve YALNIZCA özel anahtar bilgisi ile üretilebilecek bir kod oluşturmak için bir yol sağlar. Bu koda DİJİTAL İMZA denir.** 
⏩ Bir Ethereum işleminin temel olarak belirli bir Ethereum adresiyle belirli bir hesaba erişim talebi olduğunu unutmayın. _Para transferi veya akıllı sözleşmelerle etkileşim için Ethereum ağına bir işlem gönderildiğinde, söz konusu Ethereum adresine karşılık gelen özel anahtarla oluşturulan dijital bir imza ile gönderilmesi gerekir._ 
 Eliptik eğri matematiği, herkesin dijital imzasının işlem ayrıntılarıyla ve erişim talep edilen Ethereum adresiyle eşleştiğini kontrol ederek bir işlemin geçerli olduğunu doğrulayabileceği anlamına gelir. _Doğrulama, özel anahtarı hiç içermez; bu özel kalır. Ancak doğrulama süreci, işlemin yalnızca Ethereum adresinin arkasındaki açık anahtara karşılık gelen özel anahtara sahip birinden gelmiş olabileceğini şüpheye yer bırakmayacak şekilde belirtir_. Bu, açık anahtar şifrelemesinin  🃏"sihri"dir.

|
🔍İPUCU : Ethereum protokolünün bir parçası olarak şifreleme yoktur. --Ethereum ağının çalışmasının bir parçası olarak gönderilen tüm mesajlar (zorunlu olarak) herkes tarafından okunabilir.(ileride 0️⃣ZKP(sıfır bilgi ispatı) ile bazı şeyler değişeblilir.) Bu nedenle, özel anahtarlar YALNIZCA _işlem kimlik doğrulaması_ yapabilmek için **dijital imzalar oluşturmakta** kullanılır.
|

## Özel Anahtar (Private Key 🔑)
Özel anahtar, **rastgele seçilen bir sayıdır.** Özel anahtarın sahipliği ve kontrolü, ilgili Ethereum adresiyle ilişkili tüm fonlar üzerindeki kullanıcı kontrolünün yanı sıra bu adresi, **yetkilendiren sözleşmelere erişimin köküdür(başlangıcı)**. Özel anahtar, bir işlemde kullanılan fonların sahipliğini kanıtlayarak ether harcamak için gereken imzaları oluşturmak için kullanılır. **Özel anahtar her zaman gizli kalmalıdır, çünkü onu üçüncü kişilere ifşa etmek(göstermek), onlara ether ve bu özel anahtar tarafından güvence altına alınan sözleşmeler üzerinde kontrol vermekle eşdeğerdir**. 

⚠️UYARI: 
Özel anahtar da yedeklenmeli ve kazara kaybolmaya karşı korunmalıdır. Kaybedilirse geri alınamaz ve güvence altına aldığı fonlar da sonsuza kadar kaybolur.


🔍İPUCU::Ethereum özel anahtarı sadece bir sayıdır. Özel anahtarlarınızı rastgele seçmenin bir yolu, sadece bir madeni para, kurşun kalem ve kağıt kullanmaktır: **256 kez yazı tura attığınızda, bir Ethereum cüzdanında kullanabileceğiniz rastgele bir özel anahtarın ikili rakamlarına(binary) sahip olursunuz.** .Genel/açık(public) anahtar 👶 ve adres👶 daha sonrasında ---->  _özel anahtardan_ 👩‍🍼 oluşturulabilir.

## Rastgele Bir Numaradan Özel Anahtar Oluşturma
Anahtar oluşturmanın _ilk ve en önemli adımı, ⭐ güvenli bir entropi {(Entropi neeeğ yaa 😾 diyorsanız: -Kısaca Entropi: Bilgisayar biliminde entropi, kriptografide veya rastgele veri gerektiren diğer kullanımlarda kullanılmak üzere bir işletim sistemi veya uygulama tarafından **toplanan rastgeleliktir.** Bu rastgelelik genellikle, fare hareketleri gibi önceden var olan donanım kaynaklarından veya özel olarak sağlanan rastgelelik oluşturuculardan toplanır. 📽️Entropi hakkında daha fazla bilgi için [PopularScienceTR'den](https://www.youtube.com/watch?v=xadlBOXtcsg)-)} veya ⭐ rastgelelik kaynağı bulmaktır._ Bir Ethereum özel anahtarı oluşturmak, esas olarak 1 ile  2<sup>256</sup> arasında bir sayı seçmeyi içerir. Bu sayıyı seçmek için kullandığınız kesin yöntem, **tahmin edilebilir veya deterministik olmadığı** sürece önemli değildir. Ethereum yazılımı, 256 rasgele bit üretmek için temel işletim sisteminin rasgele sayı üretecini kullanır.

Daha kesin olarak; bir özel anahtar,  2<sup>256</sup> dan biraz daha küçük, büyük bir sayıya kadar _sıfır olmayan_ herhangi bir sayı olabilir ---78 basamaklı büyük bir sayı----, kabaca 1.158 * 10<sup>77</sup>. Tam sayı,  2<sup>256</sup> ile ilk _38 basamağı paylaşır ve sıra olarak tanımlanır._ 
Ethereum'da kullanılan eliptik eğrinin (bkz. Eliptik Eğri Kriptografisi Açıklaması). Özel bir anahtar oluşturmak için rastgele 256 bitlik bir sayı seçiyoruz ve geçerli aralıkta olup olmadığını kontrol ediyoruz. 
🖥️ Programlama terimleriyle, bu genellikle daha büyük bir rastgele bit dizisinin (şifreleme açısından güvenli bir rastgelelik kaynağından toplanan) _Keccak-256 veya SHA-256 gibi 256 bitlik bir karma algoritmaya_ beslenmesiyle elde edilir; her ikisi de uygun bir şekilde üretecektir (256 bitlik bir sayı yani) Sonuç geçerli aralık içindeyse, uygun bir özel anahtarımız vardır. 🟢Aksi takdirde, başka bir rastgele sayı ile tekrar denemek zorundayız.

|

🔍İPUCU :2<sup>256</sup> Ethereum'un özel anahtar alanının boyutudur.Akıl almaz derecede _büyük bir sayıdır_. Yaklaşık olarak **77 basamaklı bir sayı.** Karşılaştırmak gerkirse, **Görünür Evrenin(Visible Universe) 10<sup>77</sup> ve 10<sup>80</sup> atom içerdiği tahmin edilmektedir**. Bu nedenle, alt aralıkta, evrendeki her atoma bir Ethereum hesabı vermek için yeterli özel anahtar vardır. Rastgele bir özel anahtar seçerseniz, kimsenin onu tahmin etmesi veya kendisinin seçmesi mümkün değildir.

|

Özel anahtar oluşturma işleminin _çevrimdışı olduğunu unutmayın_; Ethereum ağı ile herhangi bir iletişim veya aslında herhangi biriyle herhangi bir iletişim gerektirmez. Bu nedenle, hiç kimsenin **seçemeyeceği bir sayı seçmek için gerçekten rastgele olması gerekir**. _Numarayı kendiniz seçerseniz,_ 🤯 bir başkasının denemesi (ve sonra etherinizle birlikte kaçması) şansı çok yüksektir. Kötü bir rasgele sayı üreteci (çoğu programlama dilindeki sözde rasgele _rand_ fonksiyonu gibi) kullanmak daha da kötüdür, çünkü daha belirgindir ve çoğaltılması daha da kolaydır. **Tıpkı çevrimiçi hesapların şifrelerinde olduğu gibi, özel anahtarın da tahmin edilemez olması gerekir**. Neyse ki, özel anahtarınızı asla hatırlamanıza gerek kalmaz, böylece onu seçmek için mümkün olan en iyi yaklaşımı uygulayabilirsiniz: yani, [GERÇEK RASTGELELİK.](https://blocking.net/7155/ethereum-2-0-randomness/)


⚠️ UYARI:
Rastgele bir sayı oluşturmak için kendi kodunuzu _yazmayın_ veya programlama diliniz tarafından sunulan "basit" bir rastgele _sayı üreteci kullanmayın_. Yeterli entropi kaynağından, kriptografik olarak güvenli bir sözde rastgele sayı üreteci (CSPRNG gibi) kullanmanız çok önemlidir. Şifreleme açısından güvenli olduğundan emin olmak için seçtiğiniz _rasgele sayı üretecinin kitaplığının belgelerini_ inceleyin. _CSPRNG kitaplığının_ doğru uygulanması, anahtarların güvenliği için kritik öneme sahiptir.
⚠️

Aşağıdaki anahtar, onaltılık biçimde gösterilen rastgele oluşturulmuş bir özel anahtardır. (her biri 4 bit, 64 onaltılık basamak olarak gösterilen 256 bit):

`f8f8a2f43c8376ccb0871305060d7b27b0554d2cc72bccf41b2705608452f372`

-------------

## Açık/Genel(Public) Anahtar

Bir Ethereum Public anahtarı, _eliptik bir eğri üzerindeki bir noktadır_, yani eliptik eğri denklemini karşılayan bir _x ve y_ koordinatları kümesidir.

Daha basit bir ifadeyle, bir Ethereum genel(public) anahtarı, **birleştirilmiş iki sayıdır.** Bu sayılar özel anahtardan sadece tek yöne gidebilen bir hesaplama ile üretilir. Bu, _özel anahtarınız varsa, bir genel anahtarı hesaplamanın önemsiz olduğu, ancak özel anahtarı genel anahtardan hesaplayamayacağınız anlamına gelir._

⚠️UYARI: Bunu yapan şey MATEMATİK'tir.💯Panik yapmayın😺. Aşağıdaki paragraflarda herhangi bir noktada kaybolmaya başlarsanız, hemen birkaç bölümü atlayabilirsiniz. Matematiği sizin yerinize yapacak birçok araç ve kitaplık vardır.Unutmayın öğrenmek hep uzun bir süreçtir.Beynimize saygımız olmalı. 

Genel anahtar, pratik olarak geri döndürülemez olan eliptik eğri çarpımı kullanılarak özel anahtardan hesaplanır: **K = k * G** ,burada:
  
  + k, özel anahtardır.
  + G, üretici noktası olarak adlandırılan sabit bir noktadır.
  + K, elde edilen genel anahtardır. 
  + `*` özel eliptik eğri _"çarpma"_ operatörüdür.
**Eliptik eğri çarpmasının normal çarpma gibi olmadığına dikkat edin.** Normal çarpma ile işlevsel nitelikleri paylaşır, ancak bununla ilgili olarak; Örneğin, "ayrık logaritmayı bulma" olarak bilinen ters işlem (normal sayılar için bölme olacaktır) --- yani, _K'yi biliyorsanız k'yi hesaplamak --- k'nin tüm olası değerlerini denemek (kaba kuvvet araması) kadar zordur._ 🔴 Bu muhtemelen bu evrenin izin vereceğinden daha fazla zaman alacaktır.( 😜 Benden sizlere küçük bir araştırma konusu bırakıyorum : Kuantum Bilgisayarlar ⚛️+💻)

Daha basit bir ifadeyle: eliptik eğri üzerindeki aritmetik, "normal" tamsayı aritmetiğinden farklıdır. Bir (G) noktası, başka bir nokta (K) üretmek için bir tam sayı (k) ile çarpılabilir. **Ancak bölme diye bir şey yoktur, bu nedenle özel anahtar k'yi hesaplamak için K genel anahtarını G noktasına basitçe "bölmek" mümkün değildir.** Bu, Açık Anahtar Şifreleme ve Kripto Para Birimi'nde açıklanan _tek yönlü matematiksel işlevdir._ 🤓 

📝NOT:
Eliptik eğri çarpması, kriptografların **"tek yönlü"** işlev dediği bir işlev türüdür: _tek yönde (çarpma) yapmak kolaydır ve ters yönde (bölme) yapmak imkansızdır._ Özel anahtarın sahibi, herkesin işlevi tersine çeviremeyeceğini ve açık anahtardan özel anahtarı hesaplayamayacağını bilerek, genel anahtarı kolayca oluşturabilir ve daha sonra dünya ile paylaşabilir. **Bu matematiksel numara, Ethereum fonlarının sahipliğini ve sözleşmelerin kontrolünü kanıtlayan, kırılmaz(hacking anlamında) ve güvenli dijital imzaların temeli haline gelir.**💻

Özel bir anahtardan nasıl açık anahtar oluşturulacağını göstermeden önce, eliptik eğri şifrelemesine biraz daha detaylı bakalım.

-----------------------

## Eliptik Eğri Kriptografisinin Açıklaması
Eliptik eğri kriptografisi, bir eliptik eğrinin noktalarında toplama ve çarpma ile ifade edilen ayrık logaritma problemine dayanan bir asimetrik veya açık anahtar şifreleme türüdür.

Eliptik bir eğrinin görselleştirilmesi⬇️,Ethereum tarafından kullanılana benzer bir eliptik eğri örneğidir.

📝NOT:Ethereum, Bitcoin ile tam olarak secp256k1 adı verilen eliptik eğriyi kullanır. Bu, Bitcoin'deki birçok eliptik eğri kitaplığını ve aracını yeniden kullanmayı mümkün kılar. 📝

<img title="eliptic curve" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/simple_elliptic_curve.png">

⬆️ Eliptik bir eğrinin görselleştirilmesi

Ethereum, ABD Ulusal Standartlar ve Teknoloji Enstitüsü (NIST) tarafından kurulan _secp256k1 adlı bir standartta tanımlandığı gibi belirli bir eliptik eğri ve matematiksel sabitler kümesi kullanır._ secp256k1 eğrisi, eliptik bir eğri oluşturan aşağıdaki fonksiyonla tanımlanır:

y 2 = ( x 3 + 7 ) over ( 𝔽 p )
veya
y 2 mod p = ( x 3 + 7 ) mod p

p modu (module asal sayı p), bu eğrinin, aynı zamanda \(\( \mathbb{F}_p \)\ olarak da yazılan, p asal dereceli sonlu bir alan üzerinde olduğunu gösterir), burada
p = 2<sup>256</sup> - 2<sup>32</sup> - 2<sup>9</sup> - 2<sup>8</sup> - 2<sup>7</sup> - 2<sup>6</sup> - 2<sup>4</sup> -1 çok büyük bir asal sayıdır_ 

-------------------------

Bu eğri, gerçek sayılar yerine **sonlu bir asal hiyerarşi alanı üzerinde tanımlandığından, iki boyutta dağılmış bir nokta düzenine benziyor ve bu da görselleştirmeyi zorlaştırıyor**. Bununla birlikte, matematik, gerçek sayılar üzerindeki eliptik bir eğrininkiyle aynıdır. Örnek olarak, Eliptik eğri kriptografisi: F(p) üzerinde bir eliptik eğrinin p=17 ile görselleştirilmesi, aynı eliptik eğriyi çok daha küçük bir asal derece 17 alanı üzerinde gösterir ve bir ızgara üzerinde bir nokta deseni gösterir. _secp256k1 Ethereum eliptik eğrisi, akıl almaz derecede büyük bir ızgara üzerinde çok daha karmaşık bir nokta modeli olarak düşünülebilir_.

<img title="grid_eliptic_curve" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/ec_over_small_prime_field.png">

⬆️ Eliptik eğri kriptografisi: p=17 ile F(p) üzerinde bir eliptik eğrinin görselleştirilmesi
Örneğin, secp256k1 eğrisi üzerinde bir nokta olan koordinatları (x,y) olan bir Q noktası aşağıdadır:

`Q =
(49790390825249384486033144355916864607616083520101638681403973749255924539515,
59574132161899900045862086493921015780032175291755807399284007721050341297360)`

Python 🐍 kullanarak bunu nasıl kontrol edebileceğinizi görelim. x ve y değişkenleri, önceki örnekte olduğu gibi Q noktasının koordinatlarıdır. p değişkeni, eliptik eğrinin asal durumudur.(tüm modulo(bölümünden kalana) işlemleri için kullanılan asal değer). _Python'un son satırı eliptik eğri denklemidir_ (Python'daki % operatörü modulo(sayının bölümünden kalan) operatörüdür). Eğer x ve y gerçekten de eliptik eğri üzerindeki bir noktanın koordinatlarıysa, denklemi sağlarlar ve sonuç sıfırdır. 0️⃣(0L, sıfır değerine sahip uzun bir tamsayıdır). Bir komut satırına **python** yazıp listedeki her satırı ( >>> işaretinden sonra) kopyalayarak kendiniz deneyin.💻

`Python 3.9.0 (default, Sep 24 2022, 21:28:17)
[GCC 4.2.1 Toshiba  5.1 (clang-503.0.38)] on Ubuntu
Type "help", "copyright", "credits" or "license" for more information.`

`>>> p = 115792089237316195423570985008687907853269984665640564039457584007908834 \671663`

`>>> x = 49790390825249384486033144355916864607616083520101638681403973749255924539515`

`>>> y = 59574132161899900045862086493921015780032175291755807399284007721050341297360`

`>>> (x ** 3 + 7 - y**2) % p`
`0L`

## Eliptik Eğri Aritmetik İşlemleri (`+,*`)
Pek çok eliptik eğri matematiği okulda öğrendiğimiz **tamsayı aritmetiğine çok benziyor ve çalışıyor**. Spesifik olarak, sayı doğrusu boyunca atlamak yerine eğri üzerindeki diğer noktalara atlayan bir _toplama_ operatörü tanımlayabiliriz. Toplama operatörüne sahip olduğumuzda, **tekrarlanan toplamaya eşdeğer olan bir nokta ile bir tam sayının çarpımını da tanımlayabiliriz.**

Eliptik eğri ekleme, eliptik eğri üzerinde iki nokta P1 ve P2 verildiğinde, yine eliptik eğri üzerinde üçüncü bir P3 = P1 + P2 noktası olacak şekilde tanımlanır.

Geometrik olarak bu üçüncü nokta _P3_, P1 ile P2 arasına bir çizgi çizilerek hesaplanır. Bu çizgi, eliptik eğriyi tam olarak bir yerde (inanılmaz bir şekilde) kesecektir. Bu noktayı **P3' = (x, y) olarak adlandırın. Sonra x eksenine yansıtarak P3 = (x, –y)** elde edin.

P1 ve P2 aynı noktaysa, P1 ve P2 "arasındaki" doğru, bu P1 noktasındaki eğriye **teğet olacak şekilde uzanmalıdır.** Bu teğet, eğriyi tam olarak yeni bir noktada kesecektir. Teğet çizginin eğimini(slope) belirlemek için calculus tekniklerini kullanabilirsiniz. İlginçtir ki, ilgimizi eğri üzerindeki iki tamsayı koordinatıyla sınırlandırmamıza rağmen, bu teknikler işe yarıyor. 🍾

Eliptik eğri matematiğinde, **"sonsuzdaki nokta"(point at infinity)** olarak adlandırılan ve kabaca sıfır 0️⃣ sayısının rolüne ek olarak karşılık gelen bir nokta da vardır. Bilgisayarlarda bazen _x = y = 0 ile temsil edilir_ (bu, eliptik eğri denklemini karşılamaz, ancak kontrol edilebilecek kolay ayrı bir durumdur). Sonsuzdaki noktaya olan ihtiyacı açıklayan birkaç özel durum vardır.

* Bazı durumlarda (örneğin, P1 ve P2 aynı x değerlerine ancak farklı y değerlerine sahipse), çizgi tam olarak dikey olacaktır, bu durumda P3 = sonsuzdaki noktadır.

* P1 sonsuzdaki nokta ise, o zaman P1 + P2 = P2. Benzer şekilde, eğer P2 sonsuzdaki nokta ise, o zaman P1 + P2 = P1.

 * (+)'nın birleştirici olduğu bellidir, yani (A + B) + C = A + (B + C). Bu, A + B + C'yi (parantezsiz) olmadan yazabileceğimiz anlamına gelir.

* Artık toplamayı tanımladığımıza göre, toplamayı genişleten standart yolla çarpmayı tanımlayabiliriz. Eliptik eğri üzerindeki bir P noktası için, k bir tam sayıysa,( k* P = P + P + P + ... + P (k kez).) Bu durumda k'nin bazen (belki de kafa karıştırıcı bir şekilde) "üs" olarak adlandırıldığını unutmayın.

## Public(Genel/Açık) Anahtar Üretimi

Rastgele oluşturulmuş bir k sayısı biçimindeki özel bir anahtarla başlayarak, eğri üzerinde başka bir yerde, karşılık gelen public(genel) anahtar K olan başka bir nokta üretmek için, bunu eğri üzerinde G (üretici noktası) olarak adlandırılan önceden belirlenmiş bir nokta ile çarparız:
_K = k * G_
Üretici noktası,(G) secp256k1 standardının bir parçası olarak belirtilir; 
secp256k1'in tüm uygulamaları için aynıdır ve bu eğriden türetilen tüm anahtarlar aynı G noktasını kullanır.
üretici noktası tüm Ethereum kullanıcıları için her zaman aynı olduğundan, G ile çarpılan bir özel anahtar k her zaman aynı genel sonuçla sonuçlanır. anahtar K. k ve K arasındaki ilişki sabittir, ancak k'den K'ye yalnızca bir yönde hesaplanabilir. Bu nedenle bir Ethereum adresi (K'den türetilmiştir) herkesle paylaşılabilir ve kullanıcının özel anahtarını açığa çıkarmaz. (k).

Önceki bölümde açıkladığımız gibi, k * G'nin çarpımı tekrarlanan toplamaya eşdeğerdir, dolayısıyla G + G + G + ... + G, k kez tekrarlanır. Özetle, bir özel anahtar k'den bir public anahtar olan K'yı üretmek için, üretici noktası G'yi kendisine k kez ekleriz.

🔍İPUCU:Özel bir anahtar, bir genel anahtara dönüştürülebilir, ancak bir genel anahtar, matematik yalnızca tek bir şekilde çalıştığı için tekrar özel bir anahtara dönüştürülemez. 

Özel Anahtarlarda size gösterdiğimiz belirli özel anahtarın genel anahtarını bulmak için bu hesaplamayı uygulayalım: 
⬇️
_Genel anahtar hesaplamasına_ olarak örnek özel anahtar

`K = f8f8a2f43c8376ccb0871305060d7b27b0554d2cc72bccf41b2705608452f315 * G`

Bir kriptografik kitaplık, eliptik eğri çarpımını kullanarak K'yi hesaplamamıza yardımcı olabilir. Ortaya çıkan public anahtar K, nokta olarak tanımlanır:
⬇️
`K = (x, y)`

Sonuç olarak burada:
⬇️
 `x = 6e145ccef1033dea239875dd00dfb4fee6e3348b84985c92f103444683bae07b`
 
 `y = 83b5c38e5e2b0c8529d7fa3f64d46daa1ece2d9ac14cab9477d042c84c32ccd0`


| Prefix(önek)       | Anlamı        | # Uzunluğu(prefix-önek bayt) |
|--------------------|---------------|------------------------------|
| 0x00    | Point at infinity     |  1                        |
| ⭐ 0x04    | Uncompressed point    | 65                        |
| 0x02    | Compressed point with even(çift) y      | 33            |
| 0x03    | Compressed point with odd(tek) y      | 33             |


Ethereum yalnızca sıkıştırılmamış(Uncompressed) genel(public) anahtarlar kullanır; 
bu nedenle ilgili tek önek (hex) 04'tür. Serileştirme ile, genel anahtarın x ve y koordinatlarını birleştirir:

`04 + x-coordinate (32 bytes/64 hex) + y-coordinate (32 bytes/64 hex)`

Bu nedenle, daha önce hesapladığımız genel anahtar şu şekilde seri hale getirilir:

`046e145ccef1033dea239875dd00dfb4fee6e3348b84985c92f103444683bae07b83b5c38e5e2b0 \
c8529d7fa3f64d46daa1ece2d9ac14cab9477d042c84c32ccd0`

## Eliptic Eğri Kütüphaneleri 📑 

Kripto para birimiyle ilgili projelerde kullanılan _secp256k1_ eliptik eğrinin birkaç uygulaması vardır:

+ [_OpenSSL_](https://www.openssl.org/)

OpenSSL kitaplığı, tam bir secp256k1 uygulaması da dahil olmak üzere kapsamlı bir şifreleme ilkelleri seti sunar. Örneğin, genel anahtarı türetmek için EC_POINT_mul işlevi kullanılabilir.

+ [_libsecp256k1_](https://github.com/bitcoin-core/secp256k1)

Bitcoin Core'un libsecp256k1, secp256k1 eliptik eğrinin ve diğer kriptografik unsurların  C dili yazılmış uygulamasıdır. Bitcoin Core yazılımındaki OpenSSL'yi değiştirmek için sıfırdan yazılmıştır ve hem performans hem de güvenlik açısından üstün olarak kabul edilir.


## Kriptografik HASH fonksiyonu #️⃣

Ethereum genelinde _kriptografik hash fonksiyonları kullanılır._ Aslında, hash fonksiyonları neredeyse tüm kriptografik sistemlerde yaygın olarak kullanılmaktadırlar. bu durum, **"Şifreleme algoritmalarından çok daha fazlası olan, tek yönlü hash fonksiyonları modern kriptografinin beygir gücüdür"** 🐎 diyen kriptograf _Bruce Schneier[(Kendisinin makalesine ulaşmak isterseniz)](http://bit.ly/2Q79qZp)_ tarafından muazzam tespit edilmiştir.🤓

Bu bölümde, hash fonksiyonlarını tartışacağız, temel özelliklerini keşfedeceğiz ve bu özelliklerin onları modern kriptografinin pek çok alanında nasıl bu kadar faydalı hale getirdiğini göreceğiz. Burada hash fonksiyonlarını ele alıyoruz çünkü bunlar Ethereum public anahtarlarının -----> adreslere dönüşümünün bir parçası. Verilerin doğrulanmasına yardımcı olan **dijital parmak izleri** oluşturmak için de kullanılabilirler.

Basit bir ifadeyle, bir [Hash Fonksiyonu](http://bit.ly/2CR26gD) "rastgele boyuttaki verileri sabit boyutlu verilere dönüştürmek için kullanılabilecek herhangi bir fonksiyondur".( ❗Burada çok soyut kalmış olabilir bu yüzden ben sizlere özel olarak ▶️ [bu kaynağı sunuyorum.Lütfen deneyin.](https://andersbrownworth.com/blockchain/hash)) **Bir hash fonksiyonu:
+ girdi 
+ ön görüntü 
+ mesaj veya girdi verileri 

olarak adlandırılır. **Çıktıya hash denir.** Kriptografik hash fonskiyon, Ethereum gibi platformları güvenli hale getirmek için yararlı olan belirli özelliklere sahip özel bir alt kategoridir.


Bir _kriptografik hash fonksiyonu_, rastgele boyuttaki verileri sabit boyutlu bir bit dizisine çeviren _tek yönlü bir hash fonksiyonudur._  🌟 **"Tek yönlü" yani yalnızca çıktı değeri bilinyorsa, girdi verilerini yeniden oluşturmanın hesaplama açısından mümkün olmadığı anlamına gelir.** 🌟 

Olası bir girdiyi çözmeninin tek yolu, her bölümde eşleşen bir çıktı için  tek tek kontrol ederek, (kısaca)kaba kuvvet araştırması(brute-force search) yapmaktır.
Bir hash'ı oluşturan bazı **girdi(input data) verileri bulsanız bile, bunlar orijinal girdi verileri olmayabilir:** _hash fonksiyonları "birden çok" fonksiyonlardır._  **Aynı çıktıda -iki girdi veri setinin bulunmasına- hash çakışması(hash collision) denir. Yani kabaca,hash fonksiyonu ne kadar iyi olursa, hash çarpışmaları o kadar nadir olur. Ethereum için bunlar fiilen imkansızdır.**💪

_Kriptografik hash fonksiyonlarının temel özelliklerine daha yakından bakalım. Bunların arasında şunları sayabiliriz_:


* Deterministik yapı

Belirli bir girdi mesajı her zaman aynı hash çıktıyı üretir.

* Doğrulanabilirlik

Bir mesajın hashı doğrulabilir olmalıdır.(doğrusal karmaşıklık).

* Korelasyonsuzluk

Mesajdaki küçük bir değişiklik (örneğin, 1 bitlik bir değişiklik), özet çıktısını, orijinal mesajın özet değeriyle ilişkilendirilemeyecek kadar kapsamlı bir şekilde değiştirmelidir.

* tersinden çıkarım yapamamak(tek yönlü)

Mesajı hash'inden hesaplamak mümkün değildir, tüm olası mesajlar arasından kaba kuvvet ile aramaya eşdeğerdir.

* Çakışmadan korunma (Collision protection)

Aynı hash çıktısını üreten iki farklı mesajı hesaplamak mümkün olmamalıdır.

⏫
Bu özelliklerin birleşimi, aşağıdakiler dahil olmak üzere çok çeşitli güvenlik uygulamaları için kriptografik hash Fonksiyonlarını kullanışlı hale getirir:

* Dijital(Verisel) Parmak izi
* Mesaj bütünlüğü (hata algılama)
* PoW (iş ispatı)
* Kimlik doğrulama (parola hasleri )
* Sahte rasgele sayı üreteçleri
* Message commitment (commit–reveal mechanisms)
* Benzersiz Kullanıcı Kimlikleri

Sistemin çeşitli katmanlarında ilerlerken bunların çoğunu Ethereum'da bulacağız.

-------------------------

## Ethereum'un Kriptografik Hash Fonksiyonu: Keccak-2️⃣5️⃣6️⃣
Ethereum birçok yerde Keccak-256 kriptografik hash fonksiyonunu kullanır. Keccak-256, 
Ulusal Standartlar ve Teknoloji Enstitüsü tarafından 2007 yılında düzenlenen **SHA-3 Cryptographic Hash Function Yarışması'na aday olarak tasarlanmıştır.** 
Keccak, 2015 yılında Federal Bilgi İşleme Standardı (FIPS 202) olarak standart kazanmış bir algoritmaydı.

Ancak Ethereum'un geliştirildiği dönemde NIST standardizasyonu henüz _kesinleşmemişti._ NIST, iddiaya göre verimliliğini artırmak için standartların sürecinin tamamlanmasının ardından Keccak'ın bazı parametrelerinde ayarlamalar yaptı. 

Bütün bunlar olurken, kahraman bir aktivist _Edward Snowden'ın_, {_-Dual_EC_DRBG- rastgele sayı üreteci standardını kasıtlı olarak zayıflatmak ve standartı rastgele sayı üretecine etkin bir şekilde bir **arka kapı(backdoor)🚪** yerleştirmek_ için Ulusal Güvenlik Ajansı(NSA) tarafından hukuki olmayan bir şekilde etkilemiş olabileceğini iifade eden belgeleri ifşa etmesiyle aynı zaman dilimine denk gelmişti.( 🎥 Benden sizlere yine harika bir film geliyor. 🍿 Edward Snowden'ı anlatan müthiş bir film: [SNOWDEN](https://www.imdb.com/title/tt3774114/) ) 

Bu olayların sonucunda, önerilen değişikliklere karşı bir tepki ve SHA-3'ün standartdizasyonunda önemli bir gecikmeye sebep oldu.Böylelikle Ethereum Vakfı kararını vermişti: **NIST tarafından değiştirildiği şekliyle SHA-3 standardı yerine, Kendi kriptografları tarafından önerildiği gibi orijinal Keccak algoritmasını uygulamaya karar verdiler.**

⚠️UYARI: Ethereum belgelerinde ve kodunda "SHA-3" den bahsedildiğini görseniz de, bu örneklerin tamamı olmasa da çoğu, FIPS-202 SHA-3 standardına değil, aslında Keccak-256'ya atıfta bulunur.

----------------------------

## Hangi Hash Fonksiyonunu Kullanıyorum? 🧐

Her ikisi de "SHA-3" olarak adlandırılabiliyorsa, kullandığınız yazılım kitaplığının FIPS-202 SHA-3 veya Keccak-256'yı kullanıp kullanmadığını nasıl anlarsınız?

Bunu söylemenin kolay bir yolu, **belirli bir girdi için beklenen bir çıktı olan bir test vektörü kullanmaktır.** Bir hash fonksiyonu için en yaygın olarak kullanılan test, _boş girdidir_. Hash fonksiyonunu girdi olarak boş bir dizeyle çalıştırırsanız, aşağıdaki sonuçları görmelisiniz:


`Keccak256("") =
  c5d2460186f7233c927e7db2dcc703c0e500b653ca82273b7bfad8045d85a470`

`SHA3("") =
  a7ffc6f8bf1ed76651c14756a061d662f580ff4de43b49fa82d80a4b80f8434a`

Fonksiyon adı ne olursa olsun, bu basit testi çalıştırarak orijinal Keccak-256 veya son NIST standardı FIPS-202 SHA-3 olup olmadığını test edebilirsiniz. Unutmayın, Ethereum, kodda genellikle SHA-3 olarak adlandırılsa da Keccak-256'yı kullanır.

😻
Şimdiii, Ethereum adreslerinin -----> genel/açık(public) anahtarlardan üretilmesine yardımcı olan Keccak-256'nın Ethereum'daki ilk uygulamasını inceleyelim.

--------------------


## Ethereum Adresleri 🔷

Ethereum adresleri, _genel anahtarlardan veya Keccak-256 tek yönlü hash fonksiyonları kullanan sözleşmelerden_ türetilen benzersiz tanımlayıcılardır.
Önceki örneklerimizde, özel bir anahtarla başladık ve bir genel anahtar türetmek için eliptik eğri çarpmasını kullandık:

Özel anahtar k:

`k = f8f8a2f43c8376ccb0871305060d7b27b0554d2cc72bccf41b2705608452f315`

Genel anahtar K (x ve y koordinatları birleştirilmiş ve hex olarak gösterilmiştir):

 `K = 6e145ccef1033dea239875dd00dfb4fee6e3348b84985c92f103444683bae07b83b5c38e5e...`

📝NOT : Adres hesaplanırken genel anahtarın (hex 04 öneki) ile biçimlendirilmediğine dikkat etmek önemlidir.📝

Bu genel anahtarın hash'ini hesaplamak için Keccak-256 kullanıyoruz:

`Keccak256(K) = 2a5bc342ed616b5ba5732269001d3f1ef827552ae1114027bd3ecf1f086ba0f9`

⭐Ardından, Ethereum adresimiz olan sadece son _20 baytı_ tutarız:

`01d3f1ef827552ae1114027bd3ecf1f086ba0f9`

Çoğu zaman, hex kodlu olduklarını belirten (0x ön ekine) sahip Ethereum adreslerini görürsünüz, şöyle:

`0x001d3f1ef827552ae1114027bd3ecf1f086ba0f9`

----------

## Ethereum Adres Formatları(Biçimleri) 🎲

Ethereum adresleri, genel anahtarın Keccak-256 hash'ınin son 20 baytından türetilen [onaltılık(hexadecimal) sayılardır](https://tr.wikipedia.org/wiki/On_altılı_sayı_sistemi).Yanlış yazılan adreslere karşı koruma sağlamak için yerleşik bir [sağlama toplamı(checksum)](https://hayateli.com/saglama-toplami-nedir/) içerecek şekilde tüm istemcilerin kullanıcı arabiriminde kodlanan _Bitcoin adreslerinden farklı olarak, Ethereum adresleri herhangi bir sağlama toplamı olmadan saf bir halde hexadecimal olarak sunulur_.

Bu kararın arkasındaki mantık, Ethereum adreslerinin sonunda sistemin daha yüksek katmanlarında soyutlamaların ( Name services(İsim hizmetleri gibi): gibi) arkasına gizleneceği ve gerekirse daha yüksek katmanlara sağlama toplamlarının eklenmesi gerektiğiydi.

Gerçekten de, bu üst katmanlar çok yavaş geliştirildiler ve bu tasarım seçimi, ekosistemin ilk günlerinde yanlış yazılan adresler ve giriş doğrulama hataları nedeniyle _fon kaybı da dahil olmak üzere bir dizi soruna yol açtı_. Ayrıca, Ethereum name services({Ethereum Name Service (ENS); kullanıcıların, Ethereum tabanlı ağa daha kolay erişmesini sağlamayı amaçlar.}) başlangıçta beklenenden daha yavaş geliştirildiğinden, alternatif kodlamalar cüzdan geliştiricileri tarafından çok yavaş benimsendiler. Sonraki aşamada kodlama seçeneklerinden birkaçına bakacağız.

📝NOTT:Benden sizlere önemli bir bilgi daha: ⏬

ENS ile .eth uzantılı adresler alınabilmektedir.
Aşağıdaki örnekte gösterildiği gibi karmaşık bir cüzdan kodu, ENS hizmeti ile daha basit ve anlaşılabilir bir hale dönüştürülebilir.

`12c6DSiU4Rq3P4ZxziKxzrL5LmMBrzjrJX --—> satoshi.eth` 
📝

## Karşılıklı İstemci Adres değişim Protokolü(Inter exchange Client Address Protocol)
Inter exchange Client Address Protocol (ICAP), Uluslararası Banka Hesap Numarası (IBAN) kodlamasıyla kısmen uyumlu olan ve Ethereum adresleri için çok yönlü, sağlama toplamı ve birlikte çalışabilir bir  _kodlama sunan bir Ethereum adres kodlamasıdır._ ICAP adresleri, Ethereum adreslerini veya bir Ethereum ad kaydına kayıtlı ortak adları kodlayabilir. ICAP hakkında daha fazla bilgiyi [Ethereum Wiki'de](https://eth.wiki/en/ideas/inter-exchange-client-address-protocol-icap) okuyabilirsiniz.

IBAN, çoğunlukla banka havaleleri için kullanılan banka hesap numaralarının tanımlanmasına yönelik uluslararası bir standarttır. SEPA ve ötesinde geniş çapta benimsenmiştir. IBAN, merkezileştirilmiş ve sıkı bir şekilde düzenlenmiş bir hizmettir. **ICAP, Ethereum adresleri için merkezi olmayan ancak uyumlu bir uygulamadır**.

**Bir IBAN, bir ülke kodu, sağlama toplamı ve banka hesabı tanımlayıcısı (ülkeye özgü olan) içeren, en fazla 34 alfa-sayısal karakterden (büyük/küçük harfe duyarlı olmayan) oluşan bir dizeden oluşur.**

ICAP, "Ethereum" anlamına gelen standart olmayan bir ülke kodu olan "XE", ardından iki karakterlik bir sağlama toplamı ve bir hesap tanımlayıcısının _üç olası_ varyasyonunu ekleyerek aynı yapıyı kullanır:

1️⃣ _Direct_

Bir Ethereum adresinin en az anlamlı 155 bitini temsil eden, 30'a kadar alfasayısal karakterden oluşan bir big-endian taban-36 tamsayı. Bu kodlama, genel bir Ethereum adresinin tam 160 bitinden daha azına sığdığından, yalnızca bir veya daha fazla sıfır bayt ile başlayan Ethereum adresleri için çalışır. **Avantajı, alan uzunluğu ve sağlama toplamı açısından IBAN ile uyumlu olmasıdır.---> Örnek: XE60HAMICDXSV5QXVJA7TJW47Q9CHWKJD (33 karakter uzunluğunda).**

2️⃣ _Basic_

31 karakter uzunluğunda olması dışında _Direct'in_ kodlaması ile aynıdır. **Bu, herhangi bir Ethereum adresini kodlamasına izin verir, ancak onu IBAN alan doğrulaması ile uyumsuz hale getirir**. -----> Örnek: XE18CHDJBPLTBCJ03FE9O2NS0BPOJVQCU2P (35 karakter uzunluğunda).

3️⃣ _Indirect_
?
Bir ad kayıt sağlayıcısı aracılığıyla bir Ethereum adresine çözümlenen bir tanımlayıcı tarafından kodlanır. bir ad (ör. TIMURLENK) içeren 16 alfasayısal karakter kullanır. Örnek: XE##ETHXREGTIMURLENK (20 karakter uzunluğunda), burada ## iki hesaplanmış olan _sağlama toplamı_ karakteriyle değiştirilmelidir.

---------------------

ICAP adresleri oluşturmak için **helpeth komut satırı aracını kullanabiliriz**. Aşağıdakilerle kurarak helpeth alabilirsiniz: 🏗️

`$ npm install -g helpeth`

Eğer npm'niz yoksa, önce nodeJS'yi kurmanız gerekebilir, bunu [Nodejs](https://nodeJS.org) adresindeki talimatları izleyerek yapabilirsiniz.

Artık helpeth'imiz olduğuna göre, örnek özel anahtarımızla (ön eki 0x olan ve helpeth'e parametre olarak geçirilen) bir ICAP adresi oluşturmayı deneyelim.)

`$ helpeth keyDetails \
  -p 0xf8f8a2f43c8376ccb0871305060d7b27b0554d2cc72bccf41b2705608452f315`

`Address: 0x001d3f1ef827552ae1114027bd3ecf1f086ba0f9`

`ICAP: XE60 HAMI CDXS V5QX VJA7 TJW4 7Q9C HWKJ D`

`Public key: 0x6e145ccef1033dea239875dd00dfb4fee6e3348b84985c92f103444683bae07b...`

_Helpeth komutu_, bizim için bir ICAP adresinin yanı sıra onaltılık  sayı sisteminde(Hex) bir Ethereum adresi oluşturur. Örnek anahtarımız için ICAP adresi:

`XE60HAMICDXSV5QXVJA7TJW47Q9CHWKJD`


Örnek Ethereum adresimiz sıfır bayt ile başladığı için, IBAN formatında geçerli olan Doğrudan ICAP kodlama yöntemi kullanılarak kodlanabilir. 33 karakter uzunluğunda olduğu için anlayabilirsiniz.

Adresimiz sıfır ile başlamasaydı, 35 karakter uzunluğunda ve IBAN olarak geçersiz olacak Temel kodlama ile kodlanacaktı.

📝 NOtT:ICAP şeklindeki adreslerimizi destekleyen cüzdanların hangileri olduğu konusuna dikkat ediniz.

## Büyük Harfte Sağlama Toplamı ile Hex Kodlaması (EIP-55) (Hex Encoding with Checksum in Capitalization)

ICAP ve ad hizmetlerinin(ENS) yavaşlığı nedeniyle, Ethereum İyileştirme Önerisi 55 (EIP-55) tarafından bir standart önerildi. EIP-55, onaltılık adresin büyük harf kullanımını değiştirerek Ethereum adresleri için geriye dönük uyumlu bir sağlama toplamı sunar. **Buradaki fikir, Ethereum adreslerinin büyük/küçük harfe duyarlı olmaması ve tüm cüzdanların, içerikte herhangi bir fark olmaksızın büyük veya küçük harflerle ifade edilen Ethereum adreslerini kabul etmesi gerektiğidir**.

Adresteki alfabetik karakterlerin **büyük harflerini değiştirerek, adresin bütünlüğünü yazma veya okuma hatalarına karşı korumak için kullanılabilecek bir sağlama toplamı iletebiliriz.** EIP-55 sağlama toplamlarını desteklemeyen cüzdanlar, adresin karışık büyük harf kullanımı içerdiği gerçeğini görmezden gelir, ancak onu destekleyenler onu doğrulayabilir ve hataları %99.986 doğrulukla tespit edebilir.

Örnek adresimiz:

`0x001d3f1ef827552ae1114027bd3ecf1f086ba0f9`


Bir EIP-55 karma büyük harf sağlama toplamı ile şu hale gelir:

`0x001d3F1ef827552Ae1114027BD3ECF1f086bA0F9`

❓
Farkı söyleyebilir misiniz? 
Onaltılık kodlama alfabesindeki(Hexadecimal) alfabetik (A–F) karakterlerden bazıları artık büyük, bazıları ise küçük harftir.

EIP-55'in uygulanması oldukça basittir. **Küçük harfli onaltılık adresin Keccak-256 hash'ini alıyoruz. Bu hash, adresin _dijital parmak izi_ görevi görerek bize uygun bir sağlama toplamı verir. Girdideki (adres) herhangi bir küçük değişiklik, ortaya çıkan hash'te (sağlama toplamı) büyük bir değişikliğe neden olmalı ve hataları etkili bir şekilde tespit etmemize izin vermelidir. Adresimizin hash'i daha sonra adresin kendisinin büyük harf kullanımında kodlanır. Adım adım parçalara ayıralım:

a) 0x öneki olmadan küçük harfli adresi hash haline getirin:

`Keccak256("001d3f1ef827552ae1114027bd3ecf1f086ba0f9") =
23a69c1653e4ebbb619b0b2cb8a9bad49892a8b9695d9a19d8f673ca991deae1`

b) hash'in karşılığında ki onaltılık basamağı 0x8'e eşit veya daha büyükse, her alfabetik adres karakterini _büyük harf yapın._ Adresi ve hash'i sıralarsak bunu göstermek daha kolaydır:

`Address: 001d3f1ef827552ae1114027bd3ecf1f086ba0f9`

`Hash   : 23a69c1653e4ebbb619b0b2cb8a9bad49892a8b9...`

Adresimiz dördüncü konumda alfabetik bir d karakteri içeriyor. 
Hash'in dördüncü karakteri 8'den küçük olan 6'dır. Yani, d'yi küçük bırakıyoruz. Adresimizde bir sonraki alfabetik karakter, altıncı konumda f'dir. Onaltılık hashın altıncı karakteri c'dir 
ve bu 8'den büyüktür. Bu nedenle, adresteki F'yi büyük harfle yazıyoruz, vb. Gördüğünüz gibi, adreste uygun şekilde büyük harf kullanmak için yalnızca 20 bayt (40 onaltılık karakter) olduğundan, sağlama toplamı olarak karmanın yalnızca ilk 20 baytını (40 onaltılık karakter) kullanıyoruz.

Ortaya çıkan karışık büyük harfleri kendiniz kontrol edin ve hangi karakterlerin büyük harfle yazıldığını ve adres karmasında hangi karakterlere karşılık geldiklerini söyleyebilip anlayamayacağınıza bakın:

`Address: 001d3F1ef827552Ae1114027BD3ECF1f086bA0F9`

`Hash   : 23a69c1653e4ebbb619b0b2cb8a9bad49892a8b9...`

--------------------
EIP-55 ile kodlanmış bir adreste bir _hata algılama_: ⛔

Şimdi EIP-55 adreslerinin nasıl hata bulmamıza yardımcı olacağına bakalım. EIP-55 kodlu bir Ethereum adresi yazdırdığımızı _varsayalım_: 

`0x001d3F1ef827552Ae1114027BD3ECF1f086bA0F9`

Şimdi bu adresi okurken basit bir hata yapalım. Son karakterden önceki karakter büyük **F**'dir. Bu örnek için bunu büyük **E** olarak yanlış okuduğumuzu ve cüzdanımıza aşağıdaki (yanlış) adresi yazdığımızı varsayalım:

`0x001d3F1ef827552Ae1114027BD3ECF1f086bA0E9`

Neyse ki cüzdanımız EIP-55 uyumlu! 🥳 Küyük harf kullanımını fark eder ve adresi doğrulamaya çalışır. Küçük harfe dönüştürür ve sağlama toplamı hash'ini hesaplar:

`Keccak256("001d3f1ef827552ae1114027bd3ecf1f086ba0e9") =
5429b5d9460122fb4b11af9cb88b7bb76d8928862e0a57d46dd18dd8e08a6927`

Gördüğünüz gibi, adres yalnızca bir karakter değişse de (aslında, e ve f birbirinden bir bit uzakta olduğundan yalnızca bir bit), adresin hash'i kökten değişti. Bu, onları _sağlama toplamları(checksum)_ için çok kullanışlı hale getiren HASH FONKSİYONLARININ özelliğidir! 💪

Şimdi ikisini sıralayalım ve büyük harf kullanımını kontrol edelim:

`001d3F1ef827552Ae1114027BD3ECF1f086bA0E9`

`5429b5d9460122fb4b11af9cb88b7bb76d892886...`

🔴 İştee Hataa! Alfabetik karakterlerin birçoğu hatalı bir şekilde büyük harfle yazılmış. Büyük harf kullanımının **doğru(correct) sağlama toplamının kodlaması** olduğunu unutmayın.

Girdiğimiz adresin büyük harf kullanımı, az önce hesaplanan _sağlama toplamı ile eşleşmiyor_, 🎯 yani adreste bir şeyler değişti ve bir hata oluştu.

## Sonuç olarak bu bölümde :

Bu bölümde, genel anahtar kriptografisi hakkında kısa bir bilgi edinmenizi sağladık ve Ethereum'da genel ve özel anahtarların kullanımına ve Ethereum adreslerinin oluşturulmasında ve doğrulanmasında _hash fonksiyonları gibi kriptografik araçların kullanımına odaklandık._ Ayrıca _dijital imzalara ve bu özel anahtarı ifşa etmeden(göstermeden), özel bir anahtarın sahipliğini nasıl gösterebileceklerine_ baktık. _Cüzdan(wallet)_ bölümünde bu fikirleri bir araya getireceğiz ve bütün anahtarları yöneterek cüzdanların nasıl kullanılabileceğini inceleyeceğiz.

---------------- 🏁 Bölüm Sonu

















