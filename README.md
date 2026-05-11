# 🚀 WINHANA - Auto Windows VPS Installer

![Banner WinHana]([https://raw.githubusercontent.com/HanaaCanss/winhana/refs/heads/Hanaaa/assets/main.jpg])

**WINHANA** adalah script otomasi canggih yang dirancang untuk menginstal sistem operasi Windows di dalam Linux VPS menggunakan teknologi Docker dan KVM. Dengan script ini, kamu bisa memiliki VPS Windows hanya dengan satu baris perintah tanpa perlu melakukan setup manual yang rumit.

---

## 🌟 Fitur Utama

- ✅ **18 Pilihan OS:** Tersedia mulai dari Windows 7, 10, 11, hingga Windows Server terbaru.
- ✅ **Deteksi Resource Otomatis:** Script akan memberikan rekomendasi RAM dan Disk agar VPS Host tidak lag.
- ✅ **Auto-Firewall:** Otomatis membuka port 8006 (Web VNC) dan 3389 (RDP) di UFW.
- ✅ **Instalasi Satu Baris:** Tidak perlu ribet, cukup jalankan perintah dan tunggu.
- ✅ **KVM Support Detection:** Pengecekan hardware virtualization untuk performa maksimal.
- ✅ **Clean UI:** Tampilan terminal yang rapi dengan efek loading yang elegan.

---

## 🖥️ Sistem yang Didukung (OS Host)

Script ini dapat berjalan dengan baik di:
- **Debian** 10 / 11 / 12
- **Ubuntu** 20.04 / 22.04 / 24.04
- **CentOS / AlmaLinux / Rocky Linux** 8 & 9

---

## ⚠️ Persyaratan Minimum

Sebelum menjalankan script, pastikan VPS kamu memenuhi kriteria berikut:
1. **Akses Root:** Harus dijalankan sebagai user `root`.
2. **KVM Support:** VPS harus mendukung *Hardware Virtualization* (KVM).
   - *Cara cek manual:* `egrep -c '(vmx|svm)' /proc/cpuinfo` (Hasil > 0 berarti support).
3. **Docker:** Jika belum ada, script akan otomatis menginstalnya.
4. **RAM & Disk:** Minimal RAM 2GB dan Disk 40GB.

---

## 🚀 Tutorial Instalasi (Langkah demi Langkah)

### 1. Jalankan Perintah Utama
Buka terminal SSH kamu (Putty/Termux/CMD) dan tempelkan perintah berikut:

```bash
curl -sL [https://raw.githubusercontent.com/Hana/winhana/main/winhana.sh](https://raw.githubusercontent.com/Hana/winhana/main/winhana.sh) | sudo bash
```

### 2. Memilih Versi Windows
Setelah logo WINHANA muncul, kamu akan diminta memilih versi Windows. Masukkan angka (1-18) sesuai keinginan kamu.

![Tampilan Menu OS](https://raw.githubusercontent.com/Hana/winhana/main/images/menu-os.jpg)

### 3. Konfigurasi Resource
Script akan menampilkan total RAM dan Disk VPS kamu.
- Tekan **ENTER** jika ingin mengikuti rekomendasi script.
- Atau ketik angka manual (Contoh: `4` untuk 4GB).

### 4. Setup Kredensial
Masukkan **Username** dan **Password** yang akan kamu gunakan untuk login ke Windows nanti.

![Tampilan Input User](https://raw.githubusercontent.com/Hana/winhana/main/images/input-user.jpg)

### 5. Proses Instalasi
Tunggu hingga muncul pesan bahwa container berhasil dieksekusi. 

---

## 🌐 Cara Mengakses Windows

Setelah instalasi dimulai, kamu bisa memantau proses instalasi melalui browser:

1. **Akses Web VNC (Untuk melihat proses install):**
   - Buka: `http://IP_VPS_KAMU:8006/`
2. **Akses RDP (Setelah instalasi selesai):**
   - Gunakan aplikasi **Remote Desktop Connection**.
   - **IP:** `IP_VPS_KAMU`
   - **User:** Username yang kamu buat tadi.
   - **Pass:** Password yang kamu buat tadi.

![Tampilan Windows Running](https://raw.githubusercontent.com/Hana/winhana/main/images/windows-running.jpg)

---

## 🛠️ Troubleshoot (Masalah Umum)

- **Akses Web 8006 Tidak Muncul:** Pastikan firewall di panel provider VPS (seperti DigitalOcean, Linode, Google Cloud) sudah membuka port 8006 dan 3389.
- **Booting Sangat Lambat:** Ini biasanya terjadi jika VPS tidak mendukung KVM (Emulasi penuh). Pastikan fitur virtualisasi aktif di VPS kamu.
- **Docker Error:** Jalankan `sudo service docker start` jika docker tidak berjalan otomatis.

---

## 🙏 Credits & Acknowledgments

*Core engine* dari instalasi Windows dalam container ini menggunakan proyek luar biasa dari **[dockur/windows](https://github.com/dockur/windows)**. 

**Hana** (melalui WINHANA) bertindak sebagai penyedia script otomasi (*wrapper*) untuk mempermudah pengguna, khususnya pemula. Script ini mengotomatiskan persiapan VPS kosong (install dependensi, pengecekan KVM, konfigurasi firewall, hingga perhitungan dinamis untuk RAM & Disk) agar instalasi image dari `dockur/windows` bisa dilakukan cukup dengan satu perintah simpel.

---

## 👨‍💻 Kontribusi & Support

Jika kamu menemukan bug pada *installer script* ini atau ingin memberikan saran fitur, silakan buka *Issue* atau hubungi melalui:

- **GitHub:** [@Hana](https://github.com/HanaaCanss)

---
*Script Installer dibuat dengan ❤️ oleh Hana untuk mempermudah komunitas.*
