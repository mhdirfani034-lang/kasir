# TokoKita - Web POS dengan Pembayaran Online

Tugas Rekayasa Perangkat Lunak - Kelompok Transistor, Teknik Informatika, Universitas Jabal Ghafur.

| Nama | NPM |
|---|---|
| Teuku Zaki Irfan | 24105111128 |
| Rafiqil A'laa | 24105111164 |
| Muhammad Rais | 24105111139 |

Web toko online ala marketplace: pelanggan dapat mendaftar, melihat katalog, memasukkan produk ke keranjang, checkout, dan membayar online (QRIS / virtual account / e-wallet lewat Midtrans). Admin mengelola produk, kategori, pesanan, dan melihat laporan penjualan.

## Fitur

**Pelanggan:** registrasi dan login, katalog + pencarian + filter kategori, detail produk, keranjang, checkout dengan alamat pengiriman, pembayaran online (Midtrans Snap), riwayat dan status pesanan, batalkan pesanan yang belum dibayar.

**Admin:** dashboard statistik, CRUD produk (termasuk **upload foto**), CRUD kategori, kelola pesanan (Dibayar -> Diproses -> Dikirim -> Selesai), laporan penjualan per rentang tanggal.

**Pembayaran:** status pesanan berubah otomatis lewat webhook Midtrans (`POST /midtrans/notifikasi`, diverifikasi dengan signature SHA-512). Jika kunci Midtrans belum diisi, tersedia tombol *Bayar (Simulasi)* agar alur tetap bisa didemokan.

## Teknologi

Laravel 12 (PHP 8.2+), MySQL (SQLite untuk pengembangan lokal), Blade + CSS biasa (tanpa build frontend), Midtrans Snap (sandbox).

Struktur database mengikuti ERD di laporan: `users`, `categories`, `products`, `cart_items`, `addresses`, `orders`, `order_items`, `payments`.
