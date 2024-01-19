```
Kubernetes adalah platform open-source untuk otomatisasi, deployment, scaling, dan operasional aplikasi kontainer. Ini memungkinkan manajemen aplikasi yang efisien dalam lingkungan kontainer.
```

```
Cara ringkas dalam melakukan install nginx dan ingress

Buat Cluster menggunakan k3s (2 node):
    Instal k3s pada masing-masing node.
    Node pertama diinisialisasi sebagai master: sudo k3s server
    Node kedua bergabung sebagai worker: sudo k3s agent --server https://<master-ip>:6443 token

Install Ingress Nginx menggunakan Manifest:
    Unduh manifest Ingress Nginx dari repositori resmi.
    Terapkan manifest menggunakan kubectl: kubectl apply -f <ingress-nginx-manifest.yaml>

Deploy Aplikasi Nginx dan Buat Ingress:
    lakukan kubectl apply -f nginx.yaml

Setup Persistent Volume (PV) pada Konfigurasi k3s:
    Tambahkan konfigurasi Persistent Volume di dalam k3s config.

Deploy Aplikasi MongoDB dengan StatefulSet dan PVC:
    Buat Persistent Volume Claim (PVC) untuk MongoDB.
    Deploy StatefulSet MongoDB dengan merujuk ke PVC yang telah dibuat.

Buat Database di MongoDB dan Isi Dummy Data:
    Akses pod MongoDB: kubectl exec -it <mongodb-pod-name>  /bin/bash -n namespace
    Masuk ke MongoDB shell: mongo
    Buat database dan isi dummy data.
```
