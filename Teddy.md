# Penjelasan Code HTML - Teddy

## 1. cart.html - Halaman Keranjang Belanja

### Fungsi Halaman
Menampilkan produk yang sudah ditambahkan ke keranjang, user bisa ubah quantity, hapus produk, input kode promo, dan lanjut ke checkout.

### Layout yang Digunakan
- **Layout 2 kolom**: Kolom kiri lebih besar (col-lg-8) untuk daftar item keranjang, kolom kanan (col-lg-4) untuk ringkasan belanja dan promo

### Komponen HTML
- **Cart item**: Setiap produk ditampilkan dalam row dengan gambar, info, quantity selector, harga, dan tombol hapus
- **Quantity selector**: Input group dengan tombol minus (-), input number, tombol plus (+)
- **Ringkasan belanja**: Card berisi subtotal, diskon, ongkir, total, dan tombol checkout
- **Input promo**: Input field dengan tombol "Gunakan"

### Bootstrap yang Digunakan
- **Grid**: `row`, `col-lg-8`, `col-lg-4`, `col-md-2/3/4` untuk layout item
- **Card**: `card`, `card-body`, `card-title` untuk ringkasan dan promo
- **Input group**: `input-group`, `input-group-text` untuk quantity selector
- **Form**: `form-control`, `form-control-sm` (input kecil)
- **Button**: `btn-sm`, `btn-outline-secondary` (minus/plus), `btn-primary`, `btn-outline-primary`, `btn-success`
- **Flexbox**: `d-flex`, `align-items-center` untuk layout item horizontal
- **Text**: `text-center`, `text-end`, `text-danger` (harga & hapus), `text-success` (ongkir gratis), `text-muted`
- **Spacing**: `mb-3`, `mt-3`, `mb-0` untuk jarak
- **Width**: `w-100` (tombol full width), inline style `max-width: 120px` untuk quantity input

### Cara Implementasi

**1. Cart Item**
```html
<div class="cart-item mb-3">
  <div class="row align-items-center">
    <div class="col-md-2">
      <img src="..." width="100" height="100">
    </div>
    <div class="col-md-4">
      <h5>Samsung Galaxy S24 Ultra</h5>
      <p class="text-muted mb-0">Warna: Titanium Black</p>
      <p class="text-muted">Kapasitas: 256GB</p>
    </div>
    <div class="col-md-2 text-center">
      <div class="input-group" style="max-width: 120px;">
        <button class="btn btn-sm btn-outline-secondary">-</button>
        <input type="text" class="form-control form-control-sm text-center" value="1">
        <button class="btn btn-sm btn-outline-secondary">+</button>
      </div>
    </div>
    <div class="col-md-3 text-end">
      <h5 class="text-danger mb-0">Rp 19.999.000</h5>
    </div>
    <div class="col-md-1 text-end">
      <button class="btn text-danger">×</button>
    </div>
  </div>
</div>
```

**2. Ringkasan Belanja**
```html
<div class="card">
  <div class="card-body">
    <h5 class="card-title">Ringkasan Belanja</h5>
    <hr>
    <div class="d-flex justify-content-between mb-2">
      <span>Total Harga (3 barang)</span>
      <span>Rp 42.197.000</span>
    </div>
    <div class="d-flex justify-content-between mb-2">
      <span>Diskon</span>
      <span class="text-danger">- Rp 8.801.000</span>
    </div>
    <div class="d-flex justify-content-between mb-2">
      <span>Ongkir</span>
      <span class="text-success">Gratis</span>
    </div>
    <hr>
    <div class="d-flex justify-content-between mb-3">
      <strong>Total Pembayaran</strong>
      <strong class="text-danger">Rp 42.197.000</strong>
    </div>
    <a href="checkout.html" class="btn btn-primary w-100 mb-2">Checkout</a>
    <a href="products.html" class="btn btn-outline-secondary w-100">Lanjut Belanja</a>
  </div>
</div>
```

**3. Card Kode Promo**
```html
<div class="card mt-3">
  <div class="card-body">
    <h6>Punya Kode Promo?</h6>
    <div class="input-group">
      <input type="text" class="form-control" placeholder="Masukkan kode">
      <button class="btn btn-outline-primary">Gunakan</button>
    </div>
  </div>
</div>
```

---

## 2. category-accessories.html

