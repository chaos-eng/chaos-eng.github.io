+++
title = "KAOS MÜHENDİSLİĞİNİN PRENSİPLERİ"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# KAOS MÜHENDİSLİĞİNİN PRENSİPLERİ
Son Güncelleme: Mayıs 2018

*Kaos Mühendisliği, canlı ortamda oluşabilecek çalkantılı koşullara dayanma kabiliyetine olan güveni artırmak için dağıtık bir sistem üzerinde deney yapma disiplinidir.*

Büyük ölçekli dağıtık sistemlerdeki gelişmeler, yazılım mühendisliği alanında oyunun kurallarını değiştirmekteler. Endüstri olarak, geliştirmenin esnekliğini ve dağıtımın sıklığını artıran değişiklikleri hızlı biçimde benimsiyoruz. Bu değişikliklerin getirdiği avantajları önemli bir soru takip ediyor: Canlı ortamlara sunduğumuz kompleks sistemlere ne kadar güvenebiliriz ?

Dağıtık bir sistemdeki tüm servisler ayrı ayrı düzgün çalışıyor olsalar bile, bu servislerin arasındaki ilişkiler beklenmeyen sonuçlar doğurabilirler. Beklenmeyen sonuçlar, canlı ortamları etkileyen nadir fakat yıkıcı gerçek dünya olayları ile birleştiklerinde, dağıtık sistemler doğal olarak kaotik olurlar.

Zayıflıkları, sistem çapında anormal davranışlara dönüşmeden önce tanımlamamız gerekir. Sistemsel zayıflıklar: servisin kullanım dışı kalması durumunda geri dönüş planlarının düzgün çalışmamasına sebep olan ayarlar; Yanlış ayarlanmış zaman aşımı süreleri sebebiyle oluşan yeniden deneme kuyrukları; Fazla trafikten kaynaklanan kesintiler; "Tek hata noktası" durumlarının üst üste gelmesi ve benzeri durumlar olarak ortaya çıkabilir. Müşterilerimizin canlı ortamlarını etkilemeden önce, en önemli zayıflıkları proaktif olarak ele almalıyız. Bu sistemlerdeki kaosu yönetmenin, artan esneklik ve hızın avantajlarını kullanmanın ve kompleksitelerine rağmen canlı ortamlarımıza olan güveni artırmanın bir yolunu bulmalıyız.

Ampirik, sistem tabanlı bir yaklaşım, dağıtık sistemlerdeki kaosu ölçeklendirir ve bu sistemlerin gerçekçi koşullara dayanma becerisine olan güveni artırır. Bizler, dağıtık bir sistemin davranışlarını, kontrollü bir deney ile gözlemleyerek öğreniyoruz. Biz buna *Kaos Mühendisliği* diyoruz.

## UYGULAMADA KAOS

Büyük Ölçekli Dağıtık sistemlerin belirsizliklerini özellikle ele almak için, Kaos Mühendisliği, sistemik zayıflıkları ortaya çıkarmak amaçlı deneylerin kolaylaştırılması olarak düşünülebilir. Bu deneyler dört adımdan oluşur:

1. Normal davranış gösteren bir sistemin ölçülebilir durumunu "Kararlı Çalışma Durumu" olarak tanımlayın.
2. Bu kararlı durumun hem kontrol grubunda hem de deney grubunda devam edeceğini varsayın.
3. Çalışmayı durduran sunucular, arıza yapan sabit diskler, kesilen ağ bağlantıları vb. gerçek dünya olaylarını yansıtan değişkenleri tanımlayın.
4. Kontrol grubu ile deney grubu arasındaki "Kararlı Çalışma Durumu"nda bir farklılık arayarak varsayımınızı çürütmeye çalışın.

İstikrarlı Durumu bozmak ne kadar zor ise, sistemin davranışına olan güvenimiz o kadar fazladır. Eğer bir zayıflık tespit edersek, bu zayıflık tüm sistem genelinde problem teşkil etmeden önce düzeltme yapmayı kendimize hedef belirlememiz gerekir.

