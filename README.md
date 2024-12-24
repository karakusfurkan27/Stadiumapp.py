# Stadium App - README

## Genel Bakış

**Stadium App** (Stadyum Uygulaması), bir stadyum için koltuk yönetimi ve bilet rezervasyonu yapmayı sağlayan Python tabanlı bir grafiksel kullanıcı arayüzü (GUI) uygulamasıdır. Uygulama, kullanıcıların farklı kategorilerden bir takım seçmelerine, koltuk rezervasyonu yapmalarına ve rezervasyon raporu oluşturmasına olanak tanır. Ayrıca, SQLite veritabanı kullanarak rezervasyon verilerini depolar ve yönetir.

### Özellikler:
1. **Admin Girişi**: Admin özelliklerine erişim için güvenli giriş ekranı.
2. **Takım Seçimi**: Farklı kategorilerden (Türkiye, Avrupa Milli Takımları, Avrupa Kulüpleri) bir takım seçme.
3. **Koltuk Rezervasyonu**: Müşteriler için koltuk rezervasyonu yapma, müşteri adı, bilet fiyatı ve seçilen takım bilgilerini girme.
4. **Koltuk Yönetimi**: Koltuk düzenini dinamik olarak ayarlama ve sıfırlama.
5. **Rezervasyon Raporu**: Yapılan tüm rezervasyonların raporunu oluşturma ve görüntüleme.
6. **SQLite Veritabanı Entegrasyonu**: Rezervasyon verilerini yerel SQLite veritabanında depolama ve alma.

## Gereksinimler

Bu uygulamayı çalıştırmak için aşağıdaki yazılımların bilgisayarınızda kurulu olması gerekmektedir:
- **Python 3.x** veya üstü
- **Tkinter**: Python'un standart GUI kütüphanesi (Python ile birlikte genellikle yüklüdür).
- **SQLite3**: Python ile gelen yerleşik veritabanı (zaten Python ile birlikte gelir).

## Kurulum

1. Projeyi klonlayın veya indirin.
2. Python 3.x'in bilgisayarınızda kurulu olduğundan emin olun.
3. Gerekli Python paketlerini yükleyin (eğer zaten kurulu değilse):
   ```bash
   pip install tkinter
   ```
4. Uygulamayı başlatmak için şu komutu çalıştırın:
   ```bash
   python stadiumapp.py
   ```

## Kullanım

1. **Giriş Yapma**:  
   Uygulama başlatıldığında admin, bir şifre girmesi için uyarılır. Varsayılan şifre `admin`'dir. Doğru şifre girildiğinde, uygulamanın ana özelliklerine erişim sağlanır.

2. **Takım Seçimi**:  
   Giriş yaptıktan sonra, bir takım kategorisi seçebilirsiniz (Türkiye, Avrupa Milli Takımları, Avrupa Kulüpleri). Uygulama, şampiyonluk sayılarıyla birlikte takımların listesini gösterir. Herhangi bir takımı seçerek detaylarını görüntüleyebilirsiniz.

3. **Koltuk Yapılandırması**:  
   Koltuk düzenini, satır sayısı ve her satırdaki koltuk sayısını belirleyerek yapılandırabilirsiniz. Bu, dinamik bir buton ızgarası oluşturur.

4. **Koltuk Rezervasyonu**:  
   Bir koltuğu rezerve etmek için, mevcut olan (yeşil) koltuklardan birine tıklayın. Müşteri adı, bilet fiyatı ve takım bilgilerini girmeniz istenecektir. Rezervasyon yapıldıktan sonra, koltuk "Booked" (Rezerve Edildi) olarak işaretlenecektir.

5. **Tüm Koltukları Sıfırlama**:  
   "Tümünü Sıfırla" butonu, tüm koltukları sıfırlayarak tüm koltukları yeniden rezerve edilebilir hale getirir.

6. **Rezervasyon Raporu Görüntüleme**:  
   "Raporu Göster" butonuna tıklayarak yapılan tüm rezervasyonların detaylı raporunu oluşturabilirsiniz. Rapor, müşteri adı, bilet fiyatı ve ilgili takımla birlikte gösterilecektir.

## Veritabanı Yapısı

Uygulama, SQLite veritabanı (`stadium.db`) kullanarak rezervasyon bilgilerini depolar. `bookings` tablosunun aşağıdaki alanları vardır:
- **id**: Otomatik artan birincil anahtar
- **row**: Rezerve edilen koltuğun satır numarası
- **seat**: Satırdaki koltuk numarası
- **customer_name**: Koltuğu rezerve eden müşteri adı
- **price**: Bilet fiyatı
- **team**: Rezervasyona ilişkin takım

## Ekran Görüntüleri

- **Giriş Ekranı**  
  Admin girişi için şifre giriş ekranı.

- **Takım Seçim Ekranı**  
  Takım kategorisini seçmek için bir açılır menü ve her takımın şampiyonluk sayılarıyla birlikte listesi.

- **Koltuk Yapılandırma Ekranı**  
  Satır ve koltuk sayısını girerek koltuk düzeni ayarlama.

- **Koltuk Rezervasyon Ekranı**  
  Koltukların bir ızgarasını gösterir, her bir koltuğa tıklanarak müşteri rezervasyonu yapılabilir.

## Hata Ayıklama

- **Geçersiz Giriş**: Admin şifresi yanlış girildiğinde, tekrar denemek için hata mesajı gösterilecektir.
- **Koltuk Zaten Rezerve Edilmiş**: Eğer bir koltuk zaten rezerve edilmişse, rezervasyon yapmaya çalıştığınızda bir uyarı mesajı görüntülenir.

## Katkı

Projeyi çatallayabilir, pull request göndererek katkıda bulunabilir veya bulduğunuz sorunları rapor edebilirsiniz.

## Lisans

Bu proje, MIT Lisansı altında lisanslanmıştır. Detaylar için LICENSE dosyasına bakabilirsiniz.

---

Bu README ile **Stadium App** uygulamasını kullanabilir ve stadyum ortamındaki koltuk yönetimi ve bilet rezervasyonunu etkili bir şekilde yapabilirsiniz.
