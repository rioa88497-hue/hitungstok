# Cara Membuat Aplikasi Ini Bisa Diakses di Android & iOS

Aplikasi ini sudah saya lengkapi jadi **PWA (Progressive Web App)** — artinya bisa
di-install seperti aplikasi asli di HP Android maupun iPhone, lengkap dengan ikon
di homescreen dan bisa dipakai offline, tanpa perlu upload ke Play Store / App Store.

File yang sudah dibuat:
- `index.html` → aplikasi utamanya (file asli kamu, sudah tersambung ke manifest & service worker)
- `manifest.json` → info aplikasi (nama, ikon, warna) supaya bisa di-install
- `sw.js` → service worker, supaya aplikasi tetap bisa dibuka walau tanpa internet
- `icon-192.png` & `icon-512.png` → ikon aplikasi

## Kenapa tidak bisa langsung dibuka dari file di HP?

PWA (fitur "Add to Home Screen" + offline + service worker) **wajib diakses lewat
alamat https://**, tidak bisa langsung dibuka dari file HTML di penyimpanan HP.
Jadi kamu perlu meng-hosting 4 file di atas ke satu tempat online dulu (gratis,
tanpa perlu jadi programmer). Ini langkah paling mudah:

### Opsi 1 — Netlify Drop (paling gampang, tanpa akun wajib)
1. Buka **https://app.netlify.com/drop** di laptop/komputer.
2. Drag & drop folder yang berisi ke-4 file tadi (index.html, manifest.json, sw.js, icon-192.png, icon-512.png) ke halaman itu.
3. Netlify akan otomatis kasih alamat, misalnya `https://nama-acak-123.netlify.app`.
4. Alamat itulah yang kamu buka di HP.

### Opsi 2 — GitHub Pages (kalau sudah punya akun GitHub)
1. Buat repository baru, upload ke-4 file tersebut.
2. Aktifkan GitHub Pages di Settings → Pages → pilih branch `main`.
3. Alamatnya akan berbentuk `https://username.github.io/nama-repo/`.

### Opsi 3 — Hosting kantor/perusahaan yang sudah ada
Kalau perusahaan sudah punya web hosting atau server internal, cukup upload
ke-4 file itu ke folder yang bisa diakses lewat https, tidak perlu langkah tambahan lain.

## Cara Install di Android (Chrome)
1. Buka alamat aplikasi di Chrome.
2. Ketuk menu titik tiga (⋮) di kanan atas.
3. Pilih **"Tambahkan ke layar utama" / "Install aplikasi"**.
4. Ikon aplikasi akan muncul di homescreen seperti aplikasi biasa.

## Cara Install di iPhone/iPad (Safari)
1. Buka alamat aplikasi di **Safari** (harus Safari, bukan Chrome).
2. Ketuk ikon **Share/Bagikan** (kotak dengan panah ke atas).
3. Pilih **"Add to Home Screen" / "Tambah ke Layar Utama"**.
4. Ketuk **Tambah**. Ikon aplikasi akan muncul di homescreen.

Setelah diinstall, aplikasi akan terbuka full-screen tanpa address bar seperti
aplikasi native, dan data yang diketik tetap tersimpan otomatis di HP masing-masing
(karena aplikasi ini memakai penyimpanan lokal browser).

## Catatan
- Karena aplikasi ini menyimpan data pakai `localStorage`, data yang diisi di satu
  HP **tidak otomatis muncul** di HP lain — tiap perangkat punya datanya sendiri.
- Fitur export ke Excel tetap berjalan normal di HP (file akan otomatis ter-download).
