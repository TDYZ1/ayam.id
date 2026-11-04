# Penjelasan Code HTML - Rasyid

## 1. product-detail.html - Halaman Detail Produk

### Fungsi Halaman
Menampilkan detail lengkap 1 produk: gambar, harga, pilihan varian (warna & kapasitas), deskripsi, spesifikasi, dan review pelanggan.

### Layout yang Digunakan
- **Breadcrumb**: Navigasi hierarki di atas (Home → Smartphone → Samsung Galaxy S24 Ultra)
- **Layout 2 kolom**: Kolom kiri (col-lg-5) untuk gambar, kolom kanan (col-lg-7) untuk info produk
- **Tabs**: 3 tab untuk Deskripsi, Spesifikasi, Review

### Komponen HTML
- **Gambar besar + thumbnail**: Gambar utama 500x500px, 3 thumbnail kecil 80x80px untuk preview
- **Badge**: Label status stok dan diskon
- **Color swatch**: Kotak warna kecil yang bisa diklik untuk pilih warna
- **Radio button styled**: Menggunakan `btn-check` + `btn-outline-primary` agar radio button tampil seperti tombol
- **Tab navigation**: `nav-tabs` untuk switch konten tanpa reload halaman
- **Table**: Tabel spesifikasi dengan 2 kolom (label & value)
- **Review card**: Card berisi nama, tanggal, rating, dan komentar

### Bootstrap yang Digunakan
- **Breadcrumb**: `breadcrumb`, `breadcrumb-item`, `active`
- **Grid**: `row`, `col-lg-5`, `col-lg-7` untuk layout gambar & info
- **Badge**: `badge bg-success` (stok tersedia), `badge bg-warning` (diskon)
- **Button**: `btn-primary`, `btn-outline-secondary`, `btn-success`, `btn-lg`
- **Button group**: `btn-check` + `btn-outline-primary` untuk radio button yang tampil seperti tombol
- **Flexbox**: `d-flex`, `gap-2`, `flex-grow-1` untuk atur layout tombol
- **Tabs**: `nav nav-tabs`, `tab-content`, `tab-pane` untuk switch konten
- **Table**: `table` dengan custom class `spec-table`
- **Text**: `text-danger` untuk harga, `text-muted` untuk harga coret dan text sekunder
- **Spacing**: `mb-3`, `mt-4`, `my-5` untuk jarak

### Cara Implementasi

**1. Breadcrumb**
```html
<nav><ol class="breadcrumb">
  <li class="breadcrumb-item">Home</li>
  <li class="breadcrumb-item">Smartphone</li>
  <li class="breadcrumb-item active">Samsung Galaxy S24 Ultra</li>
</ol></nav>
```

**2. Section Detail (2 kolom)**
- Kolom kiri: gambar besar + row berisi 3 thumbnail
- Kolom kanan: judul (h1), rating, harga + harga coret, badge stok & diskon

**3. Color Swatch**
```html
<div class="color-swatch" style="background-color: #000000;"></div>
<div class="color-swatch" style="background-color: #808080;"></div>
<div class="color-swatch" style="background-color: #ffffff; border: 1px solid #ddd;"></div>
```
Class `color-swatch` didefinisikan di CSS dengan ukuran kotak dan border-radius.

**4. Radio Button Styled (Kapasitas Storage)**
```html
<input type="radio" class="btn-check" name="storage" id="s256" checked>
<label class="btn btn-outline-primary" for="s256">256GB</label>

<input type="radio" class="btn-check" name="storage" id="s512">
<label class="btn btn-outline-primary" for="s512">512GB</label>
```
`btn-check` hidden radio input, label tampil seperti button. Saat dipilih otomatis jadi `btn-primary`.

**5. Tombol Aksi**
- Baris 1: "Tambah ke Keranjang" (flex-grow-1 agar melebar) + "Wishlist" (icon ♥)
- Baris 2: "Beli Sekarang" (btn-success w-100)

