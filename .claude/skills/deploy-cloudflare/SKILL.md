---
name: deploy-cloudflare
description: Pandu pemakai meng-online-kan folder site/ ke Cloudflare Pages (gratis), lewat sambungan GitHub (Jalur HP) atau upload manual (Jalur Laptop), dan menyambungkan domain. Pakai saat halaman siap online, atau saat pemakai perlu meng-update halaman yang sudah online.
---

# Resep: Deploy ke Cloudflare

Tujuan: halaman di folder `site/` bisa dibuka siapa saja lewat link, dengan gembok HTTPS, dan (opsional) domain sendiri.

## Sebelum mulai

1. Pastikan `site/index.html` ada.
2. Cek cepat: semua gambar yang dipakai `index.html` ada di dalam `site/`, tidak ada link ke file di luar `site/`, dan tidak ada file kerja (`riset.md`, `copy.md`, dll.) di dalam `site/`. Perbaiki kalau ada masalah.
3. Ingatkan: yang di-upload HANYA folder `site`, bukan seluruh folder proyek.

## Jalur HP: sambungkan repo GitHub ke Cloudflare (sekali saja)

Pakai bagian ini kalau sesi berjalan di cloud dan proyek ini adalah repo GitHub. Setelah tersambung, setiap perubahan yang masuk ke `main` otomatis online, tanpa upload manual.

**Kalau proyek ini dibuat lewat tombol "Deploy ke Cloudflare", sambungan ini sudah otomatis.** Lewati langkah di bawah. Cukup minta pemakai membuka dashboard Cloudflare > Workers & Pages > proyeknya, lalu menyalin alamat `.workers.dev`-nya.

Pandu pemakai satu langkah per pesan. Pemakai memakai HP, jadi sarankan membuka dash.cloudflare.com di Chrome. Kalau menunya berbeda, tanya apa yang terlihat di layarnya:

Repo ini sudah berisi `wrangler.jsonc` yang menyuruh Cloudflare memajang folder `site/`. Pastikan nilai `"name"` di file itu sama dengan nama proyek yang akan dipakai pemakai di Cloudflare (bawaan: `landing-page-saya`). Kalau pemakai memakai nama lain, ubah `"name"` dulu, lalu commit dan push.

1. Masuk ke dash.cloudflare.com (daftar gratis kalau belum punya akun).
2. Buka menu **Workers & Pages** → **Create application** → pilih impor dari Git / **Connect to Git**. Dashboard Cloudflare sekarang bisa mengarahkan ke jalur **Workers** atau **Pages**; dua-duanya bisa dipakai.
3. Pilih **GitHub**, lalu izinkan Cloudflare mengakses akun GitHub pemakai. Sarankan memberi akses hanya ke repo ini.
4. Pilih repo ini, lalu isi sesuai tampilan yang muncul:
   - **Kalau tulisannya "Configure your Worker project"** (jalur Workers): Project name sama dengan `"name"` di `wrangler.jsonc`, Build command dikosongkan, Deploy command biarkan `npx wrangler deploy`, Enable Preview builds biarkan menyala. Lalu **Deploy**. Alamatnya berakhiran `.workers.dev`.
   - **Kalau tulisannya Pages** (ada Framework preset dan Build output directory): Production branch `main`, Framework preset **None**, Build command dikosongkan, Build output directory `site`. Lalu **Save and Deploy**. Alamatnya berakhiran `.pages.dev`.
5. Tunggu sampai selesai, lalu buka link yang muncul di HP. Untuk sementara isinya "Halaman sedang disiapkan".

Cara kerja sesudahnya:
- Perubahan di branch lain (misalnya branch kerja Claude atau pull request) mendapat **link preview** sendiri, untuk dicek dulu. Linknya ada di dashboard Cloudflare dan biasanya juga di halaman pull request.
- Halaman live hanya berubah setelah perubahan masuk ke `main`, misalnya dengan merge pull request di github.com → repo → Pull requests → pilih → **Merge pull request** → **Confirm merge**.
- Kalau deploy gagal dengan pesan soal nama Worker, cek bahwa Project name di Cloudflare sama dengan `"name"` di `wrangler.jsonc`.

## Jalur Laptop: upload pertama (cara tanpa perintah, untuk pemula)

Pandu pemakai langkah demi langkah, satu langkah per pesan, dan tanya apa yang ia lihat di layar kalau menunya berbeda:

1. Masuk ke dash.cloudflare.com (daftar gratis kalau belum punya akun).
2. Buka menu **Workers & Pages** → buat aplikasi/proyek baru → pilih **Pages** → pilih opsi upload aset langsung (**Direct Upload**, "upload your static files"), bukan sambungkan ke Git.
3. Beri nama proyek (huruf kecil dan tanda hubung, misalnya `kelas-landing-page`). Nama ini menjadi alamat `nama-proyek.pages.dev`.
4. Seret folder `site` ke area upload, lalu klik **Deploy**.
5. Buka link `.pages.dev` yang muncul, dan cek di HP.

Catatan: proyek Direct Upload tidak bisa diubah menjadi proyek Git nanti. Itu tidak masalah untuk landing page.

## Jalur Laptop: upload ulang setelah ada perubahan

Buka proyek yang sama di Cloudflare → buat deployment baru → seret ulang folder `site`. Alamat tetap sama. (Di Jalur HP langkah ini tidak perlu, karena update terjadi otomatis dari GitHub.)

## Menyambungkan domain

1. Di halaman proyek Pages, buka **Custom domains** → tambahkan domain atau subdomain (misalnya `kelas.domainmu.com`).
2. Ikuti petunjuk Cloudflare. Kalau domain dibeli di tempat lain, pemakai perlu menambahkan record DNS sesuai petunjuk di layar, atau memindahkan nameserver ke Cloudflare.
3. Tunggu sampai statusnya aktif dan gembok HTTPS muncul. Bisa beberapa menit sampai beberapa jam.
4. Saran: satu produk = satu proyek Pages = satu subdomain (`produk-a.domainmu.com`, `produk-b.domainmu.com`).

## Setelah online

- Buka halaman di HP dengan data seluler (bukan WiFi) untuk merasakan kecepatan sebenarnya.
- Klik semua tombol beli, pastikan menuju halaman pembayaran yang benar.
- Tutup dengan: "Halaman online di <link>. Langkah berikutnya: ketik `/pasang-tracking` kalau pixel belum terpasang, kemudian `/audit-sebelum-iklan <link>`."

## Kalau pemakai sudah memasang Node.js dan mau pakai perintah

Alternatif: `npx wrangler pages deploy site --project-name=<nama-proyek>` (akan meminta login Cloudflare di browser saat pertama kali). Tawarkan hanya kalau pemakai memintanya.
