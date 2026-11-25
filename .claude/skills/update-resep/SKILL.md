---
name: update-resep
description: Ambil versi terbaru semua resep dari template resmi kelas dan pasang di proyek ini, tanpa menyentuh riset, copy, dan halaman pemakai. Pakai saat pemakai mengetik /update-resep atau bertanya apakah ada resep baru atau perbaikan.
---

# Resep: Update Resep

Sumber resep terbaru: https://github.com/ferryantosantoso96-alt/lp-starter (branch `main`).

## Langkah

1. Jelaskan dalam satu kalimat: kamu akan mengecek resep terbaru dari template kelas, dan data jualan pemakai tidak akan disentuh.
2. Unduh template ke folder sementara di LUAR proyek ini, misalnya `git clone --depth 1 https://github.com/ferryantosantoso96-alt/lp-starter /tmp/lp-starter-terbaru`. Kalau gagal karena jaringan, beri tahu pemakai dan berhenti.
3. Bandingkan folder `.claude/skills/` di template dengan milik proyek ini. Catat:
   - resep baru (ada di template, belum ada di proyek),
   - resep yang berubah,
   - resep yang dihapus dari template (jangan dihapus otomatis; tanyakan dulu).
4. Laporkan ke pemakai dalam bahasa biasa, paling banyak 5 poin. Contoh: "Ada 1 resep baru: /bedah-landing-page. Resep deploy diperbaiki karena tampilan Cloudflare berubah." Kalau tidak ada perubahan, bilang semuanya sudah terbaru, lalu berhenti.
5. Tanya: "Pasang update ini?" Lanjut hanya kalau pemakai setuju.
6. Salin dari template ke proyek ini:
   - semua isi `.claude/skills/` (timpa resep lama dengan versi baru),
   - `MULAI-DI-SINI.md`.
   Untuk `CLAUDE.md` dan `wrangler.jsonc`: jangan ditimpa. Kalau isinya berbeda, jelaskan perbedaannya dan tanya dulu. Di `wrangler.jsonc`, nilai `"name"` milik pemakai harus tetap dipertahankan.
7. JANGAN pernah mengubah atau menghapus: `riset.md`, `penawaran.md`, `copy.md`, `audit.md`, folder `site/`, dan folder `template/`.
8. Hapus folder sementara, lalu commit dengan pesan "Update resep dari template" dan push (Jalur HP), atau cukup simpan (Jalur Laptop).
9. Tutup dengan daftar resep yang baru atau berubah, dan satu contoh cara memakainya.
