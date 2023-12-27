Langka langkah pembuatan vm pada bizznetgio 

1. login 
2. pada dashboard sebelah kiri klik compute dan pilih neo lite 
3. klik create new 
4. isi data sesuai keinginan termasuk versi OSnya dan klik next dan order lakukan pembayaran atau jika ada promo silahkan digunakan 
5. setelah server dibuat maka lakukan ssh atau create new ssh

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
16.  sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
17.  ubah bind-addres dan mysqlx-bind-address menjadi 0.0.0.0
18.  sudo systemctl restart mysql
19.  kemudian ubah konfigurasi pada backend untuk database
20.  kemudian npm install
21.  kemudian lakukan pm2 seperti biasa
22.  kemudian masuk pada servere gateway
23.  ubah konfigurasi frontend ke bakcend agar dapat terhubung
24.  kemudian buat konfigurasi reverse backend
25.  login pada cloudflare dan buat dns record yang baru seperti api.ian.studentdumbways.my.id jangan lupa untuk membuat konfigurasnya menjadi dns only
26.  kemudian buat file secret yang isinya dns_cloudflare_email serta dns_cloudflare_api_key
27.  install certbot dan jalankan perintah sudo ln -s /snap/bin/certbot /usr/bin/certbot agar certbot dapat diakses secara global
28.  setelah itu jalankan certbot dan pilih domain yang mau dibuat sertifikat
29.  kemudian jalankan aplikasi

```sql
GRANT ALL PRIVILEGES ON *.* TO 'robo'@'%' with GRANT OPTION;
```

    
![1 hubungkan backend-frontend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/09adf502-2fa0-4f73-8598-c48fa8e14972)

![2 isi konfigurasi frontend backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/3146fd9f-d838-40a1-a4cf-55c792eda493)

![3 membuat konfigurasi reverser proxy pada backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/6481dbfb-8f3c-4809-9f5e-f4255ac26392)

![4 config reverse backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ab5ea2fa-a4d9-449a-b836-7879c5087dfa)

![5_1 buat file konfigurasi cerbot cloudflare](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/e38dc458-90ff-4a12-8b91-8312b655511d)

![5_2 secret untuk membuat certficate cerbot cloudflare](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/f536f225-8993-49d4-854f-010b41111020)

![6_1 install certbot](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/26bd5e75-2299-493f-b412-5033ca045f86)

![6_2 biar menjalankan perintah cerbot ](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/561a8243-a5db-4d67-bab3-b6943e882841)

![7 jalan cerbot](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/eb5065d8-c704-4957-8304-765e8e403b2e)

![8 pembuatan certificate](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/17ce1253-f9ee-43e0-a2ca-1e790ed9a141)

![buat user baru mysql](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/90d241c6-6320-4f76-9c8a-5d4c19a7c9b8)

![cek database](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/28f4b721-df0d-48c4-8916-e3077a88cb5a)

![grant privileges](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d6539c2d-4df8-479f-ba35-958d12a87305)

![hasil database](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/7976e83e-7074-481f-b607-101c6ae7318c)

![isi konfigurasi filenya](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d2981335-d3cd-44eb-9f74-8a8cd862ac80)

![restart database](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/91c090bb-9e36-4ac5-92fe-5e2214fdf8c1)

![test hasil 1](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/a4f1d2d9-36eb-4632-885e-a7ef1af322f5)

![test hasil 2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/dc740bff-3efe-429b-bb4b-3c87fd3530cd)

![test hasil 3](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/50c80fd4-25e9-4e80-93dd-526d43c9f0b7)

