**Dokumentasi Pembaruan Pentaho Community Edition:**

---

## Pengantar:

Dokumentasi ini memberikan panduan langkah demi langkah untuk melakukan pembaruan Pentaho Community Edition ke versi terbaru. Pembaruan Pentaho bertujuan untuk meningkatkan kinerja, mendapatkan fitur terbaru, dan memastikan keamanan dari pembaruan yang telah diperbarui oleh komunitas atau pengembang Pentaho.

### Tujuan Dokumentasi:

1. Pembaruan bertujuan untuk meningkatkan kinerja keseluruhan Pentaho Community Edition, termasuk eksekusi yang lebih cepat untuk Job dan Transformasi.
2. Memastikan akses ke fitur terbaru dan perbaikan keamanan untuk menjaga integritas dan keamanan data.
3. Menjaga dukungan komunitas dan pengembang dengan menggunakan versi yang masih didukung, memastikan pembaruan reguler dan pemecahan masalah. Melakukan uji coba di lingkungan pengembangan untuk meminimalkan risiko dan memastikan kelancaran implementasi di lingkungan produksi.

### Requirements:
Sebelum melakukan pembaruan, pastikan sistem memenuhi persyaratan instalasi/pembaruan Pentaho Community Edition, yang mencakup:

   - **Spesifikasi Hardware:**
      - Prosesor: Intel X64 atau AMD64 Dual-Core Processor atau yang lebih tinggi
      - RAM: 8 GB atau lebih.
      - Ruang Disk: 20 GB kosong setelah instalasi
      - Ukuran Layar: 1280 x 960
   
   - **Sistem Operasi:**
      - Pastikan sistem operasi yang didukung, seperti Linux atau Windows, sesuai dengan versi Pentaho yang akan diinstal.

   - **Java dan GUI:**
      - Instal Java SE 64 bit pada workstation atau laptop tempat Anda ingin menjalankan Pentaho Data Integration (PDI). Versi Java SE antara 11 hingga 18 dapat digunakan.
      - Pastikan sistem memiliki lingkungan GUI (Graphical User Interface) untuk menjalankan antarmuka Pentaho secara optimal.

   - **Koneksi Internet:**
      - Ketersediaan koneksi internet yang stabil selama proses instalasi dan pembaruan.
   
   - **Repository Lokal (Opsional):**
      - Jika tidak ada koneksi internet, pertimbangkan untuk mengunduh paket instalasi Pentaho ke server atau menggunakan repository lokal.
   
   - **Hak Akses dan Izin:**
      - Memastikan hak akses dan izin yang memadai untuk melakukan instalasi dan konfigurasi.
        
   - **Ubuntu/Linux:**
      - Untuk instalasi pada Linux/Ubuntu, pastikan untuk menginstal libwebkitgtk-1.0-0 agar PDI dapat berfungsi dengan baik. Untuk informasi lebih lanjut, kunjungi halaman Komunitas Hitachi Vantara Pentaho di [https://community.hitachivantara.com/discussion/libwebkitgtk-10-0-on-ubuntu-2204-lts](https://community.hitachivantara.com/discussion/libwebkitgtk-10-0-on-ubuntu-2204-lts).

Dengan memperhatikan persyaratan ini, pengguna dapat memastikan bahwa sistemnya siap untuk menginstal dan menjalankan Pentaho Community Edition dengan lancar.

---

## Langkah-langkah Pembaruan:

### Langkah 1: Persiapan

1. Buka dokumentasi terkait dengan versi stabil/Long Term Support Pentaho di Pentaho Product Version End of Life Policy [https://support.pentaho.com/hc/en-us/articles/205789159-Pentaho-Product-Version-End-of-Life-Policy](https://support.pentaho.com/hc/en-us/articles/205789159-Pentaho-Product-Version-End-of-Life-Policy)
2. Buka situs resmi untuk Download Pentaho Community Edition di [https://www.hitachivantara.com/en-us/products/pentaho-plus-platform/data-integration-analytics/pentaho-community-edition.html](https://www.hitachivantara.com/en-us/products/pentaho-plus-platform/data-integration-analytics/pentaho-community-edition.html).
3. Di bagian unduhan, temukan dan identifikasi versi terbaru dari Pentaho Community Edition (Direkomendasikan untuk menggunakan Long Term Support untuk Environment Production).
4. Periksa catatan rilis untuk mendapatkan informasi lebih lanjut tentang perubahan dan peningkatan.
5. Verifikasi persyaratan terkait dengan versi Pentaho yang akan diinstal. Pentaho memerlukan GUI dan Versi Java SE antara 11 hingga 18 dapat digunakan.
6. Jika diperlukan, lakukan testing di Environment Development terlebih dahulu sebelum melakukan Deployment versi Pentaho terbaru di Environment Production.
.
### Langkah 2: Backup Data dan Konfigurasi Job/Transformasi

1. Buat backup menyeluruh, termasuk konfigurasi pentaho di folder data-integration.
2. Pastikan backup mencakup folder `jobs` dan `transformations` yang berisi konfigurasi pekerjaan dan transformasi.
3. Matikan Job/transfomasi yang berjalan di Crontab/Task Schaduler.
4. Simpan konfigurasi Crontab sebelum pembaruan.

### Langkah 3: Baca Dokumentasi Resmi

1. Teliti dokumen pembaruan dan catatan rilis untuk versi terbaru terkait fitur Job dan Transformasi di [https://help.hitachivantara.com/Documentation/Pentaho](https://help.hitachivantara.com/Documentation/Pentaho).
2. Pahami perubahan yang mungkin mempengaruhi konfigurasi Job dan Transformasi Anda.

### Langkah 4: Metode Pembaruan

1. Baca dokumentasi instalasi Pentaho di [https://www.hitachivantara.com/en-us/pdf/implementation-guide/three-steps-to-install-pentaho-data-integration-ce.pdf](https://www.hitachivantara.com/en-us/pdf/implementation-guide/three-steps-to-install-pentaho-data-integration-ce.pdf)
2. Proses pembaruan Petaho harus dilakukan di folder/direktori yang sama dengan versi sebelumnya.
3. Pembaruan Pentaho Community Edition hanya dapat dilakukan secara manual dengan mengunduh versi terbaru di website. Terdapat dua sekenario untuk melakukan pembaruan Pentaho Community Edition:
   -  Overwrite Install: Pembaruan dilakukan dengan menimpa folder data-integration dari versi Pentaho sebelumnya dengan versi terbaru.
   -  Fresh Install: Menghapus folder data-integration dari versi sebelumnya dan mengekstrak versi Pentaho terbaru di direktori yang sama.

### Langkah 5: Testing Pembaruan melaui GUI Pentaho
**1. Menjalankan Antarmuka Grafis (GUI) Pentaho:**
   - a. Buka aplikasi Pentaho dengan menjalankan perintah atau menggunakan pintasan yang sesuai dengan sistem operasi yang digunakan.
   - b. Jika menggunakan lingkungan Windows, Anda dapat menggunakan shortcut pada desktop atau mencari aplikasi "Spoon" di menu Start.
   - c. Untuk lingkungan Linux, buka terminal dan navigasikan ke direktori instalasi Pentaho. Jalankan perintah `./spoon.sh` untuk memulai Spoon.
   - d. Tunggu hingga antarmuka grafis Pentaho terbuka.

**2. Pengujian Job dan Transformasi:**
   - a. Setelah antarmuka grafis terbuka, buka Job atau Transformasi yang ingin diuji dengan mengklik menu "File" dan memilih "Open" untuk memilih file yang sesuai.
   - b. Periksa setiap langkah dalam Job dan Transformasi, pastikan tidak ada kesalahan atau peringatan yang muncul.
   - c. Jalankan Job atau Transformasi secara manual dengan mengklik tombol "Run" atau menggunakan opsi yang sesuai.
   - d. Perhatikan output dan log yang dihasilkan selama proses eksekusi.

**3. Evaluasi Hasil Pengujian:**
   - a. Jika tidak ada pesan error atau peringatan selama pengujian dan Job atau Transformasi berjalan dengan normal, ini menandakan bahwa proses pembaruan Pentaho Community Edition berhasil.
   - b. Jika ada masalah, periksa log dan pesan error untuk mengidentifikasi penyebabnya.
   
### Langkah 6: Konfigurasi Crontab/Task Schaduler

1. Setlah proses pembaruan berhasil buka simpan konfigurasi Crontab dan aktifkan kembali Job/Transfomasi yang berjalan.
2. Jika terdapat perubahan,perbarui atau sesuaikan Crontab Job sesuai dengan perubahan pada Job dan Transformasi.
   
### Langkah 7: Backup Konfigurasi Job/Transformasi

1. Pastikan file konfigurasi Job/Transformasi di-backup kembali.
2. Simpan backup ini di tempat yang aman untuk pemulihan jika diperlukan.

### Langkah 8: Dukungan Komunitas
1. Bergabunglah dengan forum komunitas Pentaho jika mengalami masalah terkait Job dan Transformasi.
2. Manfaatkan sumber daya online untuk pertanyaan dan pemecahan masalah terkait Job dan Transformasi.

---

**Catatan Penting:**
- Pastikan untuk merujuk pada dokumentasi resmi yang terkait dengan versi spesifik Pentaho yang Anda perbarui.
- Proses pembaruan untuk Job dan Transformasi dapat membutuhkan uji coba yang lebih menyeluruh dan pemahaman yang mendalam terhadap perubahan yang terjadi.
- Implementasikan pembaruan terlebih dahulu di Development Environment untuk memitigasi risiko sebelum diterapkan di Production Environment.
