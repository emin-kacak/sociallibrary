# Social Library

Kullanıcıların kişisel kitap ve film kütüphaneleri oluşturabildiği, içerikleri puanlayıp yorumlayabildiği ve sosyal akış üzerinden paylaşım yapabildiği web tabanlı bir sosyal platform.

## Özellikler

### Kullanıcı Sistemi
- Kayıt ol / giriş yap (e-posta + şifre)
- Şifre sıfırlama (e-posta ile link)
- Profil sayfası: avatar, biyografi düzenleme
- Kullanıcı takip et / takipten çık

### Sosyal Akış (Feed)
- Takip edilen kullanıcıların aktivitelerini gösteren zaman tüneli
- Aktivite kartları: kim, ne yaptı, hangi içerik — görsel ve zengin içerikle
- Puanlama ve yorum aktiviteleri ayrı görsel bileşenlerle gösterilir
- Sayfalandırma: sonsuz kaydırma veya "Daha Fazla Yükle"
- Aktivitelere beğen ve yorum yapma

### İçerik Keşfi & Arama
- Kitap ve film adı ile arama
- En yüksek puanlılar ve en popüler içerikler vitrini
- Tür, yıl ve puana göre gelişmiş filtreleme

### İçerik Detay Sayfası
- Tam meta veri: kapak, özet, yıl, yönetmen/yazar, tür, süre/sayfa sayısı
- Platform ortalama puanı ve toplam oy sayısı
- 1-10 arası kullanıcı puanlama bileşeni
- Kütüphane butonları:
  - Kitap: "Okudum" / "Okunacak"
  - Film: "İzledim" / "İzlenecek"
- Özel listeye ekleme
- Kullanıcı yorumları: listeleme, ekleme, düzenleme, silme

### Kütüphanem (Profil)
- Sekmeli kütüphane: İzlediklerim, İzlenecekler, Okuduklarım, Okunacaklar
- Özel koleksiyonlar oluşturma (örn. "En İyi Bilim Kurgu Filmlerim")
- Son aktiviteler (yorumlar ve puanlamalar)

## Teknolojiler

| Katman | Teknoloji |
|--------|-----------|
| Backend | Java 21, Spring Boot 3.5.8 |
| ORM | Spring Data JPA / Hibernate |
| Veritabanı | MySQL 8 |
| API | RESTful |
| Yardımcı | Lombok, Maven |
| Harici API | TMDb (filmler), Google Books / Open Library (kitaplar) |

## Gereksinimler

- Java 21+
- Maven 3.8+
- MySQL 8+
- TMDb API anahtarı
- Google Books API anahtarı (opsiyonel)

## Kurulum

### 1. Projeyi klonla

```bash
git clone https://github.com/KULLANICI_ADIN/sociallibrary.git
cd sociallibrary
```

### 2. Veritabanını oluştur

```sql
CREATE DATABASE sociallibrary CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

### 3. Uygulama ayarlarını yapılandır

`src/main/resources/application.properties` dosyasını düzenle:

```properties
spring.application.name=sociallibrary

spring.datasource.url=jdbc:mysql://localhost:3306/sociallibrary
spring.datasource.username=YOUR_DB_USER
spring.datasource.password=YOUR_DB_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=false

# TMDb API
tmdb.api.key=YOUR_TMDB_API_KEY

# Google Books API
google.books.api.key=YOUR_GOOGLE_BOOKS_API_KEY
```

> Gerçek API anahtarlarını ve şifreleri asla GitHub'a commit etme. `.env` dosyası veya environment variable kullan.

### 4. Projeyi çalıştır

**Spring Tools Suite (STS) / Eclipse:**
1. `File > Import > Existing Maven Projects` ile projeyi aç
2. `SociallibraryApplication.java` dosyasına sağ tıkla
3. `Run As > Spring Boot App` seç

**Maven CLI:**
```bash
./mvnw spring-boot:run
```

**Windows:**
```cmd
mvnw.cmd spring-boot:run
```

Uygulama `http://localhost:8080` adresinde çalışır.

## Harici API Entegrasyonları

### TMDb (Film verileri)
- Film başlığı, özet, yayın yılı, yönetmen, oyuncular, türler, poster URL
- API Dokümanı: https://developer.themoviedb.org/docs

### Google Books / Open Library (Kitap verileri)
- Kitap başlığı, yazar(lar), açıklama, sayfa sayısı, kapak görseli
- Google Books: https://developers.google.com/books/docs/v1/using
- Open Library: https://openlibrary.org/developers/api

## Proje Yapısı

```
sociallibrary/
├── src/
│   ├── main/
│   │   ├── java/com/sociallibrary/
│   │   │   ├── SociallibraryApplication.java
│   │   │   ├── controller/
│   │   │   ├── service/
│   │   │   ├── repository/
│   │   │   ├── model/
│   │   │   └── dto/
│   │   └── resources/
│   │       └── application.properties
│   └── test/
├── pom.xml
└── README.md
```


