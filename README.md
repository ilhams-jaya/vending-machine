# 🛒 Vending Machine Application

## Deskripsi Aplikasi

Aplikasi Vending Machine adalah simulasi mesin penjual otomatis yang dibangun menggunakan **Next.js** (Frontend) dan **JSON Server** (Backend). Aplikasi ini memungkinkan pengguna untuk:

### Fitur Utama:
- **🛍️ Keranjang Belanja**: Menambah/menghapus produk, mengatur quantity
- **💰 Sistem Pembayaran**: Menerima uang dalam berbagai denominasi (Rp2.000 - Rp50.000)
- **📦 Manajemen Stok**: Update stok otomatis setelah pembelian
- **📜 Riwayat Transaksi**: Melihat semua transaksi yang telah dilakukan
- **🔄 Pengembalian Uang**: Fitur refund jika pembelian dibatalkan

### Produk yang Tersedia:
- **Minuman**: Aqua 600ml, Teh Botol 350ml, Kopi Kaleng
- **Snack**: Wafer Cokelat, Keripik Kentang 45g

### Teknologi yang Digunakan:
- **Frontend**: Next.js 15, React 19, TypeScript, Tailwind CSS
- **Backend**: JSON Server (REST API)
- **State Management**: React Hooks (useState, useEffect)
- **HTTP Client**: Axios
- **UI Components**: React Hot Toast untuk notifikasi

## Cara Instalasi & Menjalankan JSON Server

### Prerequisites:
- Node.js (versi 18 atau lebih baru)
- npm atau yarn

### 1. Install JSON Server (jika belum ada):
```bash
npm install -g json-server
```

### 2. Menjalankan JSON Server:
```bash
# Masuk ke direktori backend
cd backend

# Jalankan JSON Server pada port 3001
json-server --watch db.json --port 3001
```

**Catatan**: Pastikan JSON Server berjalan di port 3001 karena aplikasi frontend sudah dikonfigurasi untuk menggunakan `http://localhost:3001` sebagai API endpoint.

### 3. Verifikasi JSON Server:
Setelah server berjalan, Anda dapat mengakses:
- **Produk**: http://localhost:3001/products
- **Denominasi**: http://localhost:3001/denominations
- **Transaksi**: http://localhost:3001/transactions

## Cara Menjalankan Aplikasi (Dev Mode)

### 1. Install Dependencies:
```bash
# Masuk ke direktori frontend
cd frontend

# Install semua dependencies
npm install
```

### 2. Menjalankan Aplikasi:
```bash
# Jalankan dalam mode development
npm run dev
```

Aplikasi akan berjalan di **http://localhost:3000**

### 3. Akses Aplikasi:
Buka browser dan kunjungi `http://localhost:3000` untuk menggunakan aplikasi vending machine.

## Struktur Proyek

```
Vending Machine/
├── backend/
│   └── db.json              # Database JSON dengan data produk, denominasi, dan transaksi
└── frontend/
    ├── src/
    │   └── app/
    │       ├── page.tsx     # Halaman utama vending machine
    │       ├── history/
    │       │   └── page.tsx # Halaman riwayat transaksi
    │       └── layout.tsx   # Layout aplikasi
    ├── package.json         # Dependencies dan scripts
    └── README.md           # Dokumentasi frontend
```

## API Endpoints

### Produk
- `GET /products` - Mendapatkan semua produk
- `PATCH /products/:id` - Update stok produk

### Denominasi
- `GET /denominations` - Mendapatkan semua denominasi uang yang diterima

### Transaksi
- `GET /transactions` - Mendapatkan riwayat transaksi
- `POST /transactions` - Menyimpan transaksi baru

## Catatan Tambahan

### 🔧 Troubleshooting:
1. **Error "Gagal memuat data"**: Pastikan JSON Server berjalan di port 3001
2. **Port 3000 sudah digunakan**: Gunakan `npm run dev -- -p 3001` untuk mengubah port
3. **CORS Error**: JSON Server sudah dikonfigurasi untuk mengizinkan CORS

### 📝 Fitur Tambahan:
- **Responsive Design**: Aplikasi dapat diakses dari desktop maupun mobile
- **Real-time Updates**: Stok produk terupdate secara real-time
- **Error Handling**: Pesan error yang informatif untuk debugging
- **Loading States**: Indikator loading saat memuat data

### 🚀 Deployment:
Untuk deployment ke production:
1. Build aplikasi: `npm run build`
2. Start production server: `npm start`
3. Pastikan JSON Server juga berjalan di server production

### 🔒 Keamanan:
- Aplikasi ini adalah demo/simulasi
- Untuk production, implementasikan autentikasi dan validasi yang lebih ketat
- Pertimbangkan menggunakan database yang lebih robust seperti PostgreSQL atau MongoDB

### 📊 Monitoring:
- Semua transaksi disimpan dengan timestamp
- Stok produk terupdate otomatis
- Riwayat transaksi dapat diakses melalui menu "Riwayat"

---

**Dibuat dengan ❤️ menggunakan Next.js dan JSON Server**
