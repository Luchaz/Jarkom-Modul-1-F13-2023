# Jarkom-Modul-1-F13-2022

| **No** | **Nama**                         | **NRP**    |
| ------ | -------------------------------- | ---------- |
| 1      | Helmi Abiyu Mahendra             | 5025211061 |
| 2      | Muhammad Naufal Fawwaz Ramadhan  | 5025211223 |


--------------------------------

## Soal 1

User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

<ol type="a">
<li>
    Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
</li>

- 258040667

<li>
    Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?
</li>

- 1044861039

<li>
    Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
</li>

- 1044861039

<li>
    Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
</li>

- 258040696

</ol>



## Jawaban Soal 1 :

- 

--------------------------------

## Soal 2 :

Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

## Jawaban Soal 2 :

- Filter packet menggunakan query `http` kemudian follow HTTP Stream lalu search `server`

![Soal2-1](<images/2-a.jpg>)

- Maka ditemukan jawaban nya adalah **gunicorn**


--------------------------------
## Soal 3 :

Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

<ol type="a">
<li>
    Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
</li>

- 21

<li>
    Protokol layer transport apa yang digunakan?
</li>

- UDP

</ol>


## Jawaban Soal 3 :

- 
- 


--------------------------------
## Soal 4 :

Berapa nilai checksum yang didapat dari header pada paket nomor 130?

## Jawaban Soal 4 :

- Nilai checksum packet 130 terlihat di detail packet tersebut
- Menggunakan filter **frame.number == 130** digunakan untuk menunjukan packet no 130
![Soal4-1](<images/4-a.jpg>)


--------------------------------
## Soal 5 :

Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

> 60

Port berapakah pada server yang digunakan untuk service SMTP?

> 25

Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

> 74.53.140.153

## Jawaban Soal 5 :

- 
- 


--------------------------------
## (REVISI) Soal 6 :

Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan <b>"server SOURCE ADDRESS 7812 is invalid".</b> ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

## Jawaban Soal 6 :
- Untuk menyelesaikan soal pada nomor ini kita perhatikan pada pola decrypt yang diberikan yaitu ``a1 e5 u21``. Setelah itu kita lihat pada bagian yang ditandai tebal pada soal yaitu ``SOURCE ADDRESS 7812``.

- Selanjutnya kita akan mengecek PACKET bernomor 7812. Dan setelah itu kita dapat melihat ``SOURCE ADDRESS`` bersamaan dengan itu juga kita dapat melihat ``ip 
  source`` yang ada disitu. Setelah itu kita dapat membentuk suatu barisan angka yang dapat dipecah menjadi beberapa angka karena huruf hanya ada 26

Berikut adalah ``IP Source`` yang ditemukan 
```
104.18.14.101
```
![Soal6-1](<images/6-b.jpg>)

Berikutnya kita dapat menyatukan IP Source tersebut menjadi suatu deretan angka 
```
1041814101
```

Setlah itu kita dapat memecah menjadi angka yang ``<= 26``
```
10 4 18 14 10 1
```

Pada akhirnya kita dapat menghasilkan suatu kata dari pola yang telah ditemukan yaitu 
```
JDRNJA
```
![Soal6-1](<images/6-a.jpg>)


--------------------------------

## Soal 7 :

Berapa jumlah packet yang menuju IP 184.87.193.88?

## Jawaban Soal 7 :
- 
- 
- 
--------------------------------
## Soal 8 :

Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
## Jawaban Soal 8 :

-

--------------------------------

## Soal 9 :
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

## Jawaban Soal 9 :
- `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

--------------------------------

## Soal 10 :

Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

## Jawaban Soal 10 :
-
