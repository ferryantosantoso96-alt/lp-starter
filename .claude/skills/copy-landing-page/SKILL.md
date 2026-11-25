---
name: copy-landing-page
description: Tulis naskah landing page jualan (hook, masalah, manfaat, bukti, harga, FAQ, CTA) dari riset.md dan penawaran.md ke copy.md. Pakai setelah penawaran, atau saat pemakai minta revisi teks, headline, atau CTA.
---

# Resep: Copy Landing Page

Tujuan: `copy.md` berisi naskah lengkap halaman, siap dipakai `/builder-landing-page`.

## Langkah

1. Baca `riset.md` dan `penawaran.md`. Kalau salah satu kosong, minta pemakai menjalankan resep yang kurang, lalu berhenti.
2. Baca [rumus-hook.md](rumus-hook.md).
3. Tulis 5 versi headline dengan sudut berbeda (masalah, hasil + waktu, kontras, rasa penasaran, angka nyata). Tampilkan, minta pemakai memilih 1 utama + 1 cadangan untuk diuji di iklan.
4. Tulis `copy.md` mengikuti urutan blok dan format di bawah.
5. Tampilkan blok Hook dan CTA, lalu tanya: "Mau ada yang diubah sebelum halamannya dibangun?"

## Urutan blok (wajib)

| No | Blok | Tugas | Aturan |
| --- | --- | --- | --- |
| 1 | HOOK | Menahan orang yang datang dari iklan | Headline ≤ 12 kata, satu ide; subheadline 1 kalimat yang menjelaskan caranya |
| 2 | MASALAH | "Ini gue banget" | 3–4 poin pendek, pakai kata-kata asli pembeli dari riset |
| 3 | SOLUSI | Kenalkan produk sebagai jalan keluar | 1–2 kalimat cara kerjanya |
| 4 | MANFAAT | "Aku dapat apa?" | 4–6 poin hasil, bukan fitur |
| 5 | BUKTI | Hapus keraguan | Hanya bukti dari riset. Kosong → tulis `[BUTUH BUKTI: ...]` dan sarankan jenis bukti yang bisa dikumpulkan |
| 6 | ISI PRODUK | Nilai terasa nyata | Dari tabel isi di penawaran |
| 7 | BONUS | Dorong beli sekarang | Hanya dari penawaran; tidak ada → hapus blok |
| 8 | HARGA | Harga terasa masuk akal | Perbandingan dari penawaran, lalu harga |
| 9 | GARANSI | Pindahkan risiko | Syarat apa adanya dari penawaran; tidak ada → hapus blok |
| 10 | FAQ | Jawab keberatan terakhir | 5–7 tanya-jawab dari keraguan di riset + syarat sebelum membeli |
| 11 | CTA PENUTUP | Tutup penjualan | Ulang janji utama + tombol |

## Aturan CTA

- Teks tombol = kata kerja + hasil, maksimal 5 kata ("Ambil kelasnya sekarang"), bukan "Klik di sini" atau "Submit".
- Tombol muncul setelah HOOK, setelah HARGA, dan di CTA PENUTUP.
- Di bawah tombol ada satu baris kecil penenang ("Akses langsung dikirim ke email setelah bayar") — hanya kalau benar.

## Gaya menulis

- Untuk layar HP: kalimat pendek, paragraf maksimal 2–3 baris, satu ide per paragraf.
- Bahasa sehari-hari yang dipakai pembeli. Hindari kata kaku seperti "solusi komprehensif", "optimal", "inovatif".
- Tandai kata kunci dengan **tebal**, maksimal satu frasa per paragraf.

## Format copy.md

```markdown
# Copy Landing Page

## META
- Judul tab (≤ 60 karakter):
- Deskripsi untuk share link (≤ 155 karakter):

## HOOK
- Headline:
- Headline cadangan (untuk uji iklan):
- Subheadline:
- Teks tombol:
- Baris penenang:

## MASALAH
## SOLUSI
## MANFAAT
## BUKTI
## ISI PRODUK
## BONUS
## HARGA
## GARANSI
## FAQ
- T:
  J:
## CTA PENUTUP
```

## Larangan

- Janji penghasilan pasti, "100% pasti berhasil", testimoni atau angka karangan, urgensi tanpa batas nyata.
- Tutup dengan: "Copy siap. Langkah berikutnya: taruh foto/mockup di `site/gambar/`, lalu ketik `/builder-landing-page`."
