# Panduan CMS Menu Kurnia Seafood

CMS ini dipakai untuk mengubah menu online Kurnia Seafood (harga, nama menu, foto, dll) langsung dari HP -- tanpa perlu buka kode atau minta bantuan teknis tiap kali ada perubahan.

Link CMS: **https://menu.kurniaseafood.co.id/admin.html**
Menu yang tayang ke tamu (live): **https://menu.kurniaseafood.co.id/**

> Halaman `admin.html` boleh dibuka siapa saja yang tahu linknya -- tapi **tanpa token**, orang itu cuma bisa lihat-lihat / coba-coba di mode demo, **tidak bisa mengubah apa pun** di menu yang sungguhan. Jadi aman kalau link ini kebuka orang lain, asal token tidak ikut dishare.

---

## 1. Cara Bikin Token GitHub (sekali saja)

Token itu seperti "kunci" supaya CMS boleh mengubah menu. Kamu buat sekali, lalu dipakai terus sampai masa berlakunya habis.

1. Buka **github.com**, login pakai akun GitHub Patrick (atau akun yang sudah diberi akses ke repo `menu-kurnia`).
2. Klik foto profil di kanan atas -> **Settings**.
3. Di menu kiri paling bawah, klik **Developer settings**.
4. Klik **Personal access tokens** -> **Fine-grained tokens**.
5. Klik **Generate new token**.
6. Isi:
   - **Token name**: bebas, misalnya `cms-menu-kurnia`
   - **Expiration**: GitHub tidak punya preset "1 tahun" -- pilih **Custom**, lalu di kalender yang muncul klik tanggal setahun ke depan dari hari ini.
   - **Repository access**: pilih **Only select repositories** -> pilih **PatrickPLJ/menu-kurnia**
   - **Permissions** -> buka bagian **Repository permissions** -> cari **Contents** -> ubah jadi **Read and write**. **Field lain biarkan default (No access)** -- CMS ini cuma butuh izin Contents.
7. Klik **Generate token**. GitHub kadang minta kamu masukkan ulang password atau kode 2FA di layar ini dulu -- itu normal, bukan nyasar.
8. GitHub akan menampilkan token (diawali `github_pat_...`) **cuma sekali**. Salin (copy) token itu, lalu tempel di CMS.

**Catatan:** buat token ini dari akun **Patrick**, bukan akun staf -- staf cukup dikasih tokennya, tidak perlu bikin token sendiri.

### PERINGATAN PENTING soal token
- **Token = kunci masuk.** Siapa pun yang punya token itu bisa mengubah menu online.
- **Jangan pernah kirim token ke grup WhatsApp, email, atau chat manapun yang bukan cuma kamu sendiri.** "Cara aman" untuk menyerahkan token ke staf: ketik/paste langsung di HP staf saat bertemu langsung, atau kirim lewat chat 1-on-1 (bukan grup) lalu hapus pesannya begitu sudah dipaste ke CMS.
- Kalau token kepencet ke-share/bocor: buka lagi **Settings -> Developer settings -> Fine-grained tokens**, cari token-nya, klik **Revoke** (cabut), lalu bikin token baru pakai langkah di atas.
- Token cuma bisa dipakai untuk repo `menu-kurnia` dan cuma untuk ubah isi file (Contents) -- tidak bisa dipakai untuk hal lain di akun GitHub.
- Saat login, CMS otomatis mengecek apakah token itu benar-benar punya izin tulis (bukan cuma "bisa lihat repo"). Kalau izinnya kurang atau tidak bisa dipastikan, akan muncul kotak peringatan kuning di atas layar -- token tetap bisa dipakai, tapi cek lagi izin Contents-nya kalau nanti gagal simpan.

---

## 2. Cara Pakai CMS

### Masuk
1. Buka link CMS di HP.
2. Tempel token yang sudah disalin ke kolom **Token GitHub**.
3. Centang **"Ingat di perangkat ini"** kalau ini HP yang kamu pakai sehari-hari (supaya tidak perlu paste token lagi tiap buka). Kalau ini HP bersama/pinjaman, **jangan dicentang**.
4. Tekan **Masuk**.

