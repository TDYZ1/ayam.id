# Penjelasan Code HTML - Raymond

## 1. contact.html - Halaman Kontak

### Fungsi Halaman
Menampilkan form untuk user mengirim pesan, info kontak (alamat, email, telepon), link sosial media, dan peta lokasi toko.

### Layout yang Digunakan
- **Layout 2 kolom**: Kolom kiri untuk form, kolom kanan untuk info kontak dan sosial media
- **Layout full width**: Bagian peta Google Maps di bawah memakai 1 kolom penuh (col-12)

### Komponen HTML
- **Form**: Untuk user isi nama, email, telepon, subjek, dan pesan
- **Card**: Untuk membungkus form dan info kontak
- **Textarea**: Input teks panjang untuk pesan (rows="5" berarti tinggi 5 baris)
- **Iframe Google Maps**: Menampilkan peta lokasi toko di dalam halaman
- **Button sosial media**: 4 tombol outline untuk Facebook, Twitter, Instagram, WhatsApp

### Bootstrap yang Digunakan
- **Grid**: `row`, `col-lg-6` (2 kolom sama besar), `col-12` (full width untuk peta)
- **Card**: `card`, `card-body`, `h-100` (card tinggi sama di kedua kolom)
- **Form**: `form-label`, `form-control` untuk input field
- **Button**: `btn-primary w-100` untuk submit, `btn-outline-primary/info/danger/success` untuk sosmed
- **Flexbox**: `d-flex gap-3` untuk atur jarak antar tombol sosmed
- **Text**: `text-center` untuk heading, `text-muted` untuk text abu-abu
- **Spacing**: `mb-5`, `mb-3`, `mt-5` untuk jarak, `p-0` untuk hilangkan padding card-body peta

### Cara Implementasi
1. Buat container dan heading "Hubungi Kami" dengan `text-center mb-5`
2. Buat row dengan 2 kolom `col-lg-6`:
   - **Kolom kiri**: Card berisi form 5 field (nama, email, telepon, subjek, pesan)
   - **Kolom kanan**: 2 card — info kontak (alamat, email, telepon, WhatsApp, jam operasional) dan sosial media
3. Form submit: pakai button `btn-primary w-100`
4. Sosmed: bungkus 4 button dalam `d-flex gap-3`, masing-masing pakai warna outline sesuai brand
5. **Peta**: Buat row baru dengan `col-12`, taruh card dengan `card-body p-0` (hilangkan padding), isi dengan `<iframe>` Google Maps embed
6. Iframe settings: `width="100%"`, `height="400"`, `style="border:0;"`, tambahkan `loading="lazy"` agar peta baru load saat di-scroll

### Catatan
Peta saat ini menampilkan lokasi Universitas Mikroskil, bukan alamat toko di Jl. Sudirman

---

## 2. compare.html - Halaman Perbandingan Produk

### Fungsi Halaman
Membandingkan 3 produk secara side-by-side dalam tabel, menampilkan spesifikasi lengkap untuk membantu user memilih produk yang sesuai.

### Layout yang Digunakan
- **Table responsive**: Tabel lebar bisa di-scroll horizontal di layar kecil
- **Layout 4 kolom**: Kolom 1 untuk label spesifikasi, kolom 2-4 untuk 3 produk yang dibandingkan

### Komponen HTML
- **Table**: Tag `<table>` dengan `<thead>` (header) dan `<tbody>` (isi)
- **Table header**: Berisi gambar produk, nama, harga, dan tombol "Lihat Detail"
- **Table row**: Setiap baris berisi 1 aspek spesifikasi (layar, prosesor, RAM, dll)
- **Div wrapper**: `table-responsive` untuk enable horizontal scroll di mobile

### Bootstrap yang Digunakan
- **Table**: `table table-bordered` (tabel dengan garis pembatas)
- **Responsive**: `table-responsive` wrapper agar tabel bisa di-scroll di layar kecil
- **Background**: `bg-light` untuk header dan row harga
- **Image**: `img-fluid` untuk gambar produk responsif
- **Button**: `btn-sm btn-primary` untuk "Lihat Detail", `btn-primary w-100` dan `btn-outline-secondary w-100` untuk aksi di bawah
- **Text**: `text-center` untuk center konten, `text-danger` untuk harga, `mb-0` untuk hilangkan margin bawah
- **Spacing**: `mb-2` untuk jarak antar button, `mb-5` untuk heading, `mt-4` untuk link bawah

