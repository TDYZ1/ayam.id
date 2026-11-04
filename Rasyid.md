# Penjelasan Code HTML - Rasyid

## 1. product-detail.html

### Struktur Utama
- **DOCTYPE & Head**: Halaman HTML5 dengan charset UTF-8, responsive viewport, Bootstrap 5.3.0, dan CSS custom
- **Navbar**: Navigation bar dengan brand "TechStore", menu horizontal (Home, Produk, kategori), dan tombol Keranjang/Login di kanan
- **Breadcrumb**: Navigasi hierarchical (Home → Smartphone → Samsung Galaxy S24 Ultra)

### Section Detail Produk (row layout)
**Kolom Kiri (col-lg-5)**:
- Gambar produk utama besar (500x500px)
- 3 thumbnail gambar kecil (80x80px) untuk preview

**Kolom Kanan (col-lg-7)**:
- Judul produk (h1): "Samsung Galaxy S24 Ultra"
- Rating bintang dengan jumlah review
- Harga diskon (Rp 19.999.000) dan harga coret (Rp 24.999.000)
- Badge status: "Stok Tersedia" (hijau) dan "Diskon 20%" (kuning)
- **Pilihan Warna**: 3 color swatch (hitam, abu, putih) dengan inline style background-color
- **Pilihan Kapasitas**: Radio button group untuk 256GB/512GB/1TB menggunakan btn-check dan btn-outline-primary
- Tombol aksi: "Tambah ke Keranjang" (primary, flex-grow-1), "Wishlist" (outline), "Beli Sekarang" (success, full width)

### Tabs Section
**Nav Tabs** dengan 3 tab:
1. **Deskripsi**: Paragraf penjelasan produk + list fitur unggulan (S Pen, Galaxy AI, kamera 200MP, baterai 5000mAh)
2. **Spesifikasi**: Tabel spec-table dengan 9 row (Layar, Prosesor, RAM, Storage, Kamera, Baterai, OS, Berat)
3. **Review**: 2 review card dengan nama reviewer, tanggal, rating bintang, dan komentar

### Footer
4 kolom (col-md-3):
- TechStore description
- Kategori links (Smartphone, Laptop, Tablet)
- Informasi links (Tentang, Kontak, FAQ)
- Hubungi Kami (email, phone)

---

## 2. products.html

### Struktur Utama
- Navbar sama seperti product-detail, dengan "Produk" menu active
- Breadcrumb: Home → Semua Produk

### Layout 2 Kolom

**Sidebar Kiri (col-lg-3)** - Filter:
- **Kategori**: 6 checkbox (Smartphone, Laptop, Tablet, Aksesoris, Audio, Gaming)
- **Harga**: 4 checkbox range (<5jt, 5-10jt, 10-20jt, >20jt)
- **Brand**: 5 checkbox (Samsung, Apple, Xiaomi, ASUS, Sony)
- **Rating**: 3 checkbox (5 bintang, 4+ bintang, 3+ bintang)

**Content Kanan (col-lg-9)**:
- Header dengan jumlah produk (48 produk) dan dropdown sort (Harga, Rating, Terbaru)
- Grid produk: 3 kolom (col-md-4) dengan 12 produk
- **Product Card** berisi:
  - Badge discount (absolute position top-left)
  - Gambar placeholder
  - Nama produk (h5)
  - Rating bintang dengan jumlah review
  - Harga (dengan/tanpa harga coret)
  - Tombol "Lihat Detail" (primary, full width)
- **Pagination**: Bootstrap pagination component (Previous, 1-4, Next)

---

## 3. profile.html

### Layout 2 Kolom

**Sidebar Kiri (col-md-3)**:
- Card profil dengan gambar rounded-circle, nama "Budi Santoso", email
- List group menu: Profil Saya (active), Pesanan Saya, Wishlist, Logout (text-danger)

**Content Kanan (col-md-9)**:

