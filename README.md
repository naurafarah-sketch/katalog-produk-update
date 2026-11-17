# Katalog Produk UPI Store (JavaFX CRUD Desktop App)

Aplikasi desktop manajemen katalog produk berbasis **JavaFX**, **Maven**, dan **SQLite** dengan pola arsitektur **Model-View-Controller (MVC)** serta lapisan **Repository**. Aplikasi ini memungkinkan pengguna untuk menambahkan, menampilkan, memperbarui, dan menghapus data produk dalam tampilan grid kartu interaktif.

---

## Fitur Utama

* **Tambah Produk (Create):** Menambahkan produk baru dengan input nama produk, harga (bilangan bulat positif), dan pilihan foto produk (`roti.png`, `susu.png`, `kopi.png`) ke dalam database SQLite.
* **Tampilan Katalog Berbasis Kartu (Read):** Menampilkan seluruh produk dari database ke dalam komponen `TilePane` berbentuk kartu visual lengkap dengan gambar, nama, harga, ID produk, serta penghitung total jumlah produk secara otomatis.
* **Ubah Data Produk (Update):** Mengklik salah satu kartu produk pada katalog akan menyorot kartu dengan bingkai biru, mengisi form input secara otomatis sesuai data produk terpilih, dan mengaktifkan tombol **Update** untuk menyimpan perubahan ke database.
* **Hapus Produk dengan Konfirmasi (Delete):** Menghapus data produk terpilih disertai dialog konfirmasi (`Alert.AlertType.CONFIRMATION`) untuk mencegah penghapusan data secara tidak sengaja.
* **Validasi Input & Reset Form:** Memvalidasi kekosongan teks serta format angka pada kolom harga, serta menyediakan tombol **Batal** untuk membersihkan form dan mengembalikan mode input ke mode tambah produk baru.

---

## Tampilan Aplikasi

> **Catatan Penempatan Gambar:** Pastikan file tangkapan layar disimpan di dalam folder `screenshots/` pada direktori utama proyek agar tampil otomatis di halaman repositori GitHub.

### 1. Halaman Utama & Katalog Produk
![Tampilan Utama Katalog Produk](screenshots/tampilan-utama.png)

### 2. Mode Edit / Seleksi Kartu Produk (Update & Delete Aktif)
![Seleksi Kartu dan Fitur Update](screenshots/fitur-update.png)

### 3. Dialog Konfirmasi Hapus Produk
![Konfirmasi Hapus Produk](screenshots/fitur-delete.png)

---

## Teknologi yang Digunakan

* **Bahasa Pemrograman:** Java (JDK 17 / JDK 21)
* **Framework GUI:** JavaFX (`javafx-controls`, `javafx-fxml`)
* **Build Tool:** Apache Maven
* **Database:** SQLite (`sqlite-jdbc`)
* **IDE:** Apache NetBeans IDE & Scene Builder

---

## Struktur Proyek

```text
KatalogProduk/
├── data/
│   └── katalog.db                          # File database SQLite lokal
├── screenshots/
│   ├── tampilan-utama.png                  # Screenshot tampilan awal katalog
│   ├── fitur-update.png                    # Screenshot saat kartu produk dipilih
│   └── fitur-delete.png                    # Screenshot konfirmasi penghapusan
├── src/
│   └── main/
│       ├── java/
│       │   ├── controller/
│       │   │   └── KatalogController.java  # Logika UI, event klik kartu, & aksi CRUD
│       │   ├── data/
│       │   │   └── ProdukRepository.java   # Query SQL (INSERT, SELECT, UPDATE, DELETE)
│       │   ├── db/
│       │   │   └── Database.java           # Konfigurasi koneksi & inisialisasi tabel SQLite
│       │   ├── main/
│       │   │   └── MainApp.java            # Entry point aplikasi JavaFX
│       │   └── model/
│       │       └── Produk.java             # Model data entitas Produk & validasi atribut
│       └── resources/
│           ├── image/
│           │   ├── kopi.png                # Aset gambar produk kopi
│           │   ├── roti.png                # Aset gambar produk roti
│           │   └── susu.png                # Aset gambar produk susu
│           └── view/
│               ├── katalog.fxml            # Struktur tata letak antarmuka FXML
│               └── styles/
│                   └── app.css             # Styling komponen tombol dan kartu produk
├── .gitignore
├── pom.xml                                 # Konfigurasi dependensi Maven & JavaFX
└── README.md
