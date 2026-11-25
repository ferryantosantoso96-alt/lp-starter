---
name: penawaran
description: Susun penawaran (isi produk, bonus, harga, garansi, link pembayaran) dari riset.md dan tulis ke penawaran.md. Pakai setelah riset-pembeli, atau saat pemakai ingin mengubah harga, bonus, atau garansi.
---

# Resep: Penawaran

Tujuan: `penawaran.md` yang membuat harga terasa masuk akal dan semua janjinya bisa ditepati.

## Langkah

1. Baca `riset.md`. Kalau kosong atau belum ada, minta pemakai menjalankan `/riset-pembeli` dulu, lalu berhenti.
2. Tanyakan hal-hal berikut SATU PER SATU (lewati yang sudah jelas dari riset):
   1. Isi produk: bagian/modul apa saja? Untuk tiap bagian, hasil apa yang didapat pembeli?
   2. Bonus apa yang BENAR-BENAR akan kamu kirim? (Boleh "tidak ada".)
   3. Harga normal dan harga promo (kalau ada). Kalau ada promo: alasannya apa dan berakhir kapan (tanggal) atau setelah berapa pembeli?
   4. Garansi: apa syaratnya, dan apakah kamu sanggup menepatinya?
   5. Link pembayaran (misalnya payment link Mayar). Kalau belum punya, tulis `BELUM ADA`.
   6. Nomor WhatsApp untuk pertanyaan (opsional).
   7. Syarat pemakaian yang harus diketahui pembeli sebelum bayar (misalnya "butuh laptop", "butuh langganan aplikasi X").
3. Sarankan 1 kalimat **janji utama** (hasil + waktu/kemudahan) berdasarkan riset. Beri 3 pilihan, minta pemakai memilih atau mengubah.
4. Buat **perbandingan harga** yang jujur: bandingkan dengan alternatif nyata yang disebut di riset (jasa, kursus lain, waktu coba-coba sendiri). Pakai angka dari pemakai, jangan karangan.
5. Tulis `penawaran.md` dengan format di bawah, tampilkan ringkasannya, dan tanya apakah sudah pas.

## Format penawaran.md

```markdown
# Penawaran

## Nama produk
## Janji utama (1 kalimat)
## Isi produk
| Bagian | Hasil untuk pembeli |
| --- | --- |

## Bonus (hanya yang benar-benar dikirim)
-

## Harga
- Harga normal:
- Harga promo:
- Alasan & batas promo (tanggal atau jumlah pembeli):

## Perbandingan harga (angka dari pemakai)
-

## Garansi
-

## Syarat sebelum membeli
-

## Link pembayaran
-

## WhatsApp
-
```

## Aturan

- Tolak bonus yang tidak akan dikirim dan "nilai bonus" yang dibesar-besarkan. Jelaskan dengan sopan bahwa itu memicu refund dan iklan ditolak.
- Promo tanpa batas yang jelas ditulis sebagai harga biasa, bukan promo.
- Tutup dengan: "Penawaran siap. Langkah berikutnya: ketik `/copy-landing-page`."