## İLERİ DÜZEY PRENSİPLER

Aşağıdaki ilkeler, yukarıda tarif edilen deney süreçlerine uygulanan ideal bir Kaos Mühendisliği uygulamasını tanımlar. Bu ilkelerin izlenme derecesi, ölçeklendirilmiş bir sistemde sahip olabileceğimiz güven ile güçlü bir şekilde ilişkilidir.

### Kararlı Çalışma Durumu Üzerine Bir Hipotez Oluşturun

Sistemin iç öznitelikleri yerine bir sistemin ölçülebilir çıktısına odaklanın. Bu çıktının kısa bir süre içindeki ölçümleri, sistemin kararlı durumu için bir örnek oluşturur. Sistem genelindeki iş hacmi, hata oranları, gecikme yüzdeleri vb. kararlı durum davranışını temsil eden ölçütler olabilirler. Kaos, denemeler sırasında sistemik davranış kalıplarına odaklanarak, sistemin nasıl çalıştığını doğrulamaktan ziyade sistemin çalıştığını doğrular.

### Gerçek Dünya Olaylarını Çeşitlendirin

Kaos değişkenleri gerçek dünya olaylarını yansıtır. Olayları ya potansiyel etki ya da tahmini sıklık ile önceliklendirin. Sunucuların çökmesi gibi donanımsal hatalar, hatalı cevap dönüşleri gibi yazılım hataları ve trafikte artış ya da ölçekleme problemi gibi hata olmayan olayları göz önünde bulundurun. Kararlı durumu bozabilecek herhangi bir olay, bir Kaos deneyinde potansiyel bir değişkendir.

### Canlı Ortamda Deneyler Yapın

Sistemler, ortam ve trafik modellerine bağlı olarak farklı davranır. Kullanım davranışı her an değişebileceğinden, talep yoğunluğunu güvenilir şekilde yakalamanın tek yolu gerçek trafiği örneklemektir. Sistemin uygulandığı yöntemlerin gerçekliğini ve mevcut konuşlandırılmış sistemle alaka düzeyini garanti etmek için, Kaos, doğrudan canlı ortam trafiği üzerinde denemeler yapmayı tercih eder.

### Deneyleri Sürekli Çalışacak Şekilde Otomatize Edin

Deneyleri manuel çalıştırmak, iş gücü ister ve sonuç olarak sürdürülemezdir. Deneyleri otomatikleştirin ve sürekli olarak çalıştırın. Chaos Engineering, hem orkestrasyon hem de analiz için sistemin otomatize edilmesini sağlar.

### Patlama Alanını Küçültün

Canlı ortamda deney yapmak gereksiz müşteri acılarına neden olma potansiyeline sahiptir. Bazı kısa vadeli olumsuz etkiler için bir tolerans payı ayırılması gerekliliğiyle birlikte, deneylerden kaynaklanan hasarların en aza indirilmesini ve içerilmesini sağlamak Kaos Mühendisi'nin sorumluluğu ve yükümlülüğüdür.

Kaos Mühendisliği, dünya çapındaki pek çok çok-büyük ölçekli operasyonda, yazılımın nasıl tasarlandığını değiştirmekte olan güçlü bir uygulamadır. Diğer metotlar hız ve esnekliğe hitap etmekte iken, Kaos, özellikle dağıtık sistemlerde sistemik belirsizliği ele alır. Kaos İlkeleri, kitlesel ölçeklerde hızlı bir şekilde yenilik yapmaya ve müşterilere hak ettikleri yüksek kaliteli deneyimleri vermek üzere sistemlere olan güveni artırmayı hedefler.

Kaos İlkeleri ve bunların uygulamaları üzerine devam eden tartışmalara katılın Google Grubunda [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community).