**6. Tabs**
```html
<ul class="nav nav-tabs">
  <li class="nav-item">
    <a class="nav-link active" data-bs-toggle="tab" href="#desc">Deskripsi</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" data-bs-toggle="tab" href="#spec">Spesifikasi</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" data-bs-toggle="tab" href="#review">Review</a>
  </li>
</ul>
<div class="tab-content">
  <div class="tab-pane fade show active" id="desc">Konten deskripsi...</div>
  <div class="tab-pane fade" id="spec">Tabel spesifikasi...</div>
  <div class="tab-pane fade" id="review">Review cards...</div>
</div>
```
Attribute `data-bs-toggle="tab"` dan `href="#id"` untuk switch tab. Bootstrap JS handle interaction.

---

## 2. products.html - Halaman Daftar Produk

### Fungsi Halaman
Menampilkan semua produk dalam grid dengan filter di sidebar kiri (kategori, harga, brand, rating) dan sorting di atas.

### Layout yang Digunakan
- **Layout 2 kolom**: Sidebar kiri (col-lg-3) untuk filter, konten kanan (col-lg-9) untuk grid produk
- **Grid 3 kolom**: Produk ditampilkan dalam layout 3 kolom per baris
- **Pagination**: Navigasi halaman di bawah

### Komponen HTML
- **Checkbox**: Untuk filter kategori, harga, brand, rating
- **Dropdown sort**: Select untuk urutkan produk (Harga, Rating, Terbaru)
- **Product card**: Card dengan gambar, badge diskon, nama, rating, harga, button
- **Pagination**: Previous, angka halaman 1-4, Next

### Bootstrap yang Digunakan
- **Breadcrumb**: `breadcrumb`, `breadcrumb-item`
- **Grid**: `row`, `col-lg-3` (sidebar), `col-lg-9` (konten), `col-md-4` (3 produk per baris)
- **Card**: `card`, `card-body` untuk filter dan produk
- **Form**: `form-check`, `form-check-input`, `form-check-label` untuk checkbox
- **Select**: `form-select` untuk dropdown sort
- **Flexbox**: `d-flex justify-content-between align-items-center` untuk header (jumlah produk & sort)
- **Badge**: `badge bg-danger position-absolute` untuk diskon
- **Button**: `btn-primary w-100` untuk "Lihat Detail"
- **Pagination**: `pagination`, `page-item`, `page-link`, `active`, `disabled`
- **Text**: `text-danger` (harga), `text-muted` (harga coret & review count)

### Cara Implementasi

**1. Sidebar Filter**
Buat card dengan beberapa section filter, pisahkan dengan border/margin:
```html
<div class="card mb-4">
  <div class="card-body">
    <h5>Kategori</h5>
    <div class="form-check">
      <input type="checkbox" class="form-check-input" id="cat1">
      <label class="form-check-label" for="cat1">Smartphone</label>
    </div>
    <!-- repeat untuk kategori lain -->
    
    <hr class="my-3">
    
    <h5>Harga</h5>
    <div class="form-check">
      <input type="checkbox" class="form-check-input" id="price1">
      <label class="form-check-label" for="price1">< Rp 5.000.000</label>
    </div>
    <!-- repeat untuk range harga lain -->
  </div>
</div>
```

**2. Header Konten (jumlah & sort)**
```html
<div class="d-flex justify-content-between align-items-center mb-4">
  <div>Menampilkan 48 Produk</div>
  <select class="form-select w-auto">
    <option>Urutkan: Harga Terendah</option>
    <option>Urutkan: Rating Tertinggi</option>
    <option>Urutkan: Terbaru</option>
  </select>
</div>
```

**3. Grid Produk**
```html
<div class="row g-4">
  <div class="col-md-4">
    <div class="card product-card position-relative">
      <span class="badge bg-danger position-absolute">-20%</span>
      <img src="..." class="card-img-top">
      <div class="card-body">
        <h5>Samsung Galaxy S24 Ultra</h5>
        <div>★★★★★ (1234)</div>
        <div class="text-danger">Rp 19.999.000</div>
        <del class="text-muted">Rp 24.999.000</del>
        <button class="btn btn-primary w-100 mt-2">Lihat Detail</button>
      </div>
    </div>
  </div>
  <!-- repeat 11x untuk total 12 produk -->
</div>
```

