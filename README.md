# Social Library

Spring Boot ile geliştirilmiş sosyal kütüphane backend uygulaması.

## Teknolojiler

- **Java 21**
- **Spring Boot 3.5.8**
- **Spring Data JPA**
- **Spring Web (REST API)**
- **MySQL**
- **Lombok**
- **Maven**

## Gereksinimler

- Java 21+
- Maven 3.8+
- MySQL 8+

## Kurulum

### 1. Veritabanı Hazırlığı

MySQL'de bir veritabanı oluşturun:

```sql
CREATE DATABASE sociallibrary;
```

### 2. Uygulama Ayarları

`src/main/resources/application.properties` dosyasını kendi ortamınıza göre düzenleyin:

```properties
spring.application.name=sociallibrary

spring.datasource.url=jdbc:mysql://localhost:3306/sociallibrary
spring.datasource.username=YOUR_DB_USER
spring.datasource.password=YOUR_DB_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

> **Not:** `application.properties` dosyanızı asla GitHub'a şifre ile birlikte atmayın. Gerçek credentials için `.env` veya environment variable kullanın.

### 3. Projeyi Çalıştırma

**Spring Tools Suite (STS) / Eclipse ile:**
1. Proje klasörünü `File > Import > Existing Maven Projects` ile içe aktarın
2. `SociallibraryApplication.java` dosyasına sağ tıklayın
3. `Run As > Spring Boot App` seçin

**Maven CLI ile:**
```bash
./mvnw spring-boot:run
```

**Windows:**
```cmd
mvnw.cmd spring-boot:run
```

Uygulama varsayılan olarak `http://localhost:8080` adresinde çalışır.

## Proje Yapısı

```
sociallibrary/
├── src/
│   ├── main/
│   │   ├── java/com/sociallibrary/
│   │   │   └── SociallibraryApplication.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/com/sociallibrary/
│           └── SociallibraryApplicationTests.java
├── pom.xml
└── README.md
```