### Cara Implementasi
1. Buat heading "Bandingkan Produk" dengan `text-center mb-5`
2. Buat wrapper `<div class="table-responsive">`
3. Buat `<table class="table table-bordered">`
4. **Header (thead)**:
   - Baris 1: cell pertama "Spesifikasi" (width 20%), 3 cell produk (width ~27% each)
   - Setiap cell produk berisi: gambar (200x200px dengan object-fit cover), nama produk (h5), harga (h6 text-danger), button "Lihat Detail"
5. **Body (tbody)**:
   - Buat 11 baris spesifikasi: Layar, Prosesor, RAM, Storage, Kamera Belakang, Kamera Depan, Baterai, Sistem Operasi, Fitur Khusus, Berat, Rating
   - Cell pertama: label spesifikasi
   - Cell 2-4: value spesifikasi untuk masing-masing produk
   - Gunakan `<br>` untuk pisah multi-line info (contoh: baterai + fast charge)
6. **Row Harga**: Baris dengan background `bg-light`, label "Harga", dan 3 harga produk (h5 text-danger)
7. **Row Action**: Cell pertama kosong, cell 2-4 berisi 2 button stack (Tambah ke Keranjang + Lihat Detail)
8. Tambahkan link "Lihat Produk Lainnya" di bawah tabel

### Catatan
- Inline style `max-height: 200px; object-fit: cover` pada gambar agar semua gambar sama tinggi
- Cell produk pakai `text-center` agar konten rata tengah

---

## 3. checkout.html - Halaman Checkout (Proses Pembayaran)

### Fungsi Halaman
Halaman untuk user menyelesaikan pembelian: isi alamat pengiriman, pilih metode pengiriman dan pembayaran, review ringkasan pesanan, lalu bayar.

### Layout yang Digunakan
- **Layout 2 kolom**: Kolom kiri lebih besar (col-lg-8) untuk form, kolom kanan (col-lg-4) untuk ringkasan pesanan
- **3 card di kolom kiri**: Alamat Pengiriman, Metode Pengiriman, Metode Pembayaran
- **1 card di kolom kanan**: Ringkasan Pesanan

### Komponen HTML
- **Form input**: Text, tel, textarea, select dropdown untuk alamat
- **Radio button**: Untuk pilih ekspedisi dan metode pembayaran
- **Card**: Membungkus setiap section
- **Gambar produk kecil**: Thumbnail 60x60px di ringkasan pesanan

### Bootstrap yang Digunakan
- **Grid**: `row`, `col-lg-8`, `col-lg-4`, `col-md-6` untuk responsive 2 kolom
- **Card**: `card`, `card-header`, `card-body`, `bg-white` untuk header
- **Form**: `form-label`, `form-control`, `form-select` untuk dropdown, `textarea`
- **Form check**: `form-check`, `form-check-input`, `form-check-label` untuk radio button
- **Flexbox**: `d-flex justify-content-between` untuk label dan harga ekspedisi, untuk summary lines
- **Button**: `btn-success w-100` untuk tombol "Bayar Sekarang"
- **Text**: `text-muted` untuk estimasi pengiriman dan info produk, `text-danger` untuk total, `text-success` untuk ongkir gratis
- **Spacing**: `mb-3`, `mb-2`, `mb-4` untuk jarak antar elemen
- **Border**: `border-radius` untuk gambar produk

### Cara Implementasi
1. Buat heading "Checkout" dan row dengan 2 kolom
2. **Kolom kiri** (col-lg-8):
   
   **Card 1 - Alamat Pengiriman**:
   - Buat form dengan layout row: 2 input sejajar (Nama Lengkap + Nomor Telepon) pakai `col-md-6`
   - Textarea untuk alamat lengkap (rows="3")
   - 2 dropdown sejajar: Provinsi + Kota (masing-masing `col-md-6`)
   - 2 input sejajar: Kecamatan + Kode Pos
   
   **Card 2 - Metode Pengiriman**:
   - Buat 3 radio button, masing-masing dalam `form-check`
   - Label radio pakai `w-100` dan `d-flex justify-content-between` agar nama ekspedisi di kiri, harga di kanan
   - Di dalam label: nama ekspedisi (strong) dan estimasi (small text-muted) pakai `<br>` untuk pisah baris
   
   **Card 3 - Metode Pembayaran**:
   - Buat 5 radio button, label simpel (Transfer Bank, Kartu Kredit, E-Wallet, Cicilan, COD)

