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

Bir Ethereum işleminin _ödeme kısmında_, **hedeflenen alıcı(gönderilmek istenen kişi)**, bir banka havalesinde ,hak sahibi olan kişinin _hesap ayrıntılarıyla aynı şekilde kullanılan bir adet Ethereum adresiyle temsil edilir_. Birazdan daha detaylı olarak göreceğimiz gibi, bir *EOA(Externally Owned Accounts -----> Geçtiğimiz kısımlarda anlatıldı.Ama ben sadece bu bölümü okuyorum.Beni bilgilendirmek durumundasın.Pijjjlik 🐱 yapma derseniz. ▶️ [Bakınız](https://ethereum.stackexchange.com/questions/5828/what-is-an-eoa-account#5829) )* için bir Ethereum adresi, bir **anahtar çiftinin ortak anahtar kısmından üretilir**. Ancak, tüm Ethereum adresleri _genel-özel anahtar çiftlerini temsil etmez_. Akıllı sözleşme bölümünde göreceğimiz gibi, özel anahtarlarla desteklenmeyen sözleşmeleri de temsil edebilirler.

Bu bölümün geri kalanında, önce temel kriptografiyi biraz daha detaylı inceleyeceğiz ve Ethereum'da kullanılan matematiği açıklayacağız. Ardından anahtarların nasıl oluşturulduğuna, saklandığına ve yönetildiğine bakacağız. Son olarak, özel anahtarları, genel anahtarları ve adresleri temsil etmek için kullanılan çeşitli kodlama biçimlerini gözden geçireceğiz. 👨‍💻 👩‍💻

-----------------
















