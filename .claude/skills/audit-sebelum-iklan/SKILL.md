---
name: audit-sebelum-iklan
description: Periksa landing page dengan checklist 20 poin (isi, tombol, tampilan HP, kecepatan, pixel, kebijakan iklan) dan tulis laporannya ke audit.md. Pakai sebelum memasang iklan, atau setiap kali halaman selesai diubah besar.
---

# Resep: Audit Sebelum Iklan

Tujuan: menemukan masalah sebelum uang iklan terbuang.

## Langkah

1. Baca `site/index.html`, `copy.md`, dan `penawaran.md`. Kalau pemakai memberi link halaman online, buka juga link itu.
2. Jalankan semua poin di [checklist.md](checklist.md). Untuk tiap poin beri status: LULUS, PERBAIKI, atau CEK MANUAL (hal yang harus dicek pemakai sendiri, misalnya tampilan di HP-nya).
3. Untuk poin yang bisa kamu perbaiki sendiri di `site/index.html` (typo, alt gambar kosong, link tombol beda-beda, meta tag hilang), tanya dulu: "Mau aku perbaiki sekarang?" Perbaiki setelah pemakai setuju.
4. Tulis `audit.md`: tanggal, ringkasan (jumlah LULUS/PERBAIKI/CEK MANUAL), lalu tabel semua poin.
5. Beri vonis singkat:
   - **Siap iklan**: tidak ada PERBAIKI tersisa.
   - **Belum siap**: sebutkan maksimal 3 hal paling penting yang harus dibereskan dulu.
6. Kalau siap, ingatkan: halaman di Cloudflare perlu di-upload ulang setelah perbaikan (`/deploy-cloudflare`), lalu sarankan pemakai mengecek kecepatan di pagespeed.web.dev.

## Aturan

- Jangan melunakkan temuan. Klaim berisiko dan link pembayaran yang salah selalu PERBAIKI.
- Jangan menandai LULUS untuk sesuatu yang tidak bisa kamu periksa; pakai CEK MANUAL.
