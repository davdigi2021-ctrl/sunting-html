# Sunting HTML

Editor visual untuk HTML hasil AI. Tempel kodenya, ubah teks, link, gambar, ukuran, dan posisi elemen lewat klik — lalu unduh hasilnya.

**Coba langsung:** https://davdigi2021-ctrl.github.io/sunting-html/

## Kenapa ini ada

Kalau website dibuat pakai AI, hasilnya biasanya satu file HTML. Mau ganti nomor di tombol atau geser posisinya saja harus balik lagi ke AI. Editor ini untuk perubahan kecil seperti itu.

## Yang membedakan

Editor WYSIWYG umumnya mem-parsing ulang HTML kamu ke model komponen internal, lalu menulis ulang CSS-nya — di situlah layout sering rusak (class Tailwind hilang, urutan CSS berubah, script ke-strip).

Editor ini **tidak melakukan itu**. Halaman dirender apa adanya di dalam iframe, dan semua penanda (garis pilih, handle ukuran, garis sisip) berada di lapisan **luar** iframe — jadi DOM aslimu tidak pernah disentuh. Saat diekspor, yang keluar adalah HTML asli + persis perubahan yang kamu buat. Indentasi, komentar, CSS, dan script yang tidak kamu sentuh tetap utuh.

## Fitur

**Menyunting**
- Klik elemen untuk memilih, klik dua kali untuk mengubah teks
- Ubah **link** tujuan dan opsi buka di tab baru, dengan peringatan kalau alamatnya keliru
- **Ubah ukuran** dengan menarik bulatan biru, atau isi angka lebar/tinggi
- **Ganti font**, tebal huruf, jarak baris, dan perataan. Font Google dimuat otomatis
- Atur jarak dalam/luar, warna tulisan dan latar
- **Ganti ikon SVG** dari daftar siap pakai atau tempel kode SVG sendiri
- **Ganti/tambah gambar** lewat pemilih file atau seret langsung ke kanvas. Foto besar otomatis diperkecil ke 1600px dan disandikan ulang sebagai WebP sebelum ditanam, jadi berkasnya tidak membengkak — foto 1,5 MB biasanya turun ke sekitar 150 KB. SVG dan GIF tidak disentuh supaya vektor dan animasinya tetap utuh
- Geser posisi dengan menyeret, gandakan, dan hapus elemen
- **Tambah elemen**: section, judul, paragraf, tombol, gambar, 2 kolom, garis, jarak
- Undo/redo (Ctrl+Z / Ctrl+Shift+Z)

**Melihat**
- Pratinjau **ukuran layar asli** lewat tiga tombol ikon: Desktop 1440px, Tablet 820×1180, HP 390×844 — atau isi sendiri lebar dan tingginya di kotak sebelahnya. Tinggi yang dikosongkan mengikuti tinggi kanvas. Zoom menyesuaikan otomatis
- Kanvas rata tepi saat lebar penuh, dan berbingkai saat pratinjau lebih sempit
- **Rangka semua komponen** (seperti *view components* di GrapesJS), dengan label nama komponen saat kursor menyentuh elemen
- **Panel lapisan** berisi struktur halaman. Arahkan kursor ke satu baris untuk melihat letaknya disorot di kanvas
- **Lihat kode** untuk seluruh halaman atau satu elemen saja

**Memeriksa**
- Pemeriksa masalah otomatis dengan penjelasan bahasa sehari-hari dan tombol perbaiki. Yang dicek: link yang tidak akan sampai tujuan, nomor WhatsApp salah format, link tab baru yang belum aman, gambar tanpa teks pengganti, gambar dengan alamat lokal, alamat http yang rawan diblokir, link menu yang menuju bagian tidak ada, id kembar, kurung CSS yang belum ditutup, aturan CSS salah tulis, serta bahasa/judul/viewport halaman

## Coba dulu tanpa menyiapkan apa-apa

Tekan **"Pakai contoh halaman"**. Ketiga kotak langsung terisi — HTML, CSS, dan JS terpisah, seperti bentuk yang biasa keluar dari AI. Contohnya juga memuat header yang menempel, tombol WhatsApp melayang, gambar, dan beberapa kekeliruan khas (alamat WhatsApp tanpa `https://`, nomor diawali 0, link tab baru tanpa `rel`, gambar tanpa `alt`) supaya tab **Periksa** ada isinya untuk dicoba.

## Kalau file kamu terpisah-pisah

Tempel HTML di kotak utama, lalu buka **"Punya file CSS atau JS terpisah?"** dan tempel isi masing-masing. Keduanya disatukan ke dalam hasil unduhan sebagai satu berkas.

Saat itu dilakukan, acuan ke berkas lokal seperti `<link href="gaya.css">` dan `<script src="skrip.js">` dibuang. Alasannya: berkas lokal semacam itu memang tidak pernah bisa dimuat di pratinjau, dan kalau dibiarkan sementara berkas lamanya masih ada di folder yang sama, isinya akan jalan dua kali — skrip yang jalan dua kali sering justru membatalkan dirinya sendiri. Alamat penuh seperti CDN dan Google Fonts tidak disentuh.

Punya beberapa halaman HTML? Sunting satu per satu: unduh yang pertama, tekan **"Ganti kode"**, lalu tempel yang berikutnya.

## Privasi

Semuanya berjalan di browser. Tidak ada kode atau gambar yang dikirim ke server mana pun — tidak ada backend sama sekali. Satu file `index.html`, bisa juga diunduh dan dibuka offline.

## Menjalankan sendiri

Buka `index.html` langsung di browser, atau taruh di hosting statis apa pun.

## Lisensi

MIT
