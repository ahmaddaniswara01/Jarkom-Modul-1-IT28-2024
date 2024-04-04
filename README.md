# Jarkom-Modul-1-IT28-2024

## Anggota Kelompok IT28

| Nama  | NRP | 
| ----------- | ----------- |
| Angella Christie | 5027221047 | 
| Ahmad Fauzan Daniswara | 5027221057 | 

## Daftar Soal yang Dikerjakan

- [ATM or ATP or FTP](#ATM-or-ATP-or-FTP)
  - [Deskripsi soal ATM or ATP or FTP](#Deskripsi-soal-ATM-or-ATP-or-FTP)
  - [Penyelesaian soal ATM or ATP or FTP](#Penyelesaian-soal-ATM-or-ATP-or-FTP)
- [whoami](#whoami)
  - [Deskripsi soal whoami](#Deskripsi-soal-whoami)
  - [Penyelesaian soal whoami](#Penyelesaian-soal-whoami)
- [How Many Packets](#How-Many-Packets)
  - [Deskripsi soal How Many Packets](#Deskripsi-soal-How-Many-Packets)
  - [Penyelesaian soal How Many Packets](#Penyelesaian-soal-How-Many-Packets)
- [trace him](#trace-him)
  - [Deskripsi soal](#Deskripsi-soal)
  - [Penyelesaian soal](#Penyelesaian-soal)
- [malwleowleo](#malwleowleo)
  - [Deskripsi soal](#Deskripsi-soal)
  - [Penyelesaian soal](#Penyelesaian-soal)
- [creds](#creds)
  - [Deskripsi soal](#Deskripsi-soal)
  - [Penyelesaian soal](#Penyelesaian-soal)

## ATM or ATP or FTP 

### Deskripsi soal ATM or ATP or FTP

Pada soal ini praktikan diminta untuk menganalisis kejadian bruteforce login yang sedang dialami oleh Pradityo ketika Pradityo mencoba mengembangkan server FTP.
    
### Penyelesaian soal ATM or ATP or FTP

Berikut langkah-langkah pengerjaan soal ATM or ATP or FTP :
1. Buka WSL lalu salin `nc 10.15.40.20 10004`.
2. Kemudian, muncul sebuah pertanyaan yaitu apa password yang berhasil didapatkan hacker setelah melakukan bruteforce login ftp.
3. Lalu buka file wireshark bernama `ftp.pcap` lalu follow tcp streamnya.
4. Jawaban mengenai password yang berhasil didapat oleh hacker ada pada stream/halaman ke 319 dengan password yaitu `m4y_th3_Kn!fe_ch1p_&_sh4tter`.
   ![Output jawaban](https://i.imgur.com/ZoPv5O9.png)
5. Setelah menjawab pertanyaan dan hasilnya benar, flag pun berhasil didapatkan.
   ![Output jawaban](https://i.imgur.com/AEmjcnD.png)

## whoami

### Deskripsi soal whoami

Pada soal ini praktikan diminta untuk menemukan identitas attacker pada kasus creds.

### Penyelesaian soal whoami

Berikut langkah-langkah pengerjaan soal whoami :
1. Buka WSL lalu salin `nc 10.15.40.20 10009`.
2. Lalu muncullah sebuah pertanyaan yaitu siapa nama attacker yang melakukan serangan ini?
3. Kemudian buka file wireshark yang sama pada kasus creds yaitu `evidence.pcap` lalu follow tcp streamnya.
4. Jawaban mengenai identitas attacker ada pada stream/halaman ketujuh dengan jawaban sebagai berikut :
   ![Output jawaban](https://i.imgur.com/PQqBzDU.png)
5. Lalu kode kode tersebut di decode ke website `www.base64decode.net` dan menghasilkan sebuah kalimat yaitu `Hello my name is Paul Atreides
`.
   ![Output jawaban](https://i.imgur.com/9jZj0lX.png)
6. Setelah itu, jawab dengan nama Paul-Atreides dan flag pun berhasil didapatkan.   

## How Many Packets

### Deskripsi soal How Many Packets

Pada soal ini praktikan diminta untuk mencari tahu berapa kali hacker mencoba login pada sistem yang ada di soal ATM or ATP or FTP.

### Penyelesaian soal How Many Packets

Berikut langkah-langkah pengerjaan soal How Many Packets :
1. Buka WSL lalu salin `nc 10.15.40.20 10005`.
2. Kemudian muncul sebuah pertanyaan yaitu berapa total attempt login(bruteforce) yang dilakukan oleh hacker?
3. Lalu buka file wireshark yang sama dengan case ATM or ATP or FTP yaitu `ftp.pcap` lalu follow tcp streamnya.
4. Setelah dihitung, hacker telah mencoba untuk login(bruteforce) sebanyak 934 kali dengan rincian sebagai berikut :
    - Pada stream 1-304, hacker mencoba login sebanyak 3 kali(304*3=912).
      ![Output foto](https://i.imgur.com/Hx4Y7E4.png)
    - Pada stream 305-311(7 stream), hacker mencoba login sebanyak 2 kali(7*2=14).
      ![Output foto](https://i.imgur.com/d3SsoTQ.png)
    - Pada stream 312-319(8 stream), hacker mencoba login sebanyak 1 kali(total=912+14+8=934 kali).
      ![Output foto](https://i.imgur.com/ZoPv5O9.png)
5. Lalu jawab pertanyaan tadi dengan jawaban 934.
6. Setelah berhasil menjawab, flag pun berhasil didapatkan.
   ![Output jawaban](https://i.imgur.com/gvaocnM.png)

## trace him

### Deskripsi soal

Selain menghitung jumlah packet, coba lacak juga ip penyerang tersebut!

### Penyelesaian soal

Berikut langkah-langkah pengerjaan soal trace him :
1. Buka terminal WSL/Linux dan salin `nc 10.15.40.20 10006` untuk mengetahui pertanyaan hint untuk menemukan flagnya
2. Lalu buka file wireshark yang sama seperti dengan `ATM or ATP or FTP` yaitu file `ftp.pcap` dan melakukan filter menggunakan `http` yang nantinya akan ditujukan ke `tcp.stream eq 2`
   ![Screenshot 2024-03-30 230010](https://github.com/ahmaddaniswara01/Jarkom-Modul-1-IT28-2024/assets/131789727/42c11ffd-2be6-48d6-a06f-0ca13b083f46)
3. Pilih yang terdapat responses, dan akan menemukan IP yang sesuai dengan pertanyaan hintnya
4. Lalu menemukan flagnya
   ![trace him](https://github.com/ahmaddaniswara01/Jarkom-Modul-1-IT28-2024/assets/131789727/099ff503-cf13-40e5-b60a-eca31e8686ea)
     
## malwleowleo

### Deskripsi soal

Dapatkah kamu menemukan file malware yang dikirim oleh attacker melalui ftp?

### Penyelesaian soal

Berikut langkah-langkah pengerjaan soal malwleowleo :
1. Buka terminal WSL/Linux dan salin `nc 10.15.40.20 10008` untuk mengetahui pertanyaan hint untuk menemukan flagnya
2. Lalu buka file wireshark yang sama seperti dengan `creds` yaitu file `evidence.pcap` dan melakukan filter menggunakan `ftp` yang nantinya akan ditujukan ke `tcp.stream eq 2`
   ![Screenshot 2024-03-30 220557](https://github.com/ahmaddaniswara01/Jarkom-Modul-1-IT28-2024/assets/131789727/97dc82d7-0c32-4143-81fc-d681c1cb0993)
3. Pada bagian passive mode terdapat nama file malware yang di cari sesuai pertanyaan hintnya
4. Lalu menemukan flagnya
   ![malwleo](https://github.com/ahmaddaniswara01/Jarkom-Modul-1-IT28-2024/assets/131789727/cb5264e2-6b19-4983-9d16-6c239e3777f1)
## creds

### Deskripsi soal

Attacker menyadari jika dia bisa membuat clone ftp server dari target, temukan kredensialn dari server ftp yang dibuat oleh attacker

### Penyelesaian soal

Berikut langkah-langkah pengerjaan soal creds :
1. Buka terminal WSL/Linux dan salin `nc 10.15.40.20 10007` untuk mengetahui pertanyaan hint untuk menemukan flagnya
2. Lalu buka file `evidence.pcap` pada wireshark dan melakukan filter menggunakan `ftp` yang nantinya akan ditujukan ke `tcp.stream eq 2`
   ![Screenshot 2024-03-30 221525](https://github.com/ahmaddaniswara01/Jarkom-Modul-1-IT28-2024/assets/131789727/ba669ad6-a2f8-4907-917f-b4cef0fbbf4d)
3. Pada follow stream diatas terdapat username dan password yang dibutuhkan untuk menjawab pertanyaan hintnya
4. Lalu menemukan flagnya
   ![creds](https://github.com/ahmaddaniswara01/Jarkom-Modul-1-IT28-2024/assets/131789727/3c4f1026-14c7-4471-a51f-727b0e420ed9)


### Sekian Laporan Resmi Modul 1 
