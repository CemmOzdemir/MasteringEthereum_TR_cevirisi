# KRİPTOGRAFİ  🔡 🧮

Ethereum'un temel teknolojilerinden biri, **bilgisayar güvenliğinde yaygın olarak kullanılan bir matematik dalı olan kriptografidir**. Kriptografi, Latince _"gizli yazı"_ anlamına gelir, ancak **kriptografi çalışmaları, şifreleme olarak adlandırılan _gizli yazıdan_ daha fazlasını kapsar**. Örneğin kriptografi, bir gizliliği ifşa etmeden bir gizli bilgiyi kanıtlamak için (örneğin _dijital bir imza_ 🖋️ ile) veya verilerin gerçekliğini kanıtlamak için (örneğin, dijital parmak izleriyle,💻 🖐️ aynı zamanda _"hash"_ olarak da bilinir) kullanılabilir. Bu tür kriptografik kanıtlar, Ethereum platformunun (gerçek anlamda tüm blok zinciri sistemlerinin) çalışması için kritik olan **matematiksel araçlardır ve ayrıca Ethereum uygulamalarında yaygın olarak kullanılmaktadırlar.**

Ağ dağıtımı sırasında, Ethereum protokolünün hiçbir parçasının **şifreleme içermediğini** unutmayın; yani, Ethereum platformuyla ve düğümler arasındaki (işlem verileri dahil) _tüm iletişimler şifrelenmez_ 🔴 ve (zorunlu olarak) herkes tarafından görülebilir. Bu, herkesin durum güncellemelerinin doğruluğunu doğrulayabilmesi ve fikir birliğine varılabilmesi içindir. Gelecekte, sıfır bilgi kanıtı(Zero Knowledge Proof 0️⃣ ------>Bu ne demek yaaa 😸 diyorsanız: 👩‍💻[Chainlink'in Türkiye ve Avrupa sorumlusu Elif Hilal Umucu'nun yazısını bırakıyorum](https://medium.com/chainlink-community/zero-knowledge-proof-sıfır-bilgi-kanıtı-nedir-b810be4e1b29) 🔷) ve( homomorfik şifreleme [bunun içinde opsiyonel olarak buraya bırakıyorum 🌼](https://learn.microsoft.com/tr-tr/azure/architecture/solution-ideas/articles/homomorphic-encryption-seal) ) gibi gelişmiş kriptografik araçlar, bazı şifreli hesaplamaların blok zincirine kaydedilmesine izin verirken aynı şekilde consensus'u mümkün kılacaktır; bununla birlikte, Bu teknolojiler ile ilgili çalışmalar sürmektedir.

Bu bölümde, Ethereum'da kullanılan bazı kriptografiyi tanıtacağız: 
Yani, **özel anahtarlar** 🔐 ve **adresler biçiminde fon(bakiye) sahipliğini kontrol etmek için kullanılan açık anahtar kriptografisi** 🔑(PKC).----->(Public Key Crptography)

----------

## Anahtarlar ve Adresler
Kitapta daha önce gördüğümüz gibi, Ethereum'un iki farklı hesap türü vardır: 1- _harici olarak sahip olunan hesaplar (EOA'lar) ve 2-sözleşmeler._ EOA'ların ether sahipliği, dijital **özel anahtarlar**, **Ethereum adresleri** ve **dijital imzalar** aracılığıyla kurulur. Özel anahtarlar(kapalı anahtar olarakta geçer (Private Key) 🔐 ), Ethereum ile tüm kullanıcı etkileşiminin **merkezinde yer alır**. Aslında, _hesap adresleri doğrudan özel anahtarlardan türetilir_ ----> özel anahtar, hesap olarak da bilinen(account) tek bir Ethereum adresini eşsiz(unique) bir şekilde belirler.📰

Özel anahtarlar hiçbir şekilde **doğrudan** Ethereum sisteminde kullanılmaz; asla iletilmez veya Ethereum'da **depolanmaz**. 🔴  Başka bir deyişle, özel anahtarlar gizli kalmalı ve ağa iletilen iletilerde asla **görünmemeli ve zincir üzerinde depolanmamalıdır**; Ethereum sisteminde yalnızca _hesap adresleri ve dijital imzalar iletilir ve saklanır._ 🟢İlerleyen bölümlerde derince anlatılacak.

Access and control ...
