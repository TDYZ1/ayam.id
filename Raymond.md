# Penjelasan Code HTML - Raymond

## 1. contact.html

### Struktur Utama
- **Navbar**: Sticky-top navbar dengan menu "Kontak" active
- Heading "Hubungi Kami" (text-center mb-5)

### Layout 2 Kolom

**Kolom Kiri (col-lg-6)** - Form Kontak:
- Card dengan h-100 (full height)
- Heading "Kirim Pesan"
- Form dengan 5 field:
  1. **Nama Lengkap**: Text input
  2. **Email**: Email input
  3. **Nomor Telepon**: Tel input
  4. **Subjek**: Text input
  5. **Pesan**: Textarea dengan rows="5"
- Submit button "Kirim Pesan" (btn-primary w-100)

**Kolom Kanan (col-lg-6)** - Info:

**Card 1 - Informasi Kontak**:
- 5 section dengan emoji icon dan strong label:
  - 📍 **Alamat**: Jl. Sudirman dengan `<br>` untuk multi-line
  - 📧 **Email**: 2 email (info@ dan support@)
  - 📞 **Telepon**: +62 21 1234 5678
  - 💬 **WhatsApp**: +62 812 3456 7890
  - 🕐 **Jam Operasional**: 3 baris (Senin-Jumat, Sabtu, Minggu)

**Card 2 - Ikuti Kami**:
- Heading "Ikuti Kami"
- d-flex gap-3 dengan 4 button social media:
  - Facebook (btn-outline-primary)
  - Twitter (btn-outline-info)
  - Instagram (btn-outline-danger)
  - WhatsApp (btn-outline-success)

### Google Maps Section
- Row mt-5 full width (col-12)
- Card dengan card-body p-0 (no padding)
- `<iframe>` Google Maps embed:
  - src dengan embed URL (Universitas Mikroskil Building B)
  - width="100%", height="400", style="border:0;"
  - Attributes: allowfullscreen, loading="lazy", referrerpolicy="strict-origin-when-cross-origin"

---

## 2. compare.html

### Struktur Utama
- Heading "Bandingkan Produk" (text-center mb-5)
- Div table-responsive wrapper

### Comparison Table
**Bootstrap table** (table table-bordered):

**Thead** (bg-light):
- 4 kolom dengan width style:
  - Kolom 1 (20%): "Spesifikasi"
  - Kolom 2-4 (26.66% each): Product comparison
- **Product Header** di kolom 2-4:
  - Gambar 200x200px (img-fluid, inline style max-height 200px, object-fit cover)
  - h5 nama produk
  - h6 harga (text-danger)
  - Button "Lihat Detail" (btn-sm btn-primary)

**Tbody** - 13 rows:

**Row Spesifikasi** (11 rows):
1. **Layar**: Display size, type, resolution, refresh rate dengan `<br>` separator
2. **Prosesor**: Chip name
3. **RAM**: Memory size
4. **Storage**: Storage options separated by `/`
5. **Kamera Belakang**: Multiple cameras separated by `+`
6. **Kamera Depan**: Front camera MP
7. **Baterai**: Capacity + fast charge info dengan `<br>`
8. **Sistem Operasi**: OS version + UI dengan `<br>`
9. **Fitur Khusus**: 3 features separated by `<br>`
10. **Berat**: Weight in gram
11. **Rating**: Star rating + review count

**Row Harga** (bg-light):
- Label "Harga" (strong)
- 3 kolom dengan h5 text-danger mb-0

**Row Action Buttons**:
- Empty first cell
- 3 kolom text-center dengan 2 button stack:
  - "Tambah ke Keranjang" (btn-primary w-100 mb-2)
  - "Lihat Detail" (btn-outline-secondary w-100)

### Produk yang Dibandingkan:
1. Samsung Galaxy S24 Ultra (Rp 19.999.000)
2. iPhone 15 Pro Max (Rp 21.999.000)
3. Google Pixel 8 Pro (Rp 15.999.000)

### Bottom Section
- Text-center mt-4
- Link "Lihat Produk Lainnya" (btn-outline-primary) ke category-smartphone.html

---

## 3. checkout.html

### Heading & Layout
- Heading "Checkout"
- Row dengan 2 kolom: col-lg-8 (form) dan col-lg-4 (summary)

