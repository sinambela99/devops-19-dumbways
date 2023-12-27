Langka langkah pembuatan vm pada bizznetgio 1.login 2.pada dashboard sebelah kiri klik compute dan pilih neo lite 3.klik create new 4.isi data sesuai keinginan termasuk versi OSnya dan klik next dan order lakukan pembayaran atau jika ada promo silahkan digunakan 5.setelah server dibuat maka lakukan ssh atau create new ssh

Setelah server dibuat silahkan lakukan command pada linux shell

1. lakukan ssh pada server menggunakan ssh_key yang sudah di download seperti ssh -i ssh_key_1.pem ianpaulus@103.175.219.100
2. kemudian lakukan update&upgrade pada server
3. kemudian buat user baru seperti adduser
4. kemudian ubah user menjadi keluarga root seperti sudo usermod -aG sudo paul
5. kemudian ubah konfigurasi sshdnya agar bisa melakukan remote ssh pada lokal kita seperti cd /etc/ssh kemudian sudo nano sshd_config.d ubah pubkeyauthen menjadi yes dan password atuh menjadi yes
6. restart sshdnya seperti sudo systemctl restart sshd
7. git clone project backendnya
8. install nvm, install pm2
9. kemudian masuk pada direktori file frontend kemudian install npm
10. setelah itu pm2 init simple
11. edit ecosysfile
12. pm2 start ecosysfile
13. install mysql dan lakukan secure installation
14. buat user baru pada mysql CREATE USER 'nama_pengguna'@'%' IDENTIFIED BY 'password';
15.  GRANT ALL PRIVILEGES ON *.* TO 'robo'@'%' with GRANT OPTION;
16.  kemudian ubah konfigurasi pada backend untuk database
17.  kemudian npm install
18.  kemudian lakukan pm2 seperti biasa
19.  kemudian masuk pada gateway
20.  ubah konfigurasi frontend ke bakcend agar dapat terhubung
21.  kemudian buat konfigurasi reverse backend
22.  kemudian buat file secret
23.  setelah itu jalankan cerbot
24.  kemudian jalankan aplikasi

    
![1 hubungkan backend-frontend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/09adf502-2fa0-4f73-8598-c48fa8e14972)
![2 isi konfigurasi frontend backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/3146fd9f-d838-40a1-a4cf-55c792eda493)
![3 membuat konfigurasi reverser proxy pada backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/9fa2398
![4 config reverse backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/f874190c-6dee-4435-9749-7d1dadde1e56)
f-25b5-4eb8-879a-dcfea7a1066a)
![5_1 buat file konfigurasi cerbot cloudflare](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/a45b585f-710e-420a-9b5
