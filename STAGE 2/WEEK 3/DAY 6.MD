### WEEK 3 

#### Ansible & ansible-playbook
Sebelum mengerjakan tugas, mohon persiapkan :
- Akun Github dan buat repository dengan judul "devops19-dumbways-<nama kalian>"
- Gunakan file README.md untuk isi tugas kalian
- Buatlah langkah-langkah pengerjaan tugas beserta dokumentasinya

=========================================
**Reference**
[ansible-installation](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html)
[ansible-module](https://docs.ansible.com/ansible/2.9/modules/list_of_all_modules.html)


**Ansible**

[Local]
Buat konfigurasi Ansible & sebisa mungkin maksimalkan penggunaan ansbile untuk melakukan semua setup dan se freestyle kalian 

[ansible]
Buatlah ansible untuk :
 - Membuat user baru, gunakan login ssh key & password
 - Instalasi Docker
 - Deploy application frontend yang sudah kalian gunakan sebelumnya menggunakan ansible.
 - Instalasi Monitoring Server (node exporter, prometheus, grafana)
 - Setup reverse-proxy
 - Generated SSL certificate
 - dan yang paling penting make your own kind ansible script dengan rapi dan jelas. dan sebisa mungkin jangan **MENCONTEK** milik teman lain karena script akan terlihat sekali perbedaan nya di materi ansible ini.
 - simpan script kalian ke dalam github dengan format tree sebagai berikut:
```sh
  Automation  
  |  
  | Terraform
  └─|  └── main.tf 
    Ansible
    ├── ansible.cfg
    ├── lolrandom1.yaml
    ├── group_vars
    │ └── all
    ├── Inventory
    ├── lolrandom2.yaml
    └── lolrandom3.yaml
```

#### Penjelasan Singkat Mengenai IAC

Infrastructure as Code (IAC) adalah pendekatan dalam manajemen dan pengelolaan infrastruktur IT 
dengan menggunakan kode seperti bahasa pemrograman. Dengan IAC, infrastruktur dapat didefinisikan, dikelola, 
dan diotomatisasi dengan cara yang mirip dengan cara mengelola perangkat lunak.

Ansible:

    Deskripsi:
        Ansible adalah alat manajemen konfigurasi dan otomatisasi open-source yang dirancang untuk menyederhanakan tugas-tugas administratif sistem.
        Berfokus pada pendekatan yang deklaratif dan mudah dibaca.

    Cara Kerja:
        Menggunakan model agen-less, artinya tidak memerlukan instalasi agen pada host yang dielola.
        Berkomunikasi dengan host melalui SSH dan mengirimkan modul Ansible untuk menjalankan tugas tertentu.

ansible-playbook:

    Deskripsi:
        ansible-playbook adalah perangkat lunak komando pada Ansible yang digunakan untuk menjalankan playbook.
        Playbook: Berkas YAML yang berisi serangkaian tugas untuk dilakukan pada satu atau beberapa host.

    Cara Kerja:
        Playbook:
            Ditetapkan dalam format YAML yang mudah dibaca.
            Mendefinisikan langkah-langkah tugas dan peran yang akan dijalankan pada host tertentu.
        ansible-playbook Command:
            Menjalankan playbook pada satu atau lebih host sesuai konfigurasi yang diatur di playbook.

#### Langkah Pengerjaan

Ringkasan Proses Ansible & ansible-playbook:

1. Menulis Playbook:

     Membuat playbook dalam format YAML dengan mendefinisikan tugas dan peran untuk dilakukan di host.

2. Konfigurasi Inventory:

    Menentukan host atau grup host yang akan dielola di file inventory Ansible.

3. Menjalankan ansible-playbook:
    
    Menggunakan perintah ansible-playbook untuk menjalankan playbook, dengan menyertakan file playbook dan file inventory sebagai argumen.

![Screenshot from 2024-01-15 04-13-18](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/0aad96ec-dfb4-44ac-9206-b7e234446dce)

4. Komunikasi dengan Host:

    Ansible menggunakan SSH untuk berkomunikasi dengan host tanpa memerlukan instalasi agen pada host.

5. Eksekusi Tugas:

    ansible-playbook secara otomatis menjalankan langkah-langkah yang didefinisikan dalam playbook pada host yang ditentukan.

6. Monitoring dan Output:

    Ansible memberikan output yang rinci, memberikan informasi tentang tugas yang berhasil atau gagal di setiap host.

7. Rekayasa Balik dan Revisi:
    Jika diperlukan, playbook dapat dimodifikasi, dan ansible-playbook dapat dijalankan kembali untuk menerapkan perubahan atau membalik perubahan sebelumnya.

(Hasil Monitoring Menggunakan Grafana)
 ![Screenshot from 2024-01-15 04-16-50](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/2958d34e-322b-4505-bdf1-8518de08021b)

(Notifikasi Grafana pada Discord)
![Screenshot from 2024-01-15 04-17-09](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/246db752-1e1c-40d6-a177-9f81272f6ba6)