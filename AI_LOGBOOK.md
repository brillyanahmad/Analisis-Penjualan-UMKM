📝 Logbook Pemanfaatan Kecerdasan Artifisial (AI Logbook)

Nama Produk Digital: Penjualan UMKM Pro

Pengembang: Brillyan Ahmad Adi Prayanto & Oky Rizky Nihar Pradana

Asal Sekolah: SMAN 3 Jombang

Tahun Pelaksanaan: 2026

📌 Tahap 1: Eksplorasi Ide & Perancangan Solusi

Tujuan Interaksi: Menentukan konsep dasar produk digital, menganalisis kebutuhan operasional UMKM multi-channel, dan merancang arsitektur fitur utama dashboard keuangan serta manajemen stok.

Perintah (Prompt) Utama:

"Saya ingin membuat aplikasi web dashboard analisis penjualan untuk UMKM yang berjualan di berbagai marketplace. Aplikasi harus dapat menghitung omzet, laba bersih, biaya operasional, dan prediksi ketersediaan stok. Berikan masukan ide fitur dan arsitektur data yang efektif."

Rangkuman Tanggapan AI: AI menyarankan pendekatan Client-Side Standalone Application memanfaatkan teknologi LocalStorage pada peramban web (browser). AI merekomendasikan 4 modul utama:

Ringkasan KPI Finansial (Omzet, Nett Profit, Biaya Ops, Nilai Stok Gudang).

Grafik Tren Harian (SVG Chart).

Kalkulator Diskon Promo (Flash Sale Simulator).

Peringatan Dini Stok (Smart Restock Alert berdasarkan sales velocity).

Validasi & Modifikasi Mandiri:

Analisis: Mengadopsi saran arsitektur client-side karena mempercepat loading, bebas biaya server, dan menjamin privasi data keuangan UMKM tetap tersimpan di perangkat lokal pengguna.

Modifikasi Mandiri: Memperluas ide dasar AI dengan merancang sistem platform yang fleksibel (dynamic channels). AI awalnya hanya mengusulkan skema terikat untuk Shopee dan Tokopedia, namun saya memutuskan agar pengguna bebas menambah saluran penjualan seperti TikTok Shop, Lazada, WhatsApp, maupun Toko Offline/Fisik.

📌 Tahap 2: Penyusunan Kerangka Kode (Scaffolding)

Tujuan Interaksi: Merancang struktur awal kode HTML5, layout CSS modern berkonsep Glassmorphism, dan fungsi JavaScript dasar dalam satu berkas tunggal (Single-File Application).

Perintah (Prompt) Utama:

"Buatkan struktur dasar HTML, CSS modern Glassmorphism, dan JavaScript untuk aplikasi Penjualan UMKM Pro. Buatlah tab navigasi untuk Dashboard, Input Penjualan, Operasional, Simulasi Diskon, Master Produk, dan Backup Data."

Rangkuman Tanggapan AI: AI memberikan template HTML5 lengkap dengan perataan CSS Glassmorphism (backdrop-filter, warna transparan, efek blur) dan objek state JavaScript STORE untuk menangani manipulasi data lokal.

Validasi & Modifikasi Mandiri:

Analisis: Menguji keterbacaan dan keutuhan tata letak antarmuka saat dibuka melalui layar smartphone/HP.

Modifikasi Mandiri:

AI membuat tabel dan bilah navigasi yang terpotong (overflow) pada layar HP. Saya memodifikasi CSS dengan menambahkan pembungkus horizontal scroll (.nav-scroll-wrapper & .tw) agar antarmuka tetap rapi dan mobile-friendly.

Menyesuaikan skema warna CSS Variables untuk kontras teks yang lebih tinggi agar nyaman dibaca.

📌 Tahap 3: Pemecahan Masalah & Penanganan Galat (Debugging) & Pengembangan Fitur

Tujuan Interaksi: Mengembangkan fitur kelola platform dinamis, memperbaiki bug pada pemfilteran data, dan menyusun mekanisme migrasi data otomatis tanpa merusak riwayat transaksi yang tersimpan.

Perintah (Prompt) Utama:

"Tambahkan fitur dimana saya bisa mengurangi atau menambahkan platform lain, sehingga tidak hanya terpaku pada Shopee dan Tokopedia saja tanpa mengubah fitur yang lain. Berikan hasil dalam bentuk HTML."

Rangkuman Tanggapan AI: AI merestrukturisasi objek STORE dengan menyatukan array transaksi terpisah (shopee: [], tokopedia: []) menjadi satu array terpadu (penjualan: []) dengan properti penanda platform. AI juga menyertakan fungsi migrasi data dari format lama.

Validasi & Modifikasi Mandiri:

Analisis: Menemukan bahwa jika ID platform baru mengandung spasi atau huruf kapital, pemfilteran data pada tabel dan grafik tren menjadi error.

Modifikasi Mandiri:

Menambahkan fungsi pembersihan (formatting) pada input ID platform baru agar dikonversi secara otomatis menjadi huruf kecil dan menggunakan tanda hubung/garis bawah (slugify).

Memperbaiki logika rumus pada fungsi analyzeData() untuk memastikan persentase margin dan akumulasi laba bersih tetap akurat saat disaring per platform maupun secara keseluruhan (Semua Platform).

📌 Tahap 4: Refleksi & Penjelasan Kode

Tujuan Interaksi: Memverifikasi pemahaman mendalam terhadap logika pemrograman, rumus matematis keuangan, dan manajemen state aplikasi.

Refleksi Pemahaman Mandiri:

Pengelolaan Memori & State LocalStorage: Memahami alur sinkronisasi data objek JavaScript STORE dengan memori permanen browser menggunakan JSON.stringify() saat menyimpan dan JSON.parse() saat memuat aplikasi.

Formulasi Laba Bersih (Nett Profit): Memahami dan
