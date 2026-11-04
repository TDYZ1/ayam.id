# Penjelasan Code HTML - Jackie

## 1. privacy-policy.html

### Struktur Utama
- **DOCTYPE & Head**: HTML5 dengan Bootstrap 5.3.0, charset UTF-8, responsive viewport
- **Navbar**: Sticky-top navbar dengan brand "TechStore", menu horizontal, tombol Wishlist/Keranjang/Login

### Container Centered (col-lg-8 mx-auto)
- Heading "Kebijakan Privasi" + tanggal update terakhir (text-muted)
- 13 section dengan h4 heading dan paragraf/list:

**Section Kebijakan Privasi**:
1. **Pendahuluan**: Komitmen privasi TechStore
2. **Informasi yang Kami Kumpulkan**: Unordered list 4 jenis data (Pribadi, Transaksi, Teknis, Interaksi) dengan tag `<strong>` untuk label
3. **Cara Kami Mengumpulkan Informasi**: List 3 poin (form registrasi, cookies, pihak ketiga)
4. **Penggunaan Informasi**: Paragraf intro + list 6 poin tujuan penggunaan data
5. **Pembagian Informasi**: Paragraf "tidak menjual data" + list 3 kategori pembagian (Penyedia Layanan, Kewajiban Hukum, Transfer Bisnis) dengan label strong
6. **Keamanan Data**: Paragraf intro + list 4 langkah keamanan (enkripsi SSL, server aman, akses terbatas, audit berkala)
7. **Cookies**: Paragraf intro + list 3 kegunaan cookies + paragraf catatan tentang disable cookies
8. **Hak Anda**: Paragraf intro + list 5 hak user (akses, perbaiki, hapus, tolak marketing, tarik persetujuan) + paragraf kontak email
9. **Penyimpanan Data**: Paragraf durasi penyimpanan dan penghapusan data
10. **Privasi Anak-Anak**: Paragraf kebijakan usia minimal 17 tahun
11. **Tautan ke Situs Pihak Ketiga**: Disclaimer tanggung jawab
12. **Perubahan Kebijakan Privasi**: Paragraf hak update kebijakan
13. **Kontak**: Paragraf intro + list 3 kontak (email privacy@, telepon, alamat fisik)

- Alert box (alert-success) dengan komitmen TechStore

### Footer
Standard 4 kolom footer (sama dengan halaman lain)

---

## 2. order-history.html

### Layout 2 Kolom

**Sidebar Kiri (col-md-3)** - Profile Menu:
- Card dengan gambar profil (rounded-circle 100x100px), nama "Budi Santoso", email
- List group menu: Profil Saya, Pesanan Saya (active), Wishlist, Logout (text-danger)

**Content Kanan (col-md-9)**:
- Heading "Riwayat Pesanan"
- 4 order card dengan struktur sama:

**Order Card** (class order-card):
- **Header** (d-flex justify-content-between):
  - Order ID (h6) + tanggal kecil (text-muted)
  - Status badge dengan class dinamis (status-success/status-info/status-warning)
- **Product Items** (d-flex align-items-center):
  - Gambar produk 80x80px (inline style width, height, object-fit, border-radius)
  - Nama produk (h6), varian (text-muted), harga per item
  - Bisa multiple items dalam 1 order
- **Footer** (border-top, d-flex justify-content-between):
  - Total Pembayaran dengan warna (text-danger untuk paid, text-muted untuk cancelled)
  - Button group (btn-sm): "Lihat Detail", "Beli Lagi", "Lacak Paket" (tergantung status)

**Status Badge Variants**:
- `status-success` untuk "Selesai" (hijau)
- `status-info` untuk "Dikirim" (biru)
- `status-warning` untuk "Dibatalkan" (kuning)

