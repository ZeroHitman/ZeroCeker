# 🕵️ ZeroCeker

**ZeroCeker** adalah tools **multi-threaded** berbasis Go yang dirancang untuk memindai daftar URL dalam jumlah besar (hingga puluhan GB) dan mendeteksi website yang aktif.  
Tools ini secara otomatis menyortir hasil berdasarkan jenis **Web App** seperti WordPress, Joomla, OJS, Moodle, cPanel, WHM, Webmin, phpMyAdmin, Adminer, dan lainnya, serta domain khusus seperti **GOV, EDU, AC** di berbagai negara.

> Dibuat untuk kecepatan, ketepatan, dan kemudahan penggunaan. Cocok untuk pentester, bug bounty hunter, atau sekadar pengecekan massal.

---

## ✨ Fitur Utama
- 🚀 **Super Cepat** — Memproses jutaan baris hanya dalam hitungan detik dengan multi-threading.
- 🗂 **Sortir Otomatis** — Memisahkan hasil aktif ke folder kategori berdasarkan jenis web app.
- 🌐 **Deteksi Domain Khusus** — GOV, EDU, AC, dan ekstensi pemerintah/pendidikan di banyak negara.
- 🎯 **Anti Duplikat** — Hanya menyimpan data unik (full match: domain + username + password).
- 📁 **Output Rapi** — File hasil disimpan otomatis ke folder kategori dengan nama tanggal scan.
- 🔄 **Update Otomatis** — Bisa memperbarui tools langsung dari GitHub.
- 🎨 **Tampilan Menarik** — Dengan ASCII art & warna untuk status aktif.

---

## 📥 Instalasi

### 1. Download Binary
Pilih sesuai sistem operasi dan arsitektur CPU Anda:

| OS       | Arsitektur | Link Unduh |
|----------|------------|------------|
| Linux    | amd64      | [Download](https://zerohitman.github.io/ZeroCeker/v1.0.0/ceker-linux-amd64) |
| Linux    | arm64      | [Download](https://zerohitman.github.io/ZeroCeker/v1.0.0/ceker-linux-arm64) |
| macOS    | amd64      | [Download](https://zerohitman.github.io/ZeroCeker/v1.0.0/ceker-darwin-amd64) |
| macOS    | arm64      | [Download](https://zerohitman.github.io/ZeroCeker/v1.0.0/ceker-darwin-arm64) |
| Windows  | amd64      | [Download](https://zerohitman.github.io/ZeroCeker/v1.0.0/ceker-windows-amd64.exe) |

> Untuk Linux/macOS, jangan lupa beri izin eksekusi:
```bash
chmod +x ceker
```

---

## ⚡ Cara Pakai

### Menampilkan Help
```bash
./ceker
```
Akan menampilkan panduan lengkap dalam bahasa Indonesia.

### Mode Dasar
```bash
./ceker list.txt
```
Memindai semua URL di `list.txt` dan menyimpan hasil di folder `output/`.

### Mode Verbose (Menampilkan Progress)
```bash
./ceker -v list.txt
```

### Mode Sangat Detail
```bash
./ceker -vv list.txt
```

### Memindai Banyak File Sekaligus
```bash
./ceker -v /home/user/lists/*.txt
```

### Update Tools
```bash
./ceker update
```

---

## 📂 Struktur Output
Setelah proses selesai, hasil akan tersimpan seperti ini:
```
output/
 ├── wordpress/
 │    ├── 2025-08-09_01.txt
 │    ├── ...
 ├── joomla/
 ├── moodle/
 ├── ojs/
 ├── cpanel/
 ├── whm/
 ├── webmin/
 ├── phpmyadmin/
 ├── adminer/
 ├── gov/
 ├── edu/
 ├── random/
 └── active.txt
```
- **active.txt** → Semua website aktif (tanpa filter kategori).
- **random/** → Website aktif yang tidak cocok kategori manapun.

---

## 🖼 Screenshot

### Tampilan Scan
![Screenshot](screenshot.png)

---

## 🔍 Contoh List Input
Format input di `list.txt`:
```
http://example.com/wp-login.php:user:pass
example.com/administrator:user:pass
ojs.example.ac.id/index.php/index/install/install:admin:admin
```

Output akan otomatis memisahkan sesuai kategori.

---

## ⚠️ Disclaimer
Tools ini hanya untuk **pembelajaran** dan **pengujian keamanan** pada sistem milik Anda atau yang memiliki izin tertulis.  
Segala penyalahgunaan menjadi tanggung jawab pengguna.

---

## 📜 Lisensi
MIT License © 2025 [ZeroHitman](https://github.com/ZeroHitman)
