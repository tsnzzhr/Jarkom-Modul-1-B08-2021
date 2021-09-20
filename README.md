# Jarkom-Modul-1-B08-2021

## Pembahasan Praktikum Modul-1
1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! <br>
2. Temukan paket dari web-web yang menggunakan basic authentication method!<br>
3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!<br>
4. Temukan paket mysql yang mengandung perintah query select!<br>
5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!<br>
6. Cari username dan password ketika melakukan login ke FTP Server!<br>
7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")<br>
8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!<br>
9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!<br>
10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!<br>
11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! <br>
12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!<br>
13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!<br>
14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!<br>
15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!<br>

## Jawaban
### No 1 : Mencari webserver pada link `ichimarumaru.tech`
Step :
1. Membuka .pcap file
2. Mengetikkan Filter `tcp.stream eq12`
3. Pada Packet HTML Klik Kanan Kemudian Follow -> TCP Stream
4. Dapat Melihat Webserver Pada Rincian

Webserver yang digunakan pada `ichimarumaru.tech` adalah NGINX. Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No1.png)

### No 2
Step : Mencari basic authentication pada packet
1. Mengetik `http.authbasic` pada filter
Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No2.png)

### No 3 : Melaksanakan perintah pada website dengan melakukan login dengan username dan password yang sudah ditentukan.
Step :
1. Mencari username dan password dengan membuka .pcap file.
2. Username dan password ditemukan dengan mengetik filter `http.host == 'basic.ichimarumaru.tech'`
3. Mengerjakan soal sesuai perintah.

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No3-1.png)
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No3-2.png)

### No 4 : Menemukan paket mySQL yang berisi query SELECT
Step :
1. Membuka .pcap file
2. Mengetikkan filter `mysql.query`
3. Memilih satu-satu packet dan melihat detail 'MySQL Protocol' paketnya
4. Menemukan paket yang memiliki keterangan SELECT

Hasil :
#### SELECT DATABASE;
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No4-1.png)
#### SELECT USERNAME FROM USERS;
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No4-2.png)
#### SELECT COUNT( * ) FROM USERS;

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No4-3.png)

### No 5 : Mengikuti perintah pada website `portal.ichimarumaru.tech` dengan melakukan login dengan username dan password yang sudah ditetapkan.
Step :
. Membuka .pcap file
2. Mengetikkan filter `mysql.query`
3. Memilih satu-satu packet dan melihat detail 'MySQL Protocol' paketnya
4. Menemukan paket yang memiliki keterangan INSERT
5. Menemukan username dan password pada keterangan query

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No5-1.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No5-2.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No5-3.png)