**4. Pagination**
```html
<nav>
  <ul class="pagination justify-content-center mt-4">
    <li class="page-item disabled">
      <a class="page-link">Previous</a>
    </li>
    <li class="page-item active"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">4</a></li>
    <li class="page-item">
      <a class="page-link" href="#">Next</a>
    </li>
  </ul>
</nav>
```
Class `active` untuk halaman sekarang, `disabled` untuk tombol tidak aktif (Previous di halaman 1).

---

## 3. profile.html - Halaman Profil User

### Fungsi Halaman
User bisa lihat dan edit data profil (nama, email, telepon, jenis kelamin, tanggal lahir) serta mengelola alamat pengiriman.

### Layout yang Digunakan
- **Layout 2 kolom**: Sidebar kiri (col-md-3) untuk menu navigasi profil, konten kanan (col-md-9) untuk form dan data
- **2 card di konten kanan**: Card 1 untuk Informasi Profil, Card 2 untuk Alamat Pengiriman

### Komponen HTML
- **List group menu**: Menu navigasi di sidebar dengan item yang bisa diklik
- **Form horizontal**: Label di kiri (col-sm-3), input di kanan (col-sm-9)
- **Input fields**: Text, email, tel, date
- **Select dropdown**: Untuk jenis kelamin
- **Alamat tersimpan**: Kotak dengan border berisi info alamat lengkap
- **Badge**: Label "Utama" untuk alamat default

### Bootstrap yang Digunakan
- **Grid**: `row`, `col-md-3`, `col-md-9`, `col-sm-3`, `col-sm-9`
- **Card**: `card`, `card-body`, `card-header` untuk profile photo dan form sections
- **List group**: `list-group`, `list-group-item`, `list-group-item-action`, `active` untuk menu
- **Form**: `form-label`, `form-control`, `form-select`, `row mb-3` untuk form layout
- **Badge**: `badge bg-primary` untuk label "Utama"
- **Button**: `btn-primary` untuk "Simpan Perubahan", `btn-outline-primary` untuk "Tambah Alamat Baru"
- **Flexbox**: `d-flex justify-content-between` untuk header alamat (label + link edit/hapus)
- **Image**: `rounded-circle` untuk foto profil bulat
- **Text**: `text-center` (center text), `text-danger` (link Logout), `text-muted` (info sekunder)
- **Border**: `border rounded p-3 mb-3` untuk kotak alamat
- **Spacing**: `mb-3`, `mt-3` untuk jarak antar elemen
- **Offset**: `offset-sm-3` untuk align tombol dengan input field

### Cara Implementasi

**1. Sidebar Menu**
```html
<div class="col-md-3">
  <div class="card">
    <div class="card-body text-center">
      <img src="profile.jpg" class="rounded-circle mb-3" width="100">
      <h5>Budi Santoso</h5>
      <p class="text-muted">budi@email.com</p>
    </div>
  </div>
  <div class="list-group mt-3">
    <a href="#" class="list-group-item list-group-item-action active">Profil Saya</a>
    <a href="order-history.html" class="list-group-item list-group-item-action">Pesanan Saya</a>
    <a href="wishlist.html" class="list-group-item list-group-item-action">Wishlist</a>
    <a href="login.html" class="list-group-item list-group-item-action text-danger">Logout</a>
  </div>
</div>
```

**2. Form Profil Horizontal**
```html
<div class="card">
  <div class="card-body">
    <h5>Informasi Profil</h5>
    <form>
      <div class="row mb-3">
        <label class="col-sm-3 col-form-label">Nama Lengkap</label>
        <div class="col-sm-9">
          <input type="text" class="form-control" value="Budi Santoso">
        </div>
      </div>
      <div class="row mb-3">
        <label class="col-sm-3 col-form-label">Email</label>
        <div class="col-sm-9">
          <input type="email" class="form-control" value="budi@email.com">
        </div>
      </div>
      <!-- repeat untuk field lain -->
      <div class="row">
        <div class="col-sm-9 offset-sm-3">
          <button class="btn btn-primary">Simpan Perubahan</button>
        </div>
      </div>
    </form>
  </div>
</div>
```
`offset-sm-3` membuat tombol align dengan input field (skip 3 kolom label).

