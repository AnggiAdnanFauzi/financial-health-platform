# Platform Diagnostik Kesehatan Finansial

Sebuah aplikasi *full-stack* modern untuk menilai kesehatan finansial pribadi maupun perusahaan. Dibangun dengan arsitektur yang terpisah (decoupled) menggunakan antarmuka React SPA dan backend Laravel REST API yang tangguh.

## 🚀 Teknologi yang Digunakan (Tech Stack)

**Frontend:**
- React (Vite)
- TypeScript
- Tailwind CSS (UI/UX Premium)
- Lucide Icons & Framer Motion

**Backend:**
- Laravel 11.x (PHP 8.2+)
- MySQL (Database Cloud via Aiven atau XAMPP Lokal)
- Cloudinary (Penyimpanan Gambar & Aset)

---

## 🛠️ Instalasi & Persiapan Lokal

Ikuti langkah-langkah berikut untuk menjalankan proyek ini di komputer Anda.

### 1. Persiapan Backend (Laravel)

1. Masuk ke dalam folder backend:
   ```bash
   cd backend
   ```
2. Instal dependensi PHP menggunakan Composer:
   ```bash
   composer install
   ```
3. Atur Variabel Environment (Lingkungan):
   - Gandakan file `.env.example` dan ubah namanya menjadi `.env`
   - Buatlah akun Database MySQL Anda sendiri (misalnya lewat Aiven atau XAMPP lokal) dan akun Cloudinary.
   - Isi kunci rahasia dan *password* dari akun-akun tersebut ke dalam file `.env` baru Anda.
4. Buat Application Key (Kunci Aplikasi):
   ```bash
   php artisan key:generate
   ```
5. Jalankan Migrasi & Seeder Database:
   *(Perintah ini akan secara otomatis membuat struktur tabel database dan menyuntikkan akun Super Admin bawaan)*
   ```bash
   php artisan migrate --seed
   ```
6. Jalankan Server Development Laravel:
   ```bash
   php artisan serve
   ```
   *Backend API akan berjalan di http://localhost:8000*

### 2. Persiapan Frontend (React)

1. Buka terminal baru dan pastikan Anda berada di luar (folder utama proyek).
2. Instal dependensi Node.js:
   ```bash
   npm install
   ```
3. Atur Variabel Environment:
   - Buat sebuah file bernama `.env` di dalam folder utama.
   - Jika diperlukan (misalnya API Gemini), buatlah API Key Anda sendiri dan masukkan ke dalam file `.env` tersebut.
4. Jalankan Server Development Vite:
   ```bash
   npm run dev
   ```
   *Frontend akan berjalan di http://localhost:3000 (atau port lain yang ditentukan oleh Vite)*

---

## 🔐 Akun Admin Bawaan

Setelah Anda menjalankan perintah `php artisan migrate --seed` di atas, Anda bisa langsung masuk (Login) ke Panel Admin menggunakan akun berikut:

- **Email:** `admin@financialhealth.com`
- **Password:** `admin123`

---

## ☁️ Catatan Deployment (Hosting)

- Frontend sudah dioptimalkan untuk di-hosting di Vercel (Routing khusus SPA sudah diatur melalui file `vercel.json`).
- Backend membutuhkan server yang mendukung PHP (misalnya Vercel PHP, Heroku, Render, VPS, atau Shared Hosting).