3. **Kolom kanan** (col-lg-4):
   - Card header "Ringkasan Pesanan"
   - Loop 3 produk: `d-flex` untuk gambar + info produk sejajar
   - Gambar: inline style `width: 60px; height: 60px; object-fit: cover; border-radius: 8px`
   - Info produk: nama (small strong) dan qty x harga (small text-muted) pakai `<br>`
   - Divider `<hr>`
   - Summary lines (Subtotal, Ongkir, Biaya Admin) pakai `d-flex justify-content-between`
   - Total Pembayaran (strong text-danger)
   - Button "Bayar Sekarang" (btn-success w-100)

### Catatan
- Radio button harus punya atribut `name` sama agar hanya bisa pilih 1 opsi (contoh: `name="shipping"`, `name="payment"`)
- Attribute `checked` pada 1 radio untuk set default selection

---

## 4. category-tablet.html - Halaman Kategori Tablet

### Fungsi Halaman
Menampilkan daftar produk tablet dalam grid layout.

### CATATAN PENTING - ADA BUG
File ini **copy-paste error** dari category-smartphone.html:
- Title masih "Smartphone" (seharusnya "Tablet")
- Breadcrumb "Smartphone" (seharusnya "Tablet")
- Heading h2 "Smartphone" (seharusnya "Tablet")
- Navbar menu active di "Smartphone" (seharusnya tidak ada yang active)
- **Konten produk**: Menampilkan smartphone (Samsung S24, iPhone, Xiaomi, dll) bukan tablet

### Yang Seharusnya
Produk yang ditampilkan harus tablet seperti: iPad Pro, iPad Air, Samsung Galaxy Tab, Microsoft Surface, Xiaomi Pad, Lenovo Tab, dll.

### Layout yang Digunakan (setelah diperbaiki)
- **Grid 4 kolom**: `row g-4` dengan `col-md-3` untuk tiap produk
- **Breadcrumb**: Navigasi Home → Tablet

### Komponen HTML
- **Breadcrumb**: `nav` dengan `ol.breadcrumb`
- **Product card**: Card dengan gambar, badge diskon (opsional), nama, rating, harga, button

### Bootstrap yang Digunakan
- **Breadcrumb**: `breadcrumb`, `breadcrumb-item`, `active`
- **Grid**: `container`, `row g-4`, `col-md-3` (4 kolom per baris)
- **Card**: `card`, `card-body`, `position-relative` untuk card dengan badge
- **Badge**: `badge bg-danger` dengan `position-absolute` (top-left corner)
- **Button**: `btn-primary w-100` untuk "Lihat Detail"
- **Text**: `text-center`, `text-danger` untuk harga, `text-muted` untuk harga coret
- **Image**: `img-fluid` untuk gambar responsif

### Cara Implementasi (setelah diperbaiki)
1. Fix breadcrumb: ganti "Smartphone" → "Tablet"
2. Fix heading: ganti h2 dari "Smartphone" → "Tablet"
3. Fix navbar: hilangkan class `active` dari menu Smartphone
4. Ganti 12 produk smartphone dengan 12 produk tablet
5. Struktur card tetap sama: badge diskon (optional), gambar, nama, rating bintang, harga dengan harga coret (jika diskon), button

---

## 5. category-smartphone.html - Halaman Kategori Smartphone

### Fungsi Halaman
Menampilkan grid 12 produk smartphone dengan badge diskon, harga, rating, dan tombol lihat detail.

### Layout yang Digunakan
- **Breadcrumb**: Home → Smartphone
- **Grid 4 kolom**: 12 produk dalam layout 3 baris × 4 kolom