Kalau mau coba-coba dulu tanpa punya token, tekan **"Coba tanpa token (mode demo)"** -- semua tombol bisa dicoba, tapi perubahan tidak benar-benar tersimpan.

> **Kalau tab/HP tiba-tiba tertutup** (pindah ke WhatsApp, ambil foto, HP restart) sebelum sempat tekan "Simpan Perubahan", jangan panik -- buka lagi CMS-nya, nanti akan muncul tawaran "Lanjutkan Perubahan?" untuk memulihkan perubahan terakhir yang belum sempat tersimpan.

### Ubah Menu
1. Masuk ke tab **Menu**.
2. Ketuk nama kategori (mis. "Appetizer") untuk membuka daftar menunya.
3. Ketuk **Edit** di menu yang mau diubah -> ubah nama/harga/deskripsi -> tekan **Terapkan**.
   - **Terapkan** cuma menampung perubahan itu di layar ini -- BELUM naik ke website. Yang beneran mengirim ke website adalah tombol **"Simpan Perubahan"** di bar bawah (lihat langkah "Simpan ke Server").
   - Harga cukup diketik angka biasa, label harga (mis. "46K") **otomatis dibuat**. Kalau mau label yang beda dari biasanya (misal "12K/Pcs" atau "269K++"), centang **"Ubah label harga secara manual"**.
   - Kalau harga menu itu memang tidak tetap (harga pasar, mis. kepiting/lobster), centang **"Harga pasar"**.
   - Toggle **"Menu Baru (NEW)"** untuk kasih tanda NEW di menu online.
4. Tekan **"+ Tambah item"** untuk menambah menu baru di kategori itu.
5. Tombol panah atas/bawah di sebelah menu = ubah urutan tampil.
6. Untuk kategori **seafood segar** (Kepiting, Udang & Lobster, Cumi, Kerang, Ikan): ketuk **"Edit catatan, ukuran & olahan"** untuk atur daftar ukuran dan pilihan olahan/sausnya.
7. Untuk alamat & catatan umum (yang tampil di semua halaman), buka **"Info Restoran & Catatan Umum"** di paling atas tab Menu.

### Ubah Foto
1. Masuk ke tab **Foto**.
2. Ketuk **Edit** di foto yang mau diganti/diubah infonya, atau **"+ Tambah Foto"** untuk foto baru.
3. Kalau upload foto baru: pilih file foto dari galeri HP -- CMS otomatis mengecilkan ukurannya supaya website tetap cepat dibuka. Tunggu sampai muncul tanda "Siap" di bawah preview foto.
4. Isi nama/caption, tipe (**Hidangan** = foto 1 menu spesifik, **Komposisi** = foto gabungan/showcase kategori), dan kategori.
5. Kalau tipe **Hidangan**, pilih menu-nya dari daftar dropdown (bukan ketik manual) -- supaya fotonya pasti nyambung ke menu yang benar. Kalau kategorinya sudah punya satu foto gabungan (komposisi), CMS akan kasih peringatan kalau foto hidangan baru itu tidak akan tampil di menu online.
6. Tunggu sampai status di bawah preview foto berubah jadi **"Siap"** (bukan lagi "Memproses foto...") sebelum tekan **Terapkan** -- tombolnya otomatis nonaktif selama proses kompresi foto masih berjalan, jadi kalau belum bisa dipencet, tunggu saja sebentar.

Kalau kamu mengganti nama menu yang sudah punya foto, atau menghapus menu yang punya foto, CMS akan otomatis kasih tahu dan menawarkan supaya rujukan fotonya ikut diperbaiki -- tidak perlu khawatir foto jadi "nyasar".

Setelah "Simpan Perubahan" sukses, foto yang baru diunggah mungkin masih kelihatan pakai preview dari HP-mu sendiri (bukan dari website) selama ±1 menit sambil menunggu GitHub Pages selesai deploy -- itu normal, akan otomatis ganti ke versi website begitu kamu reload halaman CMS-nya.