**4 Order yang Ditampilkan**:
1. Order #TS2026100123 - Selesai - Samsung Galaxy S24 Ultra (Rp 19.999.000)
2. Order #TS2026100089 - Dikirim - 2 items: Sony WH-1000XM5 + AirPods Pro (Rp 8.198.000)
3. Order #TS2026090567 - Selesai - MacBook Air M3 (Rp 17.999.000)
4. Order #TS2026080234 - Dibatalkan - iPad Pro (Rp 14.999.000)

- Pagination 3 halaman di bawah

---

## 3. order-detail.html

### Header
- d-flex justify-content-between: Heading "Detail Pesanan" + tombol "Kembali" (btn-outline-secondary)

### Layout 2 Kolom

**Kolom Kiri (col-lg-8)**:

**Card 1 - Status Pengiriman**:
- Header: Order ID (h5) + tanggal detail + status badge
- **Timeline Vertical** dengan 5 tahap menggunakan inline style:
  - Setiap tahap: d-flex dengan icon (rounded-circle bg-success 30x30px), vertical line (bg-success 2px width, 40px height, margin-left 14px)
  - Tahap: Pesanan Selesai → Paket Diterima → Dalam Pengiriman → Pesanan Diproses → Pesanan Dibuat
  - Setiap tahap ada timestamp (text-muted)
  - Checkmark (✓) dalam circle untuk completed steps

**Card 2 - Produk yang Dibeli**:
- Card header: "Produk yang Dibeli"
- Product item: d-flex dengan gambar 100x100px, info produk (nama, varian, qty x harga), total di kanan (text-danger)
- Border-bottom pada item
- Summary section:
  - Subtotal
  - Ongkir dengan label (text-success "Gratis")
  - Biaya Admin
  - Total Pembayaran (strong, text-danger)

**Kolom Kanan (col-lg-4)**:

**Card 1 - Alamat Pengiriman**:
- Nama (strong), telepon, alamat lengkap 3 baris (text-muted) dengan `<br>` tag

**Card 2 - Metode Pembayaran**:
- Metode (strong): "Transfer Bank BCA"
- Status bayar (text-muted) dengan timestamp

**Card 3 - Nomor Resi**:
- Ekspedisi (strong): "JNE Regular"
- Nomor resi dalam `<code>` tag: JNE1234567890123
- Tombol "Lacak Paket" (btn-outline-primary btn-sm w-100)

---

## 4. login.html

### Form Login (card auth-card)
Centered card dengan class auth-card:
- Heading "Login ke TechStore" (text-center)
- Form dengan 2 input field:
  1. **Email atau Nomor Telepon**: Text input (bukan email type untuk fleksibilitas)
  2. **Password**: Password input
- **Checkbox & Link row** (d-flex justify-content-between):
  - Checkbox "Ingat Saya" (form-check-input)
  - Link "Lupa Password?" (text-decoration-none)
- Tombol "Login" (btn-primary w-100) link ke profile.html
- Text "Belum punya akun? Daftar Sekarang" (link ke register.html)
- **Divider** (hr my-4)
- **Social Login** (d-grid gap-2):
  - Button "Login dengan Google" (btn-outline-secondary)
  - Button "Login dengan Facebook" (btn-outline-secondary)

### Class auth-card
Custom class untuk styling centered login/register form

---

## 5. index.html

### Hero Section
- **hero-section** class dengan gradient/background
- Container dengan:
  - h1: "Selamat Datang di TechStore"
  - Paragraf tagline
  - CTA button "Belanja Sekarang" (btn-light btn-lg) link ke products.html

### Section Kategori Produk
- Heading "Kategori Produk" (class section-title)
- Grid 3 kolom (col-md-4, row g-4)
- 3 kategori card (class category-card):
  - Wrapped dalam `<a>` dengan inline style `text-decoration: none; color: inherit;`
  - Gambar placeholder 400x200px
  - Card body text-center dengan h5 nama kategori
- **Kategori**: Smartphone, Laptop, Tablet

