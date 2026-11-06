# NEOCX

**NEOCX** adalah workspace HTML interaktif berbasis web yang memungkinkan pengguna menulis, mengimpor, menjalankan, dan melihat hasil HTML langsung di dalam aplikasi.

## Fitur

- Editor HTML dengan syntax highlighting.
- Menjalankan kode dan menampilkan hasil melalui panel preview.
- Impor file `.html` dan `.htm`.
- Salin dan tempel kode melalui clipboard browser.
- Kontrol editor: Edit, File, Copy, Paste, Clear, dan Reset.
- Tema gelap dan tema cream.
- Efek visual, glow, serta animasi latar.
- Tampilan responsif untuk perangkat mobile.
- Riwayat preview tersimpan lokal, dapat dibuka kembali, dan dapat dihapus.
- Tombol Star yang membuka repository NEOCX di GitHub.
- PWA installable dengan dukungan offline melalui Service Worker.

## Struktur proyek

```text
NEOCX/
├── index.html
├── manifest.json
├── sw.js
├── README.md
├── DESCRIPTION.md
└── icons/
    ├── icon-192.png
    ├── icon-512.png
    └── icon-512-maskable.png
```

## Menjalankan secara lokal

Buka melalui local web server. Service Worker dan instalasi PWA memerlukan konteks aman, yaitu HTTPS atau `localhost`; membuka `index.html` langsung melalui `file://` tidak mengaktifkan PWA.

## Deploy ke GitHub Pages

1. Buat repository baru di GitHub, misalnya `NEOCX`.
2. Upload seluruh file dan folder proyek ke root repository.
3. Buka **Settings → Pages**.
4. Pada **Build and deployment**, pilih **Deploy from a branch**.
5. Pilih branch `main` dan folder `/(root)`, lalu klik **Save**.
6. Tunggu workflow Pages selesai.
7. Buka alamat GitHub Pages yang diberikan GitHub menggunakan HTTPS.

## Instalasi PWA

- **Android/Chrome:** buka situs GitHub Pages, lalu pilih tombol Install NEOCX jika tersedia, atau menu browser → **Install app / Tambahkan ke layar utama**.
- **iOS/Safari:** buka situs, tekan **Share**, lalu pilih **Add to Home Screen**.

Setelah aplikasi berhasil dimuat setidaknya sekali, app shell dapat dibuka kembali saat offline. Koneksi internet tetap diperlukan untuk kunjungan pertama dan mengambil versi terbaru.

## Riwayat preview

Riwayat preview disimpan di `localStorage` browser/perangkat yang digunakan. Maksimal 12 preview disimpan; setiap item dapat dibuka kembali dari panel **Preview History**. Tombol **Hapus History** menghapus seluruh riwayat pada perangkat tersebut. Riwayat tidak disinkronkan antarperangkat.

## Memperbarui aplikasi

Setelah mengubah file, commit dan push ke branch `main`. Untuk memaksa pembaruan cache pada rilis berikutnya, ubah nilai `CACHE_NAME` di `sw.js`, misalnya dari `neocx-shell-v1` menjadi `neocx-shell-v2`.

## Catatan

- GitHub Pages menyediakan hosting statis. Proyek ini tidak memerlukan backend untuk fitur yang tersedia saat ini.
- Clipboard dan fitur instalasi bergantung pada dukungan serta izin browser.
- Jangan menghapus `manifest.json`, `sw.js`, atau folder `icons` jika ingin mempertahankan dukungan PWA.
