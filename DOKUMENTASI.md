# 📖 DOKUMENTASI PROYEK: `channdraa-afk`
> **Kategori**: GitHub Profile OS & Tactile Developer Showcase  
> **Pengembang**: Chandra ([@channdraa-afk](https://github.com/channdraa-afk)) — Siswa Rekayasa Perangkat Lunak (RPL)  
> **Status Proyek**: 🟢 **STABIL & AKTIF (Production Ready)**  
> **Terakhir Diperbarui**: September 2026

---

## 📌 1. Ringkasan & Filosofi Proyek
Repositori ini adalah repositori khusus profil GitHub (*Special Repository* `channdraa-afk/channdraa-afk`). Repositori ini berfungsi sebagai landing page utama, etalase portofolio, dan cockpit identitas Chandra di GitHub.

### Prinsip Desain: "Playful Tactile Artisan"
- Mengadopsi baseline taktil khas **Duolingo**: tombol fisik 3D tebal dengan rim bayangan tegas, sudut membulat empuk (`rx="16"` hingga `rx="24"`), serta palet warna hangat berenergi.
- **Anti-AI-Slop**: Tidak menggunakan template generik atau gradien ungu-biru pasaran. Seluruh visual utama dibangun menggunakan **Custom Native SVG Engine** yang dirancang presisi per pixel.

---

## 🛠️ 2. Cara-cara & Setup (How-To & Operation)

### A. Alur Kerja Khusus Repositori Profil GitHub
1. Repositori dengan nama yang sama persis dengan username (`channdraa-afk/channdraa-afk`) dan bersifat publik akan secara otomatis dirender oleh GitHub sebagai halaman muka profil.
2. File utama yang dibaca oleh parser GitHub adalah [`README.md`](README.md).
3. Aset lokal disimpan di folder [`assets/`](assets/) dan dipanggil menggunakan path relatif (misal: `assets/header-clean.svg`).

### B. Automasi CI/CD: Contribution Snake Eater
Animasi ular pemakan heatmap kontribusi GitHub diatur melalui GitHub Actions:
- **Lokasi Berkas**: [`.github/workflows/snake.yml`](.github/workflows/snake.yml)
- **Jadwal Eksekusi**:
  - Otomatis setiap 24 jam sekali pada pukul 00:00 UTC via cron: `"0 0 * * *"`.
  - Otomatis setiap kali ada event `push` ke branch `main`.
  - Bisa dipicu manual melalui tab Actions di GitHub via trigger `workflow_dispatch`.
- **Mekanisme Kerja**:
  1. Action `Platane/snk/svg-only@v3` membaca riwayat kontribusi akun `channdraa-afk`.
  2. Menghasilkan dua berkas SVG di direktori sementara `dist/`: versi light dan dark.
  3. Action `crazy-max/ghaction-github-pages@v3.1.0` meng-commit dan men-deploy SVG tersebut ke branch terpisah bernama **`output`**.
  4. File SVG diakses langsung di `README.md` menggunakan URL raw GitHub:
     `https://raw.githubusercontent.com/channdraa-afk/channdraa-afk/output/github-contribution-grid-snake.svg`.

### C. Panduan Pengujian & Render Aset SVG
- Karena browser mengisolasi berkas SVG saat dimuat melalui tag `<img>` (*isolated image document context*), font eksternal berbasis `@import` Google Fonts tidak akan mengunduh font jaringan secara dinamis.
- Gunakan selalu font fallback yang aman: `font-family: 'Nunito', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;`.
- Untuk meninjau SVG secara lokal: cukup buka berkas `.svg` langsung di browser Chrome/Edge.

---

## 📦 3. Apa Saja yang Dipakai (Tech Stack & Assets)

### A. Palet Warna (Tokyonight & Duolingo Fusion)
- **Background Utama**: `#1B272C` (Deep Slate Charcoal)
- **Rim / 3D Shadow Base**: `#131F24`
- **Border Kontur**: `#2E383D` (tebal 2px - 2.5px)
- **Aksen Hijau Zamrud (Duolingo Primary)**: `#58CC02` (Base rim: `#46A302`)
- **Aksen Biru Prussian (Info/Tech)**: `#1CB0F6` (Base rim: `#1899D6`)
- **Aksen Ungu Royal (AI/Memony)**: `#CE82FF` (Base rim: `#A560DB`)
- **Aksen Emas Cerah (XP/Warning)**: `#FFC800` (Base rim: `#E5A500`)
- **Teks Terang**: `#FFFFFF` (Heading), `#A5B4BA` (Body muted), `#E5E9EB` (Chips)

### B. Daftar Aset Custom Native SVG (`assets/`)
1. `header-clean.svg`: Banner hero profil dengan avatar inisial 3D dan kartu Duolingo.
2. `btn-projects.svg`: Tombol taktil hijau 3D (`🚀 VIEW PROJECTS`).
3. `btn-techstack.svg`: Tombol taktil ungu 3D (`🧠 TECH ARSENAL`).
4. `btn-contact.svg`: Tombol taktil biru 3D (`📫 CONTACT ME`).
5. `btn-repos.svg`: Tombol taktil emas 3D (`🔥 ALL REPOSITORIES`).
6. `card-memony.svg`: Kartu showcase proyek unggulan Memony (AI Tactile Expense Ledger).
7. `card-stallmate.svg`: Kartu showcase proyek unggulan Stallmate (Tactile Cashier Engine).
8. `ai-spectrum.svg`: Visualisasi quest path AI & Intelligent Systems vertikal anti-tabrakan dengan XP bar.

### C. Integrasi Pihak Ketiga & API Endpoints
1. **GitHub Readme Stats Mirror**:
   - Endpoint: `https://github-readme-stats-eight-theta.vercel.app/api?username=channdraa-afk`
   - Top Languages: `https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=channdraa-afk`
   - *Catatan Penting*: Menggunakan mirror aktif karena domain publik utama (`github-readme-stats.vercel.app`) sering mengalami `DEPLOYMENT_PAUSED` (HTTP 503/502).
2. **GitHub Readme Streak Stats**:
   - Endpoint: `https://github-readme-streak-stats.herokuapp.com/?user=channdraa-afk`
3. **Readme Typing SVG**:
   - Endpoint: `https://readme-typing-svg.demolab.com` dengan font Fira Code cyan `#38BDF8`.
4. **Shields.io Badges**:
   - Badges tech stack dengan gaya `style=for-the-badge`.
5. **Direct Web Compose Gmail**:
   - URL: `https://mail.google.com/mail/?view=cm&fs=1&to=chandradjhon@gmail.com&su=Collaboration%20Inquiry%20-%20Chandra%20Portfolio`

---

## 📍 4. State Tracker: Riwayat Perjalanan & Status Terkini

| Fase / Tanggal | Fokus Pekerjaan | Detail Implementasi & Solusi | Status |
|---|---|---|---|
| **Sesi Inisialisasi** | Setup Repositori | Pembuatan repositori profil khusus `channdraa-afk/channdraa-afk`. | ✅ Selesai |
| **Sesi Redesain Taktil** | Duolingo Artisan Baseline | Pembuatan Custom Native SVG untuk header, kartu proyek, dan AI Horizon. Menghilangkan ketergantungan pada gambar AI generik. | ✅ Selesai |
| **Sesi Quick-Action** | 4 Tombol 3D Duolingo | Menghubungkan tombol ke anchor lokal dan direct email compose. | ✅ Selesai |
| **Sesi Automasi Snake** | CI/CD GitHub Actions | Setup workflow `snake.yml` dengan push otomatis ke branch `output`. | ✅ Selesai |
| **Sesi Debugging Kritis** | Perbaikan Bug Visual & API | 1. Memulihkan error 502 Bad Gateway dengan mengalihkan stats ke mirror aktif HTTP 200 OK.<br>2. Menghapus wrapper `<table>` pada kartu showcase dan menggantinya dengan `<p align="center">` responsif (menghilangkan border abu-abu kaku bawaan GitHub).<br>3. Menghilangkan whitespace di dalam tag `<a>` untuk memusnahkan artifact garis bawah biru (*underline glitch*).<br>4. Menyinkronkan target anchor heading `id="featured-projects"` dan `id="tech-arsenal"`. | ✅ Tuntas Sempurna |

**Status Terkini**: Seluruh elemen visual, tautan, automasi CI/CD, dan kartu statistik berfungsi 100% tanpa error.

---

## 🚀 5. Roadmap & Rencana Pengembangan Selanjutnya (Next Steps)
- [ ] Menambahkan section sertifikasi / capaian kompetensi RPL masa mendatang.
- [ ] Memperbarui statistik kartu proyek seiring perilisan versi stabil di `Memony` dan `Stallmate`.
- [ ] Menambahkan highlight repositori eksperimen AI baru jika Chandra memulai riset model deep learning.
