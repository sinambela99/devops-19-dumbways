VCS (Version Control System) Git adalah alat yang membantu kita melacak dan mengelola perubahan pada proyek perangkat lunak. 
Ini seperti "catatan perubahan" yang memungkinkan tim pengembang bekerja bersama dan menyimpan versi perangkat lunak pada setiap langkah.

Apa itu VCS Git secara mudah dipahami?
Bayangkan jika kamu dan teman-teman sedang membuat lukisan besar bersama-sama. Git ini seperti kamera yang merekam setiap langkah yang kamu ambil pada lukisan. 
Jadi, jika ada yang ingin kembali melihat atau mengubah bagian tertentu, kalian dapat dengan mudah melihat catatan-catatan tersebut. 
Ini membuat bekerja bersama menjadi lebih terorganisir dan memudahkan untuk berkolaborasi dalam proyek pengembangan perangkat lunak.


![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshots%20Day%203/image.png?raw=true)


Contoh beberapa command dari git:


git init

    Inisialisasi repositori Git pada proyek baru. (git init)

git clone

    Mengunduh repositori Git yang sudah ada dari remote repository. (git clone <url-repository>)

git add

    Menambahkan perubahan ke staging area (daftar perubahan yang akan di-commit).(git add <nama-file>)

    Untuk menambahkan semua perubahan.(git add .)

git commit

    Merealisasikan perubahan yang sudah di-staging ke dalam repositori. (git commit -m "Pesan commit disini")

git status

    Menampilkan status perubahan di working directory dan staging area. (git status)

git log

    Menampilkan riwayat commit.(git log)

git pull

    Mengambil perubahan terbaru dari remote repository. (git pull origin <branch>)

git push

    Mengirim perubahan lokal ke remote repository.(git push origin <branch>)

git branch

  Menampilkan daftar branch di repositori.(git branch)

  Untuk membuat branch baru.(git branch <nama-branch>)

git checkout

    Berpindah ke branch atau commit tertentu. (git checkout <nama-branch atau commit>)

git merge

    Menggabungkan perubahan dari satu branch ke branch lainnya. (git merge <nama-branch>)

git remote

    Menampilkan remote repository yang terhubung.(git remote -v)

git fetch

    Mengambil semua branch dan perubahan dari remote repository, namun tidak menggabungkannya dengan branch yang sedang aktif.(git fetch)

git reset

    Menghapus perubahan dari staging area.(git reset)

    Mengembalikan perubahan ke commit sebelumnya.(git reset --hard HEAD^)

    Mengembalikan perubahan ke commit tertentu.(git reset --hard <commit-hash>)

git tag

    Menandai commit tertentu dengan tag tertentu.(git tag -a <tag-name> -m "Pesan tag")

git remote remove

    Menghapus remote repository yang sudah terhubung. (git remote remove <nama-remote>)

git branch -d

    Menghapus branch lokal. (git branch -d <nama-branch>)

    Menghapus branch lokal tanpa mengecek status. (git branch -D <nama-branch>)

git revert

    Membuat commit baru yang membatalkan perubahan commit sebelumnya. (git revert <commit-hash>)

git clean

    Menghapus file yang tidak di-track oleh Git dari working directory. (git clean -n  # Menampilkan file yang akan dihapus)
    git clean -f  # Menghapus file yang tidak di-track

git rebase

    Mengubah sejarah commit dengan memindahkan commit ke tempat lain. (git rebase <nama-branch>)
    Menyatukan commit dengan menggunakan rebase interaktif. (git rebase -i <commit-hash>)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshots%20Day%203/Screenshot%20from%202023-11-24%2000-30-10.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshots%20Day%203/Screenshot%20from%202023-11-24%2000-30-18.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshots%20Day%203/Screenshot%20from%202023-11-24%2000-30-30.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshots%20Day%203/Screenshot%20from%202023-11-24%2000-31-24.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshots%20Day%203/Screenshot%20from%202023-11-24%2000-32-24.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/Screenshots%20Day%203/Screenshot%20from%202023-11-24%2000-36-45.png?raw=true)
