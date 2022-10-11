# İŞLEMLER ➡️📖⬅️

_İşlemler_, Ethereum ağı tarafından iletilen ve Ethereum blok zincirine **kaydedilen**, harici olarak sahip olunan bir hesaptan (EOA'dan) kaynaklanan _imzalı mesajlardır_. Bu temel tanım, birçok **şaşırtıcı ve büyüleyici ayrıntıyı gizler**👻. İşlemlere  başka bir perspektiften bakınca, **bir durum değişikliğini tetikleyebilecek veya EVM'de bir sözleşmenin yürütülmesine(çalışmasına) neden olabilecek TEK şey olmalarıdır**.  Ethereum, global 🌎 bir tekil(singleton) durum makinesidir ve bu durum makinesinin durumunu değiştirerek "tik-tak⏰" olan  şeyler _işlemlerdir_.(Buradaki cümlede yazar Ethereum'u bir saate ⏰ benzeterek,geçen her saniyeyi işlemlere benzetmiştir.) 

**Sözleşmeler kendi başlarına çalışamazlar. Ethereum otonom olarak çalışmaz. Her şey bir işlemle başlar.** 💥🌍

Bu bölümde işlemleri inceleyeceğiz, nasıl çalıştıklarını göstereceğiz ve detayları inceleyeceğiz. Bu bölümde çoğu kişinin, **belki de bir cüzdan uygulaması yazdıkları için kendi işlemlerini düşük düzeyde yönetmekle ilgilenenlere yönelik olduğunu unutmayın**; Buradaki detayları ilginç bulacak olsanız da, mevcut cüzdan uygulamalarını kullanmaktan memnunsanız bunun için panik yapmanıza gerek yok!☕

