# Cüzdanlar(Wallets) 💰

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




