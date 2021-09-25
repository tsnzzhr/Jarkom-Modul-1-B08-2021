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
1. Membuka .pcap file
2. Mengetikkan filter `mysql.query`
3. Memilih satu-satu packet dan melihat detail 'MySQL Protocol' paketnya
4. Menemukan paket yang memiliki keterangan INSERT
5. Menemukan username dan password pada keterangan query

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No5-1.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No5-2.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No5-3.png)

### No 6 : Cari username dan password ketika login ke FTP Server
Step : 
1. Membuka .pcap file
2. Mengetikkan filter `ftp.request.command == USER || ftp.request.command == PASS`

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No6.png)

### No 7 : Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
Step :
1. Membuka .pcap file
2. Mengetikkan filter `ftp.data.contains 'Real.pdf'`
3. Klik Kanan -> Follow -> TCP Stream
4. Show raw data -> Save as..

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No7-1.png)
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No7-2.png)
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No7-3.png)

### No 8 : Cari paket yang menunjukan pengambilan file dari FTP tersebut
Step : 
1. Membuka .pcap file.
2. Mengetikkan filter `ftp.request.command == RETR`

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No8.png)

### No 9 : Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut
Step :
1. Membuka .pcap file
2. Mengetikkan filter `ftp-data`
3. Pada paket secret.zip klik kanan -> follow -> TCP Stream
4. Save as Raw

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No9-1.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No9-2.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No9-3.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No9-4.png)

### No 10 : Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"
Step :
1. Buka .pcap file
2. Karena data yang dicari mengandung secret.zip maka mengetikkan filter `ftp-data contains secret.zip`
3. Command bash yang ditemukan dari packet secret.zip ditemukan pada file bukanapaapa.txt
4. Masukka filter baru `ftp-data`
5. Cari packet yang memuat 'bukanapaapa.txt'
6. Setelah menemukan buka line-based text data pada informasi paket dan cari passwordnya
7. Password ditemukan yaitu; d1b1langbukanapaapajugagapercaya

Hasil :
![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No10-1.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No10-2.png)

![alt text](https://github.com/tsnzzhr/Jarkom-Modul-1-B08-2021/blob/main/img/No10-3.png)

### No 11 : Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
Step : Mencari basic authentication pada packet
1. Mengetik `src port 80` pada filter
![img](img/No11.png)

### No 12 : Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
Step : Mencari basic authentication pada packet
1. Mengetik `src port 21` pada filter
![img](img/No12.png)

### No 13 : Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
Step : Mencari basic authentication pada packet
1. Mengetik `dst port 443` pada filter
![img](img/No13.png)

### No 14 : Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
Step :
1. Mengetik `dst host kemenag.go.id` pada filter
 ![img](img/No14.png)

### No 15 : Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
Step :
1. IP dapat dilihat terlebih dahulu di command prompt menggunakan ipconfig
2. Mengetik `src host 192.168.73.79`
![img](img/No15.png)


### Kendala
- Mungkin kendala pada wifi



