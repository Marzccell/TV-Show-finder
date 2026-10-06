# MARFLIXZ

Aplikasi pencarian film menggunakan React, Vite, Tailwind CSS, TMDB, dan Appwrite.

## Fitur

- Menampilkan film populer dari TMDB.
- Mencari film dengan jeda pencarian otomatis (debounce).
- Menampilkan poster, rating, bahasa, dan tahun rilis.
- Mencatat jumlah pencarian di Appwrite untuk menampilkan film trending.

## Menjalankan proyek

1. Instal Node.js dan npm.
2. Jalankan `npm ci` di folder proyek.
3. Salin `.env.example` menjadi `.env.local`, lalu isi konfigurasi:
   - `VITE_TMDB_API_KEY`: API Read Access Token TMDB (Bearer token).
   - `VITE_APPWRITE_PROJECT_ID`: ID proyek Appwrite.
   - `VITE_APPWRITE_DATABASE_ID`: ID database Appwrite.
   - `VITE_APPWRITE_COLLECTION_ID`: ID collection Appwrite.
4. Jalankan `npm run dev`, lalu buka alamat yang ditampilkan terminal.

Untuk fitur trending, buat collection Appwrite dengan atribut `searchTerm` (string),
`count` (integer), `movie_id` (integer), dan `poster_url` (string). Siapkan indeks
untuk pencarian `searchTerm` dan pengurutan `count`, serta izin baca, tambah, dan
ubah dokumen yang sesuai untuk pengguna aplikasi. Tambahkan hostname aplikasi
sebagai platform Web di proyek Appwrite.

## Perintah

```sh
npm run dev      # Server pengembangan
npm run build    # Build produksi ke folder dist
npm run preview  # Pratinjau build produksi
npm run lint     # Pemeriksaan ESLint
```

## Konfigurasi lokal

`.env.local`, `node_modules`, dan `dist` tidak disertakan dalam Git. File
`.env.example` hanya berisi nama variabel tanpa kredensial. Variabel berawalan
`VITE_` akan tersedia di browser; jangan gunakan untuk kunci server privat.
