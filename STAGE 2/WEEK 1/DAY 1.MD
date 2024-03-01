### WEEK 1 

#### DEPLOY APPLICATION FRONTEND


Sebelum mengerjakan tugas, mohon persiapkan :
- Akun Github dan buat repository dengan judul "devops19-dumbways-<nama kalian>"
- Gunakan file README.md untuk isi tugas kalian
- Buatlah langkah-langkah pengerjaan tugas beserta dokumentasinya

Buat 1 VM di BitnetGio dengan spesifikasi sebagai berikut :
   - Gateway : 1 CPU, 1 GB RAM, 60 GB Storage 

Repository :
[Wayshub Frontend](https://github.com/dumbwaysdev/wayshub-frontend)

Tasks :
[ Appserver ]
- Jelasakan langkah-langkah pembuatan VM di BiznetGio
- Setelah server sudah terbuat, buatlah suatu user baru lalu implementasikan penggunaan ssh-key pada server tersebut.
- Deploy aplikasi Wayshub-Frontend menggunakan nodejs versi 14.x
- Clone repository Wayshub frontend lalu deploy aplikasinya menggunakan PM2
- Install nginx
- Buatlah reverse proxy dan gunakan domain dengan nama kalian (ex. amanda.studentdumbways.my.id)


#### Langkah Pengerjaan

##### Proses Pembuatan VM pada Bizznet

1. Login pada dashboard cloud  (https://portal.biznetgio.com/user/login)

2. pada dashboard sebelah kiri klik compute dan pilih neo lite

3. klik create new

4. isi data sesuai keinginan termasuk versi OSnya dan klik next dan order lakukan pembayaran atau jika ada kode promo silahkan digunakan

5. setelah server dibuat maka lakukan ssh atau create new ssh

![Screenshot from 2024-03-01 21-49-53](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/c0686d4d-92a5-4bb7-9169-8ae74f337c63)

##### Setelah server dibuat silahkan lakukan command pada linux shell

1. Lakukan koneksi ke server menggunakan SSH dengan menggunakan kunci SSH yang sudah diunduh. Contoh perintah: ssh -i ssh_key_1.pem ianpaulus@103.175.219.100. Ini memastikan keamanan akses ke server.

![1_1 remote_server_ssh](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/9709a879-2cd6-4a72-a733-6d45f44fcda5)

![1_2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d6397bbc-87ca-4e7a-8de5-5c998dcf759f)

2. Setelah terkoneksi, lakukan proses pembaruan dan peningkatan sistem operasi server untuk memastikan bahwa semua paket dan dependensi terbaru telah diinstal seperti perintah update&upgrade pada server

3. Buat pengguna baru dengan perintah adduser untuk meningkatkan keamanan dan mengelola hak akses dengan lebih baik.

![1_3 buat user baru](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/500f7926-4fa1-47e1-93c1-b0a63ce0a6ac)

4. Ubah hak akses pengguna yang baru dibuat agar dapat menjalankan perintah sebagai superuser dengan menambahkannya ke grup sudo. Contoh perintah: sudo usermod -aG sudo nama_pengguna.

![1_4 sshd](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/525cb62c-3921-4a60-b7a4-38e8606a230e)

5. Sesuaikan konfigurasi SSH untuk memungkinkan koneksi SSH jarak jauh dari mesin lokal dengan mengedit file konfigurasi di direktori /etc/ssh. Pastikan autentikasi menggunakan kunci publik (PubkeyAuthentication) dan sandi (PasswordAuthentication) diaktifkan (yes).

![1_5 pengaturan config sshd](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ebd8a36e-ada6-4648-be48-a869b7192778)

6. Setelah mengubah konfigurasi SSH, lakukan restart layanan SSH untuk menerapkan perubahan.

![1_6 restart sshd](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/5dfdc1ce-8c0b-4614-98fb-8a3a707b0e3c)

7. Lakukan kloning proyek frontend dari repositori menggunakan perintah git clone.

![1_7 update upgrade](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/39a5f556-f813-467e-a16b-3c48425edf04)

![1_9 melakukan git clone](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/aebc24aa-1f00-494d-ab68-5f4403b51b79)

8. Instal Node Version Manager (NVM) dan Process Manager 2 (PM2) untuk mengelola versi Node.js dan menjalankan aplikasi Node.js secara terus menerus.

![1_10_2install nvm](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/da3d13db-2ebd-48dc-91ca-b87f2da264e1)

![1_11 install pm2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/e4885670-5920-4d88-b436-b2d2a2e38543)


9. Pindah ke direktori proyek frontend dan instal semua dependensi Node.js menggunakan npm install.

![1_12 npm i pada file clone](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/f85dab4f-8c64-4acb-9286-1918c87c60e1)


10. Inisialisasikan PM2 untuk mengelola proses aplikasi frontend secara otomatis.

![1_13 pm2 init](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/cd92f64f-e24d-44ae-aea3-0f9d2f790db1)

11. Edit file ekosistem (ecosystem.config.js) sesuai kebutuhan proyek.

![1_14_2 hasil pengubahan config pada pm2 init](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/195fa213-1126-4d10-9d4a-4f10edcf007b)

![1_14 ubah config untuk pm2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/3674e696-b24a-4bcb-8150-17ccfc2da909)

12. Jalankan aplikasi frontend menggunakan PM2 dengan perintah pm2 start ecosystem.config.js.

13. Lakukan uji coba untuk memastikan bahwa aplikasi berjalan dengan baik.

![1_15 hasil pm2 setelah di start](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d04d2a04-7fd9-46ed-861a-d7b0b3f089c7)

14. Instal Nginx sebagai web server untuk melayani aplikasi frontend.

![1_16 install nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/cb1dd2b9-92d8-400d-9dcd-3f7417caecd4)

15. Pindah ke direktori konfigurasi Nginx dan atur kepemilikan file untuk memastikan hak akses yang benar seperti cd /etc/nginx

![1_17 masuk pada folder nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/4ad53c43-d55f-4986-830b-611720fadae5)

16. sudo chown paul:paul *

17. Buat direktori 'apps' di dalam direktori Nginx untuk menyimpan konfigurasi aplikasi.

![1_18 buat direktori apps pada nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ba8f993d-6353-4353-bc8b-77792f568d45)
18. Masuk ke direktori 'apps' dan konfigurasikan reverse proxy dan SSL untuk aplikasi, pengaturan ini biasanya diatur pada dashboard Cloudflare SSL.

![1_19 reverse proxy](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/39f0ce1d-66fa-4608-a11c-64da092eb4c0)

19. Buka file konfigurasi Nginx (nginx.conf) dan tambahkan konfigurasi untuk menyertakan semua konfigurasi aplikasi.

![1_20 mengubah config nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/e0d889f3-95f5-4a0d-a28b-5cad5a56f20d)


![1_21 isi konfig](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/0350e00e-73ae-4bfd-a3e9-9f2baa3ebbfb)

20.Verifikasi status konfigurasi Nginx untuk memastikan tidak ada kesalahan sintaks seperti sudo nginx -t

![1_22 memeriksa status nginx yang telah diubah konfig](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/1de0cebb-f533-4abb-825c-07887c998312)

21. Reload Nginx untuk menerapkan perubahan konfigurasi seperti sudo systemctl reload nginx

![1_23 reload nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/edcfc3e5-473f-4955-b5bb-a0cf10149ca2)

22. Setelah semua konfigurasi diterapkan, coba buka aplikasi menggunakan domain yang telah diatur pada langkah-langkah sebelumnya.

![1_24 hasil reverse proxy ](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/6969cd2a-2a7f-405e-b3fd-438c10a4c5c0)