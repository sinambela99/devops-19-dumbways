### WEEK 2 

#### GITLAB CI
Sebelum mengerjakan tugas, mohon persiapkan :
- Akun Github dan buat repository dengan judul "devops19-dumbways-<nama kalian>"
- Gunakan file README.md untuk isi tugas kalian
- Buatlah langkah-langkah pengerjaan tugas beserta dokumentasinya

Gunakan vm Appserver kalian diskusikan saja ingin menggunakan vm siapa di dalam team

Repository && Reference:
[wget spider](https://www.labnol.org/software/wget-command-examples/28750/)


Tasks :
[ gitlab ]
- Buat akun di gitlab.com
- push SCM kalian dari local-server ke gitlab
- Buatlah beberapa Job menggunakan gitlabci untuk aplikasi kalian
  - Job Frontend
  - Job Backend
  - Untuk script CICD atur flow pengupdate an aplikasi se freestyle kalian dan harus mencangkup
     - Pull dari repository
     - Dockerize/Build aplikasi kita
     - push image ke docker hub
     - Test application
     - pull new image
     - Deploy application


#### Langkah Pengerjaan

1.    Tambahkan id_rsa.pub dari server ke GitLab:
    Sertakan kunci publik id_rsa.pub dari server ke halaman GitLab di bagian "Preferences" -> "SSH Keys" untuk memberikan akses ke repository tanpa perlu menggunakan kata sandi.

 ![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/6554b628-8f27-40ad-b3c8-c5790b98f30a)

2.    Buat Repository baru di GitLab:
    Buat repository baru di GitLab untuk menampung kode sumber aplikasi dan memfasilitasi manajemen proyek secara terpusat.

3.    Masuk ke repository masing-masing app di server:
    Navigasikan ke direktori yang berisi kode sumber aplikasi (Frontend dan Backend) di server untuk memastikan bahwa Anda berada di repositori yang benar.

4.    Tambahkan git remote ke repository GitLab:
    Tambahkan remote GitLab ke repositori lokal di server dengan perintah git remote add origin [URL GitLab] untuk menghubungkan repositori lokal dengan GitLab.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/09ec70cf-018e-49e3-8c1b-0c9e991d31cc)

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/02bdbe10-81a8-4219-867d-6eccdddc09a0)

5.    Masuk ke settings -> CI/CD -> Tambahkan variable:
    Pada halaman repository di GitLab, masuk ke bagian "Settings", kemudian ke "CI/CD" dan tambahkan variabel-variabel yang diperlukan untuk konfigurasi Continuous Integration dan Continuous Deployment (CI/CD).

6.    Masuk ke settings -> Integrations -> Tambahkan Discord Notifier:
    Di halaman repository di GitLab, masuk ke "Settings", kemudian ke "Integrations", dan tambahkan integrasi Discord Notifier untuk menerima notifikasi langsung ke server Discord terkait.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/3f49dc52-c439-4286-8265-623f44cf2c1f)

7.    Masuk pada setiap repository BE & FE:
    Pastikan Anda berada di direktori repository Backend (BE) atau Frontend (FE) pada server sebelum melanjutkan ke langkah berikutnya.


8.    Push ke GitLab:
    Lakukan operasi git push untuk mengirimkan perubahan kode ke repositori GitLab. Pastikan untuk melakukan ini pada setiap repository aplikasi.

9.    Lakukan monitoring pipeline dan tunggu sampai notifikasi pada Discord muncul:
    Amati jalannya proses pipeline pada GitLab dan tunggu hingga notifikasi muncul pada server Discord yang telah diintegrasikan untuk mendapatkan informasi tentang status dan kemajuan proses CI/CD.

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/bc5ed32a-bee4-4038-a36a-2768643a4f81)

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ee48dada-27ea-4a55-b7f2-6dab6e278be9)