**Card 1 - Informasi Profil**:
- Form dengan 5 field row layout (label col-sm-3, input col-sm-9):
  - Nama Lengkap (text input dengan value)
  - Email (email input)
  - Nomor Telepon (tel input)
  - Jenis Kelamin (select dropdown)
  - Tanggal Lahir (date input)
- Tombol "Simpan Perubahan" (primary) dengan offset-sm-3

**Card 2 - Alamat Pengiriman**:
- 2 alamat tersimpan dalam border rounded box:
  - **Alamat 1**: Label "Rumah" + badge "Utama" (primary), nama + telepon, alamat lengkap 3 baris, link Edit/Hapus di kanan
  - **Alamat 2**: Label "Kantor", sama formatnya tanpa badge utama
- Tombol "+ Tambah Alamat Baru" (outline-primary)

---

## 4. register.html

### Form Registrasi (card auth-card)
Centered form dengan 9 field:
1. **Nama Lengkap**: Text input dengan placeholder
2. **Email**: Email input
3. **Nomor Telepon**: Tel input (placeholder "08xx xxxx xxxx")
4. **Password**: Password input (minimal 8 karakter)
5. **Konfirmasi Password**: Password input
6. **Jenis Kelamin**: Radio button inline (Laki-laki/Perempuan) dengan form-check-inline
7. **Tanggal Lahir**: Date input
8. **Checkbox Agreement**: Link ke terms.html dan privacy-policy.html
9. Tombol "Daftar" (primary, full width) link ke login.html
10. Text "Sudah punya akun? Login" di bawah

---

## 5. terms.html

### Container Centered (col-lg-8 mx-auto)
- Heading "Syarat & Ketentuan" + tanggal update (text-muted)
- 11 section dengan h4 heading:
  1. **Pendahuluan**: Paragraf sambutan
  2. **Akun Pengguna**: Unordered list 4 poin (usia minimal, akurasi data, keamanan, penangguhan)
  3. **Pemesanan & Pembayaran**: List 4 poin (perubahan harga, konfirmasi pembayaran, pembatalan, metode bayar)
  4. **Pengiriman**: List 4 poin (waktu proses, estimasi, force majeure, alamat)
  5. **Retur & Pengembalian**: List 4 poin (7 hari, kondisi produk, syarat retur, biaya)
  6. **Garansi**: List 4 poin (garansi resmi, service center, pengecualian, tanggung jawab)
  7. **Hak Kekayaan Intelektual**: List 3 poin (copyright, larangan, trademark)
  8. **Pembatasan Tanggung Jawab**: List 3 poin (kerugian, akurasi, gangguan teknis)
  9. **Perubahan S&K**: Paragraf tentang hak update
  10. **Hukum yang Berlaku**: Paragraf jurisdiksi Indonesia
  11. **Kontak**: List kontak (email, telepon, WhatsApp)
- Alert box (alert-info) dengan catatan persetujuan

---

## 6. wishlist.html

### Grid Produk (row g-4)
5 produk dalam col-md-3 (4 kolom per baris):

**Product Card** dengan struktur:
- Badge discount di top-left (beberapa produk)
- Tombol close (✕) di top-right (text-danger, absolute position, z-index 10) untuk hapus dari wishlist
- Gambar produk placeholder
- Card body:
  - Nama produk (h5)
  - Rating bintang dengan jumlah review
  - Harga (dengan/tanpa harga coret)
  - 2 tombol stack (d-grid gap-2):
    - "Tambah ke Keranjang" (primary)
    - "Lihat Detail" (outline-secondary)

**Produk yang ditampilkan**:
1. Samsung Galaxy S24 Ultra (-20%)
2. iPhone 15 Pro Max (-15%)
3. MacBook Air M3 (-25%)
4. Sony WH-1000XM5 (-30%)
5. ASUS ROG Zephyrus G14 (tanpa diskon)

### Komponen Bootstrap yang Digunakan di Semua Page
- Grid system (container, row, col-*)
- Navbar & navbar-toggler
- Card & card-body
- Form controls (input, select, checkbox, radio)
- Buttons & button groups
- Badges
- Tabs & tab-pane
- Breadcrumb
- Pagination
- List group
- Alert
