Apa itu DevOps?
DevOps singkatan dari Development (pengembangan) dan Operations (operasi). DevOps adalah suatu pendekatan atau budaya dalam pengembangan perangkat lunak yang menekankan kolaborasi dan komunikasi antara tim pengembangan (developer) dan tim operasional (operations). Tujuan utamanya adalah untuk meningkatkan efisiensi dan responsifitas dalam pengembangan, meminimalisirkan human errorr, pengujian, dan pengelolaan perangkat lunak.

Pilar-pilar Utama DevOps:

    Kolaborasi:
        DevOps menekankan pentingnya kolaborasi antara tim pengembangan dan operasional. Tim ini bekerja bersama-sama dari awal hingga akhir siklus pengembangan perangkat lunak.

    Otomatisasi:
        Mengotomatisasi proses pengembangan, pengujian, dan implementasi perangkat lunak untuk mengurangi kesalahan manusia, meningkatkan kecepatan, dan mengoptimalkan sumber daya.

    Integrasi Terus-Menerus:
        Menerapkan integrasi terus-menerus (Continuous Integration) untuk menggabungkan perubahan kode secara otomatis dan secara berkala, memastikan bahwa kode yang dihasilkan dapat diuji dan diintegrasikan dengan baik.

    Pengiriman Terus-Menerus:
        Menerapkan pengiriman terus-menerus (Continuous Delivery) atau bahkan pengiriman terus-menerus (Continuous Deployment) untuk secara otomatis mengirimkan perubahan perangkat lunak ke lingkungan produksi.

    Monitoring dan Umpan Balik:
        Memiliki sistem pemantauan dan umpan balik yang kuat untuk memantau kinerja aplikasi secara real-time, mendeteksi masalah dengan cepat, dan memberikan umpan balik kepada tim pengembangan.

Manfaat DevOps:

    Pengiriman Cepat:
        Memungkinkan perubahan perangkat lunak untuk diimplementasikan dengan cepat dan konsisten.

    Kualitas yang Lebih Baik:
        Menerapkan otomatisasi pengujian dan integrasi menyebabkan perangkat lunak yang lebih handal dan berkualitas.

    Kolaborasi Tim yang Lebih Baik:
        Mengatasi kesenjangan antara tim pengembangan dan operasional, meningkatkan kolaborasi, dan mempercepat penyelesaian masalah.

    Efisiensi Operasional:
        Mengurangi manual dan tugas berulang, mengoptimalkan proses, dan meningkatkan efisiensi operasional.

    Resiliensi dan Scalability:
        Meningkatkan daya tahan sistem dan kemampuan untuk mengukur atau menurunkan skala infrastruktur dengan lebih mudah.


Cara melakukan installasi ubuntu server
Sebelum melakukan installasi kita harus mengunduh vmware dan ubuntu server , untuk vmware berikut ini adalah link downloadnya: https://customerconnect.vmware.com/en/downloads/details?downloadGroup=WKST-PLAYER-1750&productId=1377&rPId=111473, 
dan untuk ubuntu server berikut adalah linknya: https://ubuntu.com/download/server
Setelah melakukan pengunduhan maka lakukan installasi,Kemudia buka vmware tersebut,

Langkah pertama setelah membuka aplikasi vmwarenya pada sebelah kanan tinggal klik create a new virtual machine.
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/Pilih%20creata%20a%20new%20virtual%20machine%20sebelah%20kanan.png?raw=true)

Langkah kedua atur kapasitas yang sesuai dengan device dan pilih next.
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/Pilih%20disk%20capacity%20.png?raw=true)

Langkah ketiga pilih guest OS sesuai device dan klik next
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/Pilih%20guest%20os.png?raw=true)

Langkah keempat sesuaikan virtual machine name dan klik next
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/Pilih%20machine%20name.png?raw=true)

Langkah kelima masukan OS direktori dan klik next
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/Sesuaikan%20direktori%20file%20isonya%20.png?raw=true)

Langkah keenam pilih customize hardware
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20customize%20hardware.png?raw=true)

Langkah ketujuh melakukan settingan terhadap vmware dan jangan lupa ubah network dari NAT menjadi BRIDGE
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/sesuaikan%20memory%20core%20dan%20ubah%20network%20menjadi%20bridged.png?raw=true)

Langkah kedelapan pilih bahasa
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20english.png?raw=true)

Langkah kesembilan pilih keyboard
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20done.png?raw=true)

Langkah kesepuluh pilih ubuntu server
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20done%20juga.png?raw=true)

Langkah kesebelas mengubah ip menjadi statis agar bisa digunakan untuk ssh
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20ens33%20untuk%20ubah%20menjadi%20static.png?raw=true)

Langkah keduabelas pilih ipv4
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20edit%20ipv4.png?raw=true)

Langkah ketigabelas pilih manual
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/ubah%20menjadi%20manual.png?raw=true)

Langkah keempatbelas pilih settingan untuk ip
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/settingan%20untuk%20ipv4%20manual.png?raw=true)

Langkah kelimabelas pilih skip 
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/skiip%20saja.png?raw=true)

Langkah keenambelas pilih done untuk proxy 
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20done%20proxy.png?raw=true)

Langkah ketujuhbelas pilih custom storage
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/pilih%20custom%20storage%20layout.png?raw=true)

Langkah kedelapanbelas atur memory cadangan dan utama
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/memory%20cadangan.png?raw=true)
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/memory%20utama.png?raw=true)

Langkah kesembilanbelas isi nama dan nama server beserta password sesuai keinginan
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/atur%20nama%20sesuai%20keinginan.png?raw=true)

Langkah keduapuluh opsional untuk melakukan installan berikut ini
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/opsional%20installan%20pemilihan.png?raw=true)

Langkah keduapuluh satu menunggu sampai proses installasinya selesai
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/tunggu%20prosesnya%20sampai%20selesai.png?raw=true)

Langkah keduapuluh dua login sesuai settingan tadi
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/login%20menggunakan%20settingan%20yang%20sudah%20diisi%20tadi.png?raw=true)

Langkah keduapuluh tiga tampilan setelah login
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/tampilan%20setelah%20login.png?raw=true)

Langkah keduapuluh empat test internet pada server
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/testing%20internet%20pada%20server.png?raw=true)

Langkah keduapuluh lima cek ip pada server untuk melakukan ssh
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/cek%20ip%20untuk%20ssh.png?raw=true)

Langkah keduapuluh enam melakukan ssh pada terminal untuk remote server
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/untuk%20ssh%20remote%20terminal.png?raw=true)

Langkah keduapuluh tujuh melakukan ssh pada terminal untuk remote server
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/untuk%20ssh%20remote%20terminal.png?raw=true)

Langkah keduapuluh delapan melakukan uji coba pembuatan direktori dan file melalui terminal yang sudah terhubung melalui ssh
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/di%20terminal%20sudah%20berhasil%20buat%20beberapa%20dirrektori%20.png?raw=true)

Langkah keduapuluh sembilan melakukan pemeriksaan apakah di server ada atau tidak file yang sudah di buat melalui terminal
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshoots%20Day%201/di%20server%20sudah%20ada%20filenya%20menandakan%20berhasil.png?raw=true)
