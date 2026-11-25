---
name: builder-landing-page
description: Bangun landing page interaktif, modern, dan cepat di site/index.html dari copy.md dan penawaran.md. Pakai setelah copy-landing-page, atau saat pemakai minta mengubah tampilan, warna, susunan, gambar, atau link tombol.
---

# Resep: Builder Landing Page

Tujuan: `site/index.html` satu file yang terlihat mahal, terasa hidup, cepat dibuka di HP, dan semua tombolnya mengarah ke pembayaran.

## Langkah membangun pertama kali

1. Baca `copy.md` dan `penawaran.md`. Kalau `copy.md` kosong, minta pemakai menjalankan `/copy-landing-page`, lalu berhenti.
2. Lihat isi `site/gambar/`. Catat gambar yang ada. Jangan memakai gambar dari internet. Kalau kosong dan kamu berjalan di Jalur HP, beri tahu pemakai cara upload: github.com → repo ini → folder `site/gambar` → Add file → Upload files. Boleh lanjut tanpa gambar dan menambahkannya nanti.
3. Tanyakan gaya visual dengan 3 pilihan singkat yang cocok dengan produk dan pembelinya (misalnya "Bersih & profesional", "Berani & energik", "Hangat & ramah"). Tanyakan juga apakah ada warna merek.
4. Baca [desain.md](desain.md) dan ikuti semua aturannya. Untuk arah visual (palet, tipografi, tata letak), ikuti juga skill `frontend-design`. Kalau keduanya bertentangan: `frontend-design` menang soal estetika, `desain.md` menang soal hal teknis dan jualan (tombol beli, kecepatan, kejujuran, tampilan HP).
5. Bangun `site/index.html` dengan urutan blok dari `copy.md`. Pakai teks dari `copy.md` apa adanya; jangan menambah klaim baru.
6. Semua tombol beli:
   - `href` = link pembayaran dari `penawaran.md`. Kalau `BELUM ADA`, pakai `#harga` sementara dan catat sebagai pekerjaan yang belum beres.
   - Beri atribut `class="cta"` dan `data-cta="<lokasi>"` (`hero`, `harga`, `penutup`, `melayang`) supaya bisa dilacak pixel nanti.
7. Bagian `[BUTUH BUKTI: ...]` di copy: tampilkan sebagai kotak abu-abu bertuliskan "Bagian ini menunggu bukti asli" supaya pemakai ingat, dan jangan diisi karangan.
8. Hapus `site/gambar/TARUH-GAMBAR-DI-SINI.txt` kalau masih ada.
9. Setelah selesai, beri tahu pemakai cara melihat hasilnya:
   - **Jalur HP:** commit dan push, lalu tawarkan membuat pull request ke `main`. Link preview Cloudflare biasanya muncul di halaman pull request dan di dashboard Cloudflare > proyek > Deployments. Kalau Cloudflare belum disambungkan, minta pemakai menjalankan `/deploy-cloudflare` dulu.
   - **Jalur Laptop:** buka folder `site`, klik dua kali `index.html`. Untuk tampilan HP di Chrome: tekan F12, lalu Ctrl+Shift+M (Mac: Cmd+Option+I, lalu Cmd+Shift+M).
10. Tutup dengan daftar: hal yang masih kurang (bukti, gambar, link pembayaran) dan langkah berikutnya: "Kalau tampilannya sudah oke dan link pembayaran sudah tersambung, ketik `/deploy-cloudflare`."

## Saat pemakai memberi link pembayaran

Perbarui bagian "Link pembayaran" di `penawaran.md`, lalu ganti `href` SEMUA tombol `.cta` (hero, harga, penutup, melayang) dengan link itu. Sebutkan jumlah tombol yang diganti.

## Saat pemakai minta revisi

- Pemakai akan bicara dengan bahasa biasa ("tombolnya kebesaran", "warnanya kurang mewah"). Terjemahkan ke perubahan yang tepat, kerjakan, lalu sebutkan apa yang diubah dalam 1–2 kalimat.
- Ubah hanya yang diminta. Jangan merombak bagian lain.
- Kalau permintaannya melanggar aturan di `CLAUDE.md` (misalnya menambah testimoni karangan atau hitung mundur palsu), tolak dengan sopan dan tawarkan alternatif jujur.
