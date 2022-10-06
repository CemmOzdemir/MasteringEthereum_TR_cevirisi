# ETHEREUM TEMELLERİ 🏗️

Bu bölümde Ethereum'u keşfetmeye başlayacağız, cüzdanların nasıl kullanılacağını, işlemlerin nasıl oluşturulduğunu ve ayrıca temel bir akıllı sözleşmenin nasıl yürütüleceğini öğreneceğiz.

## Ether Para Birimleri

Ethereum'un para birimine **ether** denir ve "ETH" olarak veya Ξ sembolleriyle (ikonlaştırılmış bir büyük harfe (E'ye benzeyen Yunanca) "Xi" harfinden) veya daha az sıklıkla ♦: örneğin, 1 ether veya 1 ETH , veya Ξ1, veya ♦1 gösterilir.

🔍 Ξ için U+039E ve ♦ için U+2666 Unicode karakterini kullanın.

Ether, wei olarak adlandırılan ve  en küçük birime kadar daha küçük birimlere bölünebilir. Bir ether, 1 kentilyon wei'dir 
("10^^18 veya 1.000.000.000.000.000.000). İnsanların **"Ethereum a " para birimi olarak atıfta bulunduğunu da duyabilirsiniz, 
ancak bu yeni başlayanların(acemilerin) yaygın bir hatasıdır. Ethereum _sistemdir_, ether para birimidir.**

Ether değeri her zaman dahili olarak, Ethereum'da wei cinsinden işaretsiz bir tamsayı değeri olarak temsil edilir. 1 ether işlemi yaptığınızda, işlem değer olarak 10000000000000000000(18 adet 0) wei kodlar.

Ether'in çeşitli isimleri, hem Uluslararası Birimler Sistemini (SI) kullanan bilimsel bir isme hem de birçok büyük bilgi işlem ve kriptografi düşüncesine saygı gösteren günlük konuşma diline ait bir isme sahiptir.

Ether isimleri ve birim adları, çeşitli birimleri, onların konuşma dilindeki (ortak) adlarını ve SI adlarını gösterir. Değerin dahili temsiline uygun olarak, tablo, 7. satırda 10^^18(10 üstü 18) wei olarak gösterilen etherle birlikte, wei'deki (birinci sıra) tüm isimlerini gösterir.


| DEĞERİ(wei cinsinden)| KAÇ KATI     | KULLANIM ADI | BİRİM ADI(IS NAME) |
|--------------|-----------|------------|-----------|
| 1 | 1 | wei | Wei
| 1,000 | 10^^3 | Babbage | Kilowei or femtoether
| 1,000,000 | 10^^6 | Lovelace | Megawei or picoether
| 1,000,000,000 | 10^^9 | Shannon | Gigawei or nanoether
| 1,000,000,000,000 | 10^^12 | Szabo | Microether or micro
| 1,000,000,000,000,000 | 10^^15 | Finney | Milliether or milli
| ⭐ _1,000,000,000,000,000,000_ | _10^^18_ | _Ether_ | _Ether_
| 1,000,000,000,000,000,000,000 | 10^^21 | Grand | Kiloether
| 1,000,000,000,000,000,000,000,000 | 10^^24 | | Megaether

## Ethereum Cüzdanı Seçmek 💰

"Cüzdan" terimi, hepsi birbiriyle ilişkili olmasına ve günlük bazda hemen hemen aynı anlama gelmesine rağmen birçok farklı şekilde bize yansıtıldı. 
"Cüzdan" terimini, **Ethereum hesabınızı yönetmenize yardımcı olan bir yazılım uygulaması** anlamında kullanacağız. Kısacası, bir Ethereum cüzdanı, Ethereum sistemine açılan kapınızdır. Anahtarlarınızı tutar ve sizin adınıza işlemler oluşturabilir ve yayınlayabilir. Bir Ethereum cüzdanı seçmek zor olabilir çünkü farklı özelliklere ve tasarımlara sahip birçok farklı seçenek vardır. Bazıları yeni başlayanlar için, bazıları ise uzmanlar için daha uygundur. Ethereum platformunun kendisi hala geliştirilmektedir ve "en iyi" cüzdanlar genellikle platform yükseltmeleriyle birlikte gelen değişikliklere uyum sağlayanlardır.

Endişelenecek bir şey yok! Bir cüzdan seçerseniz ve işleyişini beğenmezseniz veya ilk başta beğenirseniz ancak daha sonra başka bir şey denemek isterseniz; cüzdanları kolayca değiştirebilirsiniz. Tek yapmanız gereken,**paranızı eski cüzdandan yeni cüzdana gönderen bir işlem yapmak veya özel anahtarlarınızı dışa aktarıp yenisine aktarmak.**


Kitap boyunca örnek olarak kullanmak üzere birkaç farklı cüzdan türü seçtik. Bazıları mobil, bazıları masaüstü içindir ve diğerleri web tabanlıdır. Çok çeşitli karmaşıklık ve özellikleri temsil ettikleri için farklı cüzdanlar seçtik. Ancak, bu cüzdanların seçimi, kalitelerinin veya güvenliklerinin onaylandığı 🔴 anlamına gelmez. Gösterimler ve testler için iyi bir başlangıç noktasıdırlar.


Bir cüzdan uygulamasının çalışması için **özel anahtarlarınıza(private key 🔐)** erişimi olması gerektiğini unutmayın, bu nedenle yalnızca güvendiğiniz kaynaklardan cüzdan uygulamalarını indirip kullanmanız çok önemlidir. Neyse ki, genel olarak, bir cüzdan uygulaması ne kadar popülerse, o kadar güvenilir olur. Yine de, "_tüm yumurtalarınızı bir sepete koymaktan" 🧺 kaçınmak_ ve Ethereum hesaplarınızı birkaç cüzdana dağıtmak daha iyi bir uygulamadır. 🟢

Aşağıdakilerden bazıları başlangıç için uygun cüzdanlardır: ⤵️

## Metamask 🦊

MetaMask, tarayıcınızda (Chrome, Firefox, Opera veya Brave Browser) çalışan bir *tarayıcı uzantısı cüzdanıdır.* Çeşitli Ethereum düğümlerine bağlanabildiği ve blok zincirlerini test edebildiği için kullanımı kolay ve test için uygundur. MetaMask, hem iOS hem de Android store'dan erişip mobilde de kullanbileceğiniz bir cüzdandır.

## Jaxx

Jaxx, Android, iOS, Windows, macOS ve Linux dahil olmak üzere çeşitli işletim sistemlerinde çalışan çok platformlu ve çok para birimli bir cüzdandır. Basitlik ve kullanım kolaylığı için tasarlandığı için genellikle yeni kullanıcılar için iyi bir seçimdir. Jaxx, nereye kurduğunuza bağlı olarak mobil veya masaüstü cüzdandır.

## MyEtherWallet (MEW) 

MyEtherWallet, öncelikle herhangi bir tarayıcıda çalışan web tabanlı bir cüzdandır. Ayrıca Android ve iOS'ta da mevcuttur. Örneğimizin çoğunda inceleyeceğimiz çok sayıda karmaşık özelliğe sahiptir.


## Emerald Wallet 🔷

Emerald Wallet, Ethereum Classic blok zinciriyle çalışmak üzere tasarlanmıştır, 
ancak diğer Ethereum tabanlı blok zincirleriyle uyumludur. Açık kaynaklı bir masaüstü uygulamasıdır ve Windows, macOS ve Linux altında çalışır. Emerald, _"light" modda çalışarak tam bir düğüm çalıştırabilir veya genel bir uzak düğüme bağlanabilir._ Ayrıca tüm işlemleri komut satırından yapmak için bir yardımcı araca sahiptir.

MetaMask'i bir browser'a(tarayıcı) kurarak başlayacağız, ancak önce anahtarları kontrol etmeyi ve yönetmeyi kısaca anlamalıyız.🧐

## Kontrol ve Sorumluluk 🛡️
Ethereum gibi açık blok zincirler, merkezi olmayan bir sistem olarak çalıştıkları için önemlidir. Bu çok şey ifade ediyor, ancak önemli bir yönü,_her Ethereum kullanıcısının, fonlara ve akıllı sözleşmelere erişimi kontrol eden şeyler olan -----> kendi özel anahtarlarını 🔑 kontrol edebilmesi gerektiğidir._ Bazen fonlara erişim ve akıllı sözleşmelerin aralarındaki etkileşim ile işlem yapmamızı(yapmasını) sağlayan şeylere "hesap(account)" veya "cüzdan(wallet)" diyoruz. Bu terimler kullanımlarında oldukça karmaşık hale gelebilir, bu yüzden buna daha sonra daha ayrıntılı olarak gireceğiz. Ancak **temel bir ilke olarak, bir özel anahtarın bir "hesaba" eşit olması kadar kolaydır.** Bazı kullanıcılar, **çevrimiçi değişim gibi üçüncü taraf bir emanetçi**( ⚠️ Örneğin: Siz merkezi bir borsa uygulaması olan Binance'in cüzdanında kripto paranızı tutarsanız, özel anahtarınızı 3.kişi olan binance şirketine de açmış olursunuz.) kullanarak özel anahtarları üzerindeki kontrolden vazgeçmeyi tercih eder. Bu kitapta size kendi özel anahtarlarınızı nasıl kontrol edeceğinizi ve yöneteceğinizi öğreteceğiz.

Kontrol ile birlikte büyük bir sorumluluk gelir. Özel anahtarlarınızı kaybederseniz, fonlarınıza ve sözleşmelerinize erişiminizi kaybedersiniz. Hiç kimse erişimi yeniden kazanmanıza yardımcı olamaz - paranız sonsuza kadar kilitlenir. 🔚 💸
Bu sorumluluğu yönetmenize yardımcı olacak birkaç ipucu:

  * Güvenlikte doğaçlama yapmayın. Denenmiş ve test edilmiş standart yaklaşımları kullanın.
  * En yüksek güvenlik, air-gap olan bir cihazdan elde edilir, ancak bu seviye her hesap için gerekli değildir.( 📝NOT Air-gap neymiş ya okuyamammm zamanım yok benim derseniz😸 Kısaca [Air Gap](https://en.wikipedia.org/wiki/Air_gap_(networking)): ▶️ güvenli bir bilgisayar ağının genel İnternet veya güvenli olmayan yerel ağlar gibi güvenli olmayan ağlardan fiziksel olarak izole edilmesini sağlamak için bir veya daha fazla bilgisayarda kullanılan bir ağ güvenlik önlemidir.
  * Özel anahtarınızı asla düz biçimde, özellikle dijital olarak saklamayın. Neyse ki, günümüzde çoğu kullanıcı arayüzü, saf halde özel anahtarı görmenize bile izin vermiyor.
  * Özel anahtarlar, dijital bir **"anahtar deposu(keystore)"** dosyası olarak şifrelenmiş bir biçimde saklanabilir. Şifreli olduklarından, kilidini açmak için bir şifreye ihtiyaçları vardır. Bir parola seçmeniz istendiğinde, parolayı güçlü yapın (yani uzun ve rastgele), yedekleyin ve paylaşmayın. _Parola yöneticiniz_ yoksa, bir yere not edin ve güvenli ve gizli bir yerde saklayın. 📝 _Hesabınıza erişmek için hem keystore'lara hem de parolaya ihtiyacınız vardır._
  * Dijital belgelerde, dijital fotoğraflarda, ekran görüntülerinde, çevrimiçi sürücülerde, şifreli PDF'lerde vb. herhangi bir parola saklamayın. Yine, güvenliği doğaçlama(kafanıza göre) yapmayın. **Bir parola yöneticisi veya kalem ve kağıt** kullanın.
  * Bir anahtarı, *anımsatıcı kelime(mnemonic word) dizisi* olarak yedeklemeniz istendiğinde, fiziksel bir yedekleme yapmak için *kalem ve kağıt kullanın.* Bu görevi ⚠️ "sonraya" bırakmayın;  unutacaksınız . Bu yedekler, sisteminizde kayıtlı tüm verileri kaybetmeniz veya parolanızı unutmanız veya kaybetmeniz durumunda özel anahtarınızı**yeniden oluşturmak** için kullanılabilir. Ancak, 🔫 saldırganlar tarafından özel anahtarlarınızı almak için de kullanılabilirler, bu nedenle onları asla _dijital olarak saklamayın_ ve fiziksel kopyayı kilitli bir *çekmecede veya kasada* güvenli bir şekilde saklayın.
  * Büyük meblağları (özellikle yeni adreslere) aktarmadan önce, önce küçük bir test işlemi yapın (örneğin, 1$'dan az değer) ve işlemi onaylanmasını bekleyin.
  * Yeni bir hesap oluşturduğunuzda, yeni adrese sadece küçük bir test işlemi göndererek başlayın. Test işlemini aldıktan sonra, o hesaptan tekrar göndermeyi deneyin. Hesap oluşturmanın yanlış gitmesinin birçok nedeni vardır ve yanlış gittiyse, küçük bir kayıpla bulmak daha iyidir. Testler işe yararsa, her şey yolunda demektir.
  * Genel(Public) blok explorer(Etherscan gibi uygulamalardan bahsediyor), bir işlemin ağ tarafından kabul edilip edilmediğini bağımsız olarak görmenin kolay bir yoludur. Ancak bu kolaylık gizliliğiniz üzerinde olumsuz bir etkiye sahiptir, çünkü sizi takip edebilecek kişiler için adreslerinizi açıklarsınız.( 📝NOT :ileri ki zamanlarda Zero Knowladge ZK gibi teknolojilerin artmasıyla,bazı şeyler değişecektir.0️⃣)
  * Bu kitapta gösterilen adreslerden herhangi birine para göndermeyin. Özel anahtarlar kitapta listelenir ve birileri o parayı hemen alır.
  
Anahtar yönetimi ve güvenlik için bazı temel en iyi uygulamaları ele aldığımıza göre, şimdi MetaMask kullanarak çalışmaya başlayalım! 🦊


## Metamask Ekleme(yükleme) ile başlayalım

Google Chrome tarayıcısını açın ve https://chrome.google.com/webstore/category/extensions adresine gidin.

"MetaMask" arayın ve bir tilki logosuna tıklayın.

<img title="metamask" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_download.png">

MetaMask Chrome uzantısının ayrıntı sayfası
Gerçek MetaMask uzantısını indirdiğinizi doğrulamak önemlidir, çünkü bazen insanlar kötü amaçlı uzantıları Google'ın filtrelerinden geçirebilir. Gerçek olanı:

* Adres çubuğunda nkbihfbeogaeaoehlefnkodbefgpgknn kimliğini gösterir

* https://metamask.io tarafından sunulmaktadır

* 1.500'den fazla incelemesi var

* +2.000.000'den fazla kullanıcısı var

* Doğru uzantıya baktığınızı onayladıktan sonra, yüklemek için **"Chrome'a Ekle"** yi tıklayın.

## Cüzdan Oluşturma
MetaMask yüklendikten sonra, tarayıcınızın araç çubuğunda yeni bir simge (tilki başı) görmelisiniz. 
Başlamak için üzerine tıklayın. Şartlar ve koşulları kabul etmeniz ve ardından bir şifre girerek yeni Ethereum cüzdanınızı oluşturmanız istenecektir.

<img title="MmaskAnaEkran" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_password.png">

🔍 Parola MetaMask'e erişimi kontrol eder, böylece tarayıcınıza erişimi olan herkes tarafından kullanılamaz.

Bir parola belirledikten sonra, MetaMask sizin için bir cüzdan oluşturacak ve size 12 İngilizce kelimeden oluşan bir anımsatıcı(mnemonic) gösterecektir. Bu kelimeler, MetaMask'a veya bilgisayarınıza bir şey olursa, fonlarınıza erişimi kurtarmak için herhangi bir uyumlu cüzdanda kullanılabilir.**Bu kurtarma işlemi için parolaya ihtiyacınız yoktur; 12 kelime yeterlidir.**

🔍 Anımsatıcınızı (12 kelime) kağıda iki kez yedekleyin. İki kağıta yazın ve yedeği yangına dayanıklı kasa, kilitli çekmece veya kasa gibi iki ayrı güvenli yerde saklayın. Kağıt yedeklere, Ethereum cüzdanınızda sakladığınız değere eşdeğer nakit (cash para) gibi davranın.**Bu kelimelere erişimi olan herkes erişim kazanabilir ve paranızı çalabilir.**

<img title="mnemonic" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_mnemonic.png">

Anımsatıcıyı(kısaca 12 veya 24 kelime işte yaa😃) güvenli bir şekilde sakladığınızı onayladığınızda, MetaMask'taki Ethereum hesabınızda gösterildiği gibi Ethereum hesabınızın ayrıntılarını görebileceksiniz.

<img title="account" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_account.png">

Hesap sayfanız hesabınızın adını (varsayılan olarak "Hesap 1"), bir Ethereum adresini (örnekte 0x9E713...) ve bu hesabı diğer hesaplardan görsel olarak ayırt etmenize yardımcı olacak renkli bir simgeyi gösterir. 
Hesap sayfasının üst kısmında, şu anda hangi Ethereum ağı üzerinde çalıştığınızı görebilirsiniz *(örnekte "Ana Ağ(main net)").*

Tebrikler! İlk Ethereum cüzdanınızı kurdunuz. 🎆🍾



## Ağları Değiştirme 🔵----------------> 🟢
MetaMask hesap sayfasında görebileceğiniz gibi, 
birden fazla Ethereum ağı arasından seçim yapabilirsiniz. 
*Varsayılan olarak, MetaMask ana ağa(main net) bağlanmaya çalışacaktır.* Diğer seçenekler, _genel test ağları, seçtiğiniz herhangi bir Ethereum düğümü_ veya kendi bilgisayarınızda (localhost) özel blok zincirleri çalıştıran düğümlerdir: ( ⚠️**Merge sonrası bazı test ağları kapanacak.Rinkeby gibi**)


## Ana Ethereum Ağı
Halka açık ana Ethereum blok zinciri. Gerçek ETH, gerçek değer ve gerçek sonuçlar verir.

## Ropsten Test Ağı
Ethereum genel test blok zinciri ve ağı. Bu ağdaki ETH'nin değeri yok.

## Kovan Test Ağı
Ethereum, Aura konsensüs protokolünü kullanarak, yetki belgesi (federe imzalama) ile blok zincirini ve ağı herkese açık şekilde test eder. Bu ağdaki ETH'nin değeri yok. Kovan test ağı yalnızca Parity tarafından desteklenir. Diğer Ethereum istemcileri, yetkiye dayalı doğrulamanın kanıtı için daha sonra önerilen Clique fikir birliği protokolünü kullanır.

## Rinkeby Test Ağı
Ethereum, yetki kanıtı (federe imzalama) ile Clique konsensüs protokolünü kullanarak blok zincirini ve ağını herkese açık test eder. Bu ağdaki ETH'nin değeri yok.

## Yerel bilgisayar ağı ----> 8545
Tarayıcıyla aynı bilgisayarda çalışan bir düğüme bağlanır. Düğüm, herhangi bir genel blok zincirinin (ana veya test ağı) veya özel bir test ağının parçası olabilir.

## Özel RPC
MetaMask'i Geth uyumlu bir Uzaktan işleme Çağrısı (RPC) arabirimiyle herhangi bir düğüme bağlamanıza olanak tanır. Düğüm, herhangi bir genel veya özel blok zincirinin parçası olabilir.

🔍  MetaMask cüzdanınız, bağlandığı *tüm ağlarda aynı özel anahtarı ve Ethereum adresini kullanır.* Ancak, her Ethereum ağındaki Ethereum adres bakiyeniz, farklı olacaktır. Anahtarlarınız, örneğin Ropsten'deki etheri ve sözleşmeleri kontrol edebilir, ancak ana ağdakileri değil. 


## Test için Ether Alma (Facucet 🚰)

İlk göreviniz olarak cüzdanınıza Ether göndermeniz gerekir. **Bunu ana ağda yapmayacaksınız çünkü gerçek ether paraya mal olur ve onu kullanmak biraz daha fazla deneyim gerektirir. Şimdilik, cüzdanınıza bir miktar testnet ether yükleyeceksiniz.**


MetaMask'i Ropsten Test Network'e geçirin. Para Yatırma'ya ve ardından Ropsten Test Musluğu'na(_Faucet -----> size bedava testnet etheri verecek olan yapıya faucet diyoruz._) tıklayın. MetaMask, aşağıda gösterildiği gibi yeni bir web sayfası açacaktır.

<img title="fortestnet" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_ropsten_faucet.png">

📝 Ek olarak [Chainlink Faucetinide](https://faucets.chain.link) kullanabilirsiniz. ◀️

Web sayfasının MetaMask cüzdanınızın Ethereum adresini zaten içerdiğini fark edebilirsiniz. MetaMask, Ethereum özellikli web sayfalarını MetaMask cüzdanınızla bütünleştirir ve web sayfasındaki Ethereum adreslerini "görebilir", örneğin, bir Ethereum adresini gösteren bir çevrimiçi mağazaya ödeme göndermenize olanak tanır. MetaMask ayrıca, web sayfası isterse, alıcı adresi olarak kendi cüzdanınızın adresiyle web sayfasını doldurabilir. Bu sayfada, musluk uygulaması MetaMask'tan test etheri göndermek için bir cüzdan adresi istiyor.

Yeşil butona 🟢 yani "musluktan 1 ether iste"  tıklayın. Sayfanın alt kısmında bir işlem kimliğinin göründüğünü göreceksiniz. Musluk uygulaması bir işlem yarattı. İşlem kimliği şöyle görünür:

| 0x7c7ad5aaea6474adccf6f5c5d6abed11b70a350fbc6f9590109e099568090c57 |

Birkaç saniye içinde, yeni işlem Ropsten madencileri tarafından çıkarılacak ve MetaMask cüzdanınız 1 ETH bakiyesi gösterecektir. İşlem kimliğine tıklayın ve tarayıcınız sizi blokları, adresleri ve işlemleri görselleştirmenize ve keşfetmenize izin veren bir **web sitesi olan bir ▶️ [blok explorer](https://etherscan.io/)götürecektir**. MetaMask, daha popüler Ethereum blok kaşiflerinden biri olan Etherscan blok gezginini kullanır. Ropsten Test Musluğundan yapılan ödemeyi içeren işlem Etherscan Ropsten blok gezgininde gösterilir.

<img title="Blok_Explorer" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/ropsten_block_explorer.png">

İşlem, Ropsten blok zincirine kaydedilmiştir ve herhangi bir zamanda, sadece işlem kimliğini arayarak veya bağlantıyı ziyaret ederek herhangi biri tarafından görüntülenebilir.

## MetaMaskten Ether Gönderme 

Ropsten Test faucetinden ilk test etherinizi aldıktan sonra, musluğa(faucet) azıcıkta olsa geri göndermeye çalışarak ether göndermeyi deneyebilirsiniz. Ropsten Test musluğunun sayfasında da görebileceğiniz gibi, musluğa 1 ETH bağışlama seçeneği var. Bu seçenek, testi tamamladığınızda test etherinizin geri kalanını başka birinin kullanabilmesi için geri gönderebilmeniz için mevcuttur. Test etherinin hiçbir değeri olmamasına rağmen, bazı insanlar onu biriktirir ve diğer herkesin test ağlarını kullanmasını zorlaştırır.😠

Neyse ki, biz test ether stokçuları 📛 değiliz. MetaMask'e musluğa 1 ether ödeyen bir işlem oluşturmasını söylemek için turuncu 🟠 "1 ether" düğmesini tıklayın. MetaMask, bir işlem hazırlayacak ve musluğa 1 ether gönderme bölümünde gösterildiği gibi, onay içeren bir sekme açacaktır.

<img title="sendEther" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/send_to_faucet.png">

Hay aksiii! Muhtemelen işlemi tamamlayamayacağınızı fark etmişsinizdir--->MetaMask, bakiyenizin yetersiz olduğunu söylüyor. 💸 İlk bakışta bu kafa karıştırıcı görünebilir: 1 ETH'niz var, 1 ETH göndermek istiyorsunuz, peki MetaMask neden **yeterli paranız olmadığını söylüyor?**
⬇️

Cevap, gazın ⛽ maliyetinden kaynaklanmaktadır. Her Ethereum işlemi, **işlemi doğrulamak için madenciler tarafından toplanan bir ücretin ödenmesini gerektirir.** Ethereum'daki ücretler, gaz adı verilen sanal bir para biriminde tahsil edilir. _İşlemin bir parçası olarak gaz için ether ile ödeme yaparsınız._

📝NOT:
Test ağlarında da _ücret talep edilmektedir._ Ücretler olmadan, bir test ağı ,ana ağdan farklı davranır ve bu da onu yetersiz bir test platformu haline getirir. **Ücretler, aynı zamanda, ana ağı korudukları gibi, test ağlarını DoS saldırılarından ve kötü yapılandırılmış sözleşmelerden (örneğin, sonsuz döngüler) korur.**🚓

İşlemi gönderdiğinizde MetaMask, son başarılı işlemlerin ortalama gas fiyatını gigawei anlamına gelen 3 gwei olarak hesapladı. Wei, Ether Para Birimi Birimlerinde tartıştığımız gibi, ether para biriminin en küçük alt bölümüdür. Gaz limiti, 21.000 gaz birimi olan temel bir işlem gönderme maliyetine göre belirlenir. Bu nedenle harcayacağınız maksimum ETH miktarı 3 X 21.000 gwei = 63.000 gwei = 0.000063 ETH'dir. **(Ağırlıklı olarak madenciler tarafından belirlendiği için ortalama gaz fiyatlarının değişebileceğini unutmayın.** Gerekirse işleminizin öncelikli olmasını sağlamak için gaz limitinizi nasıl artırabileceğinizi/azaltabileceğinizi daha sonraki bir bölümde göreceğiz.) ⚠️(_Değerli dostlarım unutmayın ki PoW -----> PoS geçişle birlikte bazı şeyler değişebilir ancak felsefesini tam anlamak için pow anlamaya ihtiyacımız var ve unutmamak gerekir ki PoW'u tamamen terk etmiyoruz_)

Tüm bunları söylemek gerekirse: 1 ETH işlemi yapmak 1.000063 ETH'ye mal olur. MetaMask, toplamı gösterirken kafa karıştırıcı bir şekilde 1 ETH'ye yuvarlar, ancak ihtiyacınız olan gerçek miktar 1.000063 ETH'dir ve yalnızca 1 ETH'niz vardır. Bu işlemi iptal etmek için Reddet'e tıklayın.

Hadi biraz daha test etheri alalım! Yeşil "musluktan 1 eter iste" düğmesine tekrar tıklayın ve birkaç saniye bekleyin. Endişelenmeyin, muslukta bol miktarda eter olmalı ve isterseniz size daha fazlasını verecektir.

2 ETH bakiyeniz olduğunda tekrar deneyebilirsiniz. Bu sefer turuncu renkli "1 eter" bağış butonuna tıkladığınızda işlemi tamamlamak için yeterli bakiyeniz oluyor. MetaMask ödeme penceresi açıldığında Gönder'e tıklayın. Tüm bunlardan sonra gazda 0,000063 ETH ile musluğa 1 ETH gönderdiğiniz için 0.999937 ETH bakiyesi görmelisiniz.

## Bir Adresin İşlem Geçmişini bulma 📕

Şimdiye kadar, test eteri göndermek ve almak için MetaMask kullanma konusunda uzmanlaştınız. Cüzdanınız en az iki ödeme almış ve en az birini göndermiş durumda. Tüm bu işlemleri _ropsten.etherscan.io blok gezgini_ kullanarak görüntüleyebilirsiniz. Cüzdan adresinizi kopyalayıp blok gezgininin arama kutusuna yapıştırabilir veya MetaMask'in sayfayı sizin için açmasını sağlayabilirsiniz. MetaMask'teki **hesap simgenizin yanında üç noktayı gösteren bir düğme göreceksiniz.** Hesapla ilgili seçeneklerin bir menüsünü göstermek için üzerine tıklayın.

<img title="metamask_in_History" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_account_context_menu.png">

Etherscan'da İşlem geçmişi Adresinde gösterildiği gibi, hesabınızın işlem geçmişini gösteren blok gezgininde bir web sayfası açmak için "Etherscan'da hesabı görüntüle"yi seçin.

<img title="etherscan_History" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/block_explorer_account_history.png">

Burada Ethereum adresinizin tüm işlem geçmişini görebilirsiniz. Adresinizin gönderici veya alıcı olduğu Ropsten blok zincirinde kaydedilen tüm işlemleri gösterir. Daha fazla ayrıntı görmek için bu işlemlerden birkaçına tıklayın.

Herhangi bir adresin işlem geçmişini keşfedebilirsiniz. Ropsten Test musluğu adresinin işlem geçmişine bir göz atın. 
(ek olarak: adresinize yapılan en eski ödemede listelenen "gönderen" adresidir). Musluktan size ve diğer adreslere gönderilen tüm test etherlerini görebilirsiniz. Gördüğünüz her işlem sizi daha fazla adrese ve daha fazla işleme götürebilir. Çok geçmeden birbirine bağlı verilerin labirentinde kaybolacaksınız.💥

------------------------
## Dünya Bilgisayarına 🎛️ (Ethereum) Giriş 🔷 💙
------------------------

Artık bir cüzdan oluşturdunuz ve ether gönderip aldınız. Şimdiye kadar, Ethereum'u bir kripto para birimi olarak ele aldık. Ancak Ethereum çok,çok daha fazlası.🤗 Aslında, kripto para birimi durumu, Ethereum'un merkezi olmayan bir dünya bilgisayarı olarak çalışmasına ihtiyaç duyduğundandır. Ether, Ethereum Sanal Makinesi (EVM) adı verilen durum makinesinin _bir bilgisayarda çalışan_-----> bilgisayar programları olan akıllı sözleşmelerin yürütülmesi(çalışabilmesi) için ödeme yapmak için kullanılacaktır.

EVM global bir tekildir(singleton), yani her yerde çalışan küresel, 1️⃣tek örnekli bir bilgisayarmış gibi çalışır. Ethereum ağındaki her düğüm, sözleşmenin yürütülmesini doğrulamak için**EVM'nin yerel bir kopyasını çalıştırırken, Ethereum blok zinciri, işlemleri ve akıllı sözleşmeleri işlerken bu dünya bilgisayarının değişen durumunu kaydeder.** Bunu [evm_chapter](https://github.com/ethereumbook/ethereumbook/blob/develop/02intro.asciidoc#evm_chapter) bölümünde çok daha ayrıntılı olarak tartışacağız.

## Harici Olarak Sahip Olunan Hesaplar (EOA'lar) ve Sözleşmeler

MetaMask cüzdanında oluşturduğunuz  1️⃣ hesap türüne _harici olarak sahip olunan hesap (EOA)_ denir. Harici olarak sahip olunan hesaplar, özel anahtarı olanlardır; 🔐 **özel anahtara sahip olmak, fonlara veya sözleşmelere erişim üzerinde kontrol anlamına gelir**. Şimdi, muhtemelen başka bir hesap türü olduğunu tahmin ediyorsunuz. Bu diğer hesap türü bir 2️⃣ _sözleşme hesabıdır(S.contract account)._ Bir sözleşme hesabının, basit bir EOA'nın sahip olamayacağı akıllı sözleşme kodu vardır. Ayrıca, bir **sözleşme hesabının özel anahtarı yoktur. Bunun yerine, akıllı sözleşme kodunun mantığı tarafından sahiplenilir (ve kontrol edilir): sözleşme hesabının oluşturulmasında Ethereum blok zincirine kaydedilemesi ve EVM tarafından yürütülmesini sağlayan program yatar.**

Sözleşmelerin tıpkı EOA'lar gibi adresleri vardır. _Sözleşmeler de tıpkı EOA'lar gibi ether gönderip alabilir._ Ancak, **bir işlem hedefi bir sözleşme adresi olduğunda, işlemi ve işlemin verilerini girdi olarak kullanarak bu sözleşmenin EVM'de çalışmasına neden olur.** Ether'e ek olarak, işlemler sözleşmede hangi belirli işlevin çalıştırılacağını ve bu işleve hangi parametrelerin iletileceğini gösteren verileri içerebilir. Bu şekilde, işlemler sözleşmeler içindeki fonksiyonları çağırabilir.


Bir sözleşme hesabının özel anahtarı olmadığı için bir işlem başlatamayacağını unutmayın. ⚠️ **İşlemleri yalnızca EOA'lar başlatabilir, ancak sözleşmeler işlemlere diğer sözleşmeleri çağırarak ve karmaşık yürütme yolları oluşturarak tepki verebilir.** Bunun tipik bir kullanımı, 1 ETH'yi başka bir adrese göndermek için çok imzalı bir akıllı sözleşme cüzdanına bir talep işlemi gönderen bir EOA'dır. Tipik bir DApp programlama modeli, Sözleşme A kullanıcıları arasında paylaşılan bir durumu sürdürmek için Sözleşme A'nın Sözleşme B'yi çağırmasıdır.

Sonraki birkaç bölümde ilk sözleşmemizi yazacağız. Daha sonra MetaMask cüzdanınızla bu sözleşmeyi nasıl oluşturacağınızı, fonlayacağınızı ve kullanacağınızı ve Ropsten test ağında etheri nasıl test edeceğinizi öğreneceksiniz.


## Basit bir sözleşme : Test ether Musluğu 🚰

Ethereum, **tümü bir sözleşme yazmak ve EVM bayt kodu üretmek için kullanılabilen birçok farklı üst düzey dile sahiptir.** [high_level_languages]'te en belirgin ve ilginç olanlardan birçoğunu okuyabilirsiniz. Akıllı sözleşme programlaması için açık ara en baskın seçim :**Solidity'dir.** Solidity, bu kitabın ortak yazarı Dr. Gavin Wood tarafından oluşturuldu ve Ethereum'da (ve ötesinde) en yaygın kullanılan dil haline geldi. İlk sözleşmemizi yazmak için Solidity kullanacağız.

İlk örneğimiz için bir musluğu kontrol eden bir sözleşme yazacağız. Ropsten test ağında test eteri almak için zaten bir musluk kullandınız. Bir musluk nispeten basit bir şeydir: soran herhangi bir adrese ether verir ve periyodik olarak yeniden doldurulabilir. Bir musluğu, bir insan veya bir web sunucusu tarafından kontrol edilen bir cüzdan olarak uygulayabilirsiniz.

Repoda Yazılmış olan faucet kodlarına  ulaşmak için: 

`code/Solidity/Faucet.sol`


Bu çok basit bir sözleşme, yapabileceğimiz kadar basit. Aynı zamanda, bir dizi kötü uygulamayı ve güvenlik açıklarını gösteren kusurlu bir sözleşmedir. İlerleyen bölümlerde tüm kusurlarını inceleyerek öğreneceğiz. Ama şimdilik bu sözleşmenin ne yaptığına ve nasıl işlediğine satır satır bakalım. **Solidity'nin birçok öğesinin JavaScript, Java veya C++** gibi mevcut programlama dillerine benzediğini hemen fark edeceksiniz.

İlk satır bir yorumdur: **Lisans hakları için ** 📋 ⚖️ :
 
`//SPDX-License-Identifier:CC-BY-SA-4.0`

Yorumlar(//) insanların okuması içindir ve çalıştırılan **EVM bayt koduna dahil edilmezler.** Bunları genellikle açıklamaya çalıştığımız koddan önceki satıra, bazen de aynı satıra koyarız. Yorumlar iki eğik çizgi ile başlar: //. İlk eğik çizgiden o satırın sonuna kadar her şey boş bir satır olarak kabul edilir ve yok sayılır.

Birkaç satır sonra asıl sözleşmemizin başladığı yer: 🔽

`contract Faucet{` 

Bu satır, diğer nesne yönelimli dillerdeki sınıf bildirimine benzer şekilde bir sözleşme nesnesi bildirir. Sözleşme tanımı, diğer birçok programlama dilinde süslü ayraçların nasıl kullanıldığına benzer şekilde, bir kapsamı tanımlayan süslü ayraçlar ({}) arasındaki tüm satırları içerir.

Ardından, sözleşmenin herhangi bir gelen tutarı kabul etmesini sağlıyoruz: 🔽

 `receive() external payable{}`

**Alma işlevi, sözleşmeyi tetikleyen işlem sözleşmede beyan edilen işlevlerden herhangi birini adlandırmadıysa veya veri içermiyorsa ve bu nedenle düz bir Ether aktarımıysa çağrılır.** Sözleşmelerin böyle bir alma işlevi olabilir (isimsiz) ve ether almak için kullanılır. Bu nedenle, sözleşmeye ether'i kabul edebileceği anlamına gelen harici ve ödenebilir bir işlev olarak tanımlanır. Kıvrımlı parantezlerdeki ({}) boş tanımla belirtildiği gibi. Sözleşme adresine ether gönderen bir işlem yaparsak, sanki bir cüzdanmış gibi bu fonksiyon halledecektir.

Bundan sonra, Musluk sözleşmesinin ilk işlevini belirtiyoruz :

` function withdraw(uint withdraw_amount) public { `

fonksiyon geri çekme(bakiyemizi) olarak adlandırılır ve geri çekme_tutarı adlı bir işaretsiz tamsayı (uint) argümanı alır. Bir açık(public) işlevi olarak ilan edilir, yani diğer sözleşmeler tarafından çağrılabilir. İşlev tanımı, küme parantezleri arasında gelir. Para çekme işlevinin ilk kısmı, para çekme işlemleri için bir sınır belirler:

`require(withdraw_amount <= 100000000000000000);`

çekme_miktarı 100,000,000,000,000,000 wei'den küçük veya buna eşit, ki bu etherin temel birimidir (bkz. Eter değerleri ve birim isimleri) ve 0.1 ether'e eşdeğerdir. Geri çekme işlevi, **bu miktardan daha büyük bir geri çekme_adı ile çağrılırsa, buradaki require işlevi, bir istisna dışında sözleşme yürütmesinin durdurulmasına ve başarısız olmasına neden olur.** Solidity'de ifadelerin noktalı virgülle sonlandırılması gerektiğini unutmayın.

Sözleşmenin bu kısmı musluğumuzun ana mantığıdır. Para çekme işlemlerine bir **sınır koyarak** sözleşmeden fon akışını kontrol eder. Bu çok basit bir kontrol ama size programlanabilir bir blok zincirinin gücü hakkında bir fikir verebilir:*parayı kontrol eden merkezi olmayan yazılım.*

Ardından  geri çekme tanımı geliyor:

`msg.sender.transfer(withdraw_amount);`

Burada birkaç ilginç şey oluyor. **Msg nesnesi**, tüm sözleşmelerin erişebileceği girdilerden biridir. Bu sözleşmenin yürütülmesini tetikleyen işlemi temsil eder. **Gönderici özelliği, işlemin gönderen adresidir.** transfer ilemi, mevcut sözleşmeden göndericinin adresine **etheri aktaran yerleşik bir işlevdir.**Transfer işlevi, **tek argümanı** olarak **bir miktar alır.** Parametresi olan withdraq_amount değerini birkaç satır önce bildirilen geri çekme işlevine geçiriyoruz.

Bir sonraki satır, geri çekme fonksiyonumuzun tanımının sonunu gösteren kapanış küme ayracıdır. `}`

Varsayılan işlevimizin hemen altında, sözleşme Musluğu tanımını kapatan son kapanış küme ayracı bulunur. `}` Bu kadar! 🔚

## Musluk sözleşmesinin Derlenmesi (compiling)

Artık ilk örnek sözleşmemize sahip olduğumuza göre, **Solidity kodunu EVM bayt koduna dönüştürmek** için bir Solidity derleyicisi kullanmamız gerekiyor, böylece EVM tarafından blok zincirinin kendisinde yürütülebilir.

Solidity derleyicisi, çeşitli çerçevelerin bir parçası olarak bağımsız bir yürütülebilir dosya olarak gelir ve **Entegre Geliştirme Ortamlarında (IDE'ler)** paketlenmiştir. İşleri basit tutmak için, **Remix** adı verilen daha popüler IDE'lerden birini kullanacağız. 
🖱️
https://remix.ethereum.org adresindeki Remix IDE'ye gitmek için Chrome tarayıcınızı (daha önce yüklediğiniz MetaMask cüzdanıyla) kullanın.

⚠️UYARI! :KİTAPTA KULLANILAN GÖRSELLER REMIX IDE'NİN ESKİ SÜRÜMÜNE AİT GÖRSELLER OLUP YENİ SÜRÜMÜNÜ AZ BİRAZ İNCELEDİĞİNİZDE ÇOKTA **KAFA KARIŞTIRICI OLMADIĞINI** GÖRECEKSİNİZ.☑️

Remix'i ilk yüklediğinizde, ballot.sol adlı örnek bir sözleşme ile başlayacaktır. Buna ihtiyacımız yok, bu yüzden Varsayılan örnek sekmesini kapat bölümünde görüldüğü gibi sekmenin köşesindeki x'i tıklayarak kapatın.

<img title="ballot_close" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_close_tab.png">

Şimdi, yeni bir sekme açmak için artı işaretini(+) tıklayın bölümünde görüldüğü gibi, sol üstteki araç çubuğundaki dairesel artı işaretine tıklayarak yeni bir sekme ekleyin. Yeni dosyaya Faucet.sol adını verin 

<img title="new_file" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_toolbar.png">

yazmış olduğunuz kodu Faucet.sol 'a yapıştırın veya git reposundan kop-yapıştır yapın ve açın:
 
<img title="faucet_start" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_faucet_load.png">

 
 Faucet.sol sözleşmesini Remix IDE'ye yükledikten sonra, IDE kodu otomatik olarak derleyecektir. Her şey yolunda giderse, Derleme sekmesinin altında sağda görünen ve başarılı derlemeyi onaylayan "Musluk" bulunan yeşil bir kutu göreceksiniz.
 

<img title="faucet_success" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_compile.png">

Bir şeyler ters giderse, en olası sorun Remix IDE'nin Solidity derleyicisinin 0.6'dan farklı bir sürümünü kullanmasıdır. 
Bu durumda **pragma yönergemiz Faucet.sol'ün derlenmesini engelleyecektir**. Derleyici sürümünü değiştirmek için **Ayarlar sekmesine** gidin,
sürümü ^0.6.0 olarak ayarlayın ve tekrar deneyin.

Solidity derleyicisi şimdi Faucet.sol dosyamızı **EVM bayt kodunda derledi.** Merak ediyorsanız, bayt kodu şöyle görünür:

`PUSH1 0x80 PUSH1 0x40 MSTORE CALLVALUE DUP1 ISZERO PUSH2 0x10 JUMPI PUSH1 0x0 DUP1 REVERT JUMPDEST POP PUSH1 0xF4 DUP1 PUSH2 0x1F PUSH1 0x0 CODECOPY PUSH1 0x0 RETURN INVALID PUSH1 0x80 PUSH1 0x40 MSTORE PUSH1 0x4 CALLDATASIZE LT PUSH1 0x1F JUMPI PUSH1 0x0 CALLDATALOAD PUSH1 0xE0 SHR DUP1 PUSH4 0x2E1A7D4D EQ PUSH1 0x2A JUMPI PUSH1 0x25 JUMP JUMPDEST CALLDATASIZE PUSH1 0x25 JUMPI STOP JUMPDEST PUSH1 0x0 DUP1 REVERT JUMPDEST CALLVALUE DUP1 ISZERO PUSH1 0x35 JUMPI PUSH1 0x0 DUP1 REVERT JUMPDEST POP PUSH1 0x5F PUSH1 0x4 DUP1 CALLDATASIZE SUB PUSH1 0x20 DUP2 LT ISZERO PUSH1 0x4A JUMPI PUSH1 0x0 DUP1 REVERT JUMPDEST DUP2 ADD SWAP1 DUP1 DUP1 CALLDATALOAD SWAP1 PUSH1 0x20 ADD SWAP1 SWAP3 SWAP2 SWAP1 POP POP POP PUSH1 0x61 JUMP JUMPDEST STOP JUMPDEST PUSH8 0x16345785D8A0000 DUP2 GT ISZERO PUSH1 0x75 JUMPI PUSH1 0x0 DUP1 REVERT JUMPDEST CALLER PUSH20 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF AND PUSH2 0x8FC DUP3 SWAP1 DUP2 ISZERO MUL SWAP1 PUSH1 0x40 MLOAD PUSH1 0x0 PUSH1 0x40 MLOAD DUP1 DUP4 SUB DUP2 DUP6 DUP9 DUP9 CALL SWAP4 POP POP POP POP ISZERO DUP1 ISZERO PUSH1 0xBA JUMPI RETURNDATASIZE PUSH1 0x0 DUP1 RETURNDATACOPY RETURNDATASIZE PUSH1 0x0 REVERT JUMPDEST POP POP JUMP INVALID LOG2 PUSH5 0x6970667358 0x22 SLT KECCAK256 STOP CODECOPY 0xDC DUP16 0xD SGT PUSH6 0xD2245039EDD7 RETURN CALLDATALOAD 0xC2 0xE4 SWAP9 0xF6 0x2C 0xF8 0xB3 OR JUMPDEST 0xAC 0xD8 CREATE2 SSTORE 0x4E SIGNEXTEND PUSH4 0x3164736F PUSH13 0x634300060C003300000000000`

Doğrudan EVM bayt kodunda 💥 programlama yapmak yerine *Solidity* gibi bir dil kullandığınızdan memnun olmalısınız. 😸

📝 NOT:Akıllı sözleşme yazabilmek için sadece solidity dili şart değil **Vyper, Rust, Cairo vb. dillerde vardır.**(En yaygını solidity_dir.sol 😺 )

------------
## Blokzincir üzerinde akıllı sözleşme oluşturma ⛓️
-----------

Evet elimizde bir sözleşmemiz var._(faucet.sol)_ Bunu bytecode olarak derledik. Şimdi, **Ethereum blok zincirindeki sözleşmeyi "kaydetmemiz" gerekiyor.** Sözleşmemizi test etmek için Ropsten test ağını kullanacağız, bu yüzden onu göndermek istediğimiz blokzincir Ropsten ağıdır.

Blok zincirinde bir sözleşmenin kaydedilmesi, _0x0000000000000000000000000000000000000000_ olan ve **sıfır adres** olarak da bilinen özel bir işlem oluşturmayı içerir.  0️⃣x----> Sıfır adresi, **Ethereum blok zincirine bir sözleşme kaydetmek istediğinizi söyleyen özel bir adrestir.** Neyse ki, Remix IDE hepsini sizin için halledecek ve işlemi MetaMask'a gönderecek.

İlk olarak Çalıştır sekmesine geçin ve üstdeki  kutudan _Injected Web3'ü_ seçin. Bu, **Remix IDE'yi MetaMask cüzdanına ve MetaMask aracılığıyla Ropsten test ağına bağlar.** Hesap seçim kutusunda cüzdanınızın adresini gösterir.

<img title="injected_web3" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_run.png">


Az önce onayladığınız Çalıştırma(run) ayarlarının hemen altında, oluşturulmaya hazır olan _faucet.sol_ bulunur(bizim sözleşmemiz). Injected Web3 ortamı seçiliyken Remix IDE Run sekmesinde gösterilen **deploy** düğmesine tıklayın.

Remix IDE, özel "oluşturma"(creation) işlemini oluşturacak ve *MetaMask; sözleşme oluşturma işlemini gösterildiği gibi, sizden bunu onaylamanızı isteyecektir.* Sözleşme oluşturma işleminin içinde ether olmadığını fark edeceksiniz, ancak 275 bayt veriye (derlenmiş sözleşme) sahiptir ve gaz olarak 3 gwei tüketecektir. Onaylamak için Onayla'ya basın.

<img title="confirm_mmask" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_metamask_create.png">

Şimdi biraz sabırlı olmak zorundayız. Sözleşmenin Ropsten'da yayınlanması yaklaşık 15-30 saniye civarı sürecek. Remix pek bir şey yapmıyor gibi görünse de sabırlı olun.

Sözleşme oluşturulduktan sonra **Çalıştır(run) sekmesinin altında** görünür.


<img title="conrt_interact" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_contract_interact.png">

Faucet.sol artık kendine ait bir **adresi olduğuna dikkat edin: Remix bunu “Faucet at 0x72e…​c7829” olarak gösteriyor** (ancak sizin yazacağınız sözleşmenin adresi  harfler ve sayılar farklı olacaktır çünkü her adress (_unique_)  yani benzersizdir. Tıpkı insan DNA'sı gibi 🧬). Sağdaki küçük kare simgesi, sözleşme adresini panonuza kopyalamanıza yardımcı olur 🔲. Bunu bir sonraki bölümde kullanacağız.

## Sözleşme ile etkileşime Girme 
❓
Etkileşim: TDK'ye göre ----> Birbirini karşılıklı olarak etkileme işi.Bana göre ve buradaki kullanımı kısaca sözelşmeye erişip,onun içeriklerinden yararlanma

Şimdiye kadar öğrendiklerimizi özetleyelim: Ethereum sözleşmeleri, EVM adı verilen sanal bir makinede çalışarak etheri kontrol eden programlardır. **Blok zincirine kaydedilmek üzere bayt kodlarını gönderen özel bir işlemle oluşturulurlar**. Blok zincirinde oluşturulduktan sonra, tıpkı cüzdanlar gibi bir Ethereum adreslerine sahip olurlar. Birisi bir sözleşme adresine bir işlem gönderdiğinde, sözleşmenin girdi olarak işlemle birlikte EVM'de çalışmasına neden olur. Sözleşme adreslerine gönderilen işlemler, _ether veya veri veya her ikisini birden_ içerebilir. Ether içeriyorlarsa, **sözleşme bakiyesine** "biriktirilir". Veri içeriyorlarsa, veriler sözleşmede adlandırılmış bir fonksiyon belirtebilir ve fonksiyonlara argümanlar ileterek onu çağırabilir.

## Bir Blok Gezgini'nde(Explorer /Etherscan gibi) Sözleşme Adresini Görüntüleme

Artık blok zincirinde kayıtlı bir sözleşmemiz var ve bunun bir Ethereum adresi olduğunu görebiliyoruz. Bunu **ropsten.etherscan.io** blok gezgininde kontrol edelim ve bir sözleşmenin nasıl göründüğünü görelim. Remix IDE'de, adının yanındaki kare simgesine tıklayarak sözleşmenin adresini kopyalayın.

<img title="adress_in_etherscan" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_contract_address.png">

Remix'i açık tutun; ona daha sonra tekrar döneceğiz. Şimdi tarayıcınızda ropsten.etherscan.io'ya gidin ve adresi arama kutusuna yapıştırın. Etherscan blok gezgininde faucet.sol adresini görüntüleme bölümünde gösterildiği gibi, sözleşmenin **Ethereum adres geçmişini** görmelisiniz.

<img title="etherscan_address" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/etherscan_contract_address.png">

## Sözleşmeye Ether yollama/ finanse Edilmesi(fund me please) 🤑
Şimdilik sözleşmenin geçmişinde yalnızca bir işlem var: sözleşme **oluşturma işlemi**. Gördüğünüz gibi, sözleşmede ayrıca ether (sıfır bakiye) yoktur. Bunun nedeni, yaratabilmemize rağmen sözleşmeye herhangi bir ether göndermememizdi.

Musluğumuzun paraya ihtiyacı var! İlk projemiz sözleşmeye ether göndermek için MetaMask kullanmak olacak. Sözleşmenin adresi hala panonuzda olmalıdır (eğer değilse, Remix'ten tekrar kopyalayın). MetaMask'i açın ve tıpkı diğer Ethereum adreslerine yaptığınız gibi ona **1 eter gönderin**

<img title="send_the_contract" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_send_to_contract.png">

Bir dakika içinde, Etherscan blok gezginini yeniden yüklerseniz, _sözleşme adresine başka bir işlem ve güncellenmiş 1 ether bakiyesi_ gösterecektir.

Faucet.sol kodumuzdaki:
 
`receive () external payable {}` 
⏬

Hangi fonksiyonun çağrılacağını belirten bir **veri olmadan** sözleşme adresine bir işlem gönderdiğinizde, bu **varsayılan fonksiyonu çağırdı.** Bunu ödenebilir(payable) olarak belirttiğimiz için 1 etheri kabul etti ve sözleşmenin hesap bakiyesine yatırdı. İşleminiz, sözleşmenin bakiyesini güncelleyerek EVM'de çalışmasına neden oldu.sözlemenizi finanse ettiniz!(Yani para yüklediniz) 🍾 🔥

-------
Sözleşmeden Ether çekme 💸
-------

Ardından, sözleşmeden biraz para çekelim. Geri çekmek için, _withdraw(geri çekme) fonksiyonu_ çağıran ve ona bir _withdraw_amount(geri çekilecek miktar)_ argümanı ileten bir işlem oluşturmalıyız. Şimdilik işleri basit tutmak için, Remix bu işlemi bizim için yapacak ve MetaMask'te 🦊 bunu onayımıza sunacak.

Remix sekmesine dönün ve Çalıştır sekmesindeki sözleşmeye bakın. **uint256 draw_amount** etiketli bir alan girişi ile geri çekme etiketli turuncu bir kutu 🟧 görmelisiniz.


<img title="withdraw_remix" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_contract_interact.png">

Bu, sözleşmenin Remix arayüzüdür. Sözleşmede tanımlanan fonksiyonları çağıran işlemler oluşturmamızı sağlar. Bir withdraw_amount gireceğiz ve işlemi oluşturmak için para çekme düğmesine tıklayacağız.

İlk olarak, withraw_amount bulalım. Sözleşmemizin izin verdiği _maksimum miktar olan 0.1 eter'i denemek ve çekmek istiyoruz._ Ethereum'daki tüm para birimi değerlerinin dahili olarak wei cinsinden ifade edildiğini ve para çekme işlevimizin, çekme_tutarı'nın da wei cinsinden olmasını beklediğini unutmayın. _İstediğimiz miktar 100.000.000.000.000.000 wei (1 ve ardından 17 sıfır) olan 0.1 eterdir._

🔍İPUCU: JavaScript'teki bir sınırlama nedeniyle, 10^17 kadar büyük bir sayı Remix tarafından işlenemez. Bunun yerine, **Remix'in onu bir dize olarak almasına ve bir BigNumber olarak işlemesine izin vermek için onu çift tırnak(" ") içine alırız.** Bunu tırnak içine almazsak, Remix IDE onu işlemez.Hata uyarısı olarak şunu çevirir ------> Assertion failed(Onaylama başarısız!) 🔴✖️
⬇️

<img title="withdraw_remix" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/remix_withdraw.png">


MetaMask, onaylamanız için bir işlem penceresi açacaktır. withdraw çağrınızı sözleşmeye göndermek için Onayla'ya tıklayın.

<img title="withdraw_metamask_confirm" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_withdraw.png">

Biraz bekleyin ve ardından Faucet sözleşme adres geçmişine(address history) yansıyan işlemi görmek için Etherscan blok gezginini yeniden yükleyin. 

<img title="withdraw_etherscan_confirm" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/etherscan_withdrawal_tx.png">


Şimdi hedef olarak sözleşme adresi ve 0 ether değeri ile yeni bir işlem görüyoruz. Sözleşme bakiyesi değişti ve talep edildiği gibi bize 0.1 ether gönderdiği için şimdi 0.9 eter oldu. Ancak sözleşme adresi geçmişinde bir **"OUT"** işlemi görmüyoruz.

çektiğimiz para nerede ? Sözleşmenin adres geçmişi sayfasında _Dahili İşlemler adlı yeni bir sekme belirdi._ 0.1 ether transferi sözleşme kodundan kaynaklandığı için **dahili(internal) bir işlemdir**(mesaj(message) da denir).

Bu "dahili işlem", sözleşme tarafından bu kod satırında gönderilmiştir.(Faucet.sol'deki para çekme işlevinden):

`msg.sender.transfer(withdraw_amount);`

<img title="withdraw_etherscan_internalMessage" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/etherscan_withdrawal_internal.png">

----------
Sonuç Olarak BU bölümde;
----------

Bu bölümde MetaMask kullanarak bir cüzdan kurdunuz ve bunu **Ropsten test ağında bir musluk kullanarak finanse ettiniz.** Cüzdanınızın Ethereum adresine ether aldınız, ardından musluğun Ethereum adresine ether gönderdiniz.

Ardından, Solidity'de bir musluk sözleşmesi yazdınız. Sözleşmeyi EVM bayt koduna derlemek için Remix IDE'yi kullandınız, ardından bir işlem oluşturmak için Remix'i kullandınız ve Ropsten blok zincirinde Faucet sözleşmesini oluşturdunuz. Bir kez oluşturulduğunda, faucet sözleşmesinin bir Ethereum adresi vardı ve siz ona bir miktar ether gönderdiniz. Son olarak, withdraw(para çekme) işlevini çağırmak için bir işlem oluşturdunuz ve başarılı bir şekilde 0.1 eter istediniz. Sözleşme talebi kontrol etti ve size **dahili bir işlemle(internal message)** 0.1 ether gönderdi.

Çok fazla görünmeyebilir, ancak merkezi olmayan bir dünya bilgisayarında parayı kontrol eden yazılımla başarılı bir şekilde etkileşime girdiniz.Tebriklerr 🍻
↪️
[Akıllı Sözleşmeler] 📖 bölümünde çok daha fazla akıllı sözleşme programlaması yapacağız ve [akıllı sözleşme Güvenliği] 🛡️ bölümünde en iyi uygulamaları ve güvenlikle ilgili konuları öğreneceğiz. 💙


_Bölümün SONU_ 🏁

**"Size çok önemli bir soru soracağım. Dünyayı kontrol etmenin en etkili ve verimli yolu nedir? İki kelime: Akıl Kontrolü!" 🗣️GEORGE CARLİN** 


