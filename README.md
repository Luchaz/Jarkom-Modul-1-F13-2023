# Jarkom-Modul-1-F13-2022

| **No** | **Nama**                         | **NRP**    |
| ------ | -------------------------------- | ---------- |
| 1      | Helmi Abiyu Mahendra             | 5025211061 |
| 2      | Muhammad Naufal Fawwaz Ramadhan  | 5025211223 |


--------------------------------

## (REVISI) Soal 1

User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

<ol type="a">
<li>
    Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
</li>


<li>
    Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?
</li>


<li>
    Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
</li>


<li>
    Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
</li>


</ol>



## Jawaban Soal 1 :

- Untuk menampilkan aktivitas paket, maka digunakan filter
```sh
tcp contains "STOR"
```
yang mana **"STOR"** merupakan command FTP untuk menyimpan file pada host remote.<br/>
Maka didapati Sequence Number (raw) beserta Acknowledge Number (raw) sebagai berikut
![Soal1-1](<images/1.0.png>)
<br/> SN(r) : 258040667
<br/> AN(r) : 1044861039
- Selanjutnya untuk paket response terhadap request sebelumnya dapat ditemui di bawah, dengan Sequence Number (raw) diikuti dengan Acknowledge Number (raw) berikut: <br />
![Soal1-2](<images/1.1.png>)
<br/> SN(r) : 1044861039
<br/> AN(r) : 258040696

--------------------------------

## Soal 2 :

Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

## Jawaban Soal 2 :

- Filter packet menggunakan query `http` kemudian follow HTTP Stream lalu search `server`
```sh
http.server
```

![Soal2-1](<images/2-a.jpg>)

- Maka ditemukan jawaban nya adalah **gunicorn**


--------------------------------
## (REVISI) Soal 3 :

Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

<ol type="a">
<li>
    Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
</li>

<li>
    Protokol layer transport apa yang digunakan?
</li>

</ol>


## Jawaban Soal 3 :

- Untuk melakukan filter terhadap IP dengan source maupun destination 239.255.255.250 digunakan ``ip.addr`` serta ``udp.dstport`` untuk melakukan filter port. Jika digunakan sekaligus akan sebagai berikut:
```sh
ip.addr == 239.255.255.250 && udp.dstport 3702
```
- Untuk melihat jumlah paket yang ditangkap, dapat diamati pada pojok kanan bawah, dan protokol yang digunakan pada kolom protokol yang ditampilkan dalam gambar
![Soal3-1](<images/3.0.png>)


--------------------------------
## Soal 4 :

Berapa nilai checksum yang didapat dari header pada paket nomor 130?

## Jawaban Soal 4 :

- Nilai checksum packet 130 terlihat di detail packet tersebut
- Menggunakan filter **frame.number == 130** digunakan untuk menunjukan packet no 130
![Soal4-1](<images/4-a.jpg>)


--------------------------------
## (REVISI) Soal 5 :

Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

> 60

Port berapakah pada server yang digunakan untuk service SMTP?

> 25

Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

> 74.53.140.153

## Jawaban Soal 5 :

- Bersamaan dengan file pcap soal, juga diberikan file zip yang dikunci; maka dilakukan pencarian terhadap password file zip tersebut. <br/>
Pencarian dilakukan dengan menggunakan filter ``contains`` dan keyword `"zip"` sebagai berikut:
```sh
frame contains "zip"
``` 
- Ditemukan 1 paket SMTP dengan pesan terenkripsi
![Soal5-1](<images/5.1.png>) hasil dari filtering
setelah dilakukan dekripsi, password digunakan untuk membuka note dalam file hasil ekstraksi sebelumnya. ![Soal5-2](<images/5.2.png>)
- Setelah mengikuti perintah dari file, kemudian didapati pertanyaan berupa jumlah paket hasil capture, server yang digunakan, dan IP public. Solusinya dapat dilakukan dengan melakukan filtering dengan keyword **SMTP**, dan kemudian didapati jumlah paket hasil capture di ujung kanan bawah, server pada badan paket, dan alamat IP yang tidak berawalan 10. (IP ITS)
![Soal5-2](<images/5.4.png>)



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
- Jumlah paket menuju IP 184.87.193.88 dapat ditemukan cukup dengan filter
```sh
IP.dst == 184.87.193.88
```
- Hasil yang didapat sebagai berikut ![Soal7-1](<images/7.0.png>)
--------------------------------
## Soal 8 :

Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
## Jawaban Soal 8 :

- Filtering paket menuju port 80 dengan query ascending adalah sebagai berikut 
```sh
tcp.dstport == 80 && udp.dstport == 80
```

--------------------------------

## Soal 9 :
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

## Jawaban Soal 9 :
-![Soal9-1](<images/9.0.png>)
```sh
ip.src == 10.51.40.1 && ip.dst != 10.39.55.34
```

--------------------------------

## Soal 10 :

Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

## Jawaban Soal 10 :
- Melakukan pencarian kredensial user telnet dapat dilakukan dengan filter 
```sh
telnet contains "Login"
```
dan kemudian didapati hasil sebagai berikut ![Soal10-1](<images/10.0.png>)
