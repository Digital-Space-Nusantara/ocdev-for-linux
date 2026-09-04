# OCDev Tunnel for Linux

OCDev Tunnel adalah solusi **reverse proxy** yang aman dan tangguh untuk mengekspos server lokal Anda ke internet publik secara instan.

Tanpa perlu konfigurasi **port forwarding** pada router lokal (Bypass NAT & Firewall), aplikasi lokal Anda dapat diakses melalui internet menggunakan subdomain yang telah terdaftar pada akun OCDev.

Proyek ini merupakan **Linux Client** resmi dari **DSN Data Center** untuk layanan tunneling OCDev.

---

## ✨ Fitur Unggulan

- 🚀 **Bypass NAT & Firewall**  
  Mengekspos port lokal ke internet tanpa perlu melakukan port forwarding pada router.

- 🔐 **End-to-End Encryption**  
  Koneksi tunnel diamankan menggunakan SSL/HTTPS.

- 🌐 **Custom Subdomain**  
  Gunakan subdomain yang telah terdaftar pada akun Anda.

  Contoh:

  ```text
  namakamu.tunnel.our-chat.web.id
  ```

- 🔑 **Authtoken Security**  
  Setiap sesi tunnel menggunakan Authtoken untuk autentikasi.

- 🐧 **Linux Support**  
  Mendukung sistem Linux 64-bit.

- ⚡ **Instant Tunnel**  
  Hubungkan aplikasi lokal ke internet hanya dengan satu perintah.

---

## 📋 Persyaratan

Sebelum menggunakan OCDev Tunnel, pastikan Anda memiliki:

- Linux 64-bit
- Koneksi internet aktif
- Akses Terminal
- Aplikasi/server lokal yang berjalan pada sebuah port

Contoh aplikasi:

```text
Node.js
PHP
Python
Go
Apache
Nginx
dan aplikasi TCP lainnya
```

---

## 📥 Instalasi

### 1. Download OCDev

Download executable OCDev versi terbaru melalui halaman **Releases**:

https://github.com/Digital-Space-Nusantara/ocdev-for-linux/releases

Contoh:

```bash
wget <URL_RELEASE>
```

Atau download secara manual melalui browser.

---

### 2. Berikan Permission

Setelah file `ocdev` berhasil di-download, berikan permission executable:

```bash
chmod +x ocdev
```

Kemudian jalankan:

```bash
./ocdev --help
```

Jika bantuan penggunaan muncul, berarti OCDev berhasil dijalankan.

---

### 3. Tambahkan ke PATH

Agar perintah `ocdev` dapat dijalankan dari direktori mana pun, pindahkan executable ke:

```text
/usr/local/bin
```

Gunakan:

```bash
sudo mv ocdev /usr/local/bin/ocdev
```

Kemudian cek:

```bash
ocdev --help
```

Jika berhasil, OCDev sudah dapat digunakan secara global.

---

# 🚀 Cara Penggunaan

Format perintah:

```bash
ocdev tunnel <PORT_LOKAL> <SUBDOMAIN> --token <TOKEN_ANDA>
```

### Contoh

Misalnya aplikasi lokal berjalan pada port `3000`:

```bash
ocdev tunnel 3000 namakamu --token 1234567890abcdef
```

OCDev kemudian akan menghubungkan:

```text
Internet
    │
    ▼
OCDev Tunnel
    │
    ▼
namakamu.tunnel.our-chat.web.id
    │
    ▼
localhost:3000
```

---

# 🌐 Mendapatkan Subdomain & Authtoken

Untuk menggunakan OCDev Tunnel, Anda perlu memiliki **subdomain** dan **Authtoken** yang terdaftar pada akun Anda.

Kunjungi:

https://tunnel.our-chat.web.id/dashboard/dsn-tunnel

Dari dashboard tersebut Anda dapat:

- Mengklaim subdomain
- Melihat subdomain yang tersedia
- Mendapatkan Authtoken
- Mengelola tunnel

Contoh konfigurasi:

```text
Subdomain : namakamu
Domain    : tunnel.our-chat.web.id
Token     : 1234567890abcdef
```

---

# 💻 Contoh Penggunaan

## Node.js

Jika aplikasi Node.js berjalan pada:

```text
http://localhost:3000
```

jalankan:

```bash
ocdev tunnel 3000 namakamu --token TOKEN_ANDA
```

Aplikasi kemudian dapat diakses melalui:

```text
https://namakamu.tunnel.our-chat.web.id
```

---

## PHP

Jalankan PHP development server:

```bash
php -S localhost:8000
```

Kemudian buka tunnel:

```bash
ocdev tunnel 8000 namakamu --token TOKEN_ANDA
```

---

## Python

Misalnya aplikasi Python berjalan pada port `5000`:

```bash
ocdev tunnel 5000 namakamu --token TOKEN_ANDA
```

---

## Go

Jika aplikasi Go berjalan pada port `8080`:

```bash
ocdev tunnel 8080 namakamu --token TOKEN_ANDA
```

---

# 🔧 Format Command

```text
ocdev tunnel <PORT> <SUBDOMAIN> --token <TOKEN>
```

| Parameter | Keterangan |
|---|---|
| `tunnel` | Menjalankan layanan tunnel |
| `<PORT>` | Port aplikasi lokal |
| `<SUBDOMAIN>` | Subdomain yang terdaftar |
| `--token` | Authtoken akun OCDev |

Contoh:

```bash
ocdev tunnel 3000 myapp --token abcdef123456
```

---

# 🔒 Keamanan

Jangan membagikan **Authtoken** Anda kepada orang lain.

Contoh:

```bash
ocdev tunnel 3000 namakamu --token TOKEN_ANDA
```

Simpan token sebagai informasi rahasia.

Jika Authtoken Anda bocor, segera lakukan perubahan atau regenerasi token melalui dashboard OCDev.

---

# 🛑 Menghentikan Tunnel

Untuk menghentikan tunnel yang sedang berjalan, tekan:

```text
CTRL + C
```

Tunnel akan terputus dan aplikasi lokal kembali hanya dapat diakses melalui koneksi lokal.

---

# 🐛 Bug & Issues

Jika Anda menemukan bug, error, atau masalah ketika menggunakan OCDev Tunnel, silakan buat laporan melalui GitHub Issues:

https://github.com/Digital-Space-Nusantara/ocdev-for-linux/issues

Sertakan informasi berikut jika memungkinkan:

```text
OS:
Architecture:
OCDev Version:
Command:
Error Message:
```

Contoh:

```text
OS: Ubuntu 24.04
Architecture: amd64
OCDev Version: 1.0.0
Command: ocdev tunnel 3000 myapp --token ***
Error Message: connection refused
```

---

# 📦 Releases

Versi terbaru OCDev Tunnel dapat diperoleh melalui:

https://github.com/Digital-Space-Nusantara/ocdev-for-linux/releases

---

# 🏢 Developer

**DSN Data Center**

Digital Space Nusantara

GitHub Organization:

https://github.com/Digital-Space-Nusantara/

---

## ❤️ Support

Jika proyek ini bermanfaat, jangan lupa memberikan ⭐ pada repository GitHub.

---

**OCDev Tunnel — Local Server, Public Access.**
