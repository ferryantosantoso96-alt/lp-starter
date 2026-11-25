# Aturan Desain Landing Page

## Teknis

- Satu file `site/index.html`: HTML, CSS di `<style>`, JavaScript di `<script>` di akhir `<body>`. Tanpa framework, tanpa library dari luar.
- `<html lang="id">`, `<meta name="viewport" content="width=device-width, initial-scale=1">`.
- `<title>` dan `<meta name="description">` dari blok META di `copy.md`. Tambahkan tag Open Graph (`og:title`, `og:description`, `og:image` kalau ada gambar utama) supaya link terlihat bagus saat dibagikan di WhatsApp.
- Font: system font stack, atau maksimal 1 Google Font dengan `display=swap`.
- Gambar: `loading="lazy"` (kecuali gambar paling atas), selalu ada `width`, `height`, dan `alt` yang deskriptif.
- Target ukuran HTML di bawah 150 KB (tidak termasuk gambar). Halaman harus tetap terbaca kalau JavaScript gagal.

## Tata letak (HP dulu)

- Lebar konten maksimal sekitar 680px, ditengah di layar besar. Jarak tepi minimal 20px di HP.
- Teks isi 17–18px, tinggi baris sekitar 1.6. Headline 30–36px di HP, lebih besar di laptop.
- Satu warna aksen KHUSUS untuk tombol beli; jangan dipakai untuk elemen lain. Kontras teks tombol harus mudah dibaca.
- Tombol beli: tinggi minimal 52px, lebar penuh di HP, sudut membulat, teks tebal.
- Selang-seling latar blok (putih/abu sangat muda, atau gelap/terang) supaya pembaca merasa ada kemajuan saat scroll.

## Elemen interaktif (pakai yang relevan saja)

| Elemen | Cara | Aturan |
| --- | --- | --- |
| Tombol beli melayang di HP | Bar tetap di bawah layar berisi harga + tombol; muncul setelah hero lewat dari layar, sembunyi saat blok harga terlihat | Hanya di layar < 768px; jangan menutupi isi (beri padding bawah pada body) |
| Satu momen animasi | Satu urutan animasi yang disengaja (misalnya saat halaman pertama terbuka, atau saat blok harga muncul), dengan `IntersectionObserver` bila perlu | Jangan animasikan setiap blok satu per satu; matikan untuk `prefers-reduced-motion: reduce` |
| FAQ buka-tutup | `<details>` dan `<summary>` | Semua tertutup di awal, ikon panah berputar |
| Slider testimoni | CSS `scroll-snap`, bisa digeser jari | Hanya kalau ada ≥ 2 testimoni asli |
| Kalkulator hemat | Input jumlah (misal jumlah halaman) → tampilkan perbandingan biaya | Hanya kalau ada angka perbandingan di `penawaran.md` |
| Hitung mundur | Hitung ke tanggal di `penawaran.md` | HANYA kalau batas promo berupa tanggal nyata; setelah lewat, sembunyikan dan tampilkan harga normal |
| Efek tekan tombol | `transform: scale(.98)` saat ditekan, bayangan halus saat hover | Ringan, jangan berlebihan |

## Larangan

- Popup yang muncul sendiri, autoplay video bersuara, teks berkedip.
- Hitung mundur yang ulang lagi saat halaman dibuka ulang.
- Link yang membawa pengunjung keluar (Instagram, situs lain) selain link pembayaran dan WhatsApp.
- Gambar orang terkenal, logo merek lain, atau gambar dari internet.