### Section Produk Unggulan
- Heading "Produk Unggulan" (class section-title)
- Grid 4 kolom (col-md-3, row g-4)
- 4 product card (sama struktur seperti products.html):
  - Badge discount (absolute position top-left)
  - Gambar 300x220px
  - Card body: nama (h5), rating bintang, harga + harga coret, tombol "Lihat Detail" (w-100 mt-2)
- **Produk**: Samsung S24 Ultra (-20%), iPhone 15 Pro Max (-15%), MacBook Air M3 (-25%), Sony WH-1000XM5 (-30%)

### Navbar
- Menu "Home" dengan class `active`
- Brand "ayam.id" (bukan TechStore - inconsistency dalam file)

---

## 6. faq.html

### Container Centered (col-lg-8 mx-auto)
- Heading "Frequently Asked Questions (FAQ)" (text-center mb-5)
- 5 kategori FAQ dengan h4 heading masing-masing

### Struktur FAQ dengan HTML `<details>` Element
Setiap FAQ menggunakan native HTML details/summary:
- **`<details>`** tag (mb-3)
- **`<summary>`** dengan class `p-3 bg-light rounded` dan inline style `cursor: pointer;` berisi pertanyaan dalam `<strong>`
- Konten jawaban dalam div `p-3 border border-top-0 rounded-bottom` berisi paragraf dan/atau list

**5 Kategori FAQ**:

**1. Pemesanan & Pembayaran** (3 FAQ):
- Cara memesan (ordered list 6 langkah)
- Metode pembayaran (unordered list 5 metode: Bank Transfer, Kartu Kredit, E-Wallet, Cicilan, COD)
- Pembatalan pesanan (paragraf penjelasan)

**2. Pengiriman** (3 FAQ):
- Waktu pengiriman (list 4 opsi: Same Day, JNE Express, Regular, Luar Jawa)
- Gratis ongkir (paragraf: minimal Rp 500.000)
- Cara melacak pesanan (list 3 cara)

**3. Produk & Garansi** (3 FAQ):
- Produk original (paragraf: 100% original, tidak KW)
- Masa garansi (list 3 kategori: Smartphone 1 tahun, Laptop 1-2 tahun, Aksesoris 6 bulan-1 tahun)
- Cara klaim garansi (paragraf instruksi)

**4. Retur & Pengembalian** (2 FAQ):
- Retur/tukar barang (list 3 kondisi dengan durasi 7 hari + paragraf syarat)
- Proses refund (paragraf: 3-7 hari kerja)

**5. Akun & Keamanan** (3 FAQ):
- Cara mendaftar (paragraf step-by-step)
- Reset password (paragraf instruksi)
- Keamanan data (paragraf tentang enkripsi SSL)

### CTA Card
- Card bg-light text-center di bawah FAQ
- Heading h5, paragraf, tombol "Hubungi Kami" (btn-primary) link ke contact.html

### Note
Brand inconsistency: navbar brand "ayam.id" tapi title dan footer "TechStore"

---

## Komponen Bootstrap yang Digunakan

- **Layout**: Container, row, col-* (responsive grid)
- **Cards**: card, card-header, card-body
- **Navbar**: navbar, navbar-toggler, navbar-collapse (sticky-top)
- **Badges**: badge bg-success/warning/primary
- **Buttons**: btn (primary/outline/sm/lg), btn-group
- **Forms**: form-control, form-label, form-check, form-select
- **List group**: list-group, list-group-item, list-group-item-action, active
- **Alert**: alert, alert-success, alert-info
- **Utilities**: d-flex, justify-content-between, text-center, text-muted, mb-*, mt-*, p-*, gap-*, w-100
- **Pagination**: pagination, page-item, page-link
- **Native HTML**: `<details>` dan `<summary>` untuk accordion FAQ

## Custom Classes
- `auth-card`: Styling untuk centered login/register card
- `hero-section`: Banner utama dengan background
- `section-title`: Heading untuk section
- `category-card`: Card kategori produk
- `product-card`: Card produk dengan hover effect
- `order-card`: Card untuk order item
- `status-badge`: Badge status dengan variant (success/info/warning)