### Simpan ke Server
1. Setelah selesai ubah-ubah, gulir ke bawah, tekan **"Simpan Perubahan"** (ada angka jumlah perubahan di tombolnya).
2. Kalau baru pertama kali simpan di HP itu, CMS akan tanya **nama kamu** dulu (supaya kelihatan siapa yang mengubah menu) -- cukup diisi sekali.
3. Muncul layar **Ringkasan Perubahan** berisi daftar semua yang akan naik ke menu live (hapusan ditandai warna merah) -- cek dulu, baru tekan **"Lanjut Simpan"**.
4. Semua perubahan (foto + data menu) dikirim jadi **satu paket sekaligus** ke GitHub -- kalau berhasil, semuanya berhasil bareng; kalau gagal, tidak ada satupun yang setengah-setengah tersimpan (menu live tidak akan pernah rusak/tanggung gara-gara simpan gagal di tengah jalan).
5. Kalau berhasil, akan muncul pesan **"Tersimpan!"** -- menu yang tayang ke tamu akan ter-update dalam waktu sekitar **1 menit**.

### Keluar
Tekan tombol **Keluar** di pojok kanan atas untuk logout dari HP itu (token akan dihapus dari HP).

---

## 3. Kalau Ada Masalah (Troubleshooting)

**"Token salah atau sudah kedaluwarsa"**
Token biasanya berlaku 1 tahun. Kalau sudah lewat atau salah copy, buat token baru dengan langkah di Bagian 1, lalu masuk lagi pakai token baru itu.

**"Ada perubahan lain yang masuk ke server duluan"**
Ini muncul kalau ada 2 orang mengubah menu di waktu yang hampir sama. Perubahanmu **tidak hilang** -- CMS otomatis menyimpan draft di HP itu. Tekan **"Muat Data Terbaru"**, lalu begitu halaman selesai dimuat ulang akan muncul tawaran **"Lanjutkan Perubahan?"** -- tekan **Pulihkan**, cek lagi tidak ada yang bentrok dengan perubahan orang lain, lalu tekan Simpan Perubahan lagi. Untuk menghindari ini, sebaiknya cuma 1 orang yang pegang CMS dalam satu waktu.

**Sudah tekan Simpan, tapi menu di website belum berubah**
Wajar -- proses update ke website butuh waktu sekitar **1 menit** (kadang bisa sampai beberapa menit kalau sedang ramai). Tunggu sebentar, lalu refresh halaman menu (https://menu.kurniaseafood.co.id/). Kalau lebih dari 10 menit belum berubah, hubungi Patrick.

**GitHub membatasi terlalu banyak permintaan**
Ini jarang terjadi -- biasanya karena terlalu banyak percobaan simpan berturut-turut dalam waktu singkat. Tunggu beberapa menit lalu coba lagi.

**Lupa/hilang HP yang tersimpan tokennya**
Segera minta Patrick untuk **revoke** (cabut) token itu di GitHub (lihat cara di Bagian 1), lalu buat token baru untuk HP pengganti.

---

## 4. Keterbatasan yang Belum Ditangani

- **Foto latar transparan (PNG-alpha):** CMS belum punya tombol untuk menandai foto sebagai "latar transparan". Kalau kamu mengganti foto komposisi yang aslinya transparan dengan foto baru yang bukan PNG transparan (atau sebaliknya), tampilannya di menu online bisa terlihat sedikit janggal (foto diperkecil dengan pinggiran kosong, atau foto transparan terpotong). Kalau ini terjadi, hubungi Patrick untuk perbaikan manual.
- **Kategori jadi kosong:** kalau item terakhir di sebuah kategori (non seafood-segar) dihapus, CMS akan kasih peringatan sebelum kamu konfirmasi hapus, tapi tetap mengizinkan -- kategori itu akan tampil sebagai judul tanpa isi di menu online. Sebaiknya jangan menghapus item terakhir tanpa menambah item pengganti dulu.

## 5. Catatan Keamanan Singkat

- `admin.html` **boleh dibuka siapa saja** -- tanpa token, tidak ada yang bisa diubah (cuma bisa lihat mode demo pakai data contoh).
- Yang **wajib dijaga kerahasiaannya** cuma **token**-nya, bukan link CMS-nya.
- Kalau ragu token sudah bocor, langsung revoke & bikin baru -- tidak ada biaya, prosesnya cuma 1 menit.
