**LAPORAN PRAKTIKUM KONSEP JARINGAN**

> Nama : Ahmad Shonhaji
>
> Kelas : 2 D4 IT A
>
> NRP : 3121600025

**TUGAS VLAN 2**

**Pengunaan VLAN untuk 3 VLAN yang berbeda**
Untuk skema yang saya berikan merupakan skema 3 gedung dengan 3 switch dan 1 router dan 3 vlan sehinga setiap vlan dapat menghubungi satu vlan dan tidak dengan vlan yang lain.
di bawah ini merupakan contoh skema topologi yang saya gunakan.

[![topologi.png](https://i.postimg.cc/rscrsKCT/topologi.png)](https://postimg.cc/bDCJFYBV)



**Setting VLAN dan Router**

sebelum mengulik mendaftarkan VLAN yang perlu di siapkan adalah membuat VLAN itu sendiri maka berikut skema yang saya siapkan
[![device.png](https://i.postimg.cc/YqSsC3rd/device.png)](https://postimg.cc/nM6kdqQm)

setelah semua vlan sudah di tentukan dan siapkan kita perlu mengisi alamat address pada setiap PC dengan sesuai dengan skema di atas dan alamat GATEWAY yang sesuai dengan nomer vlan yang di berikan sehingga subnetmask akan menentukan akan masuk ke vlan berapa pada PC yang di daftarka.

1. PC pada VLAN 10
    [![vlan10.png](https://i.postimg.cc/G36Xb1fm/vlan10.png)](https://postimg.cc/LhBtVGRc)

2. PC pada VLAN 20
    [![vlan20.png](https://i.postimg.cc/GtDJ4Hfh/vlan20.png)](https://postimg.cc/q6kCYM09)

3. PC pada VLAN 30
    [![vlan30.png](https://i.postimg.cc/4xPvHCWt/vlan30.png)](https://postimg.cc/MncfgL2K)

Selanjutnya kita setting pada pada Switch dan Router dengan mengunakan ClI untuk setting nya kita perlu setting pada Switch untuk mendaftarkan vlan dan mendaftarkan setiap port untuk di daftarkan pada setiap port.

dan kita perlu trunk kan setiap port yang terhubung ke router dan switch dan trunking adalah teknologi untuk menyediakan akses jaringan ke beberapa klien secara bersamaan dengan berbagi satu set sirkuit, pembawa, saluran, atau frekuensi.

1. Switch 1
    pada swtich pertama kita perlu trunk pada switch ke-2
   [![switch1.png](https://i.postimg.cc/rzX1LMQ0/switch1.png)](https://postimg.cc/zH7bCZm8)

2. Switch 2
    pada vlan ke 2 perlu 3 akses trunk dan 2 trunk pertama untuk setiap swtich dan 1 lagi untuk router

    [![vlan20.png](https://i.postimg.cc/GtDJ4Hfh/vlan20.png)](https://postimg.cc/q6kCYM09)

3. Switch 3
    pada swtich pertama kita perlu trunk pada switch ke-2
    [![switch2.png](https://i.postimg.cc/9XZ5Z1Z1/switch2.png)](https://postimg.cc/V5fVcq7b)

4. Router 1
    Fungsi router pada komunikasi antar vlan ialah, menyambungkan user client 1 dengan user client yg lain dengan mengunakan gateway dan proses ecapsulation.

    [![route1.png](https://i.postimg.cc/3R9Gc2Dq/route1.png)](https://postimg.cc/Q99VB9mg)

**Test Ping untuk cek koneksi**
1. Test VLAN 10
    [![pc-vlan-10.png](https://i.postimg.cc/TPq8BJJf/pc-vlan-10.png)](https://postimg.cc/QBtnT5zy)

2. Test VLAN 20
    [![pc-vlan-20.png](https://i.postimg.cc/WbDBsvw9/pc-vlan-20.png)](https://postimg.cc/kBm1yLZ8)

3. Test VLAN 30
    [![pc-vlan-30.png](https://i.postimg.cc/52sKzKgH/pc-vlan-30.png)](https://postimg.cc/QFWqGbRs)

4. Test Gagal jika beda VLAN
    [![pc-vlan-gagal.png](https://i.postimg.cc/Bv8pKSty/pc-vlan-gagal.png)](https://postimg.cc/QB3cLrQk)