### Bug/Issue
File ini **copy-paste error** dari category-smartphone.html:
- Title: "Smartphone" (seharusnya "Accessories")
- Breadcrumb: "Smartphone" (seharusnya "Accessories")
- Heading: "Smartphone" (seharusnya "Accessories")
- Navbar: menu "Smartphone" active (seharusnya tidak ada yang active atau Aksesoris)
- **Konten**: Menampilkan 12 smartphone, bukan accessories

### Yang Seharusnya
Kategori Accessories harus menampilkan produk seperti:
- Mouse (Logitech MX Master, Razer, dll)
- Keyboard (Mechanical, wireless, dll)
- Charger & Cable
- Case & Cover
- Screen Protector
- Power Bank
- Hub & Adapter
- dll

---

## 2. about.html - Halaman Tentang Kami

### Fungsi Halaman
Menampilkan informasi tentang TechStore: deskripsi perusahaan, statistik, keunggulan, visi & misi.

### Layout yang Digunakan
- **Section 1 - Hero**: 2 kolom (text di kiri, gambar di kanan)
- **Section 2 - Statistics**: 4 kolom berisi angka statistik
- **Section 3 - Why Choose Us**: 6 fitur dalam grid 3 kolom
- **Section 4 - Visi & Misi**: 2 kolom dengan background abu

### Komponen HTML
- **Lead text**: Paragraf pembuka dengan ukuran lebih besar menggunakan class `lead`
- **Stat cards**: Card tanpa border berisi angka besar dan label
- **Feature cards**: Card dengan emoji icon, heading, dan deskripsi
- **Background section**: Div dengan background `bg-light` dan padding besar

### Bootstrap yang Digunakan
- **Grid**: `row`, `col-lg-6`, `col-md-3`, `col-md-4` untuk berbagai section
- **Card**: `card`, `card-body`, `border-0` (hilangkan border), `h-100` (tinggi sama)
- **Image**: `img-fluid rounded` untuk gambar responsif dengan sudut melengkung
- **Text**: `text-center`, `text-primary` (warna biru untuk angka), `text-muted` (deskripsi)
- **Lead**: `lead` untuk paragraf tagline yang lebih besar
- **Background**: `bg-light` untuk section dengan background abu
- **Spacing**: `mb-5`, `mb-4`, `mb-3`, `p-5` (padding besar)
- **Rounded**: `rounded` untuk sudut section melengkung

### Cara Implementasi

**1. Hero Section**
```html
<div class="row mb-5">
  <div class="col-lg-6">
    <h1>Tentang TechStore</h1>
    <p class="lead">Toko elektronik terpercaya sejak 2020</p>
    <p>TechStore adalah toko elektronik online...</p>
    <p>Kami menyediakan produk original...</p>
  </div>
  <div class="col-lg-6">
    <img src="..." class="img-fluid rounded">
  </div>
</div>
```

**2. Statistics Section**
```html
<div class="row text-center mb-5">
  <div class="col-md-3 mb-4">
    <div class="card border-0 h-100">
      <div class="card-body text-center">
        <h2 class="text-primary mb-3">100K+</h2>
        <h5>Pelanggan Puas</h5>
      </div>
    </div>
  </div>
  <!-- repeat 3x untuk statistik lain -->
</div>
```

**3. Why Choose Us (dengan emoji)**
```html
<div class="row mb-5">
  <div class="col-12 mb-4">
    <h2 class="text-center">Mengapa Memilih TechStore?</h2>
  </div>
  <div class="col-md-4 mb-4">
    <div class="card h-100">
      <div class="card-body text-center">
        <div class="mb-3" style="font-size: 3rem;">✓</div>
        <h5>Produk 100% Original</h5>
        <p class="text-muted">Semua produk dijamin original...</p>
      </div>
    </div>
  </div>
  <!-- repeat 5x untuk fitur lain: 🚚 💳 🔒 ⚡ 💬 -->
</div>
```
Emoji dibuat besar dengan inline style `font-size: 3rem`.

**4. Visi & Misi**
```html
<div class="row bg-light p-5 rounded">
  <div class="col-12">
    <h2 class="text-center mb-4">Visi & Misi Kami</h2>
  </div>
  <div class="col-md-6 mb-4">
    <h4>Visi</h4>
    <p>Menjadi platform e-commerce...</p>
  </div>
  <div class="col-md-6 mb-4">
    <h4>Misi</h4>
    <p>Menyediakan produk berkualitas...</p>
  </div>
</div>
```

---

## 4. category-gaming.html

