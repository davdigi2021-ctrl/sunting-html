# Sunting HTML

Editor visual untuk HTML hasil AI. Tempel kodenya, ubah teks, link, gambar, ukuran, dan posisi elemen lewat klik — lalu unduh hasilnya.

**Coba langsung:** https://davdigi2021-ctrl.github.io/sunting-html/

## Kenapa ini ada

Kalau website dibuat pakai AI, hasilnya biasanya satu file HTML. Mau ganti nomor di tombol atau geser posisinya saja harus balik lagi ke AI. Editor ini untuk perubahan kecil seperti itu.

## Yang membedakan

Editor WYSIWYG umumnya mem-parsing ulang HTML kamu ke model komponen internal, lalu menulis ulang CSS-nya — di situlah layout sering rusak (class Tailwind hilang, urutan CSS berubah, script ke-strip).

Editor ini **tidak melakukan itu**. Halaman dirender apa adanya di dalam iframe, dan semua penanda (garis pilih, handle ukuran, garis sisip) berada di lapisan **luar** iframe — jadi DOM aslimu tidak pernah disentuh. Saat diekspor, yang keluar adalah HTML asli + persis perubahan yang kamu buat. Indentasi, komentar, CSS, dan script yang tidak kamu sentuh tetap utuh.

## Fitur

- Klik elemen untuk memilih, klik dua kali untuk mengubah teks
- Ubah **link** tujuan (href) dan opsi buka di tab baru
- **Ubah ukuran** dengan menarik titik biru, atau isi angka lebar/tinggi/ukuran teks
- Atur **jarak** (padding/margin), **warna** teks dan latar, serta perataan teks
- **Tambah elemen**: section, judul, paragraf, tombol, gambar, 2 kolom, garis, jarak
- **Ganti/tambah gambar** — pilih file atau seret langsung dari komputer ke kanvas (gambar disimpan sebagai data URI, jadi ikut terbawa di file hasil)
- **Geser posisi** elemen dengan seret, atau tombol naik/turun
- Duplikat dan hapus elemen
- **Undo/redo** (Ctrl+Z / Ctrl+Shift+Z)
- Pratinjau lebar **desktop / tablet / HP**
- Dukungan file **CSS dan JS terpisah** (kalau AI memberi 3 file, bukan 1)
- Unduh hasil sebagai `.html` atau salin kodenya

## Privasi

Semuanya berjalan di browser. Tidak ada kode atau gambar yang dikirim ke server mana pun — tidak ada backend sama sekali. Satu file `index.html`, bisa juga diunduh dan dibuka offline.

## Menjalankan sendiri

Buka `index.html` langsung di browser, atau taruh di hosting statis apa pun.

## Lisensi

MIT
