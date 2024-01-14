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

Ringkasan Proses Ansible & ansible-playbook:

    Menulis Playbook:
        Membuat playbook dalam format YAML dengan mendefinisikan tugas dan peran untuk dilakukan di host.

    Konfigurasi Inventory:
        Menentukan host atau grup host yang akan dielola di file inventory Ansible.

    Menjalankan ansible-playbook:
        Menggunakan perintah ansible-playbook untuk menjalankan playbook, dengan menyertakan file playbook dan file inventory sebagai argumen.

    Komunikasi dengan Host:
        Ansible menggunakan SSH untuk berkomunikasi dengan host tanpa memerlukan instalasi agen pada host.

    Eksekusi Tugas:
        ansible-playbook secara otomatis menjalankan langkah-langkah yang didefinisikan dalam playbook pada host yang ditentukan.

    Monitoring dan Output:
        Ansible memberikan output yang rinci, memberikan informasi tentang tugas yang berhasil atau gagal di setiap host.

    Rekayasa Balik dan Revisi:
        Jika diperlukan, playbook dapat dimodifikasi, dan ansible-playbook dapat dijalankan kembali untuk menerapkan perubahan atau membalik perubahan sebelumnya.
