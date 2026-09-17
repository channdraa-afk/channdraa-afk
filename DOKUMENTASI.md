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

### A. Palet Warna (Everdeck Design Tokens & Adaptive Dual-Theme)
- **Mode Gelap (Dark Mode)**:
  - Latar Belakang Kartu: `#18191E` (Everdeck Dark Slate — kontras tegas terhadap `#0d1117`)
  - Rim 3D Base: `#121316`
  - Border Kontur: `#2D3139` (tebal 2.5px)
  - Teks Utama: `#FFFFFF` (Heading) & `#94A3B8` (Body/Desc)
- **Mode Terang (Light Mode)**:
  - Latar Belakang Kartu: `#FFFFFF` (Crisp Pure White)
  - Rim 3D Base: `#CBD5E1`
  - Border Kontur: `#E2E8F0`
  - Teks Utama: `#0F172A` (Deep Slate) & `#64748B` (Muted)
- **Palet Tombol Taktil 3D (Khas Everdeck)**:
  - `btn-projects`: **Everdeck Emerald** (`#10B981`, rim: `#059669`)
  - `btn-techstack`: **Everdeck Sky Blue** (`#0EA5E9`, rim: `#0284C7`)
  - `btn-contact`: **Everdeck Amber Gold** (`#F59E0B`, rim: `#D97706`)
  - `btn-repos`: **Everdeck Royal Violet** (`#8B5CF6`, rim: `#7C3AED`)

### B. Daftar Aset Custom Native SVG (`assets/`)
1. `header-dark.svg` & `header-light.svg`: Banner hero profil adaptif dengan avatar inisial 3D.
2. `card-memony-dark.svg` & `card-memony-light.svg`: Kartu showcase proyek unggulan Memony (Dual-Theme).
3. `card-stallmate-dark.svg` & `card-stallmate-light.svg`: Kartu showcase proyek unggulan Stallmate (Dual-Theme).
4. `ai-spectrum-dark.svg` & `ai-spectrum-light.svg`: Quest path AI & Intelligent Systems Horizon (Dual-Theme).
5. `btn-projects.svg`: Tombol taktil hijau Everdeck 3D (`🚀 VIEW PROJECTS`).
6. `btn-techstack.svg`: Tombol taktil biru Everdeck 3D (`🧠 TECH ARSENAL`).
7. `btn-contact.svg`: Tombol taktil amber Everdeck 3D (`📫 CONTACT ME`).
8. `btn-repos.svg`: Tombol taktil ungu Everdeck 3D (`🔥 ALL REPOSITORIES`).
9. `card-companion-dark.svg` & `card-companion-light.svg`: Kartu companion taktil simetris (`495x195`) bersanding dengan GitHub Streak Counter. Menampilkan Chibi Violet Evergarden (membawa surat lilin merah berapi dari Everdeck) dengan Base64 embedded URI, status flame aktif, dan kutipan dedikasi kode.

### C. Integrasi Pihak Ketiga & API Endpoints
1. **GitHub Readme Stats Mirror (Dual-Theme Adaptive & Clean Metrics)**:
   - Dark: `https://github-readme-stats-eight-theta.vercel.app/api?username=channdraa-afk&theme=tokyonight&bg_color=18191E&border_color=2D3139&hide_rank=true`
   - Light: `https://github-readme-stats-eight-theta.vercel.app/api?username=channdraa-afk&theme=default&bg_color=FFFFFF&border_color=E2E8F0&hide_rank=true`
   - *Catatan Penting*: Menggunakan mirror aktif dan parameter `hide_rank=true` agar tidak menampilkan rating penilaian diri sendiri (A+).
2. **GitHub Readme Streak Stats (Dual-Theme Adaptive & Live Counter)**:
   - Dark: `theme=tokyonight&background=18191E&border_color=2D3139`
   - Light: `theme=default&background=FFFFFF&border_color=E2E8F0`
   - *Mekanisme Kerja*: Angka streak terupdate otomatis berdasarkan commit harian Chandra (bertambah +1 setiap hari jika ada minimal 1 commit sebelum 00:00 UTC, dan reset ke 0 jika absen).
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
| **Sesi Debugging Kritis** | Perbaikan Bug Visual & API | 1. Memulihkan error 502 Bad Gateway dengan mengalihkan stats ke mirror aktif HTTP 200 OK.<br>2. Menghapus wrapper `<table>` pada kartu showcase dan menggantinya dengan `<p align="center">` responsif.<br>3. Menghilangkan whitespace di dalam tag `<a>` untuk memusnahkan artifact garis bawah biru (*underline glitch*).<br>4. Menyinkronkan target anchor heading `id="featured-projects"` dan `id="tech-arsenal"`. | ✅ Tuntas Sempurna |
| **Sesi Dual-Theme Adaptif** | Jalan 1 & Palet Everdeck | 1. Menerapkan elemen `<picture>` adaptif preferensi OS/GitHub (`prefers-color-scheme`) pada seluruh komponen.<br>2. Mengharmonisasi 4 tombol 3D dengan palet resmi Everdeck (`#10B981`, `#0EA5E9`, `#F59E0B`, `#8B5CF6`).<br>3. Merilis varian SVG Dark (Everdeck Dark Slate `#18191E`) & Light (Crisp White `#FFFFFF`). | ✅ Tuntas Sempurna |
| **Sesi Pemurnian Visual** | Pembersihan Badge & Self-Rank | 1. Menghapus badge tema perantara yang mengganggu keindahan header.<br>2. Mengeliminasi lingkaran rating "A+" via `hide_rank=true` agar profil berfokus murni pada data kontribusi nyata. | ✅ Tuntas Sempurna |
| **Sesi Everdeck Companion** | Chibi Violet Companion Card | Menggantikan kartu stats kosong dengan Custom Tactile Companion Card bergambar Chibi Violet Evergarden membawa surat lilin berapi (aset dari Everdeck) yang bersanding simetris (`495x195`, `height="165"`) dengan GitHub Streak Stats. Memanfaatkan Base64 data URI embedding agar lolos proteksi sub-resource SVG di browser & GitHub Camo. | ✅ Tuntas Sempurna |

**Status Terkini**: Profil tampil bersih, seimbang dan simetris, berkarakter dengan maskot Chibi Violet Evergarden, adaptif sempurna terhadap tema terang & gelap, serta siap produksi 100%.

---

## 🚀 5. Roadmap & Rencana Pengembangan Selanjutnya (Next Steps)
- [ ] Menambahkan section sertifikasi / capaian kompetensi RPL masa mendatang.
- [ ] Memperbarui statistik kartu proyek seiring perilisan versi stabil di `Memony` dan `Stallmate`.
- [ ] Menambahkan highlight repositori eksperimen AI baru jika Chandra memulai riset model deep learning.
