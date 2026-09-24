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
- **Ganti/tambah gambar** lewat pemilih file, seret langsung ke kanvas, atau tempel alamat gambarnya (alamat tidak membesarkan berkas, tapi gambarnya harus tetap online). Foto besar otomatis diperkecil ke 1600px dan disandikan ulang sebagai WebP sebelum ditanam, jadi berkasnya tidak membengkak — foto 1,5 MB biasanya turun ke sekitar 150 KB. SVG dan GIF tidak disentuh supaya vektor dan animasinya tetap utuh
- Geser posisi dengan menyeret, gandakan, dan hapus elemen
- **Tambah elemen**: section, judul, paragraf, tombol, gambar, 2 kolom, garis, jarak
- **Ganti satu link di semua tempat sekaligus**. Masukkan link lama dan link barunya, lihat dulu berapa tempat yang akan berubah, lalu ganti semuanya dalam sekali klik. Dicari di semua atribut — termasuk `onclick`/`onsubmit` dan `action` pada form, bukan cuma `href` — dan bisa sekalian mengganti tulisan yang terlihat di halaman. Kalau elemen yang sedang dipilih memakai link yang berulang, pintasannya muncul langsung di tab Isi
- **Kembalikan satu elemen ke asal** dalam sekali klik, tanpa perlu undo berkali-kali — teks, ukuran, warna, semuanya balik seperti di kode sumber
- **Kunci elemen** supaya tidak tergeser atau terhapus tidak sengaja saat menyeret yang lain
- **Ubah warna tema halaman**: warna merek yang dipakai berulang lewat variabel CSS bisa diubah sekali untuk semua tempat
- **Pasang video** YouTube atau Vimeo — tempel alamat biasa, diubah sendiri ke bentuk sematan
- **Warnai sebagian teks**: sorot beberapa kata di kanvas lalu beri warna sendiri, sisanya tidak tersentuh
- **Hitung mundur**: angka yang ditulis ulang oleh skrip halaman dikenali dan dikatakan (mengetik di situ percuma — sedetik kemudian tertimpa). Yang bisa diubah adalah tanggal tujuannya, dan kalau tanggalnya sudah lewat itu ditandai merah
- Undo/redo (Ctrl+Z / Ctrl+Shift+Z), dan **draf tersimpan otomatis di peramban** sehingga tab yang tertutup tidak menghilangkan pekerjaan

**Menemukan jalan**
- **Tiga langkah bernomor** di atas panggung — tempel, ubah, unduh — dengan langkah yang sedang berjalan ditandai dan yang sudah lewat dicentang, jadi selalu jelas ini akan berakhir di mana
- **Sambutan sekali jalan** untuk yang baru pertama membuka: tiga hal yang paling sering bikin tersendat (halamannya bisa diklik, teks diubah dengan klik dua kali, ada Ctrl+Z). Bisa dipanggil lagi lewat tombol keterangan di bar atas
- **Panel seperti Elementor**, di kiri. Tanpa pilihan, isinya daftar elemen untuk diseret ke halaman (tiga kolom ringkas, semuanya muat sekali lihat). Begitu sesuatu dipilih, kepalanya berbunyi "Ubah judul" dengan tombol kembali, dan pengaturannya dibagi tiga seperti Elementor: **Isi** (tulisan, link, gambar, video, ikon), **Gaya** (huruf dan warna), **Lanjutan** (ukuran, jarak, letak, tindakan). Kartu hanya muncul kalau memang berlaku — gambar tidak dapat kotak teks, section tidak dapat "ganti ikon"
- Navigasi di kaki panel memakai nama sehari-hari — **Atur, Tambah, Struktur, Periksa** — dan masing-masing menjelaskan dirinya saat kursor menyentuhnya
- **Pengaturan halaman** (warna tema, tanggal hitung mundur) ada di bawah daftar elemen, bukan di setiap elemen
- **Tombol "Ganti gambar" langsung di atas gambar** saat kursor menyentuhnya — sekali klik, pilih berkas. Tetap muncul walau gambarnya tertutup tombol play atau lapisan lain, karena yang dicari seluruh tumpukan di bawah kursor, bukan cuma yang paling atas
- **Tab Gambar**: semua gambar di halaman sebagai kartu kecil dengan nama, ukuran, dan tombol Ganti. Klik kartunya untuk loncat ke gambar itu. Gambar yang tidak tampil dan gambar tertanam yang berat ditandai
- Memilih kotak yang isinya satu gambar (bingkai foto, kartu siteplan) langsung menampilkan kartu Gambar
- **Struktur ikut menyorot**: memilih di halaman menyalakan barisnya, membuka lipatan di atasnya, dan menggulir ke sana
- Tombol **"Unduh hasilnya"** dibedakan dari tombol lain dan tidak pernah ikut terpotong di jendela sempit
- Pesan salah ditulis dengan kalimat yang menyebut langkah berikutnya, bukan istilah program. Kode yang ditempel juga dikenali dulu: isi file CSS atau JavaScript yang salah kotak dikatakan apa adanya

