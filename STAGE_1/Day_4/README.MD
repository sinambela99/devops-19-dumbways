Teks Editor adalah program komputer yang digunakan untuk membuat, mengedit, dan menyimpan file teks


Membuka teks editor nano
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/Membuka%20teks%20editor%20nano.png?raw=true)

alt 6 untuk copy
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/alt%206%20untuk%20copy.png?raw=true)

alt A untuk memilih kata
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/alt%20A%20%20untuk%20memilih%20kata.png?raw=true)

alt u dan alt e untuk redo undo
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/alt%20u%20dan%20alt%20e%20untuk%20redo%20undo.png?raw=true)

control o untuk save hasil perubahan editor.
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/control%20o%20untuk%20save%20hasil%20perubahan%20editor.png?raw=true)

ctrl A untuk pindah ke awal baris
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/ctrl%20A%20untuk%20pindah%20ke%20awal%20baris.png?raw=true)

ctrl J untukk membuat tulisan yang telah di mark menjadi justify
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/ctrl%20J%20untukk%20membuat%20tulisan%20yang%20telah%20di%20mark%20menjadi%20justify.png?raw=true)

ctrl c untuk cancel
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/ctrl%20c%20untuk%20cancel.png?raw=true)

ctrl e pindah baris ke akhir
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/ctrl%20e%20pindah%20baris%20ke%20akhir.png?raw=true)

ctrl x itu untuk exit sekaligus menyimpan perubahan jika ada
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/ctrl%20x%20itu%20untuk%20exit%20sekaligus%20menyimpan%20perubahan%20jika%20ada.png?raw=true)

ctrl k untuk cut
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/ctrl%20k%20untuk%20cut.png?raw=true)

ctrl u untuk paste
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/text%20editor/ctrl%20u%20untuk%20paste.png?raw=true)


Manipulasi teks pada Linux merujuk pada berbagai operasi yang dapat dilakukan pada data teks, 
seperti pencarian, penggantian, penyaringan, pengurutan, dan manipulasi lainnya. 
Sistem operasi Linux menyediakan sejumlah perintah dan alat bawaan yang kuat untuk melakukan manipulasi teks di lingkungan terminal.

cat: Menampilkan isi file ke layar.
cat nama_file.txt

grep: Mencari pola teks dalam file.
grep "kata_kunci" nama_file.txt

sed: Melakukan manipulasi teks, seperti pencarian dan penggantian.
sed 's/kata_lama/kata_baru/' nama_file.txt

awk: Digunakan untuk pemrosesan teks dan data.
awk '{ print $1 }' nama_file.txt

sort: Mengurutkan baris dalam sebuah file.
sort nama_file.txt

cut: Memotong bagian tertentu dari setiap baris dalam file.
cut -d' ' -f1 nama_file.txt

tr: Mengganti atau menghapus karakter.
tr 'a' 'A' < nama_file.txt

wc: Menghitung jumlah baris, kata, dan karakter.
wc nama_file.txt

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/manipulation%20text/cat.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/manipulation%20text/echo%20untuk%20menambhkan%20teks.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/manipulation%20text/history%7Cgrep%20sudo.png?raw=true)

![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/manipulation%20text/sed.png?raw=true)


Apa itu Network Firewall:

Firewall adalah sistem keamanan jaringan yang memantau dan mengontrol lalu lintas yang masuk dan keluar dari jaringan. Ini dapat membantu melindungi sistem dari ancaman dan serangan.
Fungsi Firewall:

    Filtering: Memeriksa dan memfilter lalu lintas berdasarkan aturan tertentu.

    Logging: Mencatat aktivitas lalu lintas untuk analisis keamanan.

    Prevention: Mencegah akses yang tidak diinginkan atau ancaman terhadap sistem.


ufw (Uncomplicated Firewall) pada Ubuntu:

1 install ufw dan aktifkan ufw
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/ufw/1install%20ufw%20dan%20actifkan%20ufw.png?raw=true)

2 sudo ufw deny untuk melarang semua akses yang masuk
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/ufw/2%20sudo%20ufw%20deny%20untuk%20melarangsemua%20akses%20yang%20masu%20.png?raw=true)

3 verbose cek status
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/ufw/3%20verbose.png?raw=true)

4 mengijinkan semua akses yang masuk
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/ufw/4%20mengijinkan%20semua%20akses%20yang%20masuk.png?raw=true)

5 melarang semua akses untuk keluar
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/ufw/5%20melarang%20semua%20akses%20untuk%20keluar.png?raw=true)

6 mengijinkan semua aksesuntuk keluar
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/ufw/6%20mengijinkan%20semua%20aksesuntuk%20keluar.png?raw=true)

7. Test ssh ufw allow 22
![alt text](https://github.com/sinambela99/DEVOPS-BATCH-19/blob/master/ufw/test%20ssh%20ufw%20allow%2022.png?raw=true)
