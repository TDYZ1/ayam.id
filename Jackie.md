# Penjelasan Code HTML - Jackie

## 1. privacy-policy.html - Halaman Kebijakan Privasi

### Fungsi Halaman
Halaman ini menampilkan kebijakan privasi TechStore, menjelaskan bagaimana data pengguna dikumpulkan dan digunakan.

### Layout yang Digunakan
- **Container terpusat**: Menggunakan `col-lg-8 mx-auto` agar konten tidak terlalu lebar dan berada di tengah layar
- **Layout 1 kolom**: Seluruh konten text disusun vertikal dari atas ke bawah

### Komponen HTML
- **Tag `<h1>` dan `<h4>`**: Judul utama dan sub-judul untuk setiap section
- **Tag `<p>`**: Paragraf teks biasa
- **Tag `<ul>` dan `<li>`**: List bertanda bullet untuk daftar informasi
- **Tag `<strong>`**: Membuat text jadi tebal untuk penekanan
- **Alert box**: Kotak info berwarna hijau di akhir halaman (class `alert alert-success`)

### Bootstrap yang Digunakan
- **Grid**: `container`, `row`, `col-lg-8`, `mx-auto` (margin auto kiri-kanan untuk center)
- **Spacing**: `my-5` (margin atas-bawah), `mb-3` (margin bawah)
- **Text**: `text-muted` (text abu-abu untuk tanggal update)
- **Alert**: `alert alert-success` (kotak notifikasi hijau)

### Cara Implementasi
1. Buat struktur HTML dasar dengan navbar di atas
2. Buat container tengah dengan `<div class="container my-5">`
3. Buat row dan kolom terpusat dengan `<div class="row"><div class="col-lg-8 mx-auto">`
4. Tulis 13 section, masing-masing pakai `<h4>` untuk judul dan `<ul>` untuk list
5. Tambahkan alert box di akhir dengan class `alert alert-success`

---

## 2. order-history.html - Halaman Riwayat Pesanan

### Fungsi Halaman
Menampilkan daftar pesanan yang pernah dibuat user, lengkap dengan status pengiriman dan detail produk.

### Layout yang Digunakan
- **Layout 2 kolom**: Sidebar kiri (menu profil) dan konten kanan (daftar pesanan)
- **Sidebar**: `col-md-3` untuk menu navigasi profil
- **Konten**: `col-md-9` untuk menampilkan card-card pesanan

### Komponen HTML
- **Card profil**: Foto bulat user, nama, dan email di sidebar
- **List group**: Menu navigasi dengan item yang bisa diklik (Profil, Pesanan, Wishlist, Logout)
- **Order card**: Card khusus untuk setiap pesanan dengan header, isi, dan footer
- **Badge status**: Label berwarna untuk status pesanan (Selesai/Dikirim/Dibatalkan)
- **Button group**: Kumpulan tombol kecil untuk aksi (Lihat Detail, Beli Lagi, Lacak Paket)

### Bootstrap yang Digunakan
- **Grid**: `row`, `col-md-3`, `col-md-9` untuk layout 2 kolom
- **Card**: `card`, `card-body` untuk kotak profil dan pesanan
- **List group**: `list-group`, `list-group-item`, `list-group-item-action`, `active` untuk menu
- **Flexbox**: `d-flex`, `justify-content-between`, `align-items-center` untuk atur posisi elemen
- **Badge**: `badge` dengan warna custom (status-success, status-info, status-warning)
- **Button**: `btn`, `btn-sm`, `btn-primary`, `btn-outline-secondary`
- **Image**: `rounded-circle` untuk foto profil bulat
- **Text**: `text-muted` (abu-abu), `text-danger` (merah untuk harga/logout)
- **Pagination**: `pagination`, `page-item`, `page-link` untuk navigasi halaman

