# Cara Menggunakan dan Menghosting Website Latihan Kebumian

## Prasyarat
- [Git](https://git-scm.com/) terinstall pada komputer Anda.
- Akun [GitHub](https://github.com/).

## Langkah-langkah

### 1. Buat Repository Baru di GitHub
1. Masuk ke akun GitHub Anda.
2. Klik tombol **+** di pojok kanan atas, lalu pilih **New repository**.
3. Beri nama repository (misal: `latihan-kebumian`).
4. Pilih visibility (public atau private).
5. Tidak perlu menginisialisasi dengan README, .gitignore, atau license karena kita akan mengirim folder yang sudah ada.
6. Klik **Create repository**.

### 2. Clone Repository ke Lokal (Opsional)
Jika Anda ingin bekerja secara lokal, clone repository yang baru dibuat:
```bash
git clone https://github.com/username/nama-repo.git
cd nama-repo
```
Gantilah `username` dan `nama-repo` dengan nilai yang sesuai.

### 3. Salin Folder Website ke Repository
Salin seluruh isi folder `website` (yang termasuk `index.html`, `questions.json`, `assets/`, `builder.html`, `README.md`, `.gitignore`, dan `INSTRUCTIONS.md`) ke dalam folder repository lokal Anda.

### 4. Tambahkan, Commit, dan Push
```bash
git add .
git commit -m "Initial commit: website latihan kebumian dengan form builder"
git push origin main   # atau master, tergantung branch default
```

### 5. Aktifkan GitHub Pages
1. Pada repository GitHub Anda, buka tab **Settings** → **Pages**.
2. Pada bagian **Source**, pilih branch yang Anda push (misal: `main`) dan folder `/ (root)`.
3. Klik **Save**.
4. GitHub akan memberikan URL situs Anda (misal: `https://username.github.io/nama-repo/`).
5. Buka URL tersebut untuk melihat latihan.

### 6. Menggunakan Form Builder (builder.html)
Untuk membuat soal dengan mudah, buka file `builder.html` melalui browser (buka langsung dari folder website atau melalui GitHub Pages setelah Anda mem-pushnya).

Langkah penggunaan builder:
1. Pilih jenis soal (Pilihan Ganda, Benar/Salah, atau Isian Singkat) melalui tab di bagian atas.
2. Isi prompt soal, dan jika ada, unggah gambar (gambar akan disimpan hanya sebagai nama file; pastikan Anda menempatkan file gambar tersebut ke folder `assets/` setelah mengunduh questions.json).
3. Untuk Pilihan Ganda, isi opsi jawaban dan pilih jawaban yang benar.
4. Untuk Benar/Salah, pilih jawaban yang benar (Benar atau Salah).
5. Untuk Isian Singkat, isi jawaban yang benar.
6. Tambahkan penjelasan jika diperlukan.
7. Klik tombol "Tambah Soal [jenis]" untuk menambahkan soal ke daftar.
8. Ulangi langkah 2-7 untuk menambahkan soal lain.
9. Setelah selesai membuat semua soal, klik tombol **"Unduh questions.json"** untuk mengunduh file soal dalam format JSON.
10. Ganti file `questions.json` yang ada di repositori dengan file yang Anda unduh.
11. Commit dan push perubahan ke repositori Anda.

> **Catatan:** Builder ini tidak mengirim data ke server; semua operasi dilakukan di browser. Anda harus secara manual mengganti `questions.json` setelah mengunduhnya dari builder.

## Struktur Folder
- `index.html` - Halaman utama latihan
- `questions.json` - File berisi semua soal dalam format JSON
- `assets/` - Folder untuk menyimpan gambar yang digunakan dalam soal
- `builder.html` - Halaman untuk membuat soal secara mudah (form builder)
- `README.md` - Penjelasan singkat tentang website
- `.gitignore` - File untuk mengabaikan file yang tidak perlu di-track oleh Git
- `INSTRUCTIONS.md` - File ini

## Kontribusi
Jika Anda ingin berkontribusi pada pengembangan template ini, silakan buat pull request atau laporkan issues.

Selamat mengajar!