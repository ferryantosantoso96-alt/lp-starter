---
name: pasang-tracking
description: Pasang Meta Pixel, TikTok Pixel, dan/atau Microsoft Clarity di site/index.html beserta event kunjungan dan klik tombol beli. Pakai sebelum halaman diiklankan, atau saat pemakai ingin menambah/mengganti pixel.
---

# Resep: Pasang Tracking

Tujuan: platform iklan tahu siapa yang mengunjungi halaman dan siapa yang mengklik tombol beli, supaya iklan bisa belajar mencari pembeli.

## Langkah

1. Pastikan `site/index.html` ada dan tombol belinya punya `class="cta"`. Kalau belum, minta pemakai menjalankan `/builder-landing-page` dulu.
2. Tanya pemakai mau memasang yang mana: Meta Pixel (iklan FB/IG), TikTok Pixel (iklan TikTok), Microsoft Clarity (rekaman pengunjung, opsional).
3. Untuk tiap pilihan, minta pemakai MENEMPELKAN kode dasar resmi dari dashboard masing-masing. Jangan menulis kode dasar dari ingatan.
   - Meta: Events Manager → pilih sumber data (pixel) → pasang kode secara manual → salin kode dasar.
   - TikTok: TikTok Ads Manager → Events / Events Manager → buat atau pilih pixel web → pasang kode manual → salin kode dasar.
   - Clarity: clarity.microsoft.com → buat proyek → salin kode pelacakan.
   Kalau letak menunya berbeda, bantu pemakai mencarinya dengan bertanya apa yang terlihat di layarnya.
4. Cek dulu apakah kode yang sama sudah terpasang. Jangan pernah memasang pixel yang sama dua kali.
5. Tempel kode dasar di dalam `<head>`.
6. Tambahkan event di `<script>` akhir halaman:
   - Saat halaman dibuka: Meta `fbq('track', 'ViewContent', {content_name: '<nama produk>', value: <harga>, currency: 'IDR'})`; TikTok `ttq.track('ViewContent', {content_name: '<nama produk>', value: <harga>, currency: 'IDR'})`.
   - Saat elemen `.cta` diklik: Meta `fbq('track', 'InitiateCheckout', {value: <harga>, currency: 'IDR'})`; TikTok `ttq.track('InitiateCheckout', {value: <harga>, currency: 'IDR'})`. Bungkus dengan pengecekan `typeof fbq === 'function'` / `typeof ttq !== 'undefined'` supaya tidak error kalau pixel diblokir.
   - Harga = angka harga yang berlaku dari `penawaran.md` (tanpa titik pemisah).
7. Teruskan parameter UTM ke link pembayaran: kalau URL halaman berisi `utm_source`, `utm_medium`, `utm_campaign`, `utm_content`, atau `utm_term`, tambahkan parameter yang sama ke `href` semua tombol `.cta` yang mengarah ke link pembayaran. Supaya laporan di platform pembayaran tahu iklan mana yang menghasilkan.
8. Jelaskan ke pemakai soal event **Purchase** (pembelian): event ini terjadi di halaman pembayaran, bukan di halaman kita. Kalau memakai Mayar, masukkan ID pixel yang sama di pengaturan tracking produk Mayar.
9. Beri cara mengecek:
   - Meta: pasang ekstensi Chrome "Meta Pixel Helper", buka halaman, pastikan PageView dan ViewContent terbaca; klik tombol beli → InitiateCheckout terbaca. Bisa juga lewat menu Test Events di Events Manager.
   - TikTok: ekstensi "TikTok Pixel Helper" atau fitur test events di Events Manager.
   - Catatan: pengecekan paling akurat dilakukan setelah halaman online.
10. Tutup dengan langkah online-kan ulang sesuai jalur:
    - **Jalur HP:** commit dan push, buat pull request ke `main`, lalu minta pemakai merge supaya pixel ikut live.
    - **Jalur Laptop:** upload ulang folder `site` ke proyek Cloudflare yang sama (atau `/deploy-cloudflare` kalau belum pernah online).
    Lalu: "Cek pixel dengan Pixel Helper, kemudian ketik `/audit-sebelum-iklan <link>`."

## Contoh link iklan dengan UTM

`https://domainmu.com/?utm_source=facebook&utm_medium=paid&utm_campaign=kelas-lp&utm_content=hook-demo`

Satu `utm_content` berbeda untuk tiap materi iklan, supaya ketahuan materi mana yang paling banyak menghasilkan pembeli.
