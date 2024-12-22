# Implementasi Nextcloud pada Arsitektur Multi Server untuk Meningkatkan Efisiensi Data dan Keandalan Sistem

## 1. Latar Belakang
Seiring meningkatnya kebutuhan akan solusi penyimpanan data yang efisien, platform Nextcloud hadir sebagai solusi berbasis cloud untuk kolaborasi dan manajemen file secara mandiri. Proyek ini mengimplementasikan Nextcloud dengan arsitektur multi-server yang mencakup server web, database, DNS, dan load balancing untuk meningkatkan efisiensi, keandalan, dan keamanan sistem penyimpanan data. Dengan memisahkan layanan utama ke server yang berbeda, proyek ini bertujuan untuk meningkatkan performa, memperkuat keamanan, dan memberikan kontrol lebih besar atas pengelolaan data secara mandiri.

## 2. Lingkup Pekerjaan
### 2.1 Pembuatan Infrastruktur
Mengatur beberapa instance server dengan peran sebagai berikut:
- **Web Server 1**: Menjalankan aplikasi Nextcloud sebagai server utama, melayani permintaan pengguna, dan menyediakan antarmuka web.
- **Web Server 2**: Server tambahan untuk menangani permintaan ketika Web Server 1 mengalami beban tinggi atau gangguan.
- **Database Server**: Menyimpan semua data yang dibutuhkan oleh aplikasi Nextcloud dan menyediakan akses jarak jauh untuk koneksi data.
- **DNS Primary**: Mengelola sistem nama domain, menerjemahkan nama domain menjadi alamat IP, sehingga pengguna dapat mengakses aplikasi dengan nama domain.
- **DNS Secondary**: Berfungsi sebagai cadangan untuk DNS Primary, memastikan layanan DNS tetap berjalan saat DNS Primary mengalami gangguan.
- **Load Balancing**: Mendistrbusikan lalu lintas jaringan secara merata di antara server, meningkatkan kinerja dan keandalan sistem.

### 2.2 Teknologi yang Digunakan
- **Sistem Operasi**: Ubuntu 22.04
- **Perangkat Lunak**: AWS Academy Learner
- **Protokol**: HTTP untuk akses pengguna.

## 3. Implementasi
### 3.1 Persyaratan
- Akun AWS Academy Learner.
- Instance AWS EC2 dengan konfigurasi minimal:
  - 2 vCPUs
  - 4 GB RAM
  - 20 GB Storage

### 3.2 Langkah-langkah Implementasi
1. **Konfigurasi Web Server 1 dan 2**:
   - Instal Apache/Nginx sebagai server web.
   - Unduh dan pasang aplikasi Nextcloud.
   - Ubah konfigurasi file `config.php` untuk koneksi database.

2. **Konfigurasi Database Server**:
   - Instal MariaDB/MySQL.
   - Buat database untuk Nextcloud dan beri izin akses jarak jauh.

3. **Konfigurasi DNS**:
   - Konfigurasikan DNS Primary dengan BIND untuk domain utama.
   - Konfigurasikan DNS Secondary sebagai cadangan.

4. **Setup Load Balancing**:
   - Instal HAProxy atau Nginx sebagai load balancer.
   - Tambahkan backend server Web Server 1 dan Web Server 2 ke konfigurasi.

5. **Pengujian Akhir**:
   - Uji akses aplikasi Nextcloud melalui domain yang dikonfigurasi.
   - Pastikan load balancing bekerja sesuai ekspektasi.
   - Verifikasi integrasi dengan database dan layanan DNS.

## 4. Dokumentasi Tambahan
- **Official Nextcloud Documentation**: [Nextcloud Documentation](https://docs.nextcloud.com)
- **BIND DNS Setup Guide**: [BIND9 Documentation](https://bind9.readthedocs.io)
- **HAProxy Setup Guide**: [HAProxy Documentation](https://haproxy.org)

## 5. Penulis
Proyek ini dibuat oleh Erlinda Butarbutar, Audrey Zakiya Trustee, Nasywa Azizah Zharifah, Zenitha Shaula Lora.