### Cara Implementasi
1. Buat row dengan 2 kolom: `<div class="row">`
2. Kolom kiri (sidebar): buat card profil + list group menu
3. Kolom kanan: buat heading "Riwayat Pesanan"
4. Loop untuk setiap pesanan: buat card dengan 3 bagian (header, produk, footer)
5. Header pesanan pakai `d-flex justify-content-between` agar ID/tanggal di kiri, status badge di kanan
6. Bagian produk pakai `d-flex` agar gambar dan info produk sejajar horizontal
7. Footer pesanan pakai `d-flex justify-content-between` agar total di kiri, tombol di kanan
8. Tambahkan pagination di bawah untuk navigasi halaman

---

## 3. order-detail.html - Halaman Detail Pesanan

### Fungsi Halaman
Menampilkan detail lengkap dari 1 pesanan: timeline pengiriman, produk yang dibeli, alamat pengiriman, metode pembayaran, dan nomor resi.

### Layout yang Digunakan
- **Layout 2 kolom**: Kolom kiri lebih besar (col-lg-8) untuk timeline dan produk, kolom kanan (col-lg-4) untuk info pengiriman dan pembayaran
- **Timeline vertikal**: Menampilkan progress pengiriman dari bawah ke atas

### Komponen HTML
- **Timeline**: Dibuat manual pakai div dengan circle dan garis vertikal
- **Card**: Untuk grouping informasi (timeline, produk, alamat, pembayaran, resi)
- **Tag `<code>`**: Untuk menampilkan nomor resi dengan font monospace
- **Tag `<br>`**: Untuk pisah baris alamat dan info lainnya

### Bootstrap yang Digunakan
- **Grid**: `row`, `col-lg-8`, `col-lg-4` untuk layout 2 kolom
- **Card**: `card`, `card-header`, `card-body`
- **Flexbox**: `d-flex`, `justify-content-between` untuk header dan summary
- **Button**: `btn-outline-secondary` (tombol Kembali), `btn-outline-primary` (Lacak Paket)
- **Badge**: `badge bg-success` untuk status pesanan
- **Text**: `text-muted` (abu-abu), `text-danger` (merah untuk harga), `text-success` (hijau untuk gratis ongkir)
- **Border**: `border-bottom` untuk garis pemisah item produk
- **Spacing**: `mb-3`, `mt-3`, `mb-0` untuk jarak antar elemen

### Cara Implementasi Timeline Vertikal
1. Setiap step timeline pakai `d-flex` untuk taruh icon dan text sejajar
2. Icon: buat bulatan (`border-radius: 50%`) dengan background hijau, ukuran 30x30px, centang (✓) di dalamnya
3. Garis vertikal: div dengan `width: 2px`, `height: 40px`, background hijau, posisi di bawah icon (margin-left 14px)
4. Text: taruh di sebelah kanan icon dengan info tahap dan timestamp
5. Susun dari atas ke bawah: Selesai → Diterima → Dikirim → Diproses → Dibuat

### Cara Implementasi Ringkasan Harga
1. List item dengan `d-flex justify-content-between` agar label di kiri, nilai di kanan
2. Subtotal, ongkir, biaya admin dengan text biasa
3. Total Pembayaran pakai `<strong>` dan `text-danger` agar menonjol

---

## 4. login.html - Halaman Login

### Fungsi Halaman
Form login untuk user masuk ke akun mereka dengan email/telepon dan password, atau pakai login sosial media.

### Layout yang Digunakan
- **Layout centered**: Card form berada di tengah layar (class `auth-card`)
- **Layout 1 kolom**: Form disusun vertikal dari atas ke bawah

### Komponen HTML
- **Form**: Tag `<form>` untuk input data login
- **Input text**: Untuk email/nomor telepon
- **Input password**: Untuk password (text otomatis disembunyikan jadi titik-titik)
- **Checkbox**: "Ingat Saya" agar user tidak perlu login lagi
- **Link**: "Lupa Password?" untuk reset password
- **Divider**: Garis horizontal `<hr>` sebagai pemisah antara login biasa dan sosial media
- **Button**: Tombol login utama dan tombol sosial media

