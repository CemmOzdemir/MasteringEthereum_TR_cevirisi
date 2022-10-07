# Cüzdanlar(Wallets) 🔑

_"Cüzdan"_ kelimesi, Ethereum'da birkaç farklı şeyi tanımlamak için kullanılır.

Üst düzey şekilde anlamak gerekirse: ▶️ **Cüzdan, Ethereum'a birincil kullanıcı arayüzü olarak hizmet eden yazılım uygulamasıdır.** Cüzdan, bir kullanıcının parasına erişimi, anahtarları ve adresleri yönetmeyi, bakiyeyi izlemeyi ve işlem oluşturma ve imzalamayı kontrol eder. Ek olarak, bazı Ethereum cüzdanları, ERC20 jetonları gibi sözleşmelerle de etkileşime girebilir.( ✏️Hatta bazı cüzdanlar artık NFT'lerinizede erişmenizi sağlıyor.)

Daha dar anlamda, bir _programcının bakış açısından_ ▶️ **cüzdan, bir kullanıcının anahtarlarını depolamak ve yönetmek için kullanılan sistemi ifade eder**. Her cüzdanın bir _anahtar yönetim bileşeni_ vardır. Bazı cüzdanlar sadece bunun için vardır.

Diğer cüzdanlar, _Ethereum tabanlı merkezi olmayan uygulamalara arayüz olan tarayıcılar_ veya Dapp(merkezi olmayan Uygulamalar) bölümünde daha ayrıntılı olarak inceleyeceğimiz _DApp_'ler gibi çok daha geniş bir kategorinin birer parçasıdır. Cüzdan terimi altında toplanan çeşitli kategoriler arasında _net bir ayrım çizgisi yoktur._

Bu bölümde, cüzdanlarda  bulunan özel anahtarlar için, **bu anahtarları yönetmek için** gerekli sistemlere bakacağız.

----------------

## Cüzdan teknolojisine Genel bir Bakış 👀

Bu bölümde, kullanıcı dostu, güvenli ve esnek Ethereum cüzdanları oluşturmak için kullanılan çeşitli teknolojilere değineceğiz.


Cüzdan tasarımında göz önünde bulundurulması gereken en önemli noktalardan biri, ⭐ **kolaylık ve gizliliği iyi ayarlamaktır.**  En uygun Ethereum cüzdanı, _her şey için yeniden kullandığınız tek bir özel anahtara ve adrese sahip olan cüzdandır._ Ne yazık ki, _herkes tüm işlemlerinizi kolayca takip edip(etherscan vb üzerinden) ilişkilendirebileceğinden, böyle bir çözüm gizlilik için korku dolu bir kabustur_.( 📝NOT---->ZKP(zero knowladge proof) ileriki zamanlarda bu olayı çözebilir📝)  
_Her işlem için yeni bir anahtar kullanmak gizlilik için en iyisidir_, ancak yönetmesi çok zor hale gelir. 
Doğru dengeyi sağlamak zordur, ancak bu nedenle iyi cüzdan tasarımı çok önemlidir.💖

---------------

Ethereum hakkında yaygın olan bir **yanılgı** ise, **Ethereum cüzdanlarının ether veya jeton içerdiğidir. Aslında, kesin olarak konuşursak, cüzdan sadece anahtarları tutar.** Ether veya diğer belirteçler, _Ethereum blok zincirine_ kaydedilir. Kullanıcılar, cüzdanlarındaki anahtarlarla işlemleri imzalayarak ağdaki token'larını veya etherlerini kontrol eder. **_Daha iyi bir anlamda, Ethereum cüzdanı  bir ANAHTARLIKTIR._** 🔑⛓️🔑 

 Ether veya jetonları başkalarına aktarmak için gereken tek şeyin cüzdan tarafından tutulan anahtarlar olduğu göz önüne alındığında, pratikte bu ayrım oldukça önemsiz durumdadır. 
 Farkın önemli olduğu yer, kişinin zihniyetini, geleneksel bankacılığın, merkezi sistemle çalışan yapıdan farklı bir şekile değiştirmesidir.🏦

