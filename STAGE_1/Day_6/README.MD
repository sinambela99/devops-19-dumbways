Web server adalah seperti pelayan di restoran yang menerima pesanan dari pelanggan (pengguna internet) 
dan mengantarkan makanan (halaman web) kepada mereka. 
Ini adalah komputer khusus yang dirancang untuk menyimpan, mengelola, dan mengirimkan halaman web kepada perangkat pengguna.

Cara kerja web server dapat diibaratkan sebagai berikut:

    Permintaan (Request): Pengguna membuka browser dan mengetikkan alamat situs web atau mengklik tautan. Ini mengirimkan permintaan ke web server.

    Pemrosesan Permintaan: Web server menerima permintaan, memahami apa yang diminta, dan mengeksekusi perintah yang diperlukan. 
    Ini bisa mencakup mengambil data dari database, menjalankan skrip, atau mengambil file tertentu.

    Pengiriman (Response): Setelah pemrosesan selesai, web server mengirimkan hasilnya kembali ke browser pengguna. 
    Ini mungkin berupa halaman web HTML, gambar, atau file lainnya.

    Tampilan di Browser: Browser menerima respons dari server dan menampilkan halaman web sesuai dengan instruksi yang diberikan oleh server.

Seluruh proses ini terjadi dalam hitungan detik, memungkinkan pengguna untuk dengan cepat mengakses berbagai informasi dan layanan di internet. 
Jadi, web server berfungsi sebagai perantara yang menghubungkan permintaan pengguna dengan sumber daya web yang diperlukan untuk memenuhi permintaan tersebut.

Reverse Proxy
Reverse proxy, secara sederhana, dapat diibaratkan sebagai "perantara" antara pengguna (klien) dan server.
Keuntungan dari reverse proxy termasuk keamanan, peningkatan kinerja, dan manajemen lalu lintas. 
Ini juga dapat digunakan untuk menyembunyikan detail internal server dari pengguna, bertindak sebagai lapisan keamanan tambahan, 
atau mempercepat pengiriman konten dengan menyimpan salinan di server cache. 
Jadi, reverse proxy berfungsi sebagai perantara pengguna dan server di belakangnya.

Cara melakukan reverse proxy sebagai berikut

1 login multipass
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/1%20login%20multipass.png?raw=true)

2 melakukan cloning
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/2%20melakukan%20cloning.png?raw=true)

3 cek cloning file
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/3%20cek%20cloning%20file.png?raw=true)

4 install nvm
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/4%20install%20nvm.png?raw=true)

5 install npm
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/5%20install%20npm%20.png?raw=true)

6 npm start
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/6%20npm%20start.png?raw=true)

7 cek ip vm
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/7%20cek%20ip%20vm.png?raw=true)

8 siap dijalankan (test awal)
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/8%20siap%20dijalankan.png?raw=true)

9.Hasil
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/9%20hasil%20clone%20yang%20sudah%20di%20jalankan.png?raw=true)

10 install nginx
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/10%20install%20nginx.png?raw=true)

11 cek status nginx
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/11%20cek%20status%20nginx.png?raw=true)

12 ubah kepemilikan file agar dapat membuat dikerktori
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/12%20ubah%20kepemilikan%20file%20agar%20dapat%20membuat%20dikerktori.png?raw=true)

13 kepemilikan file sudah berubah menjadi ubuntu
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/13%20kepemilikan%20file%20sudah%20berubah%20menjadi%20ubuntu.png?raw=true)

14 configuration proxy sudah dibuat
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/14%20configuration%20proxy%20sudah%20dibuat.png?raw=true)

15 config pada reverse proxy sudah dibuat
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/15%20config%20pada%20reverse%20proxy%20sudah%20dibuat.png?raw=true)

16 memberikan config pada local
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/16%20memberikan%20config%20pada%20local.png?raw=true)

17 config pada local
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/17%20config%20pada%20local.png?raw=true)

18 memberikan reload pada nginx kita karena pengubahan config
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/18%20memberikan%20reload%20pada%20nginx%20kita%20karena%20pengubahan%20config.png?raw=true)

19 reverse proxy berhasil dibuat
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/reverse%20proxy/19%20reverse%20proxy%20berhasil%20dibuat.png?raw=true)

Load Balancing 
Load balancing pada server adalah konsep yang digunakan untuk membagi beban kerja (workload) di antara beberapa server agar tidak ada satu server pun yang terbebani secara berlebihan. 


Cara melakukannya sebagai berikut

1 melakukan cloning tiap tiap vm
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/1%20melakukan%20cloning%20tiap%20tiap%20vm.png?raw=true)

2 install npm
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/2%20install%20npm.png?raw=true)

3 coba jalankan aplikasi (test)
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/3%20coba%20jalankan%20aplikasi%20.png?raw=true)

4 cek ip static vm
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/4%20cek%20ip.png?raw=true)

5 aplikasi berhasil berjalan
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/5%20aplikasi%20berhasil%20berjalan.png?raw=true)

6 konfigurasi load balance
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/6%20konfigurasi%20load%20balance.png?raw=true)

7 cek status konfigurasi
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/7%20cek%20status%20konfigurasi.png?raw=true)

8 restart sistem
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/8%20restart%20sistem.png?raw=true)

9 coba jalankan alikasi
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/9%20coba%20jalankan%20alikasi.png?raw=true)

10 aplikasi dapat berjalan
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/10%20aplikasi%20dapat%20berjalan.png?raw=true)

11 test salah satu server mati
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/11%20test%20salah%20satu%20server%20mati.png?raw=true)

12 aplkasi masih dapat berjlan
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/load%20balancer/12%20aplkasi%20masih%20dapat%20berjlan%20.png?raw=true)
