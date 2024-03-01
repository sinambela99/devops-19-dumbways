### WEEK 2 

#### Jenkins
Sebelum mengerjakan tugas, mohon persiapkan :
- Akun Github dan buat repository dengan judul "devops19-dumbways-<nama kalian>"
- Gunakan file README.md untuk isi tugas kalian
- Buatlah langkah-langkah pengerjaan tugas beserta dokumentasinya

Gunakan vm Appserver kalian diskusikan saja ingin menggunakan vm siapa di dalam team

Repository && Reference:
[Certbot](https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal)
[PM2 Runtime With Docker](https://pm2.keymetrics.io/docs/usage/docker-pm2-nodejs)
[Cloudflare](https://dash.cloudflare.com/0d0e2eb306a3b985375cf565cb4ce3fc/studentdumbways.my.id/dns/records)
[Wildcard SSL](https://www.bjornjohansen.com/wildcard-certificate-letsencrypt-cloudflare)
[Jenkins Installation](https://www.jenkins.io/doc/book/installing/)
[Jenkins Reverse proxy](https://www.jenkins.io/doc/book/system-administration/reverse-proxy-configuration-with-jenkins/reverse-proxy-configuration-nginx)
[wget spider](https://www.labnol.org/software/wget-command-examples/28750/)


Tasks :
[ Jenkins ]
- Jelasakan langkah-langkah melakukan rebuild server BiznetGio, dan ubah menggunakan os ubuntu22
- Installasi Jenkins on top Docker or native
- Setup SSH-KEY di local server jenkins kalian, agar dapat login ke dalam server menggunakan SSH-KEY 
- Reverse Proxy Jenkins
  - gunakan domain ex. pipeline-team4.studentdumbways.my.id
  - reverse proxy sesuaikan dengan ketentuan yang ada di dalam Jenkins documentation
- Buatlah beberapa Job untuk aplikasi kalian
  - Job Frontend
  - Job Backend
  - Untuk script CICD atur flow pengupdate an aplikasi se freestyle kalian dan harus mencangkup
     - Pull dari repository
     - Dockerize/Build aplikasi kita
     - Test application
     - Deploy aplikasi on top Docker
     - Push ke Docker Hub
- Auto trigger setiap ada perubahan di SCM
- Buat job notification ke discord

#### Langkah Pengerjaan

1.    Rebuild server gateway untuk Jenkins menjadi OS Ubuntu 22.04:
    Perbaharui dan tingkatkan sistem operasi server gateway yang akan digunakan untuk Jenkins ke versi Ubuntu 22.04 untuk memastikan kestabilan dan keamanan.

2.    Membuat user bernama team3:
    Buat pengguna baru dengan nama "team3" untuk memfasilitasi manajemen akses dan pengelolaan keamanan server.

3.    Konfigurasi sshd_config:
    Sesuaikan konfigurasi pada file sshd_config agar mendukung koneksi SSH jarak jauh dengan autentikasi kunci publik dan sandi.

![Screenshot from 2024-03-02 00-43-19](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/93a40216-c977-4f61-943d-e509f7725f69)

4.    Restart sshd:
    Setelah mengonfigurasi sshd_config, lakukan restart layanan SSH untuk menerapkan perubahan konfigurasi.

5.    Buat bash script instalasi Docker:
    Buatlah skrip Bash untuk mengotomatisasi proses instalasi Docker pada server gateway.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/af448a11-8dcc-4ea0-b947-0b4d4237ca80)

6.    Ubah permission file script:
    Berikan izin eksekusi pada skrip instalasi Docker agar dapat dijalankan dengan perintah chmod +x script.sh.

7.    Jalankan script.sh:
    Jalankan skrip instalasi Docker untuk memulai instalasi Docker dan dependensinya sesuai dengan konfigurasi yang diinginkan.

8.    Buat file docker-compose.yaml:
    Persiapkan file docker-compose.yaml yang akan digunakan untuk menyusun dan mengelola konfigurasi kontainer Docker.

9.    Lakukan konfigurasi docker-compose.yaml:
    Atur file docker-compose.yaml sesuai dengan spesifikasi kebutuhan proyek dan aplikasi.

  ![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ff5b3dfc-75ab-4987-accf-082bfcd12d71)

10.    Add direktori reverse proxy:
    Tambahkan direktori khusus untuk menyimpan konfigurasi reverse proxy yang nantinya akan digunakan oleh Jenkins.

11.    Add file konfigurasi reverse proxy di dalam direktori yang baru dibuat:
    Susun file konfigurasi reverse proxy di dalam direktori yang telah dibuat untuk mengarahkan lalu lintas ke Jenkins.

12.    Konfigurasi file reverse proxy:
    Atur file konfigurasi reverse proxy sesuai kebutuhan untuk memastikan pengalihan lalu lintas yang tepat.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ef925235-342b-4f18-8405-584bc11bb6db)

13.    Add direktori certs:
    Persiapkan direktori "certs" untuk menyimpan sertifikat SSL yang diperlukan untuk koneksi aman.

14.    Add DNS domain Jenkins pada Cloudflare:
    Tambahkan entri DNS pada Cloudflare untuk mengarahkan domain Jenkins ke alamat IP server.

15.    Konfigurasi SSL off pada Cloudflare:
    Sesuaikan pengaturan Cloudflare untuk mematikan SSL dan mengonfigurasi tingkat enkripsi di tingkat aplikasi.

16.    Buat folder .secrets dan tambahkan file konfigurasi ssl cloudflare.ini di dalam direktori .secrets:
    Buat direktori .secrets dan tambahkan file cloudflare.ini di dalamnya untuk menyimpan informasi kredensial Cloudflare yang diperlukan oleh Certbot.

17.    Instalasi Certbot:
    Instalasi Certbot memungkinkan manajemen sertifikat SSL menjadi lebih mudah dan otomatis.

18.    Lakukan perintah sudo certbot certonly:
    Jalankan perintah Certbot untuk memperoleh sertifikat SSL yang diperlukan untuk domain Jenkins yang telah ditentukan.

19.    Pindahkan hasil yang telah di-generate ke direktori certs:
    Pindahkan sertifikat SSL yang telah dihasilkan oleh Certbot ke direktori "certs" untuk digunakan oleh kontainer Docker.

20.    Jalankan perintah docker compose up -d untuk melakukan instalasi pada Jenkins:
    Mulai instalasi Jenkins dengan menjalankan perintah Docker Compose secara background.

21.    Cek status dengan docker ps:
    Periksa status kontainer Docker untuk memastikan bahwa Jenkins telah berhasil diinstal dan berjalan.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/48fb38c7-2325-49e6-9a3c-c47f69a57f69)

22.    Docker compose down:
    Jika diperlukan, hentikan Jenkins dengan menjalankan perintah docker-compose down.

23.    Ubah permision folder jenkins_home (chmod 757):
    Sesuaikan izin pada folder jenkins_home agar Jenkins dapat mengakses dan menyimpan data secara tepat.

24.    Docker compose up -d:
    Mulai kembali Jenkins dengan menjalankan perintah docker-compose up -d.

25.    Cek status dengan docker ps:
    Periksa kembali status kontainer Docker untuk memastikan bahwa Jenkins telah berhasil dijalankan kembali.

26.    Masuk Jenkins melalui Web Browser dengan domain yang sudah dibuat:
    Buka aplikasi Jenkins melalui web browser dengan mengakses domain Jenkins yang telah ditentukan.

27.    Masukkan initial admin password untuk memulai instalasi Jenkins:
    Sambungkan ke Jenkins dengan memasukkan initial admin password yang diperlukan untuk menyelesaikan proses instalasi.

28.    Install plugin suggested:
    Instal plugin yang direkomendasikan oleh Jenkins untuk mendukung fungsi dan fitur yang optimal.

29.    Membuat user dengan nama team3:
    Buat pengguna baru dalam Jenkins dengan nama "team3" untuk manajemen dan pelacakan akses yang lebih baik.

30.    Jika sudah masuk, instalasi lagi plugin yang dibutuhkan seperti generic webhook, discord notifier, SSH agent, SSH server:
    Sesuaikan instalasi plugin dengan kebutuhan proyek, termasuk yang diperlukan untuk integrasi dengan webhook, Discord, dan manajemen kunci SSH.

31.    Tambahkan sebuah credential dengan menggunakan username dan private key dari server appserver:
    Tambahkan kredensial dengan menyertakan nama pengguna dan kunci privat yang diperlukan untuk koneksi ke server appserver.

32.   Buatlah sebuah folder bernama literature-apps yang nantinya akan diisi dengan job dari backend dan frontend:
    Persiapkan folder "literature-apps" sebagai wadah untuk menyimpan pekerjaan (jobs) yang terkait dengan backend dan frontend.

33.   Buat sebuah pipeline job dengan menggunakan pipeline from scm dan arahkan ke url dari repository kita, arahkan ke credential yang sudah dibuat. Jangan lupa untuk check list GitHub hook trigger for GITScm polling:
    Buat pekerjaan pipeline menggunakan sumber kode dari sistem kontrol versi, arahkan ke repositori yang sesuai, dan pastikan untuk mengaktifkan pemicu GitHub hook untuk polling GITScm.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/000ef818-7dd4-45d3-bdfe-66816eece4d7)

34.    Masuk pada server dan masuk ke direktori file FE & BE:
    Navigasikan ke server dan ke dalam direktori yang berisi file backend (BE) dan frontend (FE).

35.    Tambahkan file bernama Jenkinsfile dan konfigurasikan:
    Tambahkan file Jenkinsfile di masing-masing direktori dan konfigurasikan agar Jenkins dapat menjalankan langkah-langkah yang diperlukan untuk build dan deploy aplikasi.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/8f136cb6-d11e-4ccd-a30c-d7253aea6cdc)

36.    Tambahkan SSH Key public dari appserver ke GitHub:
    Tambahkan kunci publik SSH dari server appserver ke akun GitHub untuk memungkinkan Jenkins mengakses repositori.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/dcaed349-d754-4cc3-9fbf-d09c7e6e1cb1)

37.    Tambahkan sebuah webhook di GitHub dengan url dari Jenkins:
    Aktifkan webhook di GitHub dengan menambahkan URL Jenkins untuk memberi tahu Jenkins setiap kali ada perubahan di repositori.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/a565c203-dcff-4365-80bc-3ed600ca4c3a)

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/48c33598-799e-4e0c-b097-d2964dea2fb3)