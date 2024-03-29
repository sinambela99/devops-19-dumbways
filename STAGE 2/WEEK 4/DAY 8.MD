### WEEK 3 

#### Kubernetes

#### Penjelasan Singkat Mengenai Kubernetes

Kubernetes adalah platform open-source yang dirancang untuk otomatisasi, deployment, scaling, dan operasional aplikasi kontainer. Platform ini memungkinkan manajemen aplikasi yang efisien dalam lingkungan kontainer,menyediakan solusi terintegrasi untuk mengelola siklus hidup aplikasi secara menyeluruh.

#### Cara ringkas dalam melakukan instalasi Nginx dan Ingress pada Kubernetes:

Buat Cluster menggunakan k3s (2 node):
    - Instal k3s pada masing-masing node.
    - Node pertama diinisialisasi sebagai master: `sudo k3s server`
    - Node kedua bergabung sebagai worker: `sudo k3s agent --server https://<master-ip>:6443 token`

Install Ingress Nginx menggunakan Manifest:
    - Unduh manifest Ingress Nginx dari repositori resmi.
    - Terapkan manifest menggunakan kubectl: `kubectl apply -f <ingress-nginx-manifest.yaml>`

Deploy Aplikasi Nginx dan Buat Ingress:
    - Jalankan perintah: `kubectl apply -f nginx.yaml`

Setup Persistent Volume (PV) pada Konfigurasi k3s:
    - Tambahkan konfigurasi Persistent Volume di dalam konfigurasi k3s.

Deploy Aplikasi MongoDB dengan StatefulSet dan PVC:
    - Buat Persistent Volume Claim (PVC) untuk MongoDB.
    - Deploy StatefulSet MongoDB dengan merujuk ke PVC yang telah dibuat.

Buat Database di MongoDB dan Isi Dummy Data:
    - Akses pod MongoDB: `kubectl exec -it <mongodb-pod-name> /bin/bash -n namespace`
    - Masuk ke MongoDB shell: `mongo`
    - Buat database dan isi dummy data.

Konfigurasi Helm Chart untuk Ingress Nginx:

```
apiVersion: v1
kind: Namespace
metadata:
  name: ingress-nginx
---
apiVersion: helm.cattle.io/v1
kind: HelmChart
metadata:
  name: ingress-nginx
  namespace: ingress-nginx
spec:
  repo: https://kubernetes.github.io/ingress-nginx
  chart: ingress-nginx
  targetNamespace: ingress-nginx
  valuesContent: |-
    controller:
      image:
        tag: "v1.8.1"
      service:
        type: LoadBalancer
```

Konfigurasi Nginx dan Ingress untuk Aplikasi Nginx:

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-app
  namespace: appku
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: webserver
        image: nginx:alpine
        ports:
        - containerPort: 80

---

apiVersion: v1
kind: Service
metadata:
  name: nginx-app-service
  namespace: appku
spec:
  selector:
    app: nginx
  ports:
  - port: 80
    targetPort: 80
  type: NodePort

---

apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx-app-ingress
  namespace: appku
  annotations:
    kubernetes.io/ingress.class: "nginx"
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - host: kubeian.studentdumbways.my.id
    http:
      paths:
      - pathType: Prefix
        path: "/"
        backend:
          service:
            name: nginx-app-service
            port: 
              number: 80
```
![Screenshot from 2024-01-19 09-58-54](https://github.com/sinambela99/devops-19-dumbways/assets/80032508/329924bf-c1b5-4a2f-9d3b-d798892eb393)