### Bootstrap yang Digunakan
- **Card**: `card`, `card-body` untuk kotak form
- **Form**: `form-label`, `form-control` untuk label dan input field
- **Form check**: `form-check`, `form-check-input`, `form-check-label` untuk checkbox
- **Button**: `btn-primary` (biru untuk login utama), `btn-outline-secondary` (border abu-abu untuk sosmed)
- **Flexbox**: `d-flex justify-content-between` untuk baris checkbox dan link lupa password
- **Grid**: `d-grid gap-2` untuk tombol sosmed (full width dengan jarak)
- **Text**: `text-center` untuk center heading dan text "Belum punya akun"
- **Spacing**: `mb-3` (margin bawah), `my-4` (margin atas-bawah), `w-100` (lebar 100%)
- **Decoration**: `text-decoration-none` untuk hilangkan garis bawah link

### Cara Implementasi
1. Buat container dengan card centered menggunakan class custom `auth-card`
2. Buat heading "Login ke TechStore" dengan class `text-center`
3. Buat form dengan 2 input: email/telepon (type="text" untuk fleksibel) dan password (type="password")
4. Buat row dengan `d-flex justify-content-between` berisi checkbox "Ingat Saya" di kiri dan link "Lupa Password" di kanan
5. Tambahkan tombol "Login" dengan `btn-primary w-100` agar full width
6. Tambahkan text dan link ke halaman register
7. Tambahkan garis pemisah `<hr class="my-4">`
8. Buat container `d-grid gap-2` berisi 2 tombol sosmed dengan icon

---

## 5. index.html - Halaman Beranda (Homepage)

### Fungsi Halaman
Halaman utama yang pertama dilihat user, menampilkan hero banner, kategori produk, dan produk unggulan.

### Layout yang Digunakan
- **Hero section**: Banner besar di atas dengan background dan tombol CTA
- **Grid 3 kolom**: Untuk menampilkan kategori produk
- **Grid 4 kolom**: Untuk menampilkan produk unggulan

### Komponen HTML
- **Hero section**: Div besar dengan heading, tagline, dan tombol "Belanja Sekarang"
- **Card kategori**: Card yang bisa diklik (wrapped dalam tag `<a>`) dengan gambar dan nama kategori
- **Card produk**: Card produk dengan badge diskon, gambar, nama, rating, harga, dan tombol

### Bootstrap yang Digunakan
- **Hero section**: Custom class `hero-section` dengan container, heading besar, dan button
- **Grid**: `row`, `col-md-4` untuk 3 kategori, `col-md-3` untuk 4 produk, `g-4` untuk jarak antar card
- **Card**: `card`, `card-body` untuk kotak kategori dan produk
- **Badge**: `badge bg-danger` untuk label diskon di pojok kiri atas produk
- **Button**: `btn-light btn-lg` untuk hero CTA, `btn-primary w-100` untuk tombol produk
- **Text**: `text-center` untuk center text, `section-title` untuk heading section
- **Image**: `img-fluid` untuk gambar responsif
- **Position**: `position-relative` pada card, `position-absolute` pada badge diskon
- **Spacing**: `my-5`, `mb-4` untuk jarak antar section

### Cara Implementasi
1. **Hero Section**: Buat div dengan class `hero-section`, isi dengan container berisi h1, paragraf tagline, dan tombol besar "Belanja Sekarang"
2. **Section Kategori**: 
   - Buat heading "Kategori Produk" dengan class `section-title text-center`
   - Buat row dengan `g-4` untuk jarak
   - Loop 3 kategori: buat card wrapped dalam tag `<a>`, gambar di atas, text nama di bawah (center)