### Kolom Kiri (col-lg-8) - 3 Cards:

**Card 1 - Alamat Pengiriman**:
- Card header bg-white dengan h5 "Alamat Pengiriman"
- Form dengan layout row/col:
  - **Row 1** (2 kolom col-md-6):
    - Nama Lengkap (text input)
    - Nomor Telepon (tel input)
  - **Alamat Lengkap**: Textarea rows="3"
  - **Row 2** (2 kolom col-md-6):
    - Provinsi (select dropdown dengan 5 options)
    - Kota/Kabupaten (select dropdown dengan 5 options)
  - **Row 3** (2 kolom col-md-6):
    - Kecamatan (select dropdown)
    - Kode Pos (text input)

**Card 2 - Metode Pengiriman**:
- 3 radio button options dengan form-check:
  - **Layout per option**: Radio input + label w-100 dengan d-flex justify-content-between
  - Left side: Nama ekspedisi (strong) + estimasi (small text-muted) dengan `<br>`
  - Right side: Harga (strong)
- **Options**:
  1. JNE Regular (2-3 hari) - Gratis (checked)
  2. JNE Express (1 hari) - Rp 25.000
  3. Same Day Delivery (hari ini) - Rp 50.000

**Card 3 - Metode Pembayaran**:
- 5 radio button options (form-check):
  1. Transfer Bank (BCA, Mandiri, BNI, BRI) - checked
  2. Kartu Kredit/Debit
  3. E-Wallet (GoPay, OVO, Dana, ShopeePay)
  4. Cicilan 0% (Kartu Kredit)
  5. COD (Cash on Delivery)

### Kolom Kanan (col-lg-4) - Ringkasan Pesanan:

**Card** - Ringkasan Pesanan:
- Card header bg-white dengan h5
- **Product List** (3 items):
  - d-flex mb-2 structure:
    - Gambar 60x60px (inline style width, height, object-fit, border-radius)
    - Product name (small strong) + quantity x harga (small text-muted) dengan `<br>`
- **Divider** (hr)
- **Summary Lines** (d-flex justify-content-between):
  - Subtotal (3 barang): Rp 42.197.000
  - Ongkir: Gratis (text-success)
  - Biaya Admin: Rp 0
- **Divider** (hr)
- **Total** (d-flex justify-content-between mb-3):
  - Label (strong)
  - Amount (strong text-danger)
- Button "Bayar Sekarang" (btn-success w-100) link ke order-history.html

**Produk di Checkout**:
1. Samsung Galaxy S24 Ultra (Rp 19.999.000)
2. Sony WH-1000XM5 (Rp 4.199.000)
3. MacBook Air M3 13" (Rp 17.999.000)

---

## 4. category-tablet.html

### Catatan
File ini **copy-paste error** dari category-smartphone.html:
- Title masih "Smartphone" (seharusnya "Tablet")
- Breadcrumb "Smartphone" (seharusnya "Tablet")
- Heading h2 "Smartphone" (seharusnya "Tablet")
- Navbar menu active di "Smartphone" (seharusnya tidak ada yang active atau di Tablet)
- **Konten produk**: Menampilkan smartphone (Samsung S24, iPhone, Xiaomi, dll) bukan tablet

### Produk yang Seharusnya Ditampilkan
Seharusnya menampilkan produk tablet seperti:
- iPad Pro, iPad Air
- Samsung Galaxy Tab
- Microsoft Surface
- Xiaomi Pad
- Lenovo Tab
- dll

---

## 5. category-smartphone.html

### Struktur Utama
- Breadcrumb: Home → Smartphone
- Heading "Smartphone"
- Grid 4 kolom (col-md-3, row g-4)

### Produk Grid
12 product card dengan struktur standard:
- Badge discount (jika ada diskon) - position-relative di card, span absolute top-left
- Gambar placeholder 300x250px
- Card body:
  - Nama produk (h5 card-title)
  - Rating bintang dengan jumlah review
  - Harga (dengan/tanpa harga coret)
  - Button "Lihat Detail" (btn-primary w-100)

