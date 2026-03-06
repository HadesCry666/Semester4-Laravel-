# 🏡 Sistem Informasi Pengajuan Surat Desa

Aplikasi **Sistem Informasi Pengajuan Surat Desa** merupakan platform berbasis **web** yang dirancang untuk mempermudah masyarakat dalam melakukan pengajuan surat administrasi desa secara online.

Aplikasi ini bertujuan untuk membantu proses pelayanan administrasi desa agar menjadi lebih **cepat, transparan, dan terorganisir**, serta mempermudah perangkat desa dalam mengelola dan memverifikasi pengajuan surat dari masyarakat.

Melalui sistem ini, masyarakat dapat melakukan pengajuan berbagai jenis surat secara digital tanpa harus datang langsung ke kantor desa, sementara pihak **RT, RW, dan Admin Desa** dapat melakukan proses verifikasi dan pengelolaan data secara terpusat.

Project ini juga dikembangkan sebagai bagian dari **pengembangan portfolio developer** dan pembelajaran dalam membangun aplikasi **web berbasis Laravel**.

---


# 📸 Application Preview

![Poster](images/poster.png)

---
# 🚀 Features

Beberapa fitur utama dalam aplikasi ini antara lain:

### 📝 Pengajuan Surat Online
Masyarakat dapat mengajukan berbagai jenis surat administrasi desa secara online melalui sistem.

### 📂 Manajemen Master Surat
Admin dapat mengelola jenis-jenis surat yang tersedia beserta persyaratan yang dibutuhkan.

### 👨‍👩‍👧‍👦 Data Penduduk
Sistem menyediakan pengelolaan data penduduk yang digunakan untuk proses pengajuan surat.

### ✔️ Verifikasi RT dan RW
Setiap pengajuan surat akan melalui proses **verifikasi oleh RT dan RW** sebelum diproses oleh admin desa.

### 📊 Dashboard Monitoring
Dashboard menampilkan ringkasan data seperti jumlah pengajuan surat, status pengajuan, dan aktivitas sistem.

### 📄 Riwayat Pengajuan
Pengguna dapat melihat riwayat pengajuan surat yang telah dilakukan beserta statusnya.

### 🖨️ Cetak Surat
Admin desa dapat mencetak surat yang telah disetujui langsung dari sistem.

### 🔐 Sistem Login Multi Role
Sistem memiliki beberapa role pengguna seperti:
- Admin Desa
- Ketua RW
- Ketua RT
- Warga

---

# 🛠 Tech Stack

Teknologi yang digunakan dalam pengembangan aplikasi ini:

| Technology | Description |
|-----------|-------------|
| PHP | Bahasa pemrograman backend |
| Laravel | Framework backend |
| MySQL | Database management system |
| HTML5 | Struktur halaman web |
| CSS3 | Styling halaman |
| JavaScript | Interaktivitas pada website |
| Bootstrap | Framework UI |

---

# 📂 Project Structure

Struktur folder utama pada project:

```
sistem-informasi-desa
│
├── app
├── bootstrap
├── config
├── database
├── public
├── resources
│   ├── views
│   ├── css
│   └── js
├── routes
├── storage
└── README.md
```

---

# ⚙️ Installation

Ikuti langkah berikut untuk menjalankan project secara lokal.

### 1. Clone repository

```
git clone https://github.com/username/sistem-informasi-desa.git
```

### 2. Masuk ke folder project

```
cd sistem-informasi-desa
```

### 3. Install dependency

```
composer install
```

### 4. Copy file environment

```
cp .env.example .env
```

### 5. Setup database

Buat database baru di MySQL, lalu sesuaikan konfigurasi database pada file `.env`.

```
DB_DATABASE=nama_database
DB_USERNAME=root
DB_PASSWORD=
```

### 6. Generate application key

```
php artisan key:generate
```

### 7. Jalankan migration

```
php artisan migrate
```

### 8. Jalankan server

```
php artisan serve
```

### 9. Akses aplikasi

```
http://localhost:8000
```

---

# 📸 Application Preview

Tambahkan screenshot aplikasi pada folder `images`.

```
![Dashboard](images/dashboard.png)
![Pengajuan Surat](images/pengajuan.png)
![Verifikasi RT RW](images/verifikasi.png)
```

---

# 🎯 Project Goals

Tujuan utama dari pengembangan aplikasi ini:

- Mempermudah proses pengajuan surat administrasi desa
- Mengurangi proses administrasi manual
- Mempercepat proses verifikasi RT dan RW
- Meningkatkan efisiensi pelayanan publik desa
- Mengembangkan keterampilan pengembangan aplikasi web menggunakan Laravel

---