3. **Section Produk Unggulan**:
   - Buat heading "Produk Unggulan"
   - Buat row dengan 4 kolom `col-md-3`
   - Setiap produk: card dengan badge diskon (position absolute), gambar, nama, rating bintang, harga dengan harga coret, tombol "Lihat Detail"

### Catatan Khusus
- Rating bintang dibuat pakai karakter unicode ★ (bintang penuh) dan ☆ (bintang kosong)
- Badge diskon pakai `position-absolute` dengan koordinat `top: 10px; left: 10px`
- Harga coret pakai tag `<del>` atau `<s>` dengan class `text-muted`

---

## 6. faq.html - Halaman FAQ (Pertanyaan yang Sering Ditanyakan)

### Fungsi Halaman
Menampilkan daftar pertanyaan dan jawaban umum seputar layanan TechStore (cara pesan, pembayaran, pengiriman, garansi, dll).

### Layout yang Digunakan
- **Container terpusat**: `col-lg-8 mx-auto` agar konten tidak terlalu lebar
- **Accordion native**: Menggunakan tag HTML5 `<details>` dan `<summary>` untuk buka-tutup pertanyaan

### Komponen HTML
- **Tag `<details>`**: Container untuk setiap pertanyaan yang bisa dibuka/ditutup
- **Tag `<summary>`**: Bagian yang diklik untuk buka/tutup (berisi pertanyaan)
- **Heading `<h4>`**: Judul kategori FAQ (5 kategori)
- **List `<ol>` dan `<ul>`**: Untuk jawaban berupa langkah-langkah atau daftar
- **Tag `<strong>`**: Untuk menebalkan text penting

### Bootstrap yang Digunakan
- **Grid**: `container`, `row`, `col-lg-8 mx-auto`
- **Background**: `bg-light` untuk background summary
- **Border**: `border`, `border-top-0`, `rounded`, `rounded-bottom` untuk styling jawaban
- **Spacing**: `mb-3` untuk jarak antar FAQ, `mb-5` untuk jarak kategori, `p-3` untuk padding
- **Card**: `card card-body` untuk CTA box di akhir
- **Button**: `btn-primary` untuk tombol "Hubungi Kami"
- **Text**: `text-center` untuk center heading dan CTA

### Cara Implementasi
1. Buat container dengan `col-lg-8 mx-auto` agar content center dan tidak terlalu lebar
2. Buat heading utama "Frequently Asked Questions (FAQ)" dengan `text-center mb-5`
3. Buat 5 kategori FAQ, masing-masing dengan heading `<h4>`:
   - Pemesanan & Pembayaran
   - Pengiriman
   - Produk & Garansi
   - Retur & Pengembalian
   - Akun & Keamanan
4. Untuk setiap FAQ, gunakan struktur:
   ```html
   <details class="mb-3">
     <summary class="p-3 bg-light rounded" style="cursor: pointer;">
       <strong>Pertanyaan?</strong>
     </summary>
     <div class="p-3 border border-top-0 rounded-bottom">
       <p>Jawaban...</p>
     </div>
   </details>
   ```
5. Summary akan otomatis punya panah dropdown dari browser
6. Konten dalam details akan muncul saat user klik summary
7. Tambahkan CTA card di akhir dengan tombol link ke contact.html

### Keuntungan Pakai `<details>`
- Tidak perlu JavaScript untuk buka-tutup
- Browser otomatis handle interaction
- Lebih ringan dan simple daripada accordion Bootstrap

---

## Ringkasan Bootstrap yang Digunakan Jackie

### Layout & Grid
- **Container**: `container` (wrapper utama), `row` (baris), `col-md-*`, `col-lg-*` (kolom responsif)
- **Centering**: `mx-auto` (margin kiri-kanan auto untuk center kolom)
- **Grid gutter**: `g-4` untuk jarak antar kolom

### Card Components
- **Card**: `card`, `card-body`, `card-header` untuk kotak konten
- **Height**: `h-100` untuk card tinggi penuh

