# 🗄️ DatabaseJava — CRUD Application with Java Swing & MySQL

<div align="center">

![Java](https://img.shields.io/badge/Java-JDK%2017-orange?style=for-the-badge&logo=java)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue?style=for-the-badge&logo=mysql)
![Maven](https://img.shields.io/badge/Maven-Build%20Tool-red?style=for-the-badge&logo=apachemaven)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)

**Aplikasi desktop CRUD berbasis Java Swing yang terhubung dengan MySQL Database menggunakan JDBC.**

</div>

---

## 👤 Identitas

| Field | Detail |
|-------|--------|
| **Nama** | Muhammad Fikri |
| **NIM** | I.1510162 |
| **Mata Kuliah** | Bahasa Pemrograman 1 / Pemrograman Berorientasi Objek (OOP) |

---

## 📖 Deskripsi Proyek

Proyek ini merupakan implementasi **CRUD (Create, Read, Update, Delete)** menggunakan **Java Swing** dengan integrasi **MySQL Database**.

Tujuan utama dari aplikasi ini adalah:
- Membuat antarmuka GUI yang interaktif untuk pengelolaan data.
- Menghubungkan aplikasi desktop dengan database MySQL menggunakan **JDBC**.
- Melatih konsep **Object-Oriented Programming (OOP)** dalam pengembangan aplikasi nyata.

---

## ✨ Fitur Utama

| Fitur | Deskripsi |
|-------|-----------|
| ➕ **Tambah Data** | Form input dengan validasi sebelum menyimpan ke database |
| 📋 **Lihat Data** | Tabel interaktif dengan refresh otomatis setiap ada perubahan |
| ✏️ **Edit Data** | Update record langsung dari GUI tanpa perlu query manual |
| 🗑️ **Hapus Data** | Delete record dengan dialog konfirmasi |
| 🔌 **Koneksi Database** | Menggunakan JDBC untuk integrasi langsung ke MySQL |

---

## 🛠️ Teknologi yang Digunakan

- **Java** — JDK 17
- **Java Swing** — GUI Framework
- **MySQL** — Relational Database
- **JDBC** — Java Database Connectivity
- **Maven** — Project & Dependency Management

---

## 📋 Prasyarat

Sebelum menjalankan program, pastikan kamu sudah menginstall:

- ✅ [JDK 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html) atau lebih baru
- ✅ [MySQL Server](https://dev.mysql.com/downloads/mysql/) (versi 8.0 disarankan)
- ✅ [Apache Maven](https://maven.apache.org/download.cgi)
- ✅ IDE seperti [IntelliJ IDEA](https://www.jetbrains.com/idea/) atau [NetBeans](https://netbeans.apache.org/)

---

## ▶️ Cara Menjalankan Program

### 1. Clone Repository

```bash
git clone https://github.com/username/DatabaseJava_MuhammadFikri_I.2510162.git
cd DatabaseJava_MuhammadFikri_I.2510162
```

### 2. Setup Database MySQL

Buka MySQL client atau tools seperti HeidiSQL / DBeaver, lalu jalankan script berikut:

```sql
CREATE DATABASE IF NOT EXISTS db_java;
USE db_java;

CREATE TABLE IF NOT EXISTS data_mahasiswa (
    id         INT PRIMARY KEY AUTO_INCREMENT,
    nama       VARCHAR(100) NOT NULL,
    nim        VARCHAR(20)  NOT NULL UNIQUE,
    jurusan    VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

> ⚠️ Sesuaikan nama tabel dan kolom dengan struktur yang dipakai di proyek kamu.

### 3. Konfigurasi Koneksi Database

Buka file konfigurasi koneksi (biasanya `DBConnection.java` atau `config.properties`) dan sesuaikan:

```java
private static final String URL      = "jdbc:mysql://localhost:3306/db_java";
private static final String USER     = "root";
private static final String PASSWORD = "password_kamu";
```

### 4. Build dengan Maven

```bash
mvn clean install
```

### 5. Jalankan Aplikasi

```bash
mvn exec:java -Dexec.mainClass="com.namapackage.Main"
```

Atau langsung run dari IDE dengan klik kanan pada file `Main.java` → **Run**.

---

## 📁 Struktur Proyek

```
DatabaseJava_MuhammadFikri_I.2510162/
├── src/
│   └── main/
│       └── java/
│           └── com/namapackage/
│               ├── Main.java           # Entry point aplikasi
│               ├── view/
│               │   └── MainFrame.java  # GUI utama (JFrame)
│               ├── controller/
│               │   └── DataController.java
│               ├── model/
│               │   └── DataModel.java
│               └── database/
│                   └── DBConnection.java  # Konfigurasi JDBC
├── Image/
│   └── Gambar.jpg                      # Screenshot aplikasi
├── pom.xml                             # Maven config
└── README.md
```

---

## 🖼️ Screenshot Aplikasi

![Screenshot Aplikasi](Image/Gambar.jpg)

---

## 🚀 Cara Penggunaan

1. **Tambah Data** — Isi form input yang tersedia, lalu klik tombol **Simpan**.
2. **Lihat Data** — Data akan otomatis tampil di tabel setelah disimpan.
3. **Edit Data** — Pilih baris di tabel, data akan muncul di form, ubah lalu klik **Update**.
4. **Hapus Data** — Pilih baris di tabel, klik **Hapus**, konfirmasi dialog yang muncul.

---

## ⚠️ Troubleshooting

| Masalah | Solusi |
|---------|--------|
| `Communications link failure` | Pastikan MySQL Server sudah berjalan |
| `Access denied for user 'root'` | Periksa username & password di `DBConnection.java` |
| `Unknown database` | Pastikan database sudah dibuat sesuai langkah setup |
| `ClassNotFoundException: com.mysql.jdbc.Driver` | Tambahkan MySQL Connector dependency di `pom.xml` |

### Dependency MySQL Connector (pom.xml)

```xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <version>8.0.33</version>
</dependency>
```

---

## 📄 Lisensi

Proyek ini dibuat untuk keperluan **tugas akademik**. Bebas digunakan sebagai referensi belajar.

---

<div align="center">
  <strong>Muhammad Fikri</strong> — I.1510162<br>
  <sub>
    🔗 <a href="https://github.com/fiksdevploper">GitHub</a> ·
    💼 <a href="https://www.linkedin.com/in/muhammad-fikri-b3766a2b1/?skipRedirect=true">LinkedIn</a>
  </sub>
</div>
