**Dokumentasi Pembaruan Pentaho Community Edition - Pembaruan ke Versi, Job, Transformasi, dan Crontab Job:**

---

## Pengantar:

Dokumentasi ini memberikan panduan langkah demi langkah untuk melakukan pembaruan Pentaho Community Edition ke versi terbaru. Selain itu, dokumentasi ini juga mencakup pengelolaan, Job dan Transformasi, Crontab Job dalam proses pembaruan Pentaho. Pembaruan Pentaho bertujuan untuk meningkatkan kinerja, mendapatkan fitur terbaru, dan memastikan keamanan dari pembaruan yang telah diperbarui oleh komunitas atau pengembang Pentaho.

### Tujuan Dokumentasi:

1. Memandu pengguna dalam melakukan pembaruan Pentaho Community Edition ke versi terbaru.
2. Menjelaskan langkah-langkah khusus terkait pengelolaan Crontab Job dan pembaruan terkait pengelolaan pekerjaan terjadwal.
3. Memberikan sumber daya untuk memahami perubahan dan peningkatan terkait Job dan Transformasi pada versi terbaru.
4. Mendorong praktik selalu mencoba versi terbaru di lingkungan pengembangan sebelum implementasi di lingkungan produksi.

### Requirements:
Sebelum melakukan pembaruan, pastikan sistem memenuhi persyaratan instalasi Pentaho Community Edition, yang mencakup:

   - **Spesifikasi Hardware:**
      - CPU, RAM, dan ruang penyimpanan sesuai dengan rekomendasi.
   
   - **Sistem Operasi:**
      - Pastikan sistem operasi yang didukung, seperti Linux atau Windows, sesuai dengan versi Pentaho yang akan diinstal.

   - **Java dan GUI:**
      - Memerlukan Java versi 8 ke atas.
      - Pastikan sistem memiliki lingkungan GUI (Graphical User Interface) untuk menjalankan antarmuka Pentaho secara optimal.

   - **Koneksi Internet:**
      - Ketersediaan koneksi internet yang stabil selama proses instalasi dan pembaruan.
   
   - **Repository Lokal (Opsional):**
      - Jika tidak ada koneksi internet, pertimbangkan untuk mengunduh paket instalasi Pentaho ke server atau menggunakan repository lokal.
   
   - **Hak Akses dan Izin:**
      - Memastikan hak akses dan izin yang memadai untuk melakukan instalasi dan konfigurasi.

Dengan memperhatikan persyaratan ini, pengguna dapat memastikan bahwa sistemnya siap untuk menginstal dan menjalankan Pentaho Community Edition dengan lancar.

---

## Langkah-langkah Pembaruan:

### Langkah 1: Persiapan

