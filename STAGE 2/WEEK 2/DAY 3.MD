### WEEK 2 

#### Docker And Docker Compose

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


Sebelum mengerjakan tugas, mohon persiapkan :
- Akun Github dan buat repository dengan judul "devops19-dumbways-<nama kalian>"
- Gunakan file README.md untuk isi tugas kalian
- Buatlah langkah-langkah pengerjaan tugas beserta dokumentasinya

Gunakan vm Appserver kalian diskusikan saja ingin menggunakan vm siapa di dalam team

Repository && Reference:
**JIka ada File Readme.md di repository app kalian silahkan baca dengan jelas**
[literature Frontend](https://github.com/dumbwaysdev/literature-frontend)
[literature Backend](https://github.com/dumbwaysdev/literature-backend)
[Certbot](https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal)
[PM2 Runtime With Docker](https://pm2.keymetrics.io/docs/usage/docker-pm2-nodejs)
[Cloudflare](https://dash.cloudflare.com/0d0e2eb306a3b985375cf565cb4ce3fc/studentdumbways.my.id/dns/records)
[Wildcard SSL](https://www.bjornjohansen.com/wildcard-certificate-letsencrypt-cloudflare)


Tasks :
[ Docker ]
- Jelasakan langkah-langkah melakukan rebuild server BiznetGio, dan ubah menggunakan os ubuntu22
- Setelah server sudah selesai ter rebuild, buatlah suatu user baru dengan nama **team kalian** lalu implementasikan penggunaan ssh dengan menggunakan **PASSWORD ONLY** tanpa SSH-KEY.
- Buatlah bash script se freestyle mungkin untuk melakukan installasi docker. 
- Deploy aplikasi Web Server, Frontend, Backend, serta Database on top `docker compose`
  - Buat suatu docker compose yang berisi beberapa service kalian
    - Web Server
    - Frontend
    - Backend
    - Database
  - Di dalam docker-compose file buat suatu custom network dengan nama **team kalian**, lalu pasang ke setiap service yang kalian miliki.
  - Deploy database terlebih dahulu menggunakan mysql dengan versi terbaru, dan jangan lupa untuk pasang volume di bagian database.
  - Untuk building image frontend dan backend sebisa mungkin buat dockerized dengan image sekecil mungkin. dan jangan lupa untuk sesuaikan configuration dari backend ke database maupun frontend ke backend sebelum di build menjadi docker images.
  - Untuk Web Server buatlah configurasi reverse-proxy menggunakan nginx on top docker.
    - **SSL CLOUDFLARE OFF!!!**
    - Gunakan docker volume untuk membuat reverse proxy
    - SSL sebisa mungkin gunakan wildcard
    - Untuk DNS bisa sesuaikan seperti contoh di bawah ini
      - Frontend team1.studentdumbways.my.id
      - Backend api.team1.studentdumbways.my.id
  - Push image ke docker registry kalian masing".
- Aplikasi dapat berjalan dengan sesuai seperti melakukan login/register.

#### Langkah Pengerjaan

1. Buatlah user baru dengan nama "team3" untuk memfasilitasi manajemen akses dan pengelolaan keamanan server.

2. Sesuaikan file konfigurasi SSH (sshd_config) untuk memastikan pengaturan keamanan dan preferensi koneksi yang sesuai.

![Screenshot from 2024-03-02 00-00-44](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/2ee9bfa9-012d-4264-8ebd-23141d3f6b75)


3. Setelah mengonfigurasi sshd_config, lakukan restart layanan SSH agar perubahan konfigurasi dapat berlaku tanpa harus me-restart seluruh server.

4. Untuk mempermudah instalasi Docker, buatlah skrip Bash yang dapat dijalankan untuk menginstal Docker dan dependensinya.

![Screenshot from 2024-03-02 00-03-06](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ec9b7d02-2762-4120-ae95-974bbc7f8de9)

5. Berikan izin eksekusi pada skrip instalasi Docker agar dapat dijalankan dengan perintah chmod +x script.sh.

6. Jalankan skrip instalasi Docker untuk menginstal Docker sesuai konfigurasi yang diinginkan.

7. Buat file docker-compose.yaml untuk menyusun dan mengelola konfigurasi kontainer Docker dengan lebih efisien.

8. Sesuaikan file docker-compose.yaml dengan konfigurasi yang diperlukan untuk mengelola dan menyatukan layanan aplikasi.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/3b3f07e0-64ae-4eaa-83f9-e6a08f957f6a)

9. Lakukan git kloning repositori Frontend (FE) dan Backend (BE) untuk mendapatkan kode sumber aplikasi.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/2ffe4ffc-5b7b-4a0c-82fb-c3bb168f4205)

10. Navigasikan ke direktori Frontend dan Backend untuk menambahkan file Dockerfile yang mendefinisikan lingkungan kontainer.

11. Sesuaikan dan konfigurasikan file Dockerfile di masing-masing direktori Frontend dan Backend agar kontainer dapat dibangun dengan benar.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ed014738-54be-4420-b9be-8890700f4932)

12. Persiapkan direktori khusus untuk menyimpan konfigurasi reverse proxy yang memungkinkan pengarahan lalu lintas web.

13. Susun file konfigurasi untuk reverse proxy agar dapat mengarahkan permintaan dengan benar.

14. Tambahkan direktori "certs" untuk menyimpan sertifikat SSL yang diperlukan untuk koneksi aman.

15. Tambahkan entri DNS di Cloudflare untuk mengarahkan nama domain ke alamat IP server.

16. Sesuaikan pengaturan Cloudflare untuk mematikan SSL dan mengonfigurasi tingkat enkripsi di tingkat aplikasi.

17. Buat direktori .secrets dan tambahkan file cloudflare.ini di dalamnya untuk menyimpan informasi kredensial Cloudflare yang diperlukan oleh Certbot.

18. Instalasi Certbot memungkinkan manajemen sertifikat SSL menjadi lebih mudah dan otomatis.

19. Jalankan perintah Certbot untuk memperoleh sertifikat SSL yang diperlukan untuk domain yang ditentukan.

20. Pindahkan sertifikat SSL yang telah dihasilkan oleh Certbot ke direktori "certs" untuk digunakan oleh kontainer Docker.

![Screenshot from 2024-03-02 00-15-42](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/9a0a2a79-f02f-4446-867e-8e3b13439673)

21. Navigasikan ke direktori Frontend dan Backend untuk melanjutkan konfigurasi dan deployment.

22. Gunakan perintah docker build untuk membangun kontainer Docker di masing-masing direktori, mengikuti instruksi yang ada di file Dockerfile.

23. Pastikan kontainer Docker telah berhasil dibangun dengan memeriksa daftar gambar Docker yang tersedia.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/7aeab0d1-05e3-4ef2-855f-90bba66274d5)

24. Navigasikan ke direktori yang berisi file docker-compose.yaml untuk melanjutkan pengaturan dan konfigurasi Docker Compose.

25. Gunakan perintah docker-compose up -d untuk memulai kontainer Docker secara background sesuai konfigurasi yang telah ditentukan.

26. Pastikan status kontainer Docker dapat diakses dan berjalan dengan baik menggunakan perintah docker-compose ps.

27. Dengan membuka aplikasi melalui web browser dan mengakses domain yang telah ditentukan, pastikan bahwa koneksi ke layanan backend dan frontend berjalan dengan sukses.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/25ec8844-b411-48ce-a1de-4b627eff8f52)