**3. Section Alamat**
```html
<div class="card mt-3">
  <div class="card-body">
    <h5>Alamat Pengiriman</h5>
    
    <div class="border rounded p-3 mb-3">
      <div class="d-flex justify-content-between mb-2">
        <div>
          <strong>Rumah</strong>
          <span class="badge bg-primary ms-2">Utama</span>
        </div>
        <div>
          <a href="#" class="text-decoration-none">Edit</a> |
          <a href="#" class="text-decoration-none text-danger">Hapus</a>
        </div>
      </div>
      <div>Budi Santoso | 08123456789</div>
      <div class="text-muted">
        Jl. Sudirman No. 123<br>
        Kec. Medan Baru, Kota Medan<br>
        Sumatera Utara, 20111
      </div>
    </div>
    
    <!-- repeat untuk alamat ke-2 tanpa badge Utama -->
    
    <button class="btn btn-outline-primary">+ Tambah Alamat Baru</button>
  </div>
</div>
```

---

## 4. register.html - Halaman Registrasi

### Fungsi Halaman
Form untuk user buat akun baru dengan data lengkap (nama, email, telepon, password, jenis kelamin, tanggal lahir).

### Layout yang Digunakan
- **Layout centered**: Card form berada di tengah layar menggunakan class custom `auth-card`
- **Layout 1 kolom vertikal**: Semua field disusun dari atas ke bawah

### Komponen HTML
- **Form dengan 9 field**: Nama, email, telepon, password, konfirmasi password, jenis kelamin (radio), tanggal lahir (date input), checkbox persetujuan, tombol daftar
- **Radio button inline**: Untuk pilih jenis kelamin (Laki-laki/Perempuan) horizontal
- **Checkbox dengan link**: User harus setuju syarat & ketentuan (link ke terms.html dan privacy-policy.html)

### Bootstrap yang Digunakan
- **Card**: `card`, `card-body` untuk kotak form
- **Form**: `form-label`, `form-control` untuk input fields
- **Radio inline**: `form-check`, `form-check-inline`, `form-check-input`, `form-check-label`
- **Button**: `btn-primary w-100` untuk tombol "Daftar"
- **Text**: `text-center` untuk heading dan text "Sudah punya akun"
- **Spacing**: `mb-3` untuk jarak antar field
- **Link**: `text-decoration-none` untuk link tanpa underline

### Cara Implementasi

**1. Form Structure**
```html
<div class="card auth-card">
  <div class="card-body">
    <h2 class="text-center mb-4">Daftar ke TechStore</h2>
    <form>
      <div class="mb-3">
        <label class="form-label">Nama Lengkap</label>
        <input type="text" class="form-control" placeholder="Masukkan nama lengkap">
      </div>
      
      <div class="mb-3">
        <label class="form-label">Email</label>
        <input type="email" class="form-control" placeholder="email@example.com">
      </div>
      
      <div class="mb-3">
        <label class="form-label">Nomor Telepon</label>
        <input type="tel" class="form-control" placeholder="08xx xxxx xxxx">
      </div>
      
      <div class="mb-3">
        <label class="form-label">Password</label>
        <input type="password" class="form-control" placeholder="Minimal 8 karakter">
      </div>
      
      <div class="mb-3">
        <label class="form-label">Konfirmasi Password</label>
        <input type="password" class="form-control" placeholder="Ulangi password">
      </div>
      
      <div class="mb-3">
        <label class="form-label d-block">Jenis Kelamin</label>
        <div class="form-check form-check-inline">
          <input type="radio" name="gender" class="form-check-input" id="male">
          <label class="form-check-label" for="male">Laki-laki</label>
        </div>
        <div class="form-check form-check-inline">
          <input type="radio" name="gender" class="form-check-input" id="female">
          <label class="form-check-label" for="female">Perempuan</label>
        </div>
      </div>
      
      <div class="mb-3">
        <label class="form-label">Tanggal Lahir</label>
        <input type="date" class="form-control">
      </div>
      
      <div class="mb-3">
        <div class="form-check">
          <input type="checkbox" class="form-check-input" id="agree">
          <label class="form-check-label" for="agree">
            Saya setuju dengan <a href="terms.html">Syarat & Ketentuan</a> dan 
            <a href="privacy-policy.html">Kebijakan Privasi</a>
          </label>
        </div>
      </div>
      
      <button type="submit" class="btn btn-primary w-100">Daftar</button>
      
      <p class="text-center mt-3">
        Sudah punya akun? <a href="login.html">Login</a>
      </p>
    </form>
  </div>
</div>
```

