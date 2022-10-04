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

Deterministik cüzdanlar, telefonunuzun çalınması 😫📱 veya tuvalete düşmesi 🚽 gibi veri kaybı kazalarına karşı biraz daha güvenli hale getirmek üzere, tohumlar(seeds)  için genellikle _yazmanız ve kullanmanız_ için bir kelime listesi (İngilizce veya başka bir dilde de olabilir) olarak kodlanır. bir kaza durumunda bunu kullanırız.
Bunlar,cüzdanın **anımsatıcı kelimeleri(mnemonic words)** olarak bilinirler. 
 
 📝NOT-----> Genelde Nnemonic words(anımsatıcı kelimler) 12 veya 24 kelime arası değişiklik gösterirler.

Tabii ki, birisi 🧔 ,anımsatıcı kelimelerinizi(mnemonic words) ele geçirirse, **cüzdanınızı yeniden oluşturabilir ve böylece ether ve akıllı sözleşmelerinize erişim sağlayabilir.** Bu nedenle, _kurtarma kelime listenize(mnemonic words'den bahsediyor) çok ama çok dikkat edin_ ❗ **Asla elektronik olarak, bir dosyada, bilgisayarınızda veya telefonunuzda saklamayın**.🔴   
**Kağıda yazın 📕 ve güvenli bir yerde saklayın.✔️

Sonraki birkaç bölüm, bu teknolojilerin her birini ileri seviyede🥶 açıklamaktadır.( ⚠️Eğer zor gelirse moralinizi bozmayın.Kendinize zaman tanıyın.İstediğiniz zaman okuyun.Öfkenizi,üzüntünüzü,pişmanlığınızı ve birçok duyguyu okuyarak unutabilirsiniz) 

------------

## Deterministik Olmayan/Belirsiz(Rastgele) Cüzdanlar 1️⃣

İlk Ethereum cüzdanlarında (_Ethereum ön satışı için üretilmiştir_), her cüzdan dosyası rastgele oluşturulmuş **tek bir özel anahtar** depoladı. Bu tür cüzdanlar **deterministik cüzdanlarla değiştiriliyor** 🔄 çünkü bu _"eski tarz"_ cüzdanlar birçok yönden daha kalitesiz durumdalar. 
Örneğin, Ethereum kullanırken gizliliğinizi en üst düzeye çıkarmanın bir parçası olarak **Ethereum adresinin yeniden kullanılmasından kaçınmak, yani her para transferimizde yeni bir adres (yeni bir özel anahtar gerektiren yapı) kullanmak iyi bir uygulama olarak kabul edilir.** Daha fazlası,her _işlem_ için yeni bir adres kullanabilirsiniz, ancak **çok fazla token ile işlemler yaparsanız** bu **pahalı** olabilir. Uygulamada(pratikte) bu yapıyı takip ettiğimizde, **_deterministik olmayan bir cüzdanın anahtar listesini düzenli olarak artırması gerekecektir,bu da düzenli yedeklemeler 👜 yapmanız gerekeceği anlamına geliyor._** Cüzdanınızı yedeklemeyi gerçekleştirmeden verilerinizi kaybederseniz (disk arızası💾 ,içecek dökülmesi 🍻, telefonun çalınması 📱), _fonlarınıza ve akıllı sözleşmelerinize erişiminizi_ **kaybedersiniz.** 😵 

"Tip 0(type 0)0️⃣" deterministik olmayan cüzdanlar, **uğraşılması en zor olanlardır**, çünkü her yeni adres için _"tam zamanlı"_ yeni bir cüzdan dosyası oluştururlar.









