## ÖNSÖZ (Mutlaka okuyun 🃏)

Bu kitap, Andreas M. Antonopoulos ve Dr. Gavin Wood arasında bir işbirliği sonucudur. Bir dizi şanslı tesadüf, bu iki yazarı; _en iyi açık kaynak ruhu ve yaratıcı ortak kültür ruhuyla_ bu kitabı üretmek için yüzlerce katılımcıyı harekete geçiren bir çaba içinde bir araya getirdi.

Gavin, bir süredir *Yellow Paper* üzerine bir kitap yazmak istiyordu *(Ethereum protokolünün teknik açıklaması)*, öncelikle onu(Kitabı) orijinal Yunan harfli YellowPaper'ın izin verebileceğinden daha geniş bir kitleye açmak istiyordu&#x2014;Burada anlatılan şey yellowpaperda yazılan Matematiksel ifadeleri açıklamaktan bahsediyor.Biliyorsunuz ki matematikte birçok formül latince ifadelerle gösterilir. &#x2014;

Gavin, Ethereum ile görev süresinin en başından beri bu alanda kayda değer bir kişilik olarak tanıdığı Andreas ile konuştuğunda planlar yapılıyordu. --bir yayıncı bulunmuştu bile.--

Andreas kısa süre önce Bitcoin ve kripto para birimleri için hızlı bir şekilde yetkili teknik rehber haline gelen _Mastering Bitcoin_ (O'Reilly) kitabının ilk baskısını yayınlamıştı. Kitap yayınlanır yayınlanmaz okuyucuları ona "Ethereum'da Mastering'i ne zaman yazacaksınız?" diye sormaya başladı. Andreas zaten bir sonraki projesini düşünüyordu ve Ethereum'u zorlayıcı bir teknik konu olarak buldu.

Son olarak, Mayıs 2016'da Gavin ve Andreas tesadüfen aynı şehirde aynı anda bulunuyorlardı. Birlikte kitap üzerinde çalışmak hakkında sohbet etmek için ve kahve ☕ içmek için bir araya geldiler. Hem Andreas hem de Gavin, açık kaynak paradigmasına(ortak bir amaç,anlayış dizisi) adanmış olduklarından, ikisi de _Creative Commons lisansı_ altında yayınlanan bunu ortak bir çaba haline getirmeyi taahhüt ettiler(söz verdiler). Neyse ki yayıncı O'Reilly Media bunu kabul etmekten son derece mutluluk duydu ve _Mastering Ethereum_ projesi resmi olarak başlatıldı.

### Bu kitap nasıl kullanılır ?

Kitabın, hem bir referans rehberi hem de Ethereum'un baştan sona keşfedilmesine hizmet etmesi amaçlanmıştır. *İlk iki bölüm*, acemi kullanıcılar için uygun, nazik(ince) bir giriş sunar ve bu bölümlerdeki örnekler, biraz teknik beceriye sahip herkes tarafından tamamlanabilir. Bu iki bölüm size temelleri iyi bir şekilde kavrayıp, Ethereum'un temel araçlarını kullanmanıza izin verecek. 📍[Ethereum_clients_Bölümü] ve devamı, temel olarak programcılara yöneliktir ve birçok teknik konu ve programlama örnekleri içerir.

Ethereum hakkında hem bir referans rehberi hem de baştan sona bir anlatı olarak hizmet etmek için kitap,kaçınılmaz olarak bazı tekrarlar içeriyor. _Gaz(GAS)_ 🛢️ gibi bazı konuların, geri kalan konuların anlamlı olması için yeterince erken anlatılması gerekiyor, ancak aynı zamanda _kendi bölümlerinde_ derinlemesine incelenecektir.

Son olarak, kitabın dizini okuyucuların anahtar kelime ile çok özel konuları ve ilgili bölümleri kolaylıkla bulmasını sağlar.

### Hedef kitlesi 🧑‍🤝‍🧑

Bu kitap çoğunlukla kodlayıcılar(coder,developer,software engineer,geeks olan herkese uygundur) 💻 için tasarlanmıştır. Bir programlama dili kullanabiliyorsanız, bu kitap size akıllı sözleşme ile blokzincirlerinin nasıl çalıştığını, bunların nasıl kullanılacağını ve bunlarla akıllı sözleşmelerin ve merkezi olmayan uygulamaların nasıl geliştirileceğini öğretecektir. _İlk birkaç bölüm_, yazılımıcı olmayanlar için Ethereum'a derinlemesine bir giriş olarak da uygundur.

### Bu kitapta kullanılan Kurallar

_Italic_ Yeni terimleri, URL'leri, e-posta adreslerini, dosya adlarını ve dosya uzantılarını belirtir.

+Constant width+ Değişken veya fonksiyon adları, veritabanları, veri türleri, ortam değişkenleri, ifadeler ve anahtar sözcükler gibi program öğelerine atıfta bulunmak için paragraflar içinde olduğu kadar program listeleri için de kullanılır.

**`Constant width bold`**:Kullanıcı tarafından tam anlamıyla yazılması gereken komutları veya diğer metinleri gösterir.

_++Constant width italic++_ Kullanıcı tarafından sağlanan değerler veya bağlama göre belirlenen değerlerle değiştirilmesi gereken metni gösterir.

## [İPUCU] 🔍
Bu simge bir ipucu veya öneri anlamına gelir.


## [NOT] 📝
Bu simge genel bir notu(bilgilendirme) ifade eder.


## [UYARI] ⚠️

Bu simge bir uyarı belirtir.


_(Bilgilendirme 📝 :Bu işaretler normalde kitapta yok(GitHub üzerinde yayınlanmış olan).Ancak burada ben emoji ekleyerek sizlerin daha iyi bir şekilde görsel olarak anlamanıza yardımcı olmaya çalışacağım.)_

## Kod Örnekleri

kod örnekleri, elde etme ve kullanımı :Örnekler _Solidity, Vyper ve JavaScript'te ve Unix benzeri_ bir işletim sisteminin komut satırı kullanılarak yapılmıştır. Tüm kod parçacıkları GitHub deposunda _code_ alt dizini altında bulunur. Kitap kodunu çatallayın(Forking), kod örneklerini deneyin veya GitHub aracılığıyla düzeltmeleri gönderin: https://github.com/ethereumbook/ethereumbook.


Tüm kod parçacıkları, ilgili diller için minimum derleyici, yorumlayıcı ve kitaplık kurulumuyla çoğu işletim sisteminde çoğaltılabilir. Gerektiğinde, temel kurulum talimatlarını ve bu talimatların çıktılarının adım adım örneklerini sağlıyoruz.

Bazı kod parçacıkları ve kod çıktısı, yazdırma için yeniden biçimlendirilmiştir. Tüm bu durumlarda, satırlar bir ters eğik çizgi (+\+) karakteri ve ardından bir yeni satır karakteri ile bölünmüştür. Örnekleri kopyalarken, bu iki karakteri kaldırın ve satırları tekrar birleştirin ve örneklerde gösterilenlerle aynı sonuçları görmelisiniz.

Tüm kod parçacıkları mümkün olduğunda gerçek değerleri ve hesaplamaları kullanır, böylece örnekten örneğe derleyebilir ve aynı değerleri hesaplamak için yazdığınız herhangi bir kodda aynı sonuçları görebilirsiniz. Örneğin, özel anahtarlar ve karşılık gelen genel anahtarlar ve adreslerin tümü gerçektir. Örnek işlemler, sözleşmeler, bloklar ve blok zinciri referanslarının tümü, gerçek Ethereum blok zincirine tanıtılmıştır ve genel defterin bir parçasıdır, böylece bunları inceleyebilirsiniz.


## Kod Örneklerini Kullanma

Bu kitap işinizi yapmanıza yardımcı olmak için burada. Genel olarak, bu kitapla birlikte örnek kod sunuluyorsa, programlarınızda ve dokümantasyonunuzda kullanabilirsiniz. Kodun önemli bir bölümünü yeniden oluşturmuyorsanız, izin almak için bizimle iletişime geçmeniz **gerekmez**. Örneğin, bu kitaptan birkaç parça kod kullanan bir program yazmak için *izin gerekmez*. O'Reilly kitaplarından örnekler içeren bir CD-ROM'u satmak veya dağıtmak **izin gerektirir**. Bir soruyu bu kitaptan alıntı yaparak ve örnek koddan alıntı yaparak cevaplamak **izin gerektirmez**. Bu kitaptan önemli miktarda örnek kodu ürününüzün belgelerine dahil etmek **izin gerektirir**.

_Mastering Ethereum_  Creative Commons Attribution-Noncommercial-No Derivative Works 4.0 International License (CC BY-NC-ND 4.0) lisansı altında sunulmaktadır.
©️

Kod örneklerini kullanımınızın adil kullanım veya yukarıda verilen iznin dışında kaldığını düşünüyorsanız, bizimle şu adresten iletişime geçmekten çekinmeyin:
[<a href="mailto:permissions@oreilly.com">permissions@oreilly.com</a>].

## Firmalara ve Ürünlere Referanslar
Şirketlere ve ürünlere yapılan tüm referanslar eğitim, tanıtım ve referans amaçlıdır. Kitabın yazarları, belirtilen şirket veya ürünlerin hiçbirini onaylamamaktadır. Bu kitapta gösterilen ürünlerin, projelerin veya kod bölümlerinin hiçbirinin çalışmasını veya güvenliğini test etmedik. Bunları kullanmak sizin sorumluluğuzdadır! ⚠️

Bu Kitaptaki Ethereum Adresleri ve İşlemleri
Bu kitapta kullanılan _Ethereum adresleri, işlemleri, anahtarları, QR kodları ve blokzincir verileri_ **çoğunlukla gerçektir**. Bu, blok zincirine göz atabileceğiniz, örnek olarak sunulan işlemlere bakabileceğiniz, bunları kendi yazılımlarınız veya programlarınız vb. ile alabileceğiniz anlamına gelir.

Ancak, bu kitapta basılan adresleri oluşturmak için kullanılan özel anahtarların "**yakıldığını**" 🔴 unutmayın. Bu, bu adreslerden herhangi birine coin veya token gönderirseniz,Paranızın(dijital değer anlamında) ya sonsuza kadar kaybolacağı ya da (daha büyük olasılıkla) 3.kişinin zimetine geçireceği(el koyma) anlamına gelir, çünkü kitabı okuyan herkes burada basılan _özel anahtarları_ kullanarak parayı alabilir.

**UYARI!** ⚠️
BU KİTAPTA HİÇBİR ADRESE PARA GÖNDERMEYİN. Paranız başka bir okur(Kitabı okuyan veya adresleri incelen kişi) tarafından alınacak veya sonsuza kadar kaybedilecektir.

## O'Reilly Safari
📝Safari (eski adıyla Safari Books Online), işletmeler, devlet kurumları, eğitimciler ve bireyler için üyeliğe dayalı bir eğitim ve referans platformudur.

Üyeler: O'Reilly Media, Harvard Business Review, Prentice Hall Professional, Addison-Wesley Professional, Microsoft Press, Sams, Que dahil olmak üzere, 250'den fazla yayıncıdan binlerce kitaba, eğitim videosuna, Öğrenme Yollarına, etkileşimli öğreticilere ve seçilmiş oynatma listelerine erişebilir. , Peachpit Press, Adobe, Focal Press, Cisco Press, John Wiley & Sons, Syngress, Morgan Kaufmann, IBM Redbooks, Packt, Adobe Press, FT Press, Apress, Manning, New Riders, McGraw-Hill, Jones & Bartlett ve Course Teknoloji, diğerleri arasında.

Daha fazla bilgi için,Bu adresi ziyaret ediniz:[<a href="http://oreilly.com/safari" class="orm:hideurl"><em>http://oreilly.com/safari</em></a>].

## Bizimle iletişime geçmek için

kitap hakkkında bilgi için _Mastering Ethereum_ 
link:$$https://ethereumbook.info/$$[].

Lütfen bu kitapla ilgili yorum ve soruları yayıncıya iletin:

++++
<ul class="simplelist">
  <li>O'Reilly Media, Inc.</li>
  <li>1005 Gravenstein Highway North</li>
  <li>Sebastopol, CA 95472</li>
  <li>800-998-9938 (in the United States or Canada)</li>
  <li>707-829-0515 (international or local)</li>
  <li>707-829-0104 (fax)</li>
</ul>
++++

bu kitapla ilgili yorum veya teknik sorular gönderin:[<a class="email" href="mailto:bookquestions@oreilly.com"><em>bookquestions@oreilly.com</em></a>].

Kitaplarımız, kurslarımız, konferanslarımız ve haberlerimiz hakkında daha fazla bilgi için linkteki web sitemize bakın. :$$https://www.oreilly.com$$[].

Facebook: link:$$https://facebook.com/oreilly$$[]

Twitter: link:$$https://twitter.com/oreillymedia$$[]

YouTube: link:$$https://www.youtube.com/oreillymedia$$[]




**Andreas İle iletişim için ** 🔗

+Andreas M. Antonopoulos'un web sitesi:
link:$$https://antonopoulos.com/$$[]
 
+Andreas'ın YouTube kanalı:
link:$$https://www.youtube.com/aantonop$$[]

+Andreas'ın Facebook sayfası:
link:$$https://www.facebook.com/AndreasMAntonopoulos$$[]

+Andreas'ın twitter profili:
link:$$https://twitter.com/aantonop$$[]

+Andreas'ın LinkedIn: :
link:$$https://linkedin.com/company/aantonop$$[]

Andreas Patreon hesabı üzerinden destekleyebilirsiniz 💸
link:$$https://patreon.com/aantonop$$[].


## Gavin ile iletişim için: 🔗

You can contact Dr. Gavin Wood on his personal site:
link:$$http://gavwood.com/$$[]

Follow Gavin on Twitter:
link:$$https://twitter.com/gavofyork$$[]

Gavin generally hangs out in the Polkadot Watercooler on Riot.im:
link:$$http://bit.ly/2xciG68$$[]



