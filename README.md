# Website Latihan Kebumian

Ini adalah sederhana website latihan yang dapat dihosting gratis melalui GitHub Pages. Website ini menggunakan HTML, CSS, dan JavaScript murni (tanpa backend) untuk menampilkan soal dan memberikan penilaian otomatis.

## Struktur Folder

- `index.html` - Halaman utama latihan
- `questions.json` - File berisi semua soal dalam format JSON
- `assets/` - Folder untuk menyimpan gambar yang digunakan dalam soal
- `builder.html` - Haluan untuk membuat soal secara mudah (form builder)
- `README.md` - File ini

## Cara Menambahkan Soal Baru

Soal disimpan dalam file `questions.json`. Setiap soal adalah objek JSON dengan properti berikut:

- `type`: Jenis soal. Bisa berupa:
  - `"multiple_choice"` - Pilihan ganda
  - `"true_false"` - Benar/Salah
  - `"short_answer"` - Jawaban singkat (diisi manually, pengecekan dilakukan dengan exact match setelah diubah ke lowercase dan trim spasi)

- `prompt`: Teks soal (maupun pertanyaan).

- Untuk `multiple_choice`:
  - `options`: Array string berisi pilihan jawaban (misal: `["Pilihan A", "Pilihan B", "Pilihan C", "Pilihan D"]`)
  - `answerIndex`: Indeks jawaban yang benar (0-based, sehingga A=0, B=1, C=2, D=3)
  - `explanation` (opsional): Penjelasan yang ditampilkan setelah jawaban dicheck.

- Untuk `true_false`:
  - `answer`: Boolean (`true` untuk Benar, `false` untuk Salah)
  - `explanation` (opsional): Penjelasan.

- Untuk `short_answer`:
  - `answer`: String jawaban yang benar (pencocokan tidak sensitif huruf besar/kecil dan mengabaikan spasi di awal/akhir).

- `image` (opsional): Nama file gambar yang berada di folder `assets/` (misal: `"diagram1.png"`). Jika tidak ada, properti ini bisa dihilangkan atau diatur ke `null`.

### Contoh Soal Pilihan Ganda
```json
{
  "type": "multiple_choice",
  "prompt": "Apa yang merupakan lapisan bumi yang paling dalam?",
  "options": [
    "Kulit bumi",
    "Mantel",
    "Inti luar",
    "Inti dalam"
  ],
  "answerIndex": 3,
  "explanation": "Inti dalam adalah lapisan bumi yang paling dalam dan terdiri dari nikel dan besi padat.",
  "image": "earth_layers.png"
}
```

### Cara Menambahkan Gambar
1. Letakkan file gambar (PNG, JPG, SVG, dll) ke dalam folder `assets/`.
2. Pastikan nama file sama dengan yang ditulis di properti `image` dalam objek soal.
3. Gunakan nama file yang sederhana dan tanpa spasi (misal: `gunung_api.png`).

## Menggunakan Form Builder (builder.html)

Untuk mempermudah pembuatan soal, kita menyediakan halaman **builder.html** yang merupakan formulir interaktif untuk menambahkan soal.

### Cara menggunakan builder.html:
1. Buka file `builder.html` di browser (buka langsung dari folder website atau melalui GitHub Pages jika Anda sudah menghostingnya).
2. Pilih jenis soal (Pilihan Ganda, Benar/Salah, atau Isian Singkat) melalui tab di bagian atas.
3. Isi prompt soal, dan jika ada, unggah gambar (gambar akan disimpan hanya sebagai nama file; pastikan Anda menempatkan file gambar tersebut ke folder `assets/` setelah mengunduh questions.json).
4. Untuk Pilihan Ganda, isi opsi jawaban dan pilih jawaban yang benar.
5. Untuk Benar/Salah, pilih jawaban yang benar (Benar atau Salah).
6. Untuk Isian Singkat, isi jawaban yang benar.
7. Tambahkan penjelasan jika diperlukan.
8. Klik tombol "Tambah Soal [jenis]" untuk menambahkan soal ke daftar.
9. Ulangi langkah 2-8 untuk menambahkan soal lain.
10. Setelah selesai membuat semua soal, klik tombol **"Unduh questions.json"** untuk mengunduh file soal dalam format JSON.
11. Ganti file `questions.json` yang ada di repositori dengan file yang Anda unduh.
12. Commit dan push perubahan ke repositori Anda.

> **Catatan:** Builder ini tidak mengirim data ke server; semua operasi dilakukan di browser. Anda harus secara manual mengganti `questions.json` setelah mengunduhnya dari builder.

## Hosting di GitHub Pages

1. Pastikan Anda memiliki repository GitHub.
2. Push seluruh folder `website` (isi folder ini) ke repository Anda (bisa ke branch `main` atau `master`).
3. Aktifkan GitHub Pages:
   - Pada repository Anda, buka tab **Settings** → **Pages**.
   - Pada bagian **Source**, pilih branch yang Anda push (misal: `main`) dan folder `/ (root)`.
   - Klik **Save**.
4. GitHub akan memberikan URL situs Anda (misal: `https://username.github.io/repository-name/`).
5. Buka URL tersebut untuk melihat latihan.

## Catatan

- Website ini bersifat statis; semua soal harus diedit secara manual melalui file `questions.json` dan commit ke repository.
- Untuk mengganti soal, cukup edit `questions.json`, commit, dan push. GitHub Pages akan otomatis memperbarui situs dalam beberapa menit.
- Karena tidak ada backend, data jawaban siswa tidak disimpan di mana-mana. Siswa dapat mencatat skor sendiri atau mengirimkan screenshot kepada guru.

## Kontribusi

Jika Anda ingin berkontribusi pada pengembangan template ini, silakan buat pull request atau laporkan issues.

Selamat mengajar!