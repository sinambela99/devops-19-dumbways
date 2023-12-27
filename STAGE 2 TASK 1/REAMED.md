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
