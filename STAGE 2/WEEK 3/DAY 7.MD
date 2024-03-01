### WEEK 3 

#### Monitoring Server

Sebelum mengerjakan tugas, mohon persiapkan :
- Akun Github dan buat repository dengan judul "devops19-dumbways-<nama kalian>"
- Gunakan file README.md untuk isi tugas kalian
- Buatlah langkah-langkah pengerjaan tugas beserta dokumentasinya

Docker Images :
[node-exporter](https://hub.docker.com/r/prom/node-exporter)
[Prometheus](https://hub.docker.com/r/prom/prometheus)
[Grafana Dashboard](https://hub.docker.com/r/grafana/grafana)
[Cadvisor](https://github.com/google/cadvisor)

Tasks :
- Setup node-exporter, prometheus dan Grafana menggunakan docker
- install node-exporter di appserver & gateway
- Reverse Proxy
    - bebas ingin menggunakan nginx native / docker
    - Domain
      - exporter-$name.studentdumbways.my.id (node exporter)
      - prom-$name.studentdumbways.my.id (prometheus)
      - monitoring-$name.studentdumbways.my.id (grafana)
    - SSL Cloufflare on / certbot SSL biasa / wildcard SSL diperbolehkan
- Dengan Grafana, buatlah :
    -  Dashboard untuk monitor resource server (CPU, RAM & Disk Usage)  buatlah se freestyle kalian.
    -  Buat dokumentasi tentang rumus `promql` yang kalian gunakan
    -  Buat alerting dengan Contact Point pilihan kalian (discord, telegram, slack dkk)
    -  Untuk alert :
         - Boleh menggunakan alert manager / alert rule dari grafana
         - Ketentuan alerting yang harus dibuat
           - CPU Usage over 20%
           - RAM Usage over 75%
    -  Monitoring specific container
	 - deploy application frontend di app-server
         - monitoring frontend container


#### PENJELASAN SINGKAT MENGENAI MONITORING

Monitoring server adalah proses memantau dan mengumpulkan data kinerja serta status sistem untuk memahami dan mengelola sumber daya dan kesehatan server dengan lebih efektif. 
Grafana, Prometheus, dan Node Exporter adalah alat-alat populer yang digunakan bersama-sama untuk membangun sistem monitoring

#### lANGKAH PENGERJAAN

Cara menjalankan
    - Node Exporter diinstal dan dijalankan pada setiap server yang ingin dimonitor.
    - Prometheus diatur untuk menyaring metrik dari Node Exporter dan menyimpannya dalam penyimpanan time series internal.
    - Grafana dikonfigurasi untuk terhubung ke Prometheus sebagai sumber data.
    - Pengguna membuat dashboard di Grafana dengan memilih metrik yang diambil dari Prometheus.

Hasilnya adalah visualisasi waktu nyata yang memungkinkan tim IT untuk memantau dan menganalisis kinerja sistem secara efektif. 
Melalui dashboard, dapat dilihat tren, pola, dan potensi masalah di lingkungan server. 

1.  Menambahkan konfigurasi Services node exporter pada docker-compose.yaml app server.

![Screenshot from 2024-01-15 03-56-45](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/5d660ee6-5f7e-4b88-8c25-bf300020514f)

2.  Masuk pada server gateway yang nantinya berfungsi sebagai server monitoring

![Screenshot from 2024-01-15 03-55-14](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/1c71be40-4287-4f60-a9a7-dd4382fe191f)

3. Menambahkan Services node exporter, prometheus, serta grafana pada docker-compose.yaml server gateway

![Screenshot from 2024-01-15 03-55-38](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/7da9654d-7279-4dac-a4fa-1d9efaa6a2d6)

![Screenshot from 2024-01-15 03-55-49](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/ca432bda-6c77-462b-baae-9a3bd61ff776)

4. Membuat satu file bernama prometheus.yaml dan melakukan konfigurasi secara global pada gateway server

![Screenshot from 2024-01-15 03-56-05](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/0f1e2a5a-67e2-4619-aa3e-a4daf9ed5020)

5. Setelah melakukan konfigurasi pada kedua server termasuk melakukan reverse proxy,  maka dilanjutkan dengan menjalankan perintah docker compose up -d tiap server.Kemudian masuk pada grafana untuk membuat variabel agar dapat melakukan monitoring CPU, RAM, Monitoring Container pada setiap server

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/f58e9b0b-eff6-4516-a25d-b95aec126c2e)

![Screenshot from 2024-01-15 04-04-33](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/e1ef36c8-9987-4766-92b3-fc3e8f078856)

![image](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/1853e1b2-0cc6-459f-a80c-8e5b0f45ef79)