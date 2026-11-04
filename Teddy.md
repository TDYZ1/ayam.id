# Penjelasan Code HTML - Teddy

## 1. cart.html

### Struktur Utama
- **Navbar**: Standard navbar TechStore
- Heading "Keranjang Belanja"

### Layout 2 Kolom

**Kolom Kiri (col-lg-8)** - Cart Items:

**Cart Item Structure** (class cart-item):
- Row align-items-center dengan 5 kolom:
  1. **col-md-2**: Gambar produk 100x100px
  2. **col-md-4**: Info produk
     - h5 nama produk
     - 2 paragraf text-muted untuk varian/spesifikasi
  3. **col-md-2 text-center**: Quantity selector
     - input-group dengan max-width 120px (inline style)
     - Button "-" (btn-sm btn-outline-secondary)
     - Input text center (form-control-sm) dengan value
     - Button "+" (btn-sm btn-outline-secondary)
  4. **col-md-3 text-end**: Harga (h5 text-danger mb-0)
  5. **col-md-1 text-end**: Tombol hapus (✕ text-danger)

**3 Item di Cart**:
1. Samsung Galaxy S24 Ultra - Titanium Black 256GB - Rp 19.999.000
2. Sony WH-1000XM5 Headphone - Black - Rp 4.199.000
3. MacBook Air M3 13" - 8GB/256GB - Rp 17.999.000

**Kolom Kanan (col-lg-4)** - 2 Cards:

**Card 1 - Ringkasan Belanja**:
- h5 card-title "Ringkasan Belanja"
- Divider (hr)
- d-flex justify-content-between lines:
  - Total Harga (3 barang): Rp 42.197.000
  - Diskon: - Rp 8.801.000 (text-danger)
  - Ongkir: Gratis (text-success)
- Divider (hr)
- Total Pembayaran (strong, text-danger): Rp 42.197.000
- 2 buttons:
  - "Checkout" (btn-primary w-100 mb-2) link ke checkout.html
  - "Lanjut Belanja" (btn-outline-secondary w-100) link ke products.html

**Card 2 - Kode Promo** (mt-3):
- h6 "Punya Kode Promo?"
- input-group:
  - Input text (placeholder "Masukkan kode")
  - Button "Gunakan" (btn-outline-primary)

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

## 3. about.html

### Struktur Utama
- Navbar dengan menu "Tentang" active

### Section 1 - Hero About (row mb-5)

**Kolom Kiri (col-lg-6)**:
- h1 "Tentang TechStore"
- p.lead: Tagline tentang toko
- 2 paragraf deskripsi perusahaan (didirikan 2020, 100K+ pelanggan, brand partner)

**Kolom Kanan (col-lg-6)**:
- Gambar 600x400px (img-fluid rounded) placeholder

### Section 2 - Statistics (row text-center mb-5)

4 cards (col-md-3 mb-4) dengan border-0 h-100:
- **Card body** text-center:
  - h2 angka (text-primary mb-3): 100K+, 5000+, 50+, 24/7
  - h5 label: Pelanggan Puas, Produk Tersedia, Brand Partner, Customer Support

### Section 3 - Why Choose Us (row mb-5)

**Heading**: "Mengapa Memilih TechStore?" (text-center)

6 cards (col-md-4 mb-4) dengan h-100:
- **Card body text-center**:
  - Div emoji (mb-3) dengan inline style font-size 3rem: ✓, 🚚, 💳, 🔒, ⚡, 💬
  - h5 judul fitur
  - p.text-muted penjelasan

**6 Fitur**:
1. ✓ Produk 100% Original
2. 🚚 Gratis Ongkir
3. 💳 Pembayaran Mudah
4. 🔒 Transaksi Aman
5. ⚡ Pengiriman Cepat
6. 💬 Customer Support 24/7

### Section 4 - Vision & Mission (row bg-light p-5 rounded)

**Centered content**:
- h2 "Visi & Misi Kami" (text-center mb-4)
- Row dengan 2 kolom (col-md-6 mb-4):
  - **Visi**: h4 + paragraf
  - **Misi**: h4 + paragraf

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