### Bug/Issue
File ini **copy-paste error** dari category-smartphone.html - **KONTEN SALAH TOTAL**:
- Title: "Smartphone" (seharusnya "Gaming")
- Breadcrumb: "Smartphone" (seharusnya "Gaming")
- Heading: "Smartphone" (seharusnya "Gaming")
- Navbar: menu "Smartphone" active
- **Konten**: Menampilkan 12 smartphone, bukan gaming products

### Yang Seharusnya
Kategori Gaming harus menampilkan:
- Gaming Console (PlayStation 5, Xbox Series X, Nintendo Switch)
- Gaming Laptop
- Gaming Monitor
- Gaming Keyboard
- Gaming Mouse
- Gaming Headset
- VR Headset
- Gaming Chair
- dll

---

## 5. category-audio.html

### Bug/Issue
File ini **copy-paste error** dari category-smartphone.html - **KONTEN SALAH TOTAL**:
- Title: "Smartphone" (seharusnya "Audio")
- Breadcrumb: "Smartphone" (seharusnya "Audio")
- Heading: "Smartphone" (seharusnya "Audio")
- Navbar: menu "Smartphone" active
- **Konten**: Menampilkan 12 smartphone, bukan audio products

### Yang Seharusnya
Kategori Audio harus menampilkan:
- Headphone (Sony WH-1000XM5, Bose, Sennheiser, dll)
- Earbuds (AirPods Pro, Galaxy Buds, dll)
- Bluetooth Speaker (JBL, Harman Kardon, dll)
- Soundbar
- Home Audio System
- Gaming Headset
- Microphone
- dll

---

## 6. 404.html

### Struktur Utama
- **Navbar**: Standard navbar
- Container text-center dengan inline style `padding: 100px 0;`

### Error Content

**404 Display**:
- h1 dengan inline style:
  - font-size: 150px
  - font-weight: 700
  - color: #667eea
  - Text: "404"

**Error Message**:
- h2 "Oops! Halaman Tidak Ditemukan"
- p.lead "Maaf, halaman yang Anda cari tidak dapat ditemukan atau telah dipindahkan."

**Action Buttons** (d-flex justify-content-center gap-3):
- "Kembali ke Home" (btn-primary btn-lg) → index.html
- "Lihat Produk" (btn-outline-primary btn-lg) → products.html

**Suggestions Section** (mt-5):
- h4 "Mungkin Anda mencari:"
- Row g-3 justify-content-center dengan 4 button (col-auto):
  - "Smartphone" (btn-outline-secondary) → category-smartphone.html
  - "Laptop" (btn-outline-secondary) → category-laptop.html
  - "Aksesoris" (btn-outline-secondary) → category-accessories.html
  - "Kontak Kami" (btn-outline-secondary) → contact.html

---

## Custom Classes untuk Cart

**cart-item**: Class untuk styling item di cart dengan properties:
- Border/padding untuk separation
- Hover effects (kemungkinan)
- Responsive layout adjustments

## Bootstrap Components yang Digunakan

**Form Components**:
- input-group: Wrapper untuk quantity selector
- form-control, form-control-sm: Input fields
- btn-sm: Small button size

**Layout**:
- d-flex, justify-content-between, justify-content-center
- align-items-center
- gap-3: Spacing antara flex items
- text-center, text-end, text-muted
- col-auto: Auto-width column

**Cards**:
- card-title: Card heading
- border-0: Borderless card
- bg-light: Light background
- h-100: Full height

**Buttons**:
- btn-lg: Large button
- btn-outline-*: Outline button variants
- w-100: Full width

**Typography**:
- lead: Larger paragraph text
- h1-h6: Heading hierarchy

**Spacing**:
- my-5, mb-4, mt-3, mt-5, p-5: Margin/padding utilities

**Colors**:
- text-primary, text-danger, text-success, text-muted

## Bug Summary untuk Teddy's Pages

**3 File dengan Copy-Paste Error**:
1. **category-accessories.html**: Isi smartphone, seharusnya accessories
2. **category-gaming.html**: Isi smartphone, seharusnya gaming products
3. **category-audio.html**: Isi smartphone, seharusnya audio products

**Impact**: User tidak bisa browse kategori Accessories, Gaming, dan Audio dengan benar karena menampilkan produk yang salah (smartphone semua).

**Fix Needed**: Ganti konten produk di 3 file tersebut dengan produk yang sesuai kategorinya + update title, breadcrumb, heading, dan navbar active state.


