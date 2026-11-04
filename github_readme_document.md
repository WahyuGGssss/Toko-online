<div align="center">

# 🛒 Python E-Commerce Bot
### *Bot Toko Online Interaktif dengan Integrasi Maps, Auto-Ongkir, & Tracking Real-Time*

![Python Version](https://img.shields.io/badge/python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Framework](https://img.shields.io/badge/telegram-python--telegram--bot-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)
![Geopy](https://img.shields.io/badge/maps-Geopy--API-green?style=for-the-badge&logo=googlemaps&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-orange?style=for-the-badge)

---

### 🎨 Design & Brainstorming Board
**[👉 KLIK DI SINI UNTUK MEMBUKA MIRO BOARD PROJECT 👈](https://miro.com/app/board/uXjVERl2LKA=/?share_link_id=218486674026)**

*Papan perencanaan proyek memuat Mindmap, User Flow, Diagram Arsitektur, dan Pembagian Tugas Kelompok.*

---

</div>

## 📌 Alur Sistem (User Flow)

```text
┌──────────┐     ┌──────────┐     ┌───────────┐     ┌───────────┐     ┌───────────┐
│ /katalog │ ──► │  Pilih   │ ──► │ /keranjang│ ──► │  /lokasi  │ ──► │ /checkout │
│  Produk  │     │  Barang  │     │ Cek Total │     │ Share Map │     │ Cetak Nota│
└──────────┘     └──────────┘     └───────────┘     └───────────┘     └───────────┘
                                                                            │
                                                                            ▼
                                                                    ┌───────────┐
                                                                    │  /track   │
                                                                    │ Cek Status│
                                                                    └───────────┘
```

---

## ✨ Fitur Utama

### 🛍️ Untuk Pembeli (Customer)
* 📖 **Katalog Digital Interaktif** – Jelajahi produk dengan foto, deskripsi, harga, dan indikator sisa stok.
* 🧺 **Manajemen Keranjang** – Tambah/kurang jumlah pesanan dan kalkulasi total belanja secara instan.
* 🗺️ **Deteksi Lokasi & Auto-Ongkir** – Mengubah *share location* pengguna menjadi alamat jalan dan menghitung ongkir berbasis jarak secara presisi.
* 📝 **Form Checkout Modal** – Pengisian data penerima secara cepat melalui formulir interaktif.
* 🧾 **Invoice & Struk Digital** – Penerbitan nomor nota unik (`#INV-xxxx`) lengkap dengan peta rute pengiriman.
* 🚚 **Tracking Real-time** – Pantau status perjalanan barang dari diproses hingga sampai ke lokasi.

### 📦 Untuk Admin & Kurir
* 🔔 **Notifikasi Order Masuk** – Pesanan baru otomatis diteruskan ke grup admin lengkap dengan lokasi titik penjemputan.
* 🔄 **Manajemen Status Pengiriman** – Perbarui status (`Diproses` ➔ `Dikemas` ➔ `Dikirim` ➔ `Selesai`).
* 📊 **Kelola Stok & Rekap Penjualan** – Kontrol sisa stok barang dan rekapitulasi omset toko.

---

## 🧰 Teknologi & Library

| Library / Tools | Kegunaan Utama |
| :--- | :--- |
| `python-telegram-bot` | Framework bot Telegram utama |
| `discord.py` | Framework bot Discord (opsional) |
| `geopy` | Konversi koordinat lokasi & hitung jarak ongkir |
| `requests` / `aiohttp` | Integrasi API Peta Eksternal |
| `json` / `sqlite3` | Penyimpanan database katalog & pesanan |
| `datetime` & `uuid` | Pencatatan waktu transaksi & generator ID Nota |
| `Pillow` | Pembuat gambar struk belanja digital |

---

## 💻 Daftar Perintah (Commands)

### 👤 Perintah Pembeli
| Command | Deskripsi |
| :--- | :--- |
| `/start` | Memulai bot & menampilkan menu utama |
| `/katalog` | Membuka katalog produk & stok |
| `/keranjang` | Mengatur isi keranjang belanja |
| `/lokasi` | Mengirimkan titik Maps untuk ongkir |
| `/checkout` | Mengisi form pemesan & memilih pembayaran |
| `/track` | Melacak status pengiriman pesanan |
| `/batal` | Mengosongkan keranjang atau pembatalan |

### 🛠️ Perintah Admin & Kurir
| Command | Deskripsi |
| :--- | :--- |
| `/admin` | Membuka Dashboard Admin |
| `/tambahproduk` | Menambahkan item produk baru |
| `/updatestok` | Memperbarui jumlah stok barang |
| `/pesanan` | Melihat antrean pesanan masuk |
| `/updatestatus` | Mengubah status paket pengiriman |
| `/rekap` | Melihat laporan penjualan toko |

---

## 🚀 Panduan Instalasi

1. **Clone Repositori Ini**
   ```bash
   git clone https://github.com/username/bot-toko-online.git
   cd bot-toko-online
   ```

2. **Pasang Library Dependencies**
   ```bash
   pip install python-telegram-bot geopy requests Pillow
   ```

3. **Konfigurasi Environment**
   * Masukkan **BOT_TOKEN** pada file `.env` atau `config.py`.
   * Siapkan file `data/katalog.json` untuk daftar barang awal.

4. **Jalankan Bot**
   ```bash
   python main.py
   ```

---

## 📂 Struktur direktori Project

```text
.
├── 📁 data/
│   ├── katalog.json          # File database produk
│   └── pesanan.json          # Riwayat transaksi
├── 📁 modules/
│   ├── katalog.py            # Logic katalog & stok
│   ├── keranjang.py          # Logic keranjang & total
│   ├── maps_ongkir.py        # Geocoding & kalkulator ongkir
│   ├── checkout.py           # Modal form & invoice
│   └── tracking.py           # Real-time tracking
├── 📄 .gitignore
├── 📄 main.py                # Entry point aplikasi bot
├── 📄 README.md              # Dokumentasi utama
└── 📄 requirements.txt       # Daftar dependency library
```

---

<div align="center">

Dibuat dengan ❤️ untuk Tugas Proyek Pemrograman Python.

[⬆ Kembali ke atas](#-python-e-commerce-bot)

</div>