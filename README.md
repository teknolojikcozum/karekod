🎓 Akıllı Yoklama Sistemi (Google Sheets Entegreli)

Bu proje, öğretmenlerin ve akademisyenlerin yoklama alma sürecini dijitalleştiren, tamamen ücretsiz, sunucusuz (serverless) ve doğrudan Google E-Tablolar (Google Sheets) ile entegre çalışan web tabanlı bir akıllı yoklama sistemidir.

🌟 Öne Çıkan Özellikler

Tamamen Ücretsiz ve Sunucusuz: Veritabanı olarak Google Sheets kullanır. Harici bir veritabanı (Firebase, SQL vb.) maliyeti veya kurulumu gerektirmez.

Dinamik Karekod (Anti-Kopya): Sınıf tahtasına yansıtılan karekod her 10 saniyede bir yenilenir. Öğrenciler karekodun fotoğrafını çekip WhatsApp'tan arkadaşlarına atsalar bile, link 20 saniye içinde geçersiz olur (Uzaktan imza atılamaz).

Cihaz Kilitleme: Bir öğrenci kendi telefonundan imza attığında sistem cihazı kilitler. Aynı telefondan başka bir arkadaşının yerine imza atılamaz.

Canlı Senkronizasyon: Öğrenciler imza attıkça liste öğretmen ekranına anlık olarak (5 saniyede bir) düşer ve sesli bildirim verir.

Devamsızları Bulma: Sınıfın tam listesini Excel'den yükleyerek veya kopyala/yapıştır yaparak sisteme girebilirsiniz. Sistem imza atanlarla tam listeyi karşılaştırıp gelmeyenleri otomatik bulur.

Excel (.xlsx) Çıktısı Alma: Alınan yoklama listesi veya devamsızlık listesi tek tıkla düzenli bir Excel dosyası olarak indirilebilir.

Manuel Kişi Ekleme: Şarjı biten veya interneti çekmeyen öğrenciler, öğretmen tarafından manuel olarak listeye eklenebilir.

Güvenli Çıkış: Sayfa kapatıldığında veya çıkış yapıldığında hocanın Excel bağlantısı cihaz hafızasından güvenli bir şekilde silinir.

🛠️ Kullanılan Teknolojiler

Frontend: HTML5, Vanilla JavaScript, Tailwind CSS (CDN)

İkonlar: Lucide Icons

Karekod İşlemleri: QRCode.js

Excel İşlemleri (İçe/Dışa Aktarma): SheetJS (xlsx)

Backend / Veritabanı: Google Apps Script (GAS) & Google Sheets

🚀 Kurulum ve Kullanım (Öğretmenler İçin)

Sistemi kullanmak son derece basittir. Herhangi bir kodlama bilginize gerek yoktur.

Boş Bir Excel Oluşturun:

Google Drive'ınıza girin ve boş bir Google E-Tablo (Google Sheets) oluşturun.

Tablonun sağ üst köşesindeki "Paylaş" butonuna tıklayın.

Genel erişim iznini "Bağlantıya sahip olan herkes" ve rolü "Düzenleyen" olarak ayarlayın.

Sisteme Bağlanın:

Yoklama sistemi web sayfasına giriş yapın.

Sol üst köşedeki Ayarlar (Dişli Çark) ikonuna tıklayın.

Google E-Tablo'nuzun linkini (tarayıcının en üstündeki adres çubuğundan kopyalayarak) buraya yapıştırın ve kaydedin.

Yoklamayı Başlatın:

Bir Ders Adı ve Süre seçip "Karekodu Göster" butonuna basın.

Karekodu sınıfın görebileceği şekilde yansıtın (Gerekirse 'Tam Ekran Yap' butonunu kullanın).

Süre bitiminde Excel tablonuzda tüm kayıtların otomatik olarak listelendiğini göreceksiniz.

💻 Geliştirici Notları (Sistem Yöneticisi İçin)

Sistem, tüm öğretmenlerin kendi tablolarına veri yazabilmesi için bir "Ana Dağıtıcı (Master GAS)" script'i üzerinden çalışmaktadır.

Uygulamanın çalışabilmesi için index.html dosyası içindeki MASTER_GAS_URL sabitine, sistem yöneticisi tarafından oluşturulmuş ve "Herkes" (Anyone) erişimine açık olarak dağıtılmış (Deploy edilmiş) Google Apps Script Web App URL'si girilmelidir.

// index.html içindeki ilgili alan
const MASTER_GAS_URL = "[https://script.google.com/macros/s/SİZİN_SCRIPT_URL_NİZ/exec](https://script.google.com/macros/s/SİZİN_SCRIPT_URL_NİZ/exec)"; 


Ana Dağıtıcı (GAS) Kodunun Temel İşlevleri:

Gelen istekteki sheetId parametresini alarak ilgili öğretmenin tablosuna bağlanır.

CORS (Cross-Origin Resource Sharing) hatalarını önlemek için POST isteklerini text/plain olarak karşılar ve parse eder.

Yinelenen kayıt (Duplicate) kontrolü yapar.

CRUD (Create, Read, Update, Delete) işlemlerini ilgili tablo üzerinde gerçekleştirir.

📱 Ekran Görüntüleri ve Tasarım

Sistem tamamen duyarlı (responsive) bir tasarıma sahiptir.

Öğrenci Ekranı: Mobil cihazlarda kusursuz görünen, "Beni Hatırla" özelliği sayesinde ikinci derste numarayı otomatik dolduran basit bir form.

Öğretmen Ekranı: Geniş ekranlarda yoklama durumunu, karekodu ve anlık listeyi yan yana sunan modern bir kontrol paneli.

Geliştirildi ve açık kaynak / ücretsiz kullanıma uygun olarak tasarlandı.
