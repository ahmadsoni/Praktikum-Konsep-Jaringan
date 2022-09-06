# Kondisi Pertama P0 ke P1 Proses Paket (Jawab Perlu BroadCast)
Proses pengirim paket terjadi pada layer ke 2 dan ke 3 yaitu pada layer Network dan Data-link
selanjutnya kita akan membuat topologi dengan hub device kita akan berinteraksi dengan Protokol Resolusi Alamat atau disingkat PRA adalah sebuah protokol dalam TCP/IP Protocol Suite yang bertanggungjawab dalam melakukan resolusi alamat IP ke dalam alamat Media Access Control. 
Broadcast adalah alamat jaringan yang digunakan untuk mengirimkan ke semua perangkat yang terhubung ke jaringan komunikasi akses jamak. Pesan yang dikirim ke alamat broadcast dapat diterima oleh semua host yang terhubung ke jaringan.

- pc 0 dengan ip 192.168.1.1
- pc 0 dengan ip 192.168.1.2
-  pc 0 dengan ip 192.168.1.3

[![1.png](https://i.postimg.cc/mgzSMJn7/1.png)](https://postimg.cc/bZPbfCpv)

Selanjutnya kita setting terlebih simulasi ARP dengan klik menu -> Simulation -> Edit Filter dan sesuikan dengan gambar di bawah

[![3.png](https://i.postimg.cc/FKH6JNSG/3.png)](https://postimg.cc/sMbmkFwZ)

selanjutnya kita bisa cek ARP sudah memliki cache apa belum dengan perintah 
- arp -a
[![5.png](https://i.postimg.cc/WzcyfrDb/5.png)](https://postimg.cc/62zz88LD)
disini kita bisa melihat bahwa arp masih kosong kita bisa next pada tahap selanjutnya 

selanjutnya karena dari ARP sendiri masih belum memiliki ARP cache kita perlu melakukan adanya broadcast yang akan mencari semua device yang terhubung berdasarkan MAC addres 
- Proses Ping memulai permintaan ping berikutnya.
- Proses Ping membuat pesan ICMP Echo Request dan mengirimkannya ke proses yang lebih rendah.
- Alamat IP sumber tidak ditentukan. Perangkat menyetelnya ke alamat IP port.
- Alamat IP tujuan berada di subnet yang sama. Perangkat mengatur hop berikutnya ke tujuan.
- Proses ARP membuat permintaan untuk alamat IP target.
- Perangkat merangkum PDU ke dalam bingkai Ethernet.

[![6.png](https://i.postimg.cc/B6cqp2N4/6.png)](https://postimg.cc/ftynTt6r)

Selanjutnya frame paket akan di dapatkan ke MAC Adrees yang di tuju dan MAC adress yang bukan dari tujuan akan di drop. dan paket yang telah di terima oleh penerima MAC Address tujuan maka akan melakukan reply dengan broadcast hal yang sama di lakukan dengan pc 0 yang akan menerima paket tersebut dan ARP akan memetakan logical ke pysical selanjutnya kita cek 
- arp -a
[![13.png](https://i.postimg.cc/Y9qpXhPF/13.png)](https://postimg.cc/SX3FRNkQ)
maka ARP cache akan memetakan setiap device yang berhasil di broadcast


# Kondisi Kedua P0 ke P1 Apakah Terjadi Broadcast Lagi ? (Jawab Tidak Perlu BroadCast)
tetunya kita dengan adanya ARP itu sendiri maka arp akan memetakan MAC dan tentunya tidak di perlukan lagi broadcast 
untuk pembuktian bisa kita lihat dengan mengetikan perintah 
- arp -a
[![13.png](https://i.postimg.cc/Y9qpXhPF/13.png)](https://postimg.cc/SX3FRNkQ)
di situ bisa kita lihat bahwa pada pc 0 sudah memiliki MAC Address dari pc 1

[![16.png](https://i.postimg.cc/TYhKpy2h/16.png)](https://postimg.cc/F75r6HLQ)
kita bisa melihat bahwa pada layer tiga dest ip ICMP sudah bisa langsung di dapatkan
 tentu saja jawaban nya komputer tidak perlu lagi melakukan broadcast karene sudab di catat oleh arp


# Kondisi Pertama P1 ke P0 apakah perlu broadcast ? (Jawab Tidak Perlu BroadCast)
untuk menjawab pertanyaan tersebut kita harus melhiat alur kerja pada saat broadcast pertama kommputer melakukan broadcast komputer yang menerima frame broadcast akan meng reply tentu saja secara otomatis pada pc 1 juga perlu melakukan broadcast sehingga pada tahap tersebut arp juga mencatat hasil broadcast dari hasil repy ke pc0

untuk meelihatnya coba kita ketik perintah

- arp -a pada pc1
[![17.png](https://i.postimg.cc/SxFY3Sqs/17.png)](https://postimg.cc/8j4CrV7Q)
dan kita bisa melihat bahwa pc1 sudah memiliki ARP 

jadi jawabanya tidak melaukan broadcast

