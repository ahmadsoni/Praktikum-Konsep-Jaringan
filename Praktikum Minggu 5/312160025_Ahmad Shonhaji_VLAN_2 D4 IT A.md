**LAPORAN PRAKTIKUM KONSEP JARINGAN**

> Nama : Ahmad Shonhaji
>
> Kelas : 2 D4 IT A
>
> NRP : 3121600025

**TUGAS VLAN**

**Pengertian Vlan**

VLAN adalah singkatan dari Virtual Local Area Network, guna menghindari
keterbatasan fisik LAN melalui sifat yang dimilikinya, memungkinkan
skala jaringan dan segmentasi guna meningkatkan langkah-langkah keamanan
dan mengurangi adanya latensi jaringan. VLAN adalah subnetwork yang
dapat mengelompokkan kumpulan perangkat pada jaringan area lokal fisik
(LAN) yang terpisah.

**Fungsi VLAN**

Fungsi Virtual Local Area Network atau VLAN adalah mengakomodir
konfigurasi pada jaringan komputer fisik menjadi beberapa domain siaran.

Meski memiliki domain siaran berbeda, jalur yang dihasilkan oleh VLAN
tersebut masih melewati perangkat penghubung yang sama. Biasanya
dikonfigurasikan dengan mikrotik atau cisco.

**Cara kerja VLAN**

Berikut adalah setail langkah demi langkah tentang cara kerja Virtual
Local Area Network : 

1.  Virtual Local Area Network dalam jaringan diidentifikasi dengan
    nomor

2.  Rentang yang valid adalah 1-4094. Pada saklar Virtual Local Area
    Network, anda menetapkan port dengan nomor Virtual Local Area
    Network yang tepat 

3.  Saklar kemudian memungkinkan data yang perlu dikirim antara berbagai
    port yang memiliki Virtual Local Area Network yang sama 

4.  Karena hampir semua jaringan lebih besar dari satu saklar, harus ada
    cara untuk mengirim lalu lintas antara dua saklar

5.  Salah satu cara sederhana dan mudah untuk melakukannya adalah dengan
    menetapkan port pada setiap switch jaringan. Dengan Virtual Local
    Area Network dan menjalankan kabel antara keduanya. 

**TUGAS PRAKTIKUM**
Topologi yang saya gunakan adalah sebagi berikut Topologi tersebut terdiri dari 1 router, 1 switch, dan 6 pc-client dengan 2 VLAN (172.17.10.1/24 - 10  & 192.168.20.1/24 - 30 ) dan 1 Non-VLAN (192.168.1.1/24).
[![4.png](https://i.postimg.cc/0NTMvNmD/4.png)](https://postimg.cc/v1vHLb0Z)

**Configuration IP (PC)**

[![5.png](https://i.postimg.cc/MKwpRb4j/5.png)](https://postimg.cc/t7rbGP9X)

PC 0 - PC 1 : IP GATEWAY -> 172.17.1.1 Subnet Mask -> 255.255.255.0 (IP NON VLAN Router) PC 1 -PC 5 : IP GATEWAY -> 172.17.10.1 Subnet Mask -> 255.255.255.0 (IP VLAN Route 10) PC 6 - PC 7 : IP GATEWAY -> 192.168.30.1 Subnet Mask -> 255.255.255.0 (IP VLAN Route 30)


**Configuration IP (Router)**
[![7.png](https://i.postimg.cc/Dy6ZQjtb/7.png)](https://postimg.cc/XpZ448NV)
Router 0 : Interface Gig0/0/0 -> 192.168.1.1/24 (Configuration Non-VLAN IP)

**Conifguration VLAN Database (Switch)**
[![8.png](https://i.postimg.cc/NMxqhV86/8.png)](https://postimg.cc/k6DhKTpG)
Switch 0 ada 2 VLAN yang akan di gunakan yaitu VLAN Nomer [10]  VLAN Nommer [30]

**Configuration Interface (Switch)**
[![9.png](https://i.postimg.cc/mgtcXJzJ/9.png)](https://postimg.cc/JsC4tTQ5)
Switch 0 : Interface FastEhernet0/7 -> Mode TRUNK & All VLAN (Configuration for Router) Interface FastEhernet0/1 dan Interface FastEhernet0/2  -> Mode Access & VLAN 10  dan Interface FastEhernet0/3 dan Interface FastEhernet0/4 -> Mode Access & VLAN 30  Interface FastEhernet0/7 -> Mode Access TRUNK

**Configuration VLAN Database (Router)**
[![10.png](https://i.postimg.cc/Vv1jT83m/10.png)](https://postimg.cc/ZB7BB1bM)
[![11.png](https://i.postimg.cc/Y2srb3gy/11.png)](https://postimg.cc/6TCxQCMd)
Router 0 : VLAN -> VLAN Number [10] -> VLAN Number [30]


**Configuration IP VLAN (Router)**
[![12.png](https://i.postimg.cc/VvLFvw44/12.png)](https://postimg.cc/CBX8rW3f)
Router 0 : Interface Gig0/0/0.10 -> 172.17.10.1/24 untuk VLAN 10 ,Interface Gig0/0/0.30 -> 192.168.20.1/24 (Configuration VLAN 30 )

**Test Ping To Other VLAN And Non-VLAN**
[![13.png](https://i.postimg.cc/V6brzLxX/13.png)](https://postimg.cc/ftDTKZTb)
Ping di atas berasal dari PC4-PC05 172.17.10.1 - 172.17.10.3/24 (VLAN 10) berhasil melakukan ping pada IP dari PC06-PC07/24 192.168.20.1 - 192.168.20.3 (VLAN 30) yang dimana kedua IP tersebut berbeda network dan subnetting tanpa bantuan routing static karena pada Router 0 mereka terkoneksi secara Directly Connected dan bukan Remote Network.

Sehingga tidak diperlukan routing static atau semacamnya, VLAN seakaan terdapat 2 kabel pada router dengan IP yang berbeda. Dengan menambahkan IP pada virtual dengan imbuhan [.number] pada interfaces yang terkoneksi pada router secara nyata.