Uygulamada, bir hesabın cüzdanına ihtiyaç duymadan bakiyesini kontrol etmenin bağımsız bir yolu vardır.(etherscan'a girip herhangi bir işlemin üzerine tıklayıp _from-to_ kısmına bakmanız yeterli) Ayrıca, kullanmaya başladığınız cüzdan uygulamasını beğenmezseniz, bakiyenizi mevcut cüzdanınızdan farklı bir cüzdana taşıyabilirsiniz.

📝NOT:Ethereum cüzdanları, ether veya token değil, anahtar içerir. Cüzdanlar, özel ve genel anahtar çiftleri içeren anahtarlık gibidir. Kullanıcılar özel anahtarlarla işlemleri imzalayarak ethere sahip olduklarını kanıtlarlar. Ether blokzincirde depolanır.📝

İçerdikleri anahtarların birbiriyle ilişkili olup olmamasına göre ayırt edilen _iki temel cüzdan türü vardır._ ⬇️

1️⃣ İlk tür, her anahtarın bağımsız olarak _farklı bir rastgele sayıdan üretildiği_, **deterministik olmayan** bir cüzdandır. Anahtarlar birbiriyle ilişkili değildir. Bu cüzdan türü, "Sadece Bir deste Anahtar" yani _JBOK cüzdanı_ olarak da bilinir.
 
2️⃣ İkinci cüzdan türü, tüm anahtarların tohum(seed)🌱 olarak bilinen tek bir ana anahtardan türetildiği **deterministik** bir cüzdandır. Bu cüzdan türündeki tüm anahtarlar birbiriyle ilişkilidir ve _orijinal tohum varsa_ yeniden oluşturulabilir. Deterministik cüzdanlarda kullanılan bazı farklı anahtar türetme yöntemleri vardır. En yaygın olarak kullanılan türetme yöntemi, [Hiyerarşik Deterministik Cüzdan'da(BIP32/44)] açıklandığı gibi(aşşağıda görsel bir şekilde açıklanıyor ⤵️) ağaç benzeri bir yapı kullanılarak yapılır.

Deterministik cüzdanlar, telefonunuzun çalınması 😫📱 veya tuvalete düşmesi 🚽 gibi veri kaybı kazalarına karşı biraz daha güvenli hale getirmek üzere, tohumlar(seeds)  için genellikle _yazmanız ve kullanmanız_ için bir kelime listesi (İngilizce veya başka bir dilde de olabilir) olarak kodlanırlar. bir kaza durumunda bunu kullanırız.
Bunlar,cüzdanın **anımsatıcı kelimeleri(mnemonic words)** olarak bilinirler. 
 
 📝NOT-----> Genelde Nnemonic words(anımsatıcı kelimler) 12 veya 24 kelime arası değişiklik gösterirler.

Tabii ki, birisi 🧔 ,anımsatıcı kelimelerinizi(mnemonic words) ele geçirirse, **cüzdanınızı yeniden oluşturabilir ve böylece ether ve akıllı sözleşmelerinize erişim sağlayabilir.** Bu nedenle, _kurtarma kelime listenize(mnemonic words'den bahsediyor) çok ama çok dikkat edin_ ❗ **Asla elektronik olarak, bir dosyada, bilgisayarınızda veya telefonunuzda saklamayın**.🔴   
**Kağıda yazın 📕 ve güvenli bir yerde saklayın.✔️

Sonraki birkaç bölüm, bu teknolojilerin her birini ileri seviyede🥶 açıklamaktadır.( ⚠️Eğer zor gelirse moralinizi bozmayın.Kendinize zaman tanıyın.İstediğiniz zaman okuyun.Öfkenizi,üzüntünüzü,pişmanlığınızı ve birçok duyguyu okuyarak unutabilirsiniz) 

------------

## 1️⃣ Deterministik Olmayan --Rastgele-- Cüzdanlar(Nondeterministic (Random) Wallets 

İlk Ethereum cüzdanlarında (_Ethereum ön satışı için üretilmiştir_), her cüzdan dosyası rastgele oluşturulmuş **tek bir özel anahtar** depoladı. Bu tür cüzdanlar **deterministik cüzdanlarla değiştiriliyor** 🔄 çünkü bu _"eski tarz"_ cüzdanlar birçok yönden daha kalitesiz durumdalar. 
Örneğin, Ethereum kullanırken gizliliğinizi en üst düzeye çıkarmanın bir parçası olarak **Ethereum adresinin yeniden kullanılmasından kaçınmak, yani her para transferimizde yeni bir adres (yeni bir özel anahtar gerektiren yapı) kullanmak iyi bir uygulama olarak kabul edilir.** Daha fazlası,her _işlem_ için yeni bir adres kullanabilirsiniz, ancak **çok fazla token ile işlemler yaparsanız** bu **pahalı** olabilir. Uygulamada(pratikte) bu yapıyı takip ettiğimizde, **_deterministik olmayan bir cüzdanın anahtar listesini düzenli olarak artırması gerekecektir,bu da düzenli yedeklemeler 👜 yapmanız gerekeceği anlamına geliyor._** Cüzdanınızı yedeklemeyi gerçekleştirmeden verilerinizi kaybederseniz (disk arızası💾 ,içecek dökülmesi 🍻, telefonun çalınması 📱), _fonlarınıza ve akıllı sözleşmelerinize erişiminizi_ **kaybedersiniz.** 😵 

"Tip 0(type 0)0️⃣" deterministik olmayan cüzdanlar, **uğraşılması en zor olanlardır**, çünkü her yeni adres için _"tam zamanlı"_ yeni bir cüzdan dosyası oluştururlar.

Bununla birlikte, birçok Ethereum istemcisi (geth dahil), ekstra güvenlik için bir **parola ile şifrelenmiş tek bir (rastgele oluşturulmuş) özel anahtar içeren JSON ile kodlanmış bir dosya olan _anahtar deposu dosyasını_ kullanır**. JSON dosyasının içeriği şöyle görünür:


```
{
    "address": "001d3f1ef827552ae1114027bd3ecf1f086ba0f9",
    "crypto": {
        "cipher": "aes-128-ctr",
        "ciphertext":
            "233a9f4d236ed0c13394b504b6da5df02587c8bf1ad8946f6f2b58f055507ece",
        "cipherparams": {
            "iv": "d10c6ec5bae81b6cb9144de81037fa15"
        },
        "kdf": "scrypt",
        "kdfparams": {    //aşağıda belirttiği gibi .n aşşağıdaki tur(round) sayısını gösteriyor
            "dklen": 32,
            "n": 262144,
            "p": 1,
            "r": 8,
            "salt":
                "99d37a47c7c9429c66976f643f386a61b78b97f3246adca89abe4245d2788407"
        },
        "mac": "594c8df1c8ee0ded8255a50caf07e8c12061fd859f4b7c76ab704b17c957e842"
    },
    "id": "4fcb2ba4-ccdb-424f-89d5-26cce304bf9c",
    "version": 3
}

```

Anahtar deposu(key store) 🔑 formatı, ↗️[parola genişletme algoritması(password stretching algorithm)](https://miro.medium.com/max/640/1*gqoIas2TgHfFn9u_QqnO9A.png) olarak da bilinen ve 👊[kaba kuvvet saldırsı](https://www.kaspersky.com.tr/resource-center/definitions/brute-force-attack), 📗[sözlük-dictionary](https://bilgisayarkavramlari.com/2009/08/20/sozluk-saldirisi-dictionary-attack/) ve 🌈[rainbow tablosu saldırılarına](https://bilgiguvende.com/rainbow-table-saldirisi-nedir-ve-nasil-uygulanir-onlenmesine-yonelik-yontemler-nelerdir/)  karşı koruma sağlayan bir anahtar türetme fonksiyonu(Key Derivation Funct.) kullanır.

Basit bir ifadeyle, **özel anahtar doğrudan parola tarafından şifrelenmez**. Bunun yerine, parola art arda hash edilerek uzatılır. hash fonksiyonu(karma işlev), JSON anahtar deposundaki _crypto.kdfparams.n_ parametresi olarak görülebilen _262,144_ tur için tekrarlanır. Parolayı kaba kuvvetle zorlamaya çalışan bir saldırganın, denemeye çalıştığı her parola için 262.144 tur karma(hash) uygulaması gerekir; bu, saldırıyı yeterli karmaşıklık ve uzunlukta parolalar için olanaksız hale getirmek için 🐢 yavaşlatır.

⬇️ aşağıdaki görseli size yardımcı olsun diye bırakıyorum.

<img title="KDF" src="https://miro.medium.com/max/640/1*gqoIas2TgHfFn9u_QqnO9A.png">


JavaScript kitaplığında [keythereum](https://github.com/ethereumjs/keythereum) gibi anahtar deposu biçimini okuyabilen ve yazmamıza olanak sağlayan bir dizi yazılım kitaplığı vardır.

🔍İPUCU----> Basit testler dışındaki herhangi bir şey için deterministik olmayan cüzdanların kullanılması **önerilmez**. En temel durumlar dışında herhangi bir şey için yedeklemek ve kullanmak için çok yavaştırlar. Bunun yerine, **yedekleme** için **anımsatıcı bir tohum içeren( mnemonic seed) endüstri standardı tabanlı** bir [HD cüzdan](https://www.investopedia.com/terms/h/hd-wallet-hierarchical-deterministic-wallet.asp) kullanın. 
(HD cüzdan yazısı uzun geldiyse kısacak sizin için😽---> Hiyerarşik deterministik (HD) cüzdan, Bitcoin ve Ethereum gibi kripto para birimleri sahipleri için dijital anahtarları depolamak için yaygın olarak kullanılan bir dijital cüzdandır. Hem genel(public) hem de parola benzeri özel(private) anahtarın bir kopyasına sahip olan herkes, hesaptaki bakiyeyi kontrol edebilir.Aşağıda daha detaylı açıklanacaktır⬇️)

-------------

## 2️⃣Deterministik -Tohumlu- Cüzdanlar (Deterministic (Seeded) Wallets) 🌱

Deterministik veya "tohumlu"🌱cüzdanlar, **tümü tek bir ana anahtardan veya tohumdan türetilen özel anahtarlar içeren cüzdanlardır.** _Tohum_,🟢 herhangi bir sayıda özel anahtar türetmek için bir _dizin numarası_ veya _"zincir kodu"-chain code_-(Genişletilmiş genel ve özel anahtarlar bölümünde açıklanacak⏬) gibi diğer verilerle **birleştirilen rastgele oluşturulmuş bir sayıdır.**

Deterministik bir cüzdanda, 🌱tohum; _türetilmiş tüm anahtarları kurtarmak için yeterlidir_ ve bu nedenle, oluşturma zamanında yapacağınız _tek bir yedekleme, cüzdandaki tüm fonları ve akıllı sözleşmeleri güvence altına almak için yeterlidir._ Tohum ayrıca, bir cüzdanın dışa veya içe aktarma işlemi için yeterlidir ve tüm anahtarların farklı cüzdan uygulamaları arasında kolayca taşınmasına olanak tanır. 💯

Bu tasarım, tüm cüzdana erişmek için yalnızca tohuma ihtiyaç duyulduğundan, **tohum güvenliğini son derece önemli hale getirir.** 🛡️ _Güvenlik her şeydir_  
Öte yandan, güvenlik çabalarını _tek bir veri parçasına(tohuma)_ odaklayabilmek bir beyaz şapkalı dostlarımız için bir avantaj olarak görülebilir.✔️

-------------

## 2️⃣🅰️ Hiyerarşik Deterministik Cüzdanlar(BIP-32/BIP-44) (Hierarchical Deterministic(HD) Wallets ) 👨‍👩‍👧‍👦

Deterministik cüzdanlar, tek bir tohumdan birçok anahtarın türetilmesini kolaylaştırmak için geliştirildiler. Şu anda, deterministik cüzdanın en gelişmiş şekli, _Bitcoin'in BIP-32 standardı_ tarafından tanımlanan **hiyerarşik deterministik (HD) cüzdandır**. HD cüzdanlar bir ağaç yapısında türetilmiş anahtarlar içerir, öyle ki bir _ana(parent) anahtar, her biri bir dizi çocuk(child) ve torun anahtarı türetebilen bir dizi **alt anahtar** türetebilir._ 🌴 

⬇️Bu ağaç yapısı, HD cüzdanda gösterilmektedir.----> tek bir tohumdan üretilen bir anahtar ağacı.

<img title="HD cüzdan:tek bir tohumdan üretilen bir anahtar ağacı" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/hd_wallet.png">

HD cüzdanlar, daha basit deterministik cüzdanlara göre birkaç önemli avantaj sunar. 1️⃣ İlk olarak, **ağaç yapısı, gelen ödemeleri almak için 🌲 _belirli bir alt anahtar dalı_ kullanıldığında ve giden ödemelerden kaynaklı değişikliklerin sonucundan 🌳 _farklı bir dal_ kullanıldığında olduğu gibi**, 
🏢Kurumsal mantıkta düşündüğümüzde;
Anahtar dalları, kurumsal ortamlarda----> departmanlara, yan kuruluşlara, belirli işlevlere veya muhasebe kategorilerine farklı dallar(anahtar demek istenmiş🔑) tahsis ederek de kullanılabilir.

HD cüzdanların 2️⃣ ikinci avantajı, kullanıcıların **ilgili özel anahtarlara erişmeden bir dizi public(açık) anahtar oluşturabilmeleridir.** Bu, HD cüzdanların güvenli olmayan bir sunucuda veya cüzdanın bakiyesindeki parayı harcayabilecek( _özel anahtarlara sahip olmadığı_ ) ve sadece izleme veya para alma görevlerinde kullanılmasına olanak tanır.

-------------

## Tohumlar ve Anımsatıcı Kodlar/kelimeler (Mnemonic Codes) (BIP-39) 🔠 
_Güvenli yedekleme_ 🛡️ ve _gönderim(alma) işlemleri_ 💸 için **özel anahtarı kodlamanın birçok yolu vardır**. Şu anda tercih edilen yöntem, doğru bir sırayla, özel anahtarı benzersiz bir şekilde yeniden oluşturabilen _bir dizi 📰 sözcük kullanmaktır_. Bu genellikle **anımsatıcı olarak bilinir** ve yaklaşım **BIP-39 tarafından standardize edilmiştir.** Bugün, birçok Ethereum cüzdanı (ve diğer kripto para birimleri için cüzdanlar) bu standardı kullanır ve birlikte çalışabilen anımsatıcıları kullanarak _yedekleme ve kurtarma için tohumları içe ve dışa_ aktarabilirler.

Bu yaklaşımın neden popüler💃 hale geldiğini görmek için bir örneğe bakalım ⬇️

Hex cinsinden yazılan deterministik cüzdanda, tohum şu şekildedir:

`FCCF1AB3329FD5DA3DA9577511F8F137`

deterministik bir cüzdanın tohumunun 12 kelimelik mnemonic kelimleri

```
wolf juice proud gown wool unfair
wall cliff insect more detail hub

```
Uygulamada, Hex cinsinden yazarken bir hata olasılığı aşırı derecede yüksektir. Buna karşılık, bilinen kelimelerin listesinin üstesinden gelmek oldukça kolaydır, çünkü esas olarak kelimelerin (özellikle İngilizce kelimelerin) _yazımında_ daha iyi düzeyde yarar vardır. Eğer **"wolğf"** 🐶 kelimesi kazara yazmış olsaydık, cüzdanı kurtarmaya ihtiyaç duyduğumuzda, _"wolğf_"in geçerli bir İngilizce kelime olmadığını🔴 ve bunun yerine **"wolf**"un 🐺 kullanılması gerektiği çabucak anlardık.

Bu yaptığımız tohumun bir temsilini yazmaktan ibarettir.(Yani mnemonic-anımsatıcıları- kelimeleri). Bu HD cüzdanlarını yönetirken iyi bir uygulamadır: veri kaybı durumunda (veri sızıntısı veya ransomware gibi) bir cüzdanı **kurtarmak için tohum gereklidir**, bu nedenle bir **yedekleme yapmak çok gereklidir**. Ancak, tohum son derece **gizli tutulmalıdır**, bu nedenle _dijital yedeklemelerden_ 🔴 dikkatli bir şekilde kaçınılmalıdır; bu nedenle, daha önceki tavsiyelerimizinden kağıta yazarak yedeklemek daha uygundur 🟢 📖 .

Özetle, bir HD cüzdan için tohumun şifrelenmesi için bir kurtarma kelime listesinin kullanılması, güvenli bir şekilde dışa aktarmanın, kopyalamanın, kağıda kaydetmenin,bir _özel anahtar setini_ başka bir cüzdana aktarmanın **en kolay yolunu sağlar**.📶

## Cüzdan En İyi Uygulamaları:

Kripto para cüzdan teknolojisi geliştikçe, cüzdanları geniş çapta birlikte çalışabilir, kullanımı kolay, güvenli ve esnek hale getiren belirli ortak endüstri standartları ortaya çıktı. 
Bu standartlar ayrıca cüzdanların, **tümü tek bir anımsatıcıdan birden çok farklı kripto para birimi için anahtar türetmesine olanak tanır.** 📖 

⬇️Bu ortak standartlar şunlardır:
 * BIP-39'a dayalı anımsatıcı kod sözcükleri

 * BIP-32'ye dayalı HD cüzdanlar

 * BIP-43'e dayalı çok amaçlı HD cüzdan yapısı

 * BIP-44'e dayalı çok para birimli ve çok hesaplı cüzdanlar

Bu standartlar gelecekteki gelişmelerle değişebilir(şuanlık değişmiş olabilir) veya eskimiş olabilir, ancak şimdilik çoğu blok zinciri platformu ve kripto para birimleri için **fiili cüzdan standardı haline gelen bir dizi birbirine bağlı bir teknoloji oluşturuyorlar.** ✒️

**Standartlar**, çok çeşitli yazılım ve donanım cüzdanları tarafından benimsenerek tüm bu cüzdanları birlikte çalışabilir hale getirdi. 
Bir kullanıcı, bu cüzdanlardan birinde oluşturulan bir **anımsatıcıyı dışa aktarabilir ve tüm anahtarları ve adresleri kurtararak başka bir cüzdana aktarabilir.**

Bu standartları destekleyen bazı**yazılım cüzdan** 💻 örnekleri arasında {**Jaxx, MetaMask, MyCrypto ve MyEtherWallet(MEW)**} bulunur. 

Bu standartları destekleyen **donanım cüzdanlarına** 💾 örnek olarak {**Keepkey, Ledger ve Trezor**} verilebilir.

Aşağıdaki bölümlerde bu teknolojilerin her biri ayrıntılı olarak incelenmektedir. ⬇️

🔍 İPUCU Bir Ethereum cüzdanı kullanıyorsanız, açıklandığı gibi _BIP-32, BIP-39, BIP-43 ve BIP-44 standartlarını_ izleyerek yedekleme için anımsatıcı kod olarak şifrelenmiş(kodlanmış) bir tohum ile bir HD cüzdan olarak oluşturulmalıdır. 🔍

## Anımsatıcı Kod Kelimeleri /Mnemonic Code Words  (BIP-39) 🔡#️⃣  

Anımsatıcı kod sözcükleri, **deterministik bir cüzdan türetmek için tohum olarak kullanılan rastgele bir sayıyı kodlayan sözcük dizileridir**. Sözcük dizisi, tohumu yeniden oluşturmak ve oradan, yani cüzdandan türetilmiş tüm anahtarları yeniden oluşturmak için yeterlidir. Anımsatıcı kelimelerle deterministik cüzdanlar uygulayan bir cüzdan uygulaması, _ilk cüzdan oluştururken kullanıcıya 12 ila 24 kelimelik bir dizi_ gösterecektir.Bu sözcük dizisi cüzdanın yedeğidir ve aynı veya herhangi bir uyumlu cüzdan uygulamasındaki tüm anahtarları kurtarmak ve yeniden oluşturmak için kullanılabilir. Daha önce açıkladığımız gibi, anımsatıcı kelime listeleri, kullanıcıların cüzdanlarını yedeklemelerini kolaylaştırır, çünkü bunların **okunması ve doğru şekilde kopyalanması kolaydır**.


📝NOT:Anımsatıcı kelimeler(Mnemonic words ) genellikle _"beyin cüzdanları"_ 🧠 ile karıştırılır. Bunlar aynı şeyler değildirler. Birincil fark, bir 🧠 beyin cüzdanının **kullanıcı tarafından seçilen kelimelerden oluşması**, 🔡anımsatıcı kelimelerin ise cüzdan tarafından **rastgele oluşturulup kullanıcıya sunulmasıdır**. Bu önemli fark, anımsatıcı sözcükleri çok daha güvenli hale getirir, çünkü insanlar _çok zayıf rastgelelik kaynaklarıdır_(bilgisayarlara kıyasla). Belki daha da önemlisi, "beyin cüzdanı" terimini kullanmak, **kelimelerin ezberlenmesi gerektiğini gösterir** ki bu korkunç bir fikirdir ve ihtiyaç duyduğunuzda yedeğinizin olmaması Türkiyede araba almak için 💸 500000 TL kredi çekip ömrünün sonuna kadar faizi ödemek için çalışmak gibibidir.🚙 📝  

Anımsatıcı kodlar _BIP-39'da_ tanımlanmıştır. BIP-39'un bir anımsatıcı kod standardının bir uygulaması olduğunu unutmayın. [_Electrum Bitcoin cüzdanı_](https://electrum.org/#home) tarafından kullanılan ve BIP-39'dan önce gelen, farklı bir kelime grubuyla farklı bir standartı vardı. BIP-39, trezor şirketinin desteğiyle Trezor donanım cüzdanıyla önerildi ve  bu cüzdan Electrum'un uygulamasıyla uyumlu değil. Bununla birlikte, _BIP-39 artık yüzlerce birlikte çalışabilen, uygulamada geniş endüstri desteği elde etmiştir ve **fiili endüstri standardı olarak kabul edilmelidir**. Ayrıca, _BIP-39, Ethereum'u destekleyen çok para birimli cüzdanlar üretmek için kullanılabilirken_, Electrum tohumları bunu yapamaz.

-------------------

BIP-39, ⬇️ burada dokuz adımda 9️⃣ açıkladığımız bir _anımsatıcı kod ve tohum_(Mnemonic code 🔡 & seed 🌱) oluşturulmasını tanımlar.Daha iyi bir açıklama yapabilmek için, süreç iki bölüme ayrılmıştır:(aşağıda görsel şekilde açıklanmıştır.) 

🅰️--1️⃣'den 6️⃣'ya kadar olan adımlar, _Anımsatıcı sözcükler oluşturma_ bölümünde gösterilir.

🅱️--7️⃣'den 9️⃣'a kadar olan adımlar, anımsatıcıdan ----> tohuma bölümünde gösterilir.

## Anımsatıcı kelimeler üretmek 🅰️

Anımsatıcı kelimeler, BIP-39'da tanımlanan standartlaştırılmış süreç kullanılarak cüzdan tarafından otomatik olarak oluşturulur. **Cüzdan bir entropi kaynağından başlar, bir sağlama toplamı ekler ve ardından entropiyi bir kelime listesine eşler**: 

1️⃣ 128 ile 256 bitlik kriptografik olarak rastgele bir S dizisi oluşturun.

2️⃣ S'nin SHA-256 karma değerinin ilk S uzunluğunu ÷ 32 bitini alarak bir S sağlama toplamı oluşturun.

3️⃣ Sağlama toplamını rastgele S dizisinin sonuna ekleyin.

4️⃣ Sıra ve sağlama toplamı birleştirmeyi 11 bitlik bölümlere ayırın.

5️⃣ Her 11 bitlik değeri önceden tanımlanmış 2048 kelimelik sözlükten bir kelimeye eşleyin.

6️⃣ Sırayı koruyarak, kelime dizisinden anımsatıcı kodu oluşturun.

Entropi oluşturmak ve anımsatıcı sözcükler olarak kodlamak, anımsatıcı sözcükleri oluşturmak için entropinin nasıl kullanıldığını gösterir.

⏬Aşağıda açıklanmıştır.

Tablo 1. Anımsatıcı kodlar: _Entropi ve kelime uzunluğu_ 📊

| Entropi(bit)| toplam sağlamı(bit) |entropi+toplam sağlamı |Anımsatıcı Kelimesi(sayı olarak) |
| ----------- | ----------- | ----------| --------|
|  128     |  4      | 132|12 |
| 160 | 5        |165 |15 |
|192|6|198|18|
|224|7|231|21|
|256|8|264|24|

🅰️'nın görseli ⬇️

<img title="Entropi oluşturma ve anımsatıcı sözcükler olarak kodlama" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/bip39-part1.png">


## Anımsatıcılardan Tohuma 🅱️

Anımsatıcı kelimeler, 128 ile 256 bit uzunluğundaki entropiyi temsil eder. 
Entropi daha sonra, _PBKDF2_ anahtar uzatma fonksiyonu kullanılarak daha uzun (512 bit) bir tohum elde etmek için kullanılır. 🌱 Üretilen tohum, deterministik bir cüzdan oluşturmak ve anahtarlarını elde etmek için kullanılır.

Anahtar uzatma fonksiyonu **iki parametre alır**-----> 1️⃣Mnemonic ve 2️⃣Salt.
Anahtar uzatma fonksiyonundaki bir **Salt'ın** amacı, _kaba kuvvet 👊 saldırısına olanak tanıyan bir arama tablosu oluşturmayı zorlaştırmaktır_. BIP-39 standardında Salt'ın başka bir amacı daha vardır: BIP-39'daki İsteğe bağlı parola bölümünde daha ayrıntılı olarak açıklayacağımız gibi, **tohumu koruyan ek bir güvenlik 🛡️faktörü görevi gören bir parolanın girilmesine olanak tanır.**

7'den 9'a kadar olan adımlarda açıklanan süreç, önceki bölümde açıklanan sürecin devamı niteliğindedir:

7️⃣ _PBKDF2 anahtar uzatma fonksiyonu_ ilk parametresi, 6. adımda üretilen anımsatıcıdır.

8️⃣ PBKDF2 anahtar uzatma işlevinin ikinci parametresi Salt'tır. Salt, kullanıcı tarafından sağlanan isteğe bağlı bir parola ile birleştirilmiş "anımsatıcı" dize sabitinden oluşur.

9️⃣ PBKDF2, HMAC-SHA512 algoritmasıyla 2048 tur hashing(karma) kullanarak anımsatıcı ve salt parametrelerini uzatır(genişletir) ve nihai çıktı olarak 512 bitlik bir değer üretir. **Bu 512 bitlik değer TOHUMDUR** 🌱.

Anımsatıcıdan tohuma, bir tohum oluşturmak için bir anımsatıcının nasıl kullanıldığını gösterir.⬇️

🅱️'nin görseli

<img title="BIP-39Seed" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/bip39-part2.png">

Anahtar uzatma işlevi, 2048 tur karma(hashing) ile, anımsatıcı veya parolaya karşı kaba kuvvet saldırılarına karşı bir şekilde etkili bir korumadır. Birkaç binden fazla parola ve anımsatıcı kombinasyonu denemeyi (hesaplamada) maliyetli hale getirirken, olası türetilmiş tohumların sayısı çok büyük (2^^512(^^ sembolü üstü şeklindedir) veya yaklaşık 10^^154) - görünür evrendeki atomların sayısından (yaklaşık olarak 10^^80) çok daha fazladır.)

tablo-2  📊

| Entropy input (128 bits)       |0c1e24e5917779d297e14d45f14e1a1a   | 
|--------------|-----------|
|Mnemonic (12 words) | army van defense carry jealous true garbage claim echo media make crunch     | 
| Seed (512 bits)    | 5b56c417303faa3fcba7e57400e120a0ca83ec5a4fc9ffba757fbe63fbd77a89a1a3be4c67196f57c39 a88b76373733891bfaba16ed27a813ceed498804c0570 |
|Passphrase |(none) |

tablo-3 📊

| Entropy input (128 bits)       |0c1e24e5917779d297e14d45f14e1a1a   | 
|--------------|-----------|
|Mnemonic (12 words) | army van defense carry jealous true garbage claim echo media make crunch     | 
| Seed (512 bits)    | 3b5df16df2157104cfdd22830162a5e170c0161653e3afe6c88defeefb0818c793dbb28ab3ab091897d0 715861dc8a18358f80b79d49acf64142ae57037d1d54 |
|Passphrase |SuperDuperSecret |

tablo-4 📊

| Entropy input (256 bits)       | 2041546864449caff939d32d574753fe684d3c947c3346713dd8423e74abcf8c  | 
|--------------|-----------|
|Mnemonic (24 words) | cake apple borrow silk endorse fitness top denial coil riot stay wolf luggage oxygen faint major edit measure invite love trap field dilemma oblige     | 
| Seed (512 bits)    | 3269bce2674acbd188d4f120072b13b088a0ecf87c6e4cae41657a0bb78f5315b33b3a04356e53d062e5 5f1e0deaa082df8d487381379df848a6ad7e98798404 |
|Passphrase |(none)|

-----------

## BIP-39'da İsteğe Bağlı Parola

BIP-39 standardı, tohumun türetilmesinde isteğe bağlı bir parola kullanılmasına izin verir. 
Parola kullanılmazsa, anımsatıcı, "mnemonic" sabit dizesinden oluşan bir Salt'la genişletilir ve herhangi bir anımsatıcıdan belirli bir 512 bitlik tohum üretilir. Bir parola kullanılırsa, germe işlevi aynı anımsatıcıdan farklı bir tohum üretir. 🌱 Aslında, tek bir anımsatıcı verildiğinde, olası her parola farklı bir tohuma yol açar. Esasen, **"yanlış" bir parola yoktur. Tüm parolalar geçerlidir ve hepsi farklı tohumlara yol açarak çok sayıda başlatılmamış cüzdan kümesi oluşturur.** Muhtemel cüzdanlar grubu o kadar büyüktür (2^^512) ki, parola yeterli karmaşıklığa ve uzunluğa sahip olduğu sürece, kullanımda olanı kaba zorlama veya rastgele tahmin etme olasılığı yoktur.

🔍İPUCU : BIP-39'da "yanlış" parola yoktur. Her parola, daha önce kullanılmadığı sürece boş olacak bir cüzdana yol açar.🔍

İsteğe bağlı parola iki önemli özellik oluşturur:

 + Bir anımsatıcıyı kendi başına işe yaramaz hale getiren ve anımsatıcı yedekleri bir hırsız(hacker) tarafından tehlikeye atılmaya karşı koruyan ikincil bir faktör(ezberlenmiş bir şeyi hırsız tahmin edemez).
 
 + makul bir reddedilebilirlik(Hacker veya hırsız açısından) 

Ancak, bir parola kullanmanın aynı zamanda bazı kayıplarıda beraberinde getirdiğine dikkat etmemiz gerekir:
 
 + Cüzdan sahibi komada veya ölmüşse ve başka kimse parolayı bilmiyorsa, tohum işe yaramaz ve cüzdanda depolanan tüm fonlar sonsuza kadar kaybolur. 💸
 
 +  Tersine, sahibi parolayı tohumla aynı yerde yedeklerse, ikinci bir faktörün amacını bozar.


Parolalar çok kullanışlı olsa da, varislerin hayatta kalanların kripto para birimini geri kazanabilme olasılığı göz önünde bulundurularak, yalnızca yedekleme ve kurtarma için dikkatlice planlanmış bir süreçle birlikte kullanılmalıdır.

## Anımsatıcı kodlarla çalışma(Working with mnemonic codes)

BIP-39, birçok farklı programlama dilinde bir kütüphane olarak uygulanmaktadır. Örneğin:

1️⃣ [python-mnemonic](https://github.com/trezor/python-mnemonic)

Python'da BIP-39'u öneren _SatoshiLabs_ ekibi tarafından standartın uygulaması

2️⃣[ConsenSys/eth-lightwallet](https://github.com/ConsenSys/eth-lightwallet)

 JS Ethereum cüzdanı (düğümler ve tarayıcılar için)

3️⃣[npm/bip39](https://www.npmjs.com/package/bip39)

Bitcoin BIP-39'un JavaScript uygulaması: Deterministik anahtarlar oluşturmak için anımsatıcı kod üretme paketi

Ayrıca, bağımsız bir web sayfasında (bağımsız bir web sayfası olarak bir BIP-39 oluşturucu) uygulanan bir **BIP-39 oluşturucu** da vardır ve bu, **test ve deneme için son derece kullanışlıdır**. [Anımsatıcı Kod Dönüştürücü(Mnemonic Code Converter)](https://iancoleman.io/bip39/)sayesinde _anımsatıcılar, tohumlar ve genişletilmiş özel anahtarlar_ üretir. Bir tarayıcıda _çevrimdışı olarak kullanılabilir veya çevrimiçi olarak erişilebilir._

<img title="BIP-39 generator" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/bip39_web.png">

---------------------

## Tohumdan bir HD Cüzdan Oluşturma 🌱+💰

HD cüzdanlar, 128-bit, 256-bit veya 512-bit sayı olan rastgele tek bir kök tohumdan oluşturulur. **En yaygın olarak, bu tohum, önceki bölümde de ayrıntılı olarak açıklandığı gibi bir anımsatıcıdan oluşturulur.**

HD cüzdandaki her anahtar deterministik olarak bu **kök tohumdan türetilir**, bu da tüm HD cüzdanın o tohumdan uyumlu herhangi bir HD cüzdanda yeniden oluşturulmasını mümkün kılar. Bu, yalnızca kök tohumun türetildiği anımsatıcıyı aktararak binlerce hatta milyonlarca anahtar içeren **HD cüzdanları dışa aktarmayı, yedeklemeyi, geri yüklemeyi ve içe aktarmayı kolaylaştırır.**

----------

## HD Cüzdanlar (BIP-32) ve Yollar(Paths) (BIP-43/44)

Çoğu HD cüzdan, deterministik anahtar üretimi için pratikte bir endüstri standardı haline gelen BIP-32 standardını takip eder.

Burada BIP-32'nin tüm ayrıntılarını tartışmayacağız, sadece cüzdanlarda nasıl kullanıldığını anlamak için gerekli bileşenleri tartışacağız. Temel önemli husus, HD cüzdanda görebileceğiniz gibi, türetilmiş anahtarların sahip olabileceği ağaç benzeri hiyerarşik ilişkilerdir: ⏫(Yukarıda bahsetmiştik.) 
Tek bir tohumdan üretilen bir anahtar ağacı.🎄🔑 
Aşağıdaki bölümlerde açıklanan **genişletilmiş anahtarlar(extended keys) ve zorlaştırılmış(sertleştirilmiş/Hardened) anahtarların** fikirlerini anlamak da önemlidir.

Birçok yazılım Kütüphanesinde 📚 sunulan düzinelerce birlikte çalışabilir BIP-32 uygulaması vardır. Bunlar çoğunlukla **adresleri farklı bir şekilde uygulayan, ancak [Ethereum'un BIP-32 uyumlu olan cüzdanlarla](https://github.com/ConsenSys/eth-lightwallet) aynı anahtar türetme uygulamasını paylaşan Bitcoin cüzdanları için tasarlanmıştır**. _Ethereum için tasarlanmış olanını kullanın_ veya  _bir Ethereum adresini🔵 yazılım kütüphanesine uygularak 🟡 Bitcoin'den uyarlayın_.

Ayrıca, BIP-32 ile test ve denemeler yapmak için çok kullanışlı olan bağımsız bir _web sayfası_ olarak uygulanan bir [BIP-32 oluşturucu](http://bip32.org) da bulunmaktadır.

⚠️UYARI--->Yukarıdaki site(BIP-32 oluşturucu) ⤴️ bir _HTTPS_ sitesi değildir. Bu, size bu aracın kullanımının güvenli olmadığını hatırlatmak içindir. Sadece test amaçlıdır. Bu sitenin ürettiği anahtarlarları gerçek parayla yapılacak işlemlerde kullanmayınız. ⚠️


## Genişletilmiş(Uzatılmış/Extended) genel ve özel anahtarlar

BIP-32 terminolojisinde anahtarlar _"genişletilebilir"_. Doğru matematiksel işlemlerle, bu genişletilmiş 👪 **"Ana(Parent)"** anahtarlar, **"alt(child)"** 👶 anahtarları türetmek için kullanılabilir, böylece daha önce açıklanan anahtarlar ve adresler hiyerarşisi oluşturulur._Ana anahtarın ağacın tepesinde olması gerekmez._ ağaç hiyerarşisinin 🎄 _herhangi bir yerinden seçilebilir_.Bir _anahtarın genişletilmesi, anahtarın kendisini almayı ve ona özel bir zincir kodu(chain code) eklemeyi içerir_.Bir **zincir kodu(chain code), alt anahtarları üretmek için her anahtarla karıştırılan 256-bitlik bir ikili(binary) sistemde üretilmiş Metindir.**

Anahtar,Özel(private) bir anahtarsa, **xprv** önekiyle ayırt edilen genişletilmiş bir özel anahtar olur:

`xprv9s21ZrQH143K2JF8RafpqtKiTbsbaxEeUaMnNHsm5o6wCW3z8ySyH4UxFVSfZ8n7ESu7fgir8i....`

Genişletilmiş bir Genel(public) anahtar, **xpub** öneki ile ayırt edilir:

`xpub661MyMwAqRbcEnKbXcCqD2GT1di5zQxVqoHPAgHNe8dv5JP8gWmDproS6kFHJnLZd23tWevhdn...`