### Komponen HTML
- **Product card**: Card dengan posisi relative untuk taruh badge absolute di pojok
- **Badge discount**: Span dengan position absolute di top-left
- **Rating bintang**: Karakter unicode ★ (penuh) dan ☆ (kosong)
- **Harga coret**: Tag `<del>` atau `<s>` untuk harga sebelum diskon

### Bootstrap yang Digunakan
- **Breadcrumb**: `breadcrumb`, `breadcrumb-item`, `active`
- **Grid**: `row g-4`, `col-md-3`
- **Card**: `card`, `card-body`, `card-title`, `position-relative`
- **Badge**: `badge bg-danger position-absolute` (custom positioning via CSS)
- **Button**: `btn-primary w-100`
- **Image**: `img-fluid`
- **Text**: `text-danger` (harga), `text-muted` (harga coret dan review count)

### Cara Implementasi
1. Buat breadcrumb: `<nav><ol class="breadcrumb"><li>Home</li><li class="active">Smartphone</li></ol></nav>`
2. Buat heading h2 "Smartphone"
3. Buat `<div class="row g-4">`
4. Loop 12 produk, setiap produk dalam `<div class="col-md-3">`:
   - Card dengan class `position-relative`
   - Badge diskon (jika ada): `<span class="badge bg-danger position-absolute">-20%</span>`
   - Gambar: `<img src="..." class="card-img-top img-fluid">`
   - Card body: nama (h5), rating bintang, harga (jika diskon: tampilkan harga baru + harga coret), button

### Produk yang Ditampilkan (12 smartphone)
Samsung Galaxy S24 Ultra, iPhone 15 Pro Max, Xiaomi 14 Pro, Google Pixel 8 Pro, OnePlus 12, OPPO Find X7 Pro, Vivo X100 Pro, Realme GT 5 Pro, Samsung Galaxy S23 Ultra, Nothing Phone 2, Asus ROG Phone 8 Pro, Sony Xperia 1 V

---

## 6. category-laptop.html - Halaman Kategori Laptop

### Fungsi Halaman
Menampilkan grid 12 produk laptop dengan informasi lengkap dan harga.

### Layout yang Digunakan
- **Breadcrumb**: Home → Laptop
- **Grid 4 kolom**: Sama seperti category-smartphone

### Komponen HTML & Bootstrap
Struktur sama persis dengan category-smartphone.html, hanya konten produk berbeda.

### Cara Implementasi
Sama seperti category-smartphone.html

### Produk yang Ditampilkan (12 laptop)
MacBook Air M3, MacBook Pro 14" M3 Pro, ASUS ROG Zephyrus G14, Dell XPS 13 Plus, Lenovo ThinkPad X1 Carbon, HP Spectre x360, MSI Stealth 14 Studio, Acer Swift X, ASUS Vivobook Pro 15, Razer Blade 14, Microsoft Surface Laptop 5, LG Gram 17"

---

## Ringkasan Bootstrap yang Digunakan Raymond

### Layout & Grid
- **Container**: `container` (wrapper utama halaman)
- **Row & Column**: `row`, `col-lg-*`, `col-md-*`, `col-12` (full width)
- **Gutter**: `g-4`, `g-3` (jarak antar kolom)
- **Grid auto**: `col-auto` (lebar kolom sesuai konten)

### Table Components
- **Base**: `table` (styling tabel dasar Bootstrap)
- **Border**: `table-bordered` (garis pembatas pada semua cell)
- **Responsive**: `table-responsive` (wrapper untuk scroll horizontal di mobile)
- **Background**: `bg-light` untuk header dan baris tertentu

### Card Components
- **Base**: `card`, `card-header`, `card-body`
- **Background**: `bg-white` untuk card header
- **Height**: `h-100` (tinggi card penuh, berguna untuk card sejajar)
- **Padding**: `p-0` untuk hilangkan padding (dipakai di card peta)

### Form Components
- **Label & Input**: `form-label`, `form-control`
- **Dropdown**: `form-select` untuk `<select>` element
- **Radio/Checkbox**: `form-check`, `form-check-input`, `form-check-label`
- **Textarea**: `form-control` juga bisa untuk textarea

