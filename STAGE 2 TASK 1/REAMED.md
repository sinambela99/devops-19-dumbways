Langka langkah pembuatan vm pada bizznetgio
1.login
2.pada dashboard sebelah kiri klik compute dan pilih neo lite
3.klik create new
4.isi data sesuai keinginan termasuk versi OSnya dan klik next dan order lakukan pembayaran atau jika ada promo silahkan digunakan
5.setelah server dibuat maka lakukan ssh atau create new ssh

Setelah server dibuat silahkan lakukan command pada linux shell
1. lakukan ssh  pada server menggunakan ssh_key yang sudah di download seperti ssh -i ssh_key_1.pem ianpaulus@103.175.219.100
2. kemudian lakukan update&upgrade pada server
3. kemudian buat user baru seperti adduser
4. kemudian ubah user menjadi keluarga root seperti sudo usermod -aG sudo paul
5. kemudian ubah konfigurasi sshdnya agar bisa melakukan remote ssh pada lokal kita seperti cd /etc/ssh kemudian sudo nano sshd_config.d ubah pubkeyauthen menjadi yes dan password atuh menjadi yes
6. restart sshdnya seperti sudo systemctl restart sshd
7. git clone project frontendnya
8. install nvm, install pm2
9. kemudian masuk pada direktori file frontend kemudian install npm
10. setelah itu pm2 init simple
11. edit ecosysfile
12. pm2 start ecosysfile
13. test aoakah sudah berjalan
14. install nginx
15. cd /etc/nginx
16. sudo chown paul:paul *
17. mkdir apps
18. masuk ke apps kemudian lakukan reverse proxy dan ssl cloudflare di atur pada dashboard ssl
19. sudo nano nginx.conf
20. tambahkan configuration include/etc/nginx/apps/*;
21. cek status configurasinya sudo nginx -t
22. sudo systemctl reload nginx
23. coba buka aplikasi dengan domain

![1_1 remote_server_ssh](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/9709a879-2cd6-4a72-a733-6d45f44fcda5)
![1_2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d6397bbc-87ca-4e7a-8de5-5c998dcf759f)
![1_3 buat user baru](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/500f7926-4fa1-47e1-93c1-b0a63ce0a6ac)
![1_4 sshd](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/525cb62c-3921-4a60-b7a4-38e8606a230e)
![1_5 pengaturan config sshd](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ebd8a36e-ada6-4648-be48-a869b7192778)
![1_6 restart sshd](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/5dfdc1ce-8c0b-4614-98fb-8a3a707b0e3c)
![1_7 update upgrade](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/39a5f556-f813-467e-a16b-3c48425edf04)
![1_8 authotized_keys](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/163e77
![1_9 melakukan git clone](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/aebc24aa-1f00-494d-ab68-5f4403b51b79)
![1_10_2install nvm](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/da3d13db-2ebd-48dc-91ca-b87f2da264e1)
![1_10_2install nvm](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/63deab9d-daa5-47e7-9ba7-64aa3008
![1_11 install pm2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/e4885670-5920-4d88-b436-b2d2a2e38543)
![1_12 npm i pada file clone](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/f85dab4f-8c64-4acb-9286-1918c87c60e1)
![1_13 pm2 init](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/cd92f64f-e24d-44ae-aea3-0f9d2f790db1)
![1_14_2 hasil pengubahan config pada pm2 init](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/195fa213-1126-4d10-9d4a-4f10edcf007b)
![1_14 ubah config untuk pm2](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/3674e696-b24a-4bcb-8150-17ccfc2da909)
![1_15 hasil pm2 setelah di start](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/d04d2a04-7fd9-46ed-861a-d7b0b3f089c7)
![1_16 install nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/cb1dd2b9-92d8-400d-9dcd-3f7417caecd4)
![1_17 masuk pada folder nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/4ad53c43-d55f-4986-830b-611720fadae5)
![1_18 buat direktori apps pada nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ba8f993d-6353-4353-bc8b-77792f568d45)
![1_19 reverse proxy](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/39f0ce1d-66fa-4608-a11c-64da092eb4c0)
![1_20 mengubah config nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/e0d889f3-95f5-4a0d-a28b-5cad5a56f20d)
![1_21 isi konfig](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/0350e00e-73ae-4bfd-a3e9-9f2baa3ebbfb)
![1_22 memeriksa status nginx yang telah diubah konfig](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/1de0cebb-f533-4abb-825c-07887c998312)
![1_23 reload nginx](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/edcfc3e5-473f-4955-b5bb-a0cf10149ca2)
![1_24 hasil reverse proxy ](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/6969cd2a-2a7f-405e-b3fd-438c10a4c5c0)






    