**Seret-lepas**
- Halaman **menggulir sendiri** saat kursor dibawa ke tepi atas/bawah kanvas, dan roda mouse tetap bekerja selama menyeret — elemen bisa ditaruh jauh di bawah bagian yang sedang terlihat
- Label kecil menempel di kursor ("Pindahkan judul", "Paragraf") dan garis biru tidak berkedip bolak-balik saat kursor ada di tengah elemen
- Kata yang ditebalkan atau dimiringkan di tengah kalimat tidak dianggap tempat jatuh
- **Bayangan jatuh diukur, bukan ditebak**: salinan tak terlihat dari yang dibawa ditaruh sesaat di tempat jatuhnya, lalu bayangan digambar di tempat salinan itu mendarat — jadi "di samping" atau "di bawah" yang terlihat saat menyeret sama dengan hasilnya, termasuk di grid, baris yang bisa turun, dan deretan tombol
- **Elemen melayang** (lencana di pojok foto, caption di tepi gambar) digeser bebas mengikuti kursor seperti elemen absolut di Elementor. Pergeserannya ditulis sebagai `translate`, jadi posisi dan lebar aslinya dari kode halaman tetap utuh

**Aman di HP**
- Lebar yang diatur di desktop tidak pernah melebihi layar HP: ditulis sebagai `min(640px, 100%)`, jadi di desktop tepat 640 px dan di HP mengalah ke lebar layar. Tinggi kotak berisi teks ditulis sebagai tinggi minimum supaya tulisannya tidak tumpah saat membungkus lebih banyak baris
- Pratinjau HP dan tablet tidak memakai scrollbar komputer, jadi "HP 390 px" memang 390 px
- Setiap kali ukuran pratinjau diganti, halaman diperiksa apakah bisa digeser ke samping — termasuk tulisan yang dilarang turun baris — dengan tombol perbaikan yang tidak mengubah tampilan desktop

**Melihat**
- Pratinjau **ukuran layar asli** lewat tiga tombol ikon: Desktop 1440px, Tablet 820×1180, HP 390×844 — atau isi sendiri lebar dan tingginya di kotak sebelahnya. Tinggi yang dikosongkan mengikuti tinggi kanvas. Zoom menyesuaikan otomatis
- Kanvas rata tepi saat lebar penuh, dan berbingkai saat pratinjau lebih sempit
- Saat menyeret, muncul **bayangan seukuran isinya** di tempat jatuh — bukan cuma garis tipis — jadi terlihat seberapa besar section barunya nanti
- **Rangka semua komponen** (seperti *view components* di GrapesJS), dengan label nama komponen saat kursor menyentuh elemen
- **Struktur** berisi peta seluruh halaman. Arahkan kursor ke satu baris untuk melihat letaknya disorot di kanvas
- **Pratinjau**: semua alat bantu disingkirkan dan halaman jadi bisa dipakai betulan — menu HP membuka, tombol buka-tutup bekerja, animasi masuk jalan. Link yang berpindah halaman tetap ditahan supaya pratinjau tidak melompat keluar. Tekan Esc untuk kembali menyunting
- **Lihat kode** untuk seluruh halaman atau satu elemen saja

**Memeriksa**
- Pemeriksa masalah otomatis dengan penjelasan bahasa sehari-hari dan tombol perbaiki. Yang dicek: link yang tidak akan sampai tujuan, nomor WhatsApp salah format, link tab baru yang belum aman, gambar tanpa teks pengganti, gambar dengan alamat lokal, alamat http yang rawan diblokir, link menu yang menuju bagian tidak ada, id kembar, kurung CSS yang belum ditutup, aturan CSS salah tulis, serta bahasa/judul/viewport halaman

## Coba dulu tanpa menyiapkan apa-apa

Tekan **"Pakai contoh halaman"**. Ketiga kotak langsung terisi — HTML, CSS, dan JS terpisah, seperti bentuk yang biasa keluar dari AI. Contohnya juga memuat header yang menempel, tombol WhatsApp melayang, gambar, dan beberapa kekeliruan khas (alamat WhatsApp tanpa `https://`, nomor diawali 0, link tab baru tanpa `rel`, gambar tanpa `alt`) supaya tab **Periksa** ada isinya untuk dicoba.

## Potongan untuk widget HTML Elementor

Kode yang bukan halaman utuh — misalnya isi widget HTML Elementor, yang diawali `<style>` atau `<div>` tanpa `<html>` — dibuka apa adanya dan **keluar lagi sebagai potongan**, tanpa `<html>`, `<head>`, atau `<body>` tambahan, supaya bisa langsung ditempel balik ke widgetnya. Draf yang dilanjutkan tetap ingat bentuk potongannya, dan pemeriksaan yang hanya berlaku untuk halaman utuh (judul, bahasa, pengaturan HP) dilewati.

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

Ikon memakai [Hugeicons](https://github.com/hugeicons/hugeicons) gaya *stroke-rounded*, juga berlisensi MIT. Logo dan favicon dibuat sendiri untuk proyek ini.
