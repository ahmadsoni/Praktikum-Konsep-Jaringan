## Documentation Task Wireshark
# Colors Rule
Wireshark menggunakan warna untuk membantu mengidentifikasi jenis lalu lintas secara sekilas. Secara default, hijau adalah lalu lintas TCP, biru tua adalah lalu lintas DNS, biru muda adalah lalu lintas UDP, dan hitam mengidentifikasi paket TCP dengan masalah — misalnya, mereka bisa saja dikirim tidak sesuai pesanan.
| Color in Wireshark |                                  Packet Type                                 |
|:------------------:|:----------------------------------------------------------------------------:|
|    Light purple    |                                      TCP                                     |
|     Light blue     |                                      UDP                                     |
|        Black       |                              Packets with errors                             |
|     Light green    |                                 HTTP traffic                                 |
|    Light yellow    | Windows-specific traffic,  including Server Message Blocks (SMB) and NetBIOS |
|     Dark yellow    |                                    Routing                                   |
|      Dark gray     |                         TCP SYN, FIN and ACK traffic                         |
|         Red        |                            Invalid Display Filter                            |
 Black Color
[![black.png](https://i.postimg.cc/B6VvyYdR/black.png)](https://postimg.cc/ZB6ZvcYL)

Light blue and Light purple	
[![blue-and-pink.png](https://i.postimg.cc/rwfzxwf8/blue-and-pink.png)](https://postimg.cc/cv8sN0qj)

Dark gray and Red
[![brown.png](https://i.postimg.cc/4xDq8zLw/brown.png)](https://postimg.cc/mPSmkFGF)

Light yellow and Light yellow
[![color-whireshark.png](https://i.postimg.cc/90p5qrcV/color-whireshark.png)](https://postimg.cc/5Q6kh9Hk)


## Packet Analyzer

[![IP-Address.png](https://i.postimg.cc/fbwrHFVK/IP-Address.png)](https://postimg.cc/Hrhzn64c)

Dengan menggunakan ping pada default gateway yang diberikan oleh router (wifi) sudah bisa melakukan analisa suatu packet dengan bantuan Wireshark.

[![Capture-Analyzer.png](https://i.postimg.cc/wB5dMPP8/Capture-Analyzer.png)](https://postimg.cc/1gzdYWsJ)

Gambar di atas menunjukkan bahwa IP Address pada adaptor wifi yakni 192.168.18.52 dan default gatewaynya 192.168.18.1 dengan data tersebut kita bisa mengetahui packet yang terlintas pada Wireshark.

[![Detail-Capture-IPV4.png](https://i.postimg.cc/LXs6MNbk/Detail-Capture-IPV4.png)](https://postimg.cc/yJwzmXBW)
Dalam box Internet Protocol terdapat:
-  Version: 4
Menunjukkan versi yang digunakan adalah versi 4
- Header length: 20 bytes
Menunjukkan panjangnya header yang ada di lapisan network adalah
sebesar 20 bytes
- Source: 192.168.18.52 Destination: 192.168.18.1
Menunjukkan IP dari source yaitu 192.168.18.52 dan IP dari destination
yaitu 192192.168.18.1
- Kesimpulan:
Lapisan network, panjangnya header yang diberikan sebesar 20 bytes
dengan IP source 192.168.18.52 dan IP destination yaitu 192.168.18.1

## ICMP pada whireshark
Internet Control Message Protocol (ICMP) adalah salah satu protokol inti dari keluarga
protokol internet. ICMP utamanya digunakan oleh sistem operasi komputer jaringan untuk
mengirim pesan kesalahan yang menyatakan, sebagai contoh, bahwa komputer tujuan tidak
bisa dijangkau. ICMP berbeda tujuan dengan TCP dan UDP dalam hal ICMP tidak digunakan
secara langsung oleh aplikasi jaringan milik pengguna. salah satu pengecualian adalah
aplikasi ping yang mengirim pesan ICMP Echo Request (dan menerima Echo Reply) untuk
menentukan apakah komputer tujuan dapat dijangkau dan berapa lama paket yang dikirimkan
dibalas oleh komputer tujuan. (id.wikipedia.org)

[![icmp.png](https://i.postimg.cc/PJWDRdVV/icmp.png)](https://postimg.cc/sG21BCr5)

[![icmp-new.png](https://i.postimg.cc/DZZFN6C9/icmp-new.png)](https://postimg.cc/LqrrYtFD)
Dari tabel ICMP saat echo ping request tersebut, icmp bertype 8, code 0, dengan
algoritma checksum 0x4cf9, banyak identifier (ident ifikasi) 256 bytes dan Sequence
number25088 byte. Serta hasil diatas menunjukkan saat proses request ping, paket
dari source (192.168.18.18) IP address dari komputer kita akan merequest ({echo (ping)
request) ke destinat ion (192.168.18.1) IP address router wifi biznet.

[![Detail-Capture-Frame.png](https://i.postimg.cc/445bPdzr/Detail-Capture-Frame.png)](https://postimg.cc/qgN3MpDL)

Dalam box frame terdapat:
a) Arrival Time: Sep  2, 2022 19:45:37.659417000 SE Asia Standard Time
Menunjukkan waktu saat pengiriman data
b) [Time delta from previous captured frame: 0.521990000 seconds]
[Time delta from previous displayed frame: 0.521990000 seconds]
[Time since reference or first frame: 22.274074000 seconds]
Menunjukkan waktu sebelum capture dari frame, yaitu 0.041639000
seconds, waktu setelah frame ditampilkan yaitu 1.146981000 seconds,
dan waktu sejak awal frame 48.550947000 seconds.
c) Frame Number: 4344
Menunjukkan nomor dari frame tersebut yaitu 4344
d) Frame Length: 74 bytes (592 bits)
Menunjukkan panjangnya frame adalah sebasar 74 bytes
e) [Protocols in frame: eth:ethertype:ip:icmp:data]
Menunjukkan protokol-protokol apa saja yang ada di frame 4344 yaitu
ada Ethernet, Internet Protocol (IP), Internet Control Message Protocol
(ICMP) & Data
d) Kesimpulan:
Lapisan ini menunjukkan apa saja yang ada dalam satu frame yaitu
JOBSHEET TEUM
seperti protokol-protokol yang ada di lapisan ini Ethernet, Internet
Protocol (IP), Transmission Control Protocol (TCP), Hypertext Transfer
Protocol (HTTP), dan data-text-lines.


Some text

- Instruction 1
- Instruction 2
- Instruction 3