**12 Smartphone yang Ditampilkan**:
1. Samsung Galaxy S24 Ultra (-20%) - Rp 19.999.000
2. iPhone 15 Pro Max 256GB (-15%) - Rp 21.999.000
3. Xiaomi 14 Pro 12GB/512GB - Rp 12.999.000
4. Google Pixel 8 Pro 256GB - Rp 15.999.000
5. OnePlus 12 16GB/512GB (-12%) - Rp 13.199.000
6. OPPO Find X7 Pro 16GB/512GB - Rp 16.999.000
7. Vivo X100 Pro 12GB/512GB (-18%) - Rp 13.099.000
8. Realme GT 5 Pro 12GB/256GB - Rp 8.999.000
9. Samsung Galaxy S23 Ultra (-25%) - Rp 16.999.000
10. Nothing Phone 2 12GB/256GB - Rp 7.999.000
11. Asus ROG Phone 8 Pro (-10%) - Rp 17.999.000
12. Sony Xperia 1 V 12GB/256GB - Rp 18.999.000

### Navbar
Menu "Smartphone" dengan class active

---

## 6. category-laptop.html

### Struktur Utama
- Breadcrumb: Home → Laptop
- Heading "Laptop"
- Grid 4 kolom (col-md-3, row g-4)

### Produk Grid
12 product card dengan struktur sama seperti category-smartphone

**12 Laptop yang Ditampilkan**:
1. MacBook Air M3 13" 8GB/256GB (-25%) - Rp 17.999.000
2. MacBook Pro 14" M3 Pro 18GB/512GB - Rp 34.999.000
3. ASUS ROG Zephyrus G14 RTX 4070 - Rp 24.999.000
4. Dell XPS 13 Plus i7 16GB/512GB (-15%) - Rp 22.099.000
5. Lenovo ThinkPad X1 Carbon Gen 11 - Rp 28.999.000
6. HP Spectre x360 14" i7 16GB/1TB (-20%) - Rp 23.999.000
7. MSI Stealth 14 Studio RTX 4060 - Rp 26.999.000
8. Acer Swift X SFX14 Ryzen 7 RTX 3050 (-18%) - Rp 12.299.000
9. ASUS Vivobook Pro 15 OLED i7 - Rp 14.999.000
10. Razer Blade 14 Ryzen 9 RTX 4070 (-22%) - Rp 31.199.000
11. Microsoft Surface Laptop 5 i7 16GB - Rp 21.999.000
12. LG Gram 17" i7 16GB/512GB (-12%) - Rp 19.799.000

### Navbar
Menu "Laptop" dengan class active

---

## Komponen Bootstrap yang Digunakan

**Forms & Inputs**:
- form-control: Text, email, tel, textarea inputs
- form-label: Label untuk input
- form-select: Dropdown/select element
- form-check: Radio button/checkbox container
- form-check-input: Radio/checkbox input
- form-check-label: Label untuk radio/checkbox

**Tables**:
- table: Base table class
- table-bordered: Border pada semua cell
- table-responsive: Wrapper untuk horizontal scroll
- thead, tbody, tr, td, th: Table elements

**Cards**:
- card, card-header, card-body
- bg-white: White background untuk header
- h-100: Full height card

**Layout**:
- container, row, col-lg-*, col-md-*
- d-flex, justify-content-between, gap-3
- text-center, mb-*, mt-*, p-0

**Buttons**:
- btn-primary, btn-outline-primary
- btn-success, btn-outline-success
- btn-info, btn-outline-info
- btn-danger, btn-outline-danger
- btn-sm: Small button
- w-100: Full width button

**Utilities**:
- text-danger, text-success, text-muted
- mb-*, mt-*: Margin spacing
- img-fluid: Responsive image

**Navbar**:
- navbar, navbar-expand-lg
- sticky-top: Fixed navbar saat scroll

**Breadcrumb**:
- breadcrumb, breadcrumb-item

## Custom Classes dari CSS
- product-card: Styling untuk card produk
- badge-discount: Badge diskon di corner produk
- product-rating: Styling rating bintang
- product-price: Styling harga produk
- product-price-old: Harga coret (sebelum diskon)

## Bug/Issue yang Ditemukan
1. **category-tablet.html**: Salah konten, masih copy dari smartphone
2. **Google Maps iframe**: Menampilkan lokasi Universitas Mikroskil (bukan TechStore Jakarta)
