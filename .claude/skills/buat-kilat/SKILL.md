---
name: buat-kilat
description: Bikin landing page jualan lengkap dari satu cerita singkat pemakai (riset, penawaran, copy, desain, sampai halaman online) dalam satu kali jalan. Pakai saat pemakai ingin cepat jadi, atau menulis "/buat-kilat" diikuti gambaran produknya.
---

# Resep: Buat Kilat

Tujuan: dari satu cerita singkat, pemakai mendapat landing page yang sudah online, menjual, dan rapi di HP. Pemakai tidak perlu menjalankan resep lain satu per satu.

## Langkah

1. **Ambil cerita pemakai.** Kalau pesan pemakai sudah berisi gambaran produk, pakai itu. Kalau belum, minta dalam SATU pesan:
   "Ceritakan singkat saja: produkmu apa, untuk siapa, harganya berapa, dan (kalau sudah ada) link pembayarannya. Boleh juga gaya tampilan yang kamu mau."

2. **Tanya paling banyak 3 hal**, dan hanya kalau benar-benar belum jelas. Urutan prioritas:
   1. Siapa pembelinya dan masalah utama mereka.
   2. Harga (dan promo kalau ada, beserta batas waktunya).
   3. Bukti yang sudah dimiliki (testimoni asli, hasil, pengalaman). Boleh dijawab "belum ada".
   Gabungkan pertanyaan dalam satu pesan bernomor. Untuk tiap pertanyaan, beri satu contoh jawaban supaya pemakai tinggal mengiyakan atau mengubah. Kalau pemakai bilang "terserah kamu", pakai tebakan terbaik dan sebutkan di laporan akhir.

3. **Tulis bahan kerja dengan cepat**, mengikuti format dan aturan resep yang sudah ada:
   - `riset.md` → format di [../riset-pembeli/SKILL.md](../riset-pembeli/SKILL.md)
   - `penawaran.md` → format di [../penawaran/SKILL.md](../penawaran/SKILL.md)
   - `copy.md` → urutan blok, aturan CTA, dan larangan di [../copy-landing-page/SKILL.md](../copy-landing-page/SKILL.md) serta [../copy-landing-page/rumus-hook.md](../copy-landing-page/rumus-hook.md). Pilih sendiri 1 headline terbaik dan simpan 1 cadangan.
   Jangan bertanya lagi di tahap ini.

4. **Bangun halaman** `site/index.html` mengikuti [../builder-landing-page/SKILL.md](../builder-landing-page/SKILL.md), [../builder-landing-page/desain.md](../builder-landing-page/desain.md), dan skill `frontend-design`. Pilih sendiri gaya visual yang cocok dengan produk dan pembelinya, kecuali pemakai sudah menyebutkan gaya. Pakai gambar di `site/gambar/` kalau ada.

5. **Online-kan:**
   - **Jalur HP / cloud:** commit, lalu coba push langsung ke `main`. Kalau push ke `main` ditolak, push ke branch kerja, buat pull request ke `main`, dan beri tahu pemakai cara merge dari HP: github.com → repo → Pull requests → pilih → **Merge pull request** → **Confirm merge**.
   - **Jalur Laptop:** arahkan pemakai ke `/deploy-cloudflare`.

6. **Laporan akhir** (singkat, untuk dibaca di HP):
   - Halaman sudah online di link `.workers.dev` miliknya (ada di dashboard Cloudflare > Workers & Pages > proyek ini). Perubahan biasanya muncul 1–2 menit setelah masuk ke `main`.
   - Tebakan yang kamu ambil sendiri (gaya, harga, pembeli), kalau ada.
   - Yang masih kurang: bukti asli, foto produk, link pembayaran. Untuk gambar, ingatkan caranya: github.com → repo → folder `site/gambar` → Add file → Upload files.
   - Cara revisi: "Ketik saja yang mau diubah, misalnya 'warnanya lebih mewah' atau 'testimoni pindah ke atas harga'."
   - Langkah berikutnya sebelum iklan: `/pasang-tracking`, lalu `/audit-sebelum-iklan`.

## Aturan

- Semua aturan di `CLAUDE.md` tetap berlaku: tanpa testimoni atau angka karangan, tanpa janji penghasilan, tanpa urgensi palsu.
- Bagian yang butuh bukti tapi belum ada ditampilkan sebagai kotak "Bagian ini menunggu bukti asli", bukan diisi karangan.
- Kalau link pembayaran belum ada, semua tombol beli sementara mengarah ke `#harga` dan sebutkan ini di laporan.
