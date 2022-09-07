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

Kontrol ile birlikte büyük bir sorumluluk gelir. Özel anahtarlarınızı kaybederseniz, fonlarınıza ve sözleşmelerinize erişiminizi kaybedersiniz. Hiç kimse erişimi yeniden kazanmanıza yardımcı olamaz - paranız sonsuza kadar kilitlenir. Bu sorumluluğu yönetmenize yardımcı olacak birkaç ipucu:
