### Form Components
- **Input**: `form-control` (styling input), `form-label` (label input)
- **Checkbox/Radio**: `form-check`, `form-check-input`, `form-check-label`
- **Inline**: `form-check-inline` untuk checkbox/radio horizontal

### Button
- **Style**: `btn-primary` (biru), `btn-outline-secondary` (border abu), `btn-success` (hijau)
- **Size**: `btn-sm` (kecil), `btn-lg` (besar)
- **Width**: `w-100` (lebar penuh)

### List Group (untuk menu navigasi)
- **Base**: `list-group`, `list-group-item`
- **Interactive**: `list-group-item-action` (bisa diklik)
- **Active**: `active` (highlight menu terpilih)

### Badge & Label
- **Badge**: `badge` dengan warna `bg-success`, `bg-danger`, `bg-warning`, `bg-info`
- Custom: `status-success`, `status-info`, `status-warning` untuk status pesanan

### Alert (kotak notifikasi)
- **Base**: `alert` dengan varian `alert-success`, `alert-info`

### Flexbox Utilities
- **Display**: `d-flex` (aktifkan flexbox), `d-grid` (grid layout)
- **Alignment**: `justify-content-between` (space between), `justify-content-center` (center)
- **Items**: `align-items-center` (vertical center)
- **Gap**: `gap-2`, `gap-3` (jarak antar flex items)

### Text Utilities
- **Align**: `text-center` (center), `text-end` (kanan)
- **Color**: `text-muted` (abu), `text-danger` (merah), `text-success` (hijau)
- **Decoration**: `text-decoration-none` (hilangkan underline link)

### Spacing (margin & padding)
- **Margin**: `m-*`, `my-*` (atas-bawah), `mb-*` (bawah), `mt-*` (atas), `mx-*` (kiri-kanan)
- **Padding**: `p-*`, `py-*`, `p-3`, `p-5`
- Angka 0-5 untuk ukuran (0 = 0px, 1 = 0.25rem, 2 = 0.5rem, 3 = 1rem, 4 = 1.5rem, 5 = 3rem)

### Border & Rounded
- **Border**: `border`, `border-top-0`, `border-bottom`
- **Rounded**: `rounded` (sudut melengkung), `rounded-circle` (bulat penuh untuk foto profil), `rounded-bottom`

### Background Color
- **Color**: `bg-white`, `bg-light`, `bg-primary`, `bg-success`

### Image
- **Responsive**: `img-fluid` (gambar auto resize sesuai layar)
- **Shape**: `rounded-circle` (foto bulat)

### Pagination
- **Base**: `pagination`, `page-item`, `page-link`
- Untuk navigasi halaman (Previous, 1, 2, 3, Next)

### Position
- **Type**: `position-relative`, `position-absolute`
- **Fixed**: `sticky-top` untuk navbar tetap di atas saat scroll

### Custom Classes (didefinisikan di style.css)
- `auth-card`: Styling untuk centered login/register card
- `hero-section`: Banner homepage dengan background
- `section-title`: Heading untuk section
- `category-card`: Card kategori produk
- `product-card`: Card produk dengan hover effect
- `order-card`: Card untuk item pesanan
- `status-badge`: Badge status dengan varian warna

### Cara Menggunakan Bootstrap
1. **Include Bootstrap CSS** di `<head>`: Link CDN Bootstrap 5.3.0
2. **Include Bootstrap JS** sebelum `</body>`: Script CDN Bootstrap bundle (untuk komponen interaktif)
3. **Gunakan class** langsung di HTML: `<div class="container">`, `<button class="btn btn-primary">`, dll
4. **Combine multiple classes**: `<div class="card shadow-sm mb-4 h-100">` (card + shadow + margin + height)
5. **Responsive**: Gunakan breakpoint `col-sm-*`, `col-md-*`, `col-lg-*` untuk tampilan berbeda di layar berbeda
