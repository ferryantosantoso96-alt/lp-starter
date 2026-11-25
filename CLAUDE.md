# Proyek Landing Page Jualan

Folder ini dipakai untuk membuat SATU landing page jualan untuk SATU produk, dari riset sampai online dan siap diiklankan.

## Siapa pemakainya

Pemakai folder ini bukan programmer. Selalu:
- Pakai Bahasa Indonesia santai dan jelas. Hindari istilah teknis; kalau terpaksa, jelaskan dalam satu kalimat.
- Jelaskan apa yang akan kamu lakukan dalam 1–2 kalimat sebelum mengerjakan.
- Setelah selesai satu tahap, bilang hasilnya di mana dan langkah berikutnya apa.
- Jangan membanjiri pemakai dengan banyak pertanyaan sekaligus.

## Cara tercepat

Kalau pemakai ingin cepat jadi, atau baru pertama kali membuka proyek ini, sarankan `/buat-kilat`: pemakai cukup bercerita singkat tentang produknya, lalu kamu mengerjakan riset, penawaran, copy, desain, dan halaman sampai online dalam satu kali jalan.

## Dua jalur kerja

Cek dulu kamu berjalan di mana:

- **Jalur HP / Cloud**: sesi berjalan di komputer cloud dan proyek ini adalah repo GitHub. Pemakai biasanya memakai HP.
  - Setelah menyelesaikan satu tahap, commit dan push, lalu beri tahu pemakai dalam satu kalimat.
  - Perubahan di folder `site/` baru tampil di halaman live setelah masuk ke `main`. Coba push langsung ke `main` supaya pemakai tidak perlu langkah tambahan, kecuali pemakai minta cek preview dulu. Kalau push ke `main` ditolak, push ke branch kerja, buat pull request ke `main`, dan jelaskan cara merge dari HP: github.com → repo → Pull requests → pilih → Merge pull request → Confirm merge.
  - Link preview untuk branch lain ada di dashboard Cloudflare > Workers & Pages > proyek ini.
  - Pemakai tidak bisa membuka file di HP-nya lewat kamu. Gambar produk di-upload pemakai sendiri lewat github.com: buka repo → folder `site/gambar` → Add file → Upload files.
- **Jalur Laptop / Local**: sesi berjalan di laptop pemakai dan file ada di laptopnya. Preview dengan membuka `site/index.html` di browser, lalu online-kan lewat `/deploy-cloudflare`.

## Daftar resep

| Resep | Gunanya |
| --- | --- |
| `/buat-kilat` | Semua langkah sekaligus dari satu cerita singkat (disarankan) |
| `/riset-pembeli` | Riset pembeli → `riset.md` |
| `/penawaran` | Isi, bonus, harga, garansi → `penawaran.md` |
| `/copy-landing-page` | Naskah halaman → `copy.md` |
| `/builder-landing-page` (+ skill `frontend-design`) | Bangun atau ubah tampilan → `site/index.html` |
| `/deploy-cloudflare` | Panduan online-kan halaman dan sambungkan domain |
| `/pasang-tracking` | Pasang Meta/TikTok Pixel dan Clarity |
| `/audit-sebelum-iklan` | Cek 20 poin sebelum iklan → `audit.md` |
| `/gandakan-produk` | Siapkan proyek untuk produk berikutnya |
| `/update-resep` | Ambil resep terbaru dan perbaikan dari template kelas |

Kalau pemakai memakai resep satuan dan melompat tahap padahal file sebelumnya masih kosong, beri tahu dengan sopan dan tawarkan `/buat-kilat` atau resep yang kurang.

## Letak file

- `riset.md`, `penawaran.md`, `copy.md`, `audit.md` = bahan kerja, tidak dipublikasikan ke halaman. Sarankan pemakai menjadikan repo GitHub-nya **Private** (github.com → repo → Settings → paling bawah: Change visibility) supaya bahan kerja ini tidak bisa dilihat orang lain. Halaman jualan tetap bisa dilihat semua orang walaupun repo-nya private.
- `site/` = satu-satunya folder yang dipublikasikan. Semua file halaman (HTML, gambar) wajib di dalam `site/`.
- `site/gambar/` = foto produk, mockup, logo, screenshot testimoni.
- `wrangler.jsonc` = pengaturan Cloudflare. Jangan diubah kecuali diminta resep deploy.

## Aturan yang tidak boleh dilanggar

- Jangan pernah mengarang testimoni, angka penjualan, jumlah pembeli, atau hasil murid.
- Jangan menulis janji penghasilan pasti ("pasti balik modal", "dijamin cuan").
- Jangan membuat urgensi palsu: hitung mundur dan "sisa kuota" hanya kalau tanggal atau batasnya nyata dan tertulis di `penawaran.md`.
- Jangan memakai logo atau nama merek lain seolah-olah bermitra resmi.
- Halaman selalu dirancang untuk layar HP dulu, baru laptop.