### Button
- **Solid**: `btn-primary` (biru), `btn-success` (hijau)
- **Outline**: `btn-outline-primary`, `btn-outline-info`, `btn-outline-danger`, `btn-outline-secondary`, `btn-outline-success`
- **Size**: `btn-sm` (kecil), `btn-lg` (besar)
- **Width**: `w-100` (lebar penuh container)

### Breadcrumb (navigasi hierarki)
- **Base**: `breadcrumb`, `breadcrumb-item`
- **Active**: `active` pada item terakhir (tidak diklik)

### Badge
- **Base**: `badge` dengan warna `bg-danger`, `bg-success`, `bg-warning`, etc
- **Position**: Dikombinasi dengan `position-absolute` untuk badge di pojok gambar produk

### Flexbox Utilities
- **Display**: `d-flex` (aktifkan flexbox)
- **Direction**: `flex-column` (vertikal), default horizontal
- **Justify**: `justify-content-between` (space between), `justify-content-center` (center)
- **Align**: `align-items-center` (vertical center)
- **Gap**: `gap-2`, `gap-3` (jarak antar flex items tanpa margin)

### Text Utilities
- **Align**: `text-center` (tengah), `text-end` (kanan)
- **Color**: `text-danger` (merah untuk harga), `text-success` (hijau untuk gratis), `text-muted` (abu-abu untuk info sekunder)
- **Weight**: `fw-bold` (tebal)
- **Size**: `small` (text kecil dalam tag `<small>`)

### Spacing (margin & padding)
- **Margin**: `m-*` (semua sisi), `mt-*` (top), `mb-*` (bottom), `my-*` (top & bottom), `mx-*` (left & right)
- **Padding**: `p-*` (semua sisi), `py-*` (top & bottom), `p-0` (hilangkan padding)
- Ukuran: 0-5 (0 = 0px, 1 = 0.25rem, 2 = 0.5rem, 3 = 1rem, 4 = 1.5rem, 5 = 3rem)

### Image
- **Responsive**: `img-fluid` (gambar otomatis resize sesuai container)
- **Object fit**: Inline style `object-fit: cover` untuk crop gambar tanpa distorsi

### Position
- **Relative**: `position-relative` (untuk parent container badge)
- **Absolute**: `position-absolute` (untuk badge di pojok gambar)
- **Sticky**: `sticky-top` (navbar tetap di atas saat scroll)

### Border & Rounded
- **Border**: `border`, `border-0` (hilangkan border)
- **Rounded**: `rounded` (sudut melengkung), `rounded-circle` (bulat penuh)

### Custom Classes (didefinisikan di style.css)
- `product-card`: Styling khusus untuk card produk
- `badge-discount`: Badge diskon di pojok produk
- `product-rating`: Rating bintang produk
- `product-price`: Harga produk
- `product-price-old`: Harga coret (sebelum diskon)

### Cara Menggunakan Bootstrap

**1. Include CSS & JS**
- CSS di `<head>`: `<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">`
- JS sebelum `</body>`: `<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>`

**2. Struktur Grid Dasar**
```html
<div class="container">
  <div class="row">
    <div class="col-md-6">Kolom 1</div>
    <div class="col-md-6">Kolom 2</div>
  </div>
</div>
```

**3. Responsive Breakpoints**
- `col-*`: Semua ukuran layar
- `col-sm-*`: ≥576px (smartphone landscape)
- `col-md-*`: ≥768px (tablet)
- `col-lg-*`: ≥992px (desktop)
- `col-xl-*`: ≥1200px (large desktop)

**4. Combine Classes**
Gabungkan multiple classes untuk styling kompleks:
```html
<button class="btn btn-primary w-100 mb-3">Tombol</button>
<div class="card shadow-sm h-100 mb-4">Card</div>
```

**5. Form Layout**
```html
<div class="mb-3">
  <label class="form-label">Nama</label>
  <input type="text" class="form-control">
</div>
```

**6. Radio Button dengan Flexbox**
```html
<div class="form-check">
  <input type="radio" name="pilihan" class="form-check-input">
  <label class="form-check-label w-100 d-flex justify-content-between">
    <span>Opsi A</span>
    <strong>Rp 10.000</strong>
  </label>
</div>
```
