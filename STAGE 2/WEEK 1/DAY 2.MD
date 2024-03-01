### WEEK 1 

#### DEPLOY APPLICATION BACKEND

Sebelum mengerjakan tugas, mohon persiapkan :
- Akun Github dan buat repository dengan judul "devops19-dumbways-<nama kalian>"
- Gunakan file README.md untuk isi tugas kalian
- Buatlah langkah-langkah pengerjaan tugas beserta dokumentasinya

Buat 1 VM di BitnetGio dengan spesifikasi sebagai berikut :
   - Gateway : 2 CPU, 2 GB RAM, 60 GB Storage 

Repository && Reference:
[Wayshub Backend](https://github.com/dumbwaysdev/wayshub-backend)
[Wayshub Frontend](https://github.com/dumbwaysdev/wayshub-frontend)
[Certbot](https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal)
[PM2](https://www.npmjs.com/package/pm2)
[Cloudflare](https://dash.cloudflare.com/0d0e2eb306a3b985375cf565cb4ce3fc/studentdumbways.my.id/dns/records)

Tasks :
[ Appserver ]
- Jelasakan langkah-langkah pembuatan VM di BiznetGio
- Setelah server sudah terbuat, buatlah suatu user baru lalu implementasikan penggunaan ssh config pada server tersebut.
- Deploy database mysql
	- Setup secure_installation
	- Add password for `root` user
	- Create new user for mysql
	- Create new database
	- Create privileges for new users so they can access the database you created
	- Dont forget to change the mysql bind address on `/etc/mysql/mysql.conf.d/mysqld.cnf`
	- Try to remote your database from your local computer or gateway server

- Deploy aplikasi Wayshub-Backend 
	- Clone wayshub backend application
	- Use Node Version 14
	- Dont forget to change configuration on `wayshub-backend/config/config.json` and then adjust it to your database.
	- Install sequelize-cli 
	- Running migration
	- Deploy apllication on Top PM2

- Deploy aplikasi Wayshub-Frontend
	- Clone wayshub frontend application
	- Dont forget to change configuration on `wayshub-frontend/src/config/api.js` and then adjust it to your backend application.
	- Deploy apllication on Top PM2

- Web Server
	- Frontend (ex. amanda.studentdumbways.my.id)
	- Backend (ex. api.amanda.studentdumbways.my.id)
	- SSL CLOUDFLARE OFF, use certbot for generate certificate. Below is an example of a template for using API keys in Cloudflare using Certbot
	```sh
	dns_cloudflare_email = "demo.dumbways@gmail.com"
	dns_coudflare_api_key = "000safaAGTy21666999LLop20521esWa"
	```

#### Langkah Pengerjaan

##### Proses Pembuatan VM pada Bizznet

1. Login pada dashboard cloud  (https://portal.biznetgio.com/user/login)

2. pada dashboard sebelah kiri klik compute dan pilih neo lite

3. klik create new

4. isi data sesuai keinginan termasuk versi OSnya dan klik next dan order lakukan pembayaran atau jika ada kode promo silahkan digunakan

5. setelah server dibuat maka lakukan ssh atau create new ssh

![Screenshot from 2024-03-01 21-49-53](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/c0686d4d-92a5-4bb7-9169-8ae74f337c63)

##### Setelah server dibuat silahkan lakukan command pada linux shell

1. Lakukan koneksi ke server menggunakan SSH dengan kunci SSH yang sudah diunduh. Perintah contoh: ssh -i ssh_key_1.pem ianpaulus@103.175.219.100. Pastikan akses ke server terjamin.

2. Setelah terkoneksi, lakukan pembaruan dan peningkatan sistem operasi server dengan perintah sudo apt update && sudo apt upgrade.

3. Buat pengguna baru menggunakan perintah adduser untuk meningkatkan keamanan dan manajemen hak akses.

4. Ubah hak akses pengguna baru agar dapat menjalankan perintah sebagai superuser dengan menambahkannya ke grup sudo. Contoh perintah: sudo usermod -aG sudo nama_pengguna.

5. Sesuaikan konfigurasi SSH untuk memungkinkan koneksi SSH jarak jauh, termasuk mengaktifkan autentikasi dengan kunci publik dan sandi.

6. Setelah mengubah konfigurasi SSH, lakukan restart layanan SSH untuk menerapkan perubahan.

7. Lakukan kloning proyek backend dari repositori menggunakan perintah git clone.

8. Instal Node Version Manager (NVM) dan Process Manager 2 (PM2) untuk mengelola versi Node.js dan menjalankan aplikasi Node.js secara terus menerus.

9. Pindah ke direktori proyek backend dan instal semua dependensi Node.js menggunakan npm install.

10. Inisialisasikan PM2 untuk mengelola proses aplikasi backend secara otomatis.

11. Edit file ekosistem (ecosystem.config.js) sesuai kebutuhan proyek.

12. Jalankan aplikasi backend menggunakan PM2 dengan perintah pm2 start ecosystem.config.js.

13. Instal MySQL dan lakukan instalasi aman (secure installation).

14. Buat pengguna baru pada MySQL dengan perintah CREATE USER 'nama_pengguna'@'%' IDENTIFIED BY 'password';.

![buat user baru mysql](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/90d241c6-6320-4f76-9c8a-5d4c19a7c9b8)

15. Berikan hak akses lengkap kepada pengguna baru dengan perintah GRANT ALL PRIVILEGES ON *.* TO 'nama_pengguna'@'%' WITH GRANT OPTION;.

![grant privileges](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d6539c2d-4df8-479f-ba35-958d12a87305)


16. Buka file konfigurasi MySQL di /etc/mysql/mysql.conf.d/mysqld.cnf dengan perintah sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf.

17. Ubah nilai bind-address dan mysqlx-bind-address menjadi 0.0.0.0 untuk mengizinkan koneksi dari luar.

18. Restart layanan MySQL dengan perintah sudo systemctl restart mysql.

19. Sesuaikan konfigurasi pada aplikasi backend untuk terhubung ke database MySQL.

20. Lakukan instalasi dependensi Node.js dengan perintah npm install.

21. Inisialisasikan dan jalankan aplikasi menggunakan PM2 seperti biasa.

22. Lakukan koneksi ke server gateway.

23. Ubah konfigurasi aplikasi frontend untuk terhubung ke backend.

![1 hubungkan backend-frontend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/09adf502-2fa0-4f73-8598-c48fa8e14972)

![2 isi konfigurasi frontend backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/3146fd9f-d838-40a1-a4cf-55c792eda493)

24. Buat konfigurasi reverse backend pada Nginx.

![3 membuat konfigurasi reverser proxy pada backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/6481dbfb-8f3c-4809-9f5e-f4255ac26392)

![4 config reverse backend](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ab5ea2fa-a4d9-449a-b836-7879c5087dfa)

25. Login pada Cloudflare dan buat DNS record baru seperti api.ian.studentdumbways.my.id, pastikan konfigurasinya menjadi "DNS Only".

26. Buat file secret yang berisi informasi akun Cloudflare seperti dns_cloudflare_email dan dns_cloudflare_api_key.

![isi konfigurasi filenya](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d2981335-d3cd-44eb-9f74-8a8cd862ac80)

![5_2 secret untuk membuat certficate cerbot cloudflare](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/f536f225-8993-49d4-854f-010b41111020)


27. Install Certbot dan buat symlink agar dapat diakses secara global dengan perintah sudo ln -s /snap/bin/certbot /usr/bin/certbot.

![5_1 buat file konfigurasi cerbot cloudflare](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/e38dc458-90ff-4a12-8b91-8312b655511d)

![6_1 install certbot](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/26bd5e75-2299-493f-b412-5033ca045f86)

![6_2 biar menjalankan perintah cerbot ](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/561a8243-a5db-4d67-bab3-b6943e882841)

28. Jalankan Certbot dan pilih domain yang ingin dibuatkan sertifikat.

![7 jalan cerbot](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/eb5065d8-c704-4957-8304-765e8e403b2e)

![8 pembuatan certificate](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/17ce1253-f9ee-43e0-a2ca-1e790ed9a141)

29. Terakhir, jalankan aplikasi backend untuk memastikan bahwa konfigurasi dan semua langkah sebelumnya telah berhasil diimplementasikan.


![test hasil 1](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/a4f1d2d9-36eb-4632-885e-a7ef1af322f5)

![test hasil 2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/dc740bff-3efe-429b-bb4b-3c87fd3530cd)

![test hasil 3](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/50c80fd4-25e9-4e80-93dd-526d43c9f0b7)

(Hasil database ketika pengujian aplikasi)
![hasil database](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/7976e83e-7074-481f-b607-101c6ae7318c)
