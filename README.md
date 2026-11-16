# SIPADUHOK

Sistem informasi terpadu dan Learning Management System (LMS) untuk Pusat Kegiatan Belajar Masyarakat (PKBM) — lembaga pendidikan nonformal kesetaraan Paket A, B, dan C.

Sistem ini menggabungkan administrasi sekolah dan pembelajaran daring dalam satu platform dengan rantai validasi antar-jabatan, sehingga setiap keputusan penting harus melalui verifikasi bertingkat.

---

## Fitur Utama

- Integrasi Keuangan & Akademik: Status pembayaran tagihan berfungsi sebagai gerbang otomatis untuk akses ujian semester dan rapor.
- Rantai Validasi Rapor: Alur berjenjang (Wali Kelas -> Bendahara -> Ketua PKBM -> Terbit) untuk mencegah penerbitan rapor sepihak.
- LMS Daring: Pembagian materi, penugasan, forum diskusi, dan ujian online dengan sistem pengawasan perilaku real-time (deteksi perpindahan tab & heartbeat).
- Bantuan AI (Human-in-the-Loop): Pembuatan draf soal ujian dan rekomendasi penilaian esai menggunakan AI, dengan keputusan akhir tetap di tangan guru.
- Pembayaran Online: Integrasi Midtrans Snap dengan validasi webhook SHA-512.
- Keamanan: Dilengkapi Cloudflare Turnstile, RBAC 9 peran pengguna, proteksi IDOR, enkripsi credential pembayaran, dan audit log finansial.
- Multi-Cabang & Arsip: Pemisahan data per cabang serta fitur arsip materi/soal lintas tahun ajaran.

---

## Tech Stack

- Backend: Laravel 11 (PHP ^8.2)
- Frontend: Blade, Bootstrap 5, Vite, Tailwind CSS
- Database: MySQL
- AI Integration: Groq API (utama), Google Gemini API (cadangan)
- Payment Gateway: Midtrans
- Testing: PHPUnit 10

---

## Statistik Sistem

- Peran Pengguna: 9 role
- Rute: Sekitar 800 rute
- Database: 54 model, 57 migrasi
- Pengujian Otomatis: 80 test, 427 assertions

---

## Cara Instalasi

1. Clone repositori dan install dependensi:
   composer install
   npm install

2. Siapkan environment file:
   cp .env.example .env
   php artisan key:generate

3. Sesuaikan konfigurasi database dan API key di file .env:
   - Database (DB_*)
   - Midtrans (MIDTRANS_*)
   - AI Service (GROQ_API_KEY / GOOGLE_AI_API_KEY)
   - Cloudflare Turnstile (TURNSTILE_*)

4. Jalankan migrasi dan seeder:
   php artisan migrate --seed

5. Build asset frontend:
   npm run build

6. Jalankan server lokal:
   php artisan serve

---

## Pengujian

Untuk menjalankan unit dan feature test otomatis:

php artisan test

---

## Lisensi

Proyek ini menggunakan lisensi MIT.