**2. Radio Button Inline**
- `form-check-inline` membuat radio button horizontal (sejajar)
- `name` attribute harus sama agar hanya bisa pilih 1 opsi

**3. Input Type**
- `type="email"`: Validasi format email otomatis
- `type="tel"`: Keyboard numerik di mobile
- `type="password"`: Text otomatis disembunyikan jadi titik-titik
- `type="date"`: Date picker otomatis dari browser

---

## 5. terms.html - Halaman Syarat & Ketentuan

### Fungsi Halaman
Menampilkan syarat dan ketentuan layanan TechStore yang harus disetujui user saat registrasi.

### Layout yang Digunakan
- **Container terpusat**: `col-lg-8 mx-auto` agar konten tidak terlalu lebar dan berada di tengah

### Komponen HTML
- **Heading & sub-heading**: h1 untuk judul utama, h4 untuk setiap section
- **List**: ul/li untuk poin-poin ketentuan
- **Alert box**: Kotak info biru di akhir halaman
- **Tag `<strong>`**: Untuk label yang penting

### Bootstrap yang Digunakan
- **Grid**: `container`, `row`, `col-lg-8 mx-auto`
- **Text**: `text-muted` untuk tanggal update terakhir
- **Alert**: `alert alert-info` untuk kotak notifikasi biru
- **Spacing**: `my-5`, `mb-3`, `mb-4` untuk jarak antar section

### Cara Implementasi
1. Buat container dengan `col-lg-8 mx-auto`
2. Heading utama "Syarat & Ketentuan" + tanggal update dengan class `text-muted`
3. Buat 11 section, masing-masing dengan h4 heading dan konten (paragraf atau list):
   - Pendahuluan
   - Akun Pengguna (4 poin list)
   - Pemesanan & Pembayaran (4 poin list)
   - Pengiriman (4 poin list)
   - Retur & Pengembalian (4 poin list)
   - Garansi (4 poin list)
   - Hak Kekayaan Intelektual (3 poin list)
   - Pembatasan Tanggung Jawab (3 poin list)
   - Perubahan S&K (paragraf)
   - Hukum yang Berlaku (paragraf)
   - Kontak (list kontak)
4. Tambahkan alert box info di akhir dengan catatan persetujuan

---

## 6. wishlist.html - Halaman Wishlist (Daftar Keinginan)

### Fungsi Halaman
Menampilkan produk yang di-save user untuk dibeli nanti. User bisa hapus produk dari wishlist atau tambahkan langsung ke keranjang.

### Layout yang Digunakan
- **Grid 4 kolom**: `row g-4` dengan `col-md-3` untuk tiap produk (4 produk per baris)

### Komponen HTML
- **Product card**: Sama seperti halaman produk lain, tapi ada tombol close (×) di pojok kanan atas
- **Tombol close**: Button dengan karakter × untuk hapus produk dari wishlist
- **2 tombol aksi**: "Tambah ke Keranjang" dan "Lihat Detail" disusun vertikal dengan gap

