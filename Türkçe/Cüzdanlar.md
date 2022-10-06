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
        "kdfparams": {    //aşşağıda belirttiği gibi .n aşşağıdaki tur(round) sayısını gösteriyor
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

⬇️ aşağıdaki görseli size yarrdımcı olsun diye bırakıyorum.

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

## Tohumlar ve Anımsatıcı Kodlar/kelimeler (Mnemonic Codes) (BIP-39)  
_Güvenli yedekleme_ 🛡️ ve _gönderim(alma) işlemleri_ 💸 için **özel anahtarı kodlamanın birçok yolu vardır**. Şu anda tercih edilen yöntem, doğru bir sırayla, özel anahtarı benzersiz bir şekilde yeniden oluşturabilen _bir dizi 📰 sözcük kullanmaktır_. Bu genellikle **anımsatıcı olarak bilinir** ve yaklaşım **BIP-39 tarafından standardize edilmiştir.** Bugün, birçok Ethereum cüzdanı (ve diğer kripto para birimleri için cüzdanlar) bu standardı kullanır ve birlikte çalışabilen anımsatıcıları kullanarak _yedekleme ve kurtarma için tohumları içe ve dışa_ aktarabilirler.

Bu yaklaşımın neden popüler💃 hale geldiğini görmek için bir örneğe bakalım ⬇️

Hex cinsinden yazılan deterministik cüzdanda, tohum şu şekildedir:

`FCCF1AB3329FD5DA3DA9577511F8F137`

deterministik bir cüzdanın tohumunun 12 kelimelik mnemonic kelimleri

```
wolf juice proud gown wool unfair
wall cliff insect more detail hub

```
Uygulamada, Hex cinsinden yazarken bir hata olasılığı aşırı derecede yüksektir. Buna karşılık, bilinen kelimelerin listesinin üstesinden gelmek oldukça kolaydır, çünkü esas olarak kelimelerin (özellikle İngilizce kelimelerin) _yazımında_ daha iyi düzeyde yarar vardır. Eğer **"wolğf"** 🐶 kelimesi kazara kaydedilmiş olsaydı, cüzdan kurtarmaya ihtiyaç duyduğumuzda, _"wolğf_"in geçerli bir İngilizce kelime olmadığını🔴 ve bunun yerine **"wolf**"un 🐺 kullanılması gerektiği çabucak anlardık.

























