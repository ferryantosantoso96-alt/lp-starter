---
name: gandakan-produk
description: Siapkan folder baru untuk produk berikutnya dengan memakai desain halaman yang sudah jadi sebagai template. Pakai saat pemakai ingin membuat landing page untuk produk lain.
---

# Resep: Gandakan untuk Produk Baru

Tujuan: produk kedua dan seterusnya cukup 30–60 menit, karena desain dan resep sudah terbukti.

## Jalur HP

Di sesi cloud kamu hanya bisa mengubah repo ini, jadi pemakai yang membuat repo baru:

1. Tanyakan nama produk baru, lalu sarankan nama repo pendek (huruf kecil dan tanda hubung).
2. Minta pemakai membuat repo baru yang kosong dan Private di github.com, lalu memberi akses repo itu ke Claude.
3. Di repo INI, salin `site/index.html` menjadi `template/index-template.html`, commit, dan push. Jelaskan bahwa di sesi baru nanti, file ini dan semua resep perlu dibawa ke repo baru.
4. Jelaskan langkah selanjutnya: buka sesi Claude Code baru di repo baru, minta Claude menyalin `.claude/`, `CLAUDE.md`, `MULAI-DI-SINI.md`, dan `template/index-template.html` dari repo ini (repo lama perlu ikut disambungkan ke sesi itu), lalu mulai dari `/riset-pembeli`. Cloudflare disambungkan ulang ke repo baru lewat `/deploy-cloudflare`.

## Jalur Laptop

1. Tanyakan nama produk baru, lalu buat nama folder pendek dari situ (huruf kecil dan tanda hubung, misalnya `ebook-resep-jualan`).
2. Jelaskan: kamu akan membuat folder baru di sebelah folder ini (satu tingkat di atas), dan mungkin aplikasi meminta izin karena menulis di luar folder sekarang.
3. Buat folder `../<nama-folder>/` lalu salin:
   - `.claude/` (semua resep)
   - `CLAUDE.md` dan `MULAI-DI-SINI.md`
   - `site/index.html` disalin menjadi `template/index-template.html` (sebagai contoh desain, BUKAN halaman final)
4. Di folder baru, buat file kosong `riset.md`, `penawaran.md`, `copy.md`, dan folder `site/gambar/`.
5. Tambahkan catatan di awal `CLAUDE.md` folder baru:
   "Saat menjalankan `/builder-landing-page`, pakai `template/index-template.html` sebagai acuan gaya dan susunan (warna, font, komponen). Semua teks, harga, gambar, dan link harus diganti dari `copy.md` dan `penawaran.md` produk ini. Jangan membawa teks produk lama."
6. Jangan menyalin `riset.md`, `penawaran.md`, `copy.md`, `audit.md`, atau gambar produk lama.
7. Tutup dengan petunjuk:
   - Taruh gambar produk baru di `site/gambar/`.
   - Di aplikasi Claude, buka folder baru lewat **Open folder…**.
   - Mulai dari `/riset-pembeli`. Tahap pembangunan halaman akan jauh lebih cepat karena memakai template.
   - Saat deploy, buat proyek Cloudflare Pages baru dan subdomain baru untuk produk ini.
