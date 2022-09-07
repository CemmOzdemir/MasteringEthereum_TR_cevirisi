# ETHEREUM TEMELLERİ 🏗️

örnek olarak dursun:

<img title="a title" alt="Alt text" src="/images/boo.svg">


Bu bölümde Ethereum'u keşfetmeye başlayacağız, cüzdanların nasıl kullanılacağını, işlemlerin nasıl oluşturulduğunu ve ayrıca temel bir akıllı sözleşmenin nasıl yürütüleceğini öğreneceğiz.

## Ether Para Birimleri

Ethereum'un para birimine **ether** denir ve "ETH" olarak veya Ξ sembolleriyle (ikonlaştırılmış bir büyük harfe (E'ye benzeyen Yunanca) "Xi" harfinden) veya daha az sıklıkla ♦: örneğin, 1 eter veya 1 ETH , veya Ξ1, veya ♦1 gösterilir.

🔍 Ξ için U+039E ve ♦ için U+2666 Unicode karakterini kullanın.

Eter, wei olarak adlandırılan mümkün olan en küçük birime kadar daha küçük birimlere bölünür. Bir eter, 1 kentilyon wei'dir 
("10^^18 veya 1.000.000.000.000.000.000). İnsanların "Ethereum" para birimine atıfta bulunduğunu da duyabilirsiniz, 
ancak bu yeni başlayanların yaygın bir hatasıdır. Ethereum _sistemdir_, ether para birimidir.**

Eter değeri her zaman dahili olarak, Ethereum'da wei cinsinden işaretsiz bir tamsayı değeri olarak temsil edilir. 1 ether işlemi yaptığınızda, işlem değer olarak 10000000000000000000(18 adet 0) wei kodlar.

Ether'in çeşitli isimleri, hem Uluslararası Birimler Sistemini (SI) kullanan bilimsel bir isme hem de birçok büyük bilgi işlem ve kriptografi düşüncesine saygı gösteren günlük konuşma diline ait bir isme sahiptir.

Ether isimleri ve birim adları, çeşitli birimleri, onların konuşma dilindeki (ortak) adlarını ve SI adlarını gösterir. Değerin dahili temsiline uygun olarak, tablo, 7. satırda **10**18(10 üstü 18) wei olarak gösterilen eterle birlikte, wei'deki (birinci sıra) tüm isimlerini gösterir.


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


Kitap boyunca örnek olarak kullanmak üzere birkaç farklı cüzdan türü seçtik. Bazıları mobil, masaüstü içindir ve diğerleri web tabanlıdır. Çok çeşitli karmaşıklık ve özellikleri temsil ettikleri için farklı cüzdanlar seçtik. Ancak, bu cüzdanların seçimi, kalitelerinin veya güvenliklerinin onaylandığı 🔴 anlamına gelmez. Gösterimler ve testler için iyi bir başlangıç noktasıdırlar.


Bir cüzdan uygulamasının çalışması için **özel anahtarlarınıza(private key 🔐)** erişimi olması gerektiğini unutmayın, bu nedenle yalnızca güvendiğiniz kaynaklardan cüzdan uygulamalarını indirip kullanmanız çok önemlidir. Neyse ki, genel olarak, bir cüzdan uygulaması ne kadar popülerse, o kadar güvenilir olur. Yine de, "_tüm yumurtalarınızı bir sepete koymaktan" 🧺 kaçınmak_ ve Ethereum hesaplarınızı birkaç cüzdana dağıtmak daha iyi bir uygulamadır. 🟢

Aşağıdakiler bazıları iyi bir başlangıç için uygun cüzdanlardır: ⤵️

## Metamask 🦊

MetaMask, tarayıcınızda (Chrome, Firefox, Opera veya Brave Browser) çalışan bir *tarayıcı uzantısı cüzdanıdır.* Çeşitli Ethereum düğümlerine bağlanabildiği ve blok zincirlerini test edebildiği için kullanımı kolay ve test için uygundur. MetaMask, hem iOS hem de Android store'dan erişip mobilde de kullanbileceğiniz bir cüzdandır.

## Jaxx

Jaxx, Android, iOS, Windows, macOS ve Linux dahil olmak üzere çeşitli işletim sistemlerinde çalışan çok platformlu ve çok para birimli bir cüzdandır. Basitlik ve kullanım kolaylığı için tasarlandığı için genellikle yeni kullanıcılar için iyi bir seçimdir. Jaxx, nereye kurduğunuza bağlı olarak mobil veya masaüstü cüzdandır.

MyEtherWallet (MEW) 

MyEtherWallet, öncelikle herhangi bir tarayıcıda çalışan web tabanlı bir cüzdandır. Ayrıca Android ve iOS'ta da mevcuttur. Örneğimizin çoğunda inceleyeceğimiz çok sayıda karmaşık özelliğe sahiptir.


Emerald Wallet 🔷

Emerald Wallet, Ethereum Classic blok zinciriyle çalışmak üzere tasarlanmıştır, 
ancak diğer Ethereum tabanlı blok zincirleriyle uyumludur. Açık kaynaklı bir masaüstü uygulamasıdır ve Windows, macOS ve Linux altında çalışır. Emerald, _"light" modda çalışarak tam bir düğüm çalıştırabilir veya genel bir uzak düğüme bağlanabilir._ Ayrıca tüm işlemleri komut satırından yapmak için bir yardımcı araca sahiptir.

MetaMask'i bir masaüstüne kurarak başlayacağız, ancak önce anahtarları kontrol etmeyi ve yönetmeyi kısaca anlamalıyız.🧐

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


## Metamask ile başlayalım

Google Chrome tarayıcısını açın ve https://chrome.google.com/webstore/category/extensions adresine gidin.

"MetaMask" arayın ve bir tilki logosuna tıklayın.

<img title="metamask" src="https://github.com/ethereumbook/ethereumbook/blob/develop/images/metamask_download.png">
