### Bootstrap yang Digunakan
- **Grid**: `row g-4`, `col-md-3`
- **Card**: `card`, `card-body`, `position-relative`
- **Badge**: `badge bg-danger position-absolute` untuk diskon
- **Button**: `btn-primary`, `btn-outline-secondary` dalam `d-grid gap-2` (stack vertikal)
- **Close button**: `position-absolute` dengan koordinat `top: 10px; right: 10px; z-index: 10`
- **Text**: `text-danger` untuk tombol close dan harga, `text-muted` untuk harga coret

### Cara Implementasi
```html
<div class="row g-4">
  <div class="col-md-3">
    <div class="card product-card position-relative">
      <!-- Badge diskon -->
      <span class="badge bg-danger position-absolute" style="top: 10px; left: 10px;">-20%</span>
      
      <!-- Tombol hapus wishlist -->
      <button class="btn-close text-danger position-absolute" style="top: 10px; right: 10px; z-index: 10;">×</button>
      
      <img src="..." class="card-img-top">
      <div class="card-body">
        <h5>Samsung Galaxy S24 Ultra</h5>
        <div>★★★★★ (1234)</div>
        <div class="text-danger">Rp 19.999.000</div>
        <del class="text-muted">Rp 24.999.000</del>
        
        <!-- Button stack vertikal -->
        <div class="d-grid gap-2 mt-3">
          <button class="btn btn-primary">Tambah ke Keranjang</button>
          <button class="btn btn-outline-secondary">Lihat Detail</button>
        </div>
      </div>
    </div>
  </div>
  <!-- repeat untuk produk lain -->
</div>
```

**Z-index**: Tombol close diberi `z-index: 10` agar berada di atas badge diskon (yang juga position absolute).
 
 
---

## Ringkasan Bootstrap yang Digunakan Rasyid

### Layout & Grid System
- **Container**: `container` (wrapper utama dengan max-width responsif)
- **Row & Column**: `row`, `col-lg-*`, `col-md-*`, `col-sm-*`
- **Gutter**: `g-4`, `g-3` (jarak antar kolom dalam grid)
- **Auto margin**: `mx-auto` (center kolom horizontal)
- **Offset**: `offset-sm-3` (skip kolom untuk alignment)

### Breadcrumb (navigasi hierarki)
- **Base**: `breadcrumb`, `breadcrumb-item`
- **Active**: `active` pada item terakhir (tidak bisa diklik)

### Card Components
- **Base**: `card`, `card-body`, `card-header`, `card-title`
- **Image**: `card-img-top` untuk gambar di atas card
- **Height**: `h-100` (card tinggi penuh, berguna untuk card dalam row yang sama)

### Badge & Labels
- **Base**: `badge` dengan warna `bg-success`, `bg-danger`, `bg-warning`, `bg-primary`
- **Position**: Dikombinasi dengan `position-absolute` untuk badge di pojok produk (diskon)

### Button Components
- **Solid**: `btn-primary` (biru), `btn-success` (hijau), `btn-danger` (merah)
- **Outline**: `btn-outline-primary`, `btn-outline-secondary`
- **Size**: `btn-sm` (kecil), `btn-lg` (besar)
- **Width**: `w-100` (lebar penuh), `w-auto` (sesuai konten)
- **Special**: `btn-check` (hidden radio/checkbox input untuk membuat button toggle)

### Form Components
- **Label & Input**: `form-label`, `form-control`
- **Horizontal label**: `col-form-label` untuk label dalam row layout
- **Select**: `form-select` untuk dropdown
- **Checkbox/Radio**: `form-check`, `form-check-input`, `form-check-label`
- **Inline**: `form-check-inline` untuk checkbox/radio horizontal

### Navigation Tabs
- **Base**: `nav`, `nav-tabs`, `nav-item`, `nav-link`
- **Content**: `tab-content`, `tab-pane`
- **State**: `active` (tab terpilih), `fade show` (animasi transisi)
- **Toggle**: Attribute `data-bs-toggle="tab"` dan `href="#id"` untuk switch tab

### Cara Menggunakan Bootstrap
Bootstrap JS otomatis handle interaksi seperti tabs, collapse, modal tanpa perlu JavaScript custom. Cukup tambahkan attribute data seperti `data-bs-toggle="tab"`.