1. Buka dokumentasi terkait dengan versi stabil/Long Term Support Pentaho di Pentaho Product Version End of Life Policy [https://support.pentaho.com/hc/en-us/articles/205789159-Pentaho-Product-Version-End-of-Life-Policy](https://support.pentaho.com/hc/en-us/articles/205789159-Pentaho-Product-Version-End-of-Life-Policy)
2. Buka situs resmi untuk Download Pentaho Community Edition di [https://www.hitachivantara.com/en-us/products/pentaho-plus-platform/data-integration-analytics/pentaho-community-edition.html](https://www.hitachivantara.com/en-us/products/pentaho-plus-platform/data-integration-analytics/pentaho-community-edition.html).
3. Di bagian unduhan, temukan dan identifikasi versi terbaru dari Pentaho Community Edition (Direkomendasikan untuk menggunakan Long Term Support untuk Environment Production).
4. Periksa catatan rilis untuk mendapatkan informasi lebih lanjut tentang perubahan dan peningkatan.
5. Verifikasi persyaratan terkait dengan versi Pentaho yang akan diinstal. Pentaho memerlukan GUI dan Java versi 8 ke atas.
6. Jika diperlukan, lakukan testing di Environment Development terlebih dahulu sebelum melakukan Deployment versi Pentaho terbaru di Environment Production.
.
### Langkah 2: Backup Data dan Konfigurasi Job/Transformasi

1. Buat backup menyeluruh, termasuk konfigurasi pentaho di folder data-integration.
2. Pastikan backup mencakup folder `jobs` dan `transformations` yang berisi definisi pekerjaan dan transformasi.
3. Matikan Job/transfomasi yang berjalan di Crontab/Task Schaduler.

### Langkah 3: Baca Dokumentasi Resmi

1. Teliti dokumen pembaruan dan catatan rilis untuk versi terbaru terkait fitur Job dan Transformasi.
2. Pahami perubahan yang mungkin mempengaruhi definisi Job dan Transformasi Anda.

### Langkah 4: Metode Pembaruan

1. Baca dokumentasi instalasi Pentaho di [https://www.hitachivantara.com/en-us/pdf/implementation-guide/three-steps-to-install-pentaho-data-integration-ce.pdf](https://www.hitachivantara.com/en-us/pdf/implementation-guide/three-steps-to-install-pentaho-data-integration-ce.pdf)
2. Proses pembaruan Petaho harus dilakukan di folder/direktori yang sama dengan versi sebelumnya.
3. Pembaruan Pentaho Community Edition hanya dapat dilakukan secara manual dengan mengunduh versi terbaru di website. Terdapat dua sekenario untuk melakukan pembaruan Pentaho Community Edition:
   -  Pembaruan dilakukan dengan menimpa folder data-integration dari versi Pentaho sebelumnya dengan versi terbaru.
   -  Menghapus folder data-integration dari versi sebelumnya dan mengekstrak versi Pentaho terbaru di direktori yang sama.

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
   - b. Jika ada masalah, periksa log dan pesan error untuk mengidentifikasi penyebabnya, dan ambil langkah-langkah yang diperlukan untuk penyelesaian.
   
### Langkah 6: Konfigurasi Crontab/Task Schaduler

1. Jika menggunakan Crontab Job, simpan konfigurasi Crontab sebelum pembaruan.
2. Perbarui atau sesuaikan Crontab Job sesuai dengan perubahan mungkin pada definisi Job dan Transformasi.

### Langkah 8: Testing Job dan Transformasi

1. Lakukan uji coba menyeluruh pada Job dan Transformasi setelah pembaruan.
2. Perhatikan log dan hasil eksekusi untuk mendeteksi potensi masalah atau perubahan perilaku.

### Langkah 9: Perubahan dan Peningkatan Job dan Transformasi

1. Baca catatan rilis secara rinci untuk memahami perubahan dan peningkatan khusus pada Job dan Transformasi.
2. Komunikasikan perubahan ini kepada tim pengguna atau admin yang terkait.

### Langkah 10: Tinjau Konfigurasi dan Integrasi Job dan Transformasi

1. Tinjau kembali konfigurasi Pentaho untuk memastikan integrasi yang baik dengan Job dan Transformasi.
2. Sesuaikan konfigurasi jika diperlukan untuk mempertahankan integrasi.

### Langkah 11: Backup Konfigurasi dan Definisi Job/Transformasi

1. Pastikan file konfigurasi dan definisi Job/Transformasi di-backup kembali.
2. Simpan backup ini di tempat yang aman untuk pemulihan jika diperlukan.

### Langkah 12: Dukungan Komunitas atau Vendor

1. Bergabunglah dengan forum komunitas Pentaho atau hubungi dukungan teknis jika mengalami masalah terkait Job dan Transformasi.
2. Manfaatkan sumber daya online untuk pertanyaan dan pemecahan masalah terkait Job dan Transformasi.

---

**Catatan Penting:**
- Pastikan untuk merujuk pada dokumentasi resmi yang terkait dengan versi spesifik Pentaho yang Anda perbarui.
- Proses pembaruan untuk Job dan Transformasi dapat membutuhkan uji coba yang lebih menyeluruh dan pemahaman yang mendalam terhadap perubahan yang terjadi.
- Implementasikan pembaruan terlebih dahulu di lingkungan pengembangan untuk memitigasi risiko sebelum diterapkan di lingkungan produksi.
