# 🛒 Discord E-Commerce Bot

### *Bot Toko Online Interaktif Berbasis Discord dengan Integrasi Maps, Auto-Ongkir, & Tracking Real-Time*

### 🎨 Design & Brainstorming Board

[**👉 KLIK DI SINI UNTUK MEMBUKA MIRO BOARD PROJECT 👈**](https://miro.com/app/board/uXjVERl2LKA=/?share_link_id=218486674026)

*Papan perencanaan proyek memuat Mindmap, User Flow, Diagram Arsitektur, dan Pembagian Tugas Kelompok.*

## 📌 Alur Sistem (User Flow)

```
┌──────────┐     ┌──────────┐     ┌───────────┐     ┌───────────┐     ┌───────────┐
│ /katalog │ ──► │  Pilih   │ ──► │ /keranjang│ ──► │  /lokasi  │ ──► │ /checkout │
│  Produk  │     │  Barang  │     │ Cek Total │     │ Input Map │     │ Modal Form│
└──────────┘     └──────────┘     └───────────┘     └───────────┘     └───────────┘
                                                                            │
                                                                            ▼
                                                                    ┌───────────┐
                                                                    │  /track   │
                                                                    │ Cek Status│
                                                                    └───────────┘
```

## ✨ Fitur Utama

### 🛍️ Untuk Pembeli (Customer)

* 📖 **Katalog Digital Interaktif** – Jelajahi produk menggunakan tampilan **Discord Embed**, foto high-res, deskripsi, harga, dan tombol interaktif (`discord.ui.Button`).
* 🧺 **Manajemen Keranjang Belanja** – Tambah/kurang jumlah pesanan dan kalkulasi subtotal belanja secara otomatis di dalam server.
* 🗺️ **Deteksi Lokasi & Auto-Ongkir** – Mengubah koordinat/link Google Maps menjadi alamat lengkap dan menghitung tarif ongkir berbasis jarak secara presisi.
* 📝 **Form Checkout Pop-Up (Modal)** – Pengisian data penerima (Nama, No HP, Alamat) langsung melalui **Discord Modal Form** interaktif.
* 🧾 **Invoice & Struk Digital** – Penerbitan nomor nota unik (`#INV-xxxx`) dalam format Rich Embed lengkap dengan peta rute pengiriman.
* 🚚 **Tracking Real-time** – Pantau status perjalanan paket pesanan secara langsung melalui Discord Slash Commands.

### 📦 Untuk Admin & Kurir

* 🔔 **Notifikasi Order Channel** – Pesanan baru otomatis masuk ke Channel Discord khusus Admin/Kurir lengkap dengan lokasi penjemputan.
* 🔄 **Manajemen Status Pengiriman** – Perbarui status paket (`Diproses` ➔ `Dikemas` ➔ `Dikirim` ➔ `Selesai`) dengan klik tombol di Discord.
* 📊 **Kelola Stok & Rekap Penjualan** – Kontrol sisa stok barang dan rekapitulasi omset toko langsung dari server Discord.

## 🧰 Teknologi & Library

| Library / Tools | Kegunaan Utama |
| ----- | ----- |
| `discord.py` | Framework Bot Discord Utama (Commands, UI Buttons, Modals) |
| `geopy` | Konversi koordinat lokasi & hitung jarak ongkir |
| `requests` / `aiohttp` | Integrasi API Peta Eksternal secara Asynchronous |
| `json` / `sqlite3` | Penyimpanan database katalog & data transaksi |
| `datetime` & `uuid` | Pencatatan waktu transaksi & generator ID Invoice |
| `Pillow` | Pembuat gambar struk belanja digital (opsional) |

## 💻 Daftar Perintah (Slash Commands)

### 👤 Perintah Pembeli

| Command | Deskripsi |
| ----- | ----- |
| `/start` | Memulai bot & menampilkan menu navigasi utama |
| `/katalog` | Membuka katalog produk dengan tombol pembelian |
| `/keranjang` | Mengatur isi keranjang belanja & melihat total |
| `/lokasi` | Input titik lokasi / koordinat Maps untuk ongkir |
| `/checkout` | Membuka Modal Form pemesan & metode pembayaran |
| `/track` | Melacak status pengiriman pesanan (`#INV-xxxx`) |
| `/batal` | Mengosongkan keranjang atau membatalkan pesanan |

### 🛠️ Perintah Admin & Kurir

| Command | Deskripsi |
| ----- | ----- |
| `/admin` | Membuka Dashboard Admin toko |
| `/tambahproduk` | Menambahkan item produk baru ke katalog |
| `/updatestok` | Memperbarui sisa stok barang |
| `/pesanan` | Melihat antrean pesanan masuk di server |
| `/updatestatus` | Mengubah status paket pengiriman pembeli |
| `/rekap` | Melihat laporan total omset penjualan toko |

## 🚀 Panduan Instalasi & Setup Discord Bot

1. **Clone Repositori Ini**
   ```bash
   git clone https://github.com/username/discord-bot-toko-online.git
   cd discord-bot-toko-online
   ```

2. **Pasang Library Dependencies**
   ```bash
   pip install discord.py geopy requests Pillow
   ```

3. **Konfigurasi Bot Token Discord**
   * Buat aplikasi bot di [Discord Developer Portal](https://discord.com/developers/applications).
   * Aktifkan **Message Content Intent** dan **Server Members Intent**.
   * Masukkan **DISCORD_TOKEN** pada file `.env` atau `config.py`.
   * Siapkan file `data/katalog.json` untuk daftar barang awal.

4. **Jalankan Bot**
   ```bash
   python main.py
   ```

## 📂 Struktur Direktori Project

```text
.
├── 📁 data/
│   ├── katalog.json          # Database produk & stok
│   └── pesanan.json          # Riwayat transaksi
├── 📁 modules/
│   ├── katalog.py            # Discord Embed & View Katalog
│   ├── keranjang.py          # Logika keranjang & kalkulasi
│   ├── maps_ongkir.py        # Geocoding & kalkulator ongkir
│   ├── checkout.py           # Discord Modal Form & Invoice Embed
│   └── tracking.py           # Real-time status tracking
├── 📄 .env.example           # Template variabel DISCORD_TOKEN
├── 📄 main.py                # Entry point aplikasi bot
├── 📄 README.md              # Dokumentasi utama
└── 📄 requirements.txt       # Daftar dependency library
```

---
Dibuat dengan ❤️ untuk Tugas Proyek Pemrograman Python.

[⬆ Kembali ke atas](#-discord-e-commerce-bot)