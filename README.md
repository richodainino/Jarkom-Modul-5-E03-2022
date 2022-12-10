# Jarkom-Modul-5-E03-2022

## Kelompok E03

- Pedro T. Korwa              05111940007003
- Made Rianja Richo Dainino   5025201236
- Syaiful Bahri Dirgantara    5025201203

### A. Topologi

![Modul5](https://user-images.githubusercontent.com/33245436/206869513-24bfe0dd-3251-41a1-b69c-70e1a600c3c0.png)

### B. Subnetting

#### VLSM Tree

![Modul5_Tree](https://user-images.githubusercontent.com/33245436/206869515-d3a6195f-07f2-4bc5-8025-4fbe70242da7.png)

#### Tabel Subnetting

| Subnet | Jumlah IP | Length | IP          | Subnet Mask     |
| ------ | --------- | ------ | ----------- | --------------- |
| A1     | 3         | /29    | 10.23.7.128 | 255.255.255.248 |
| A2     | 2         | /30    | 10.23.7.144 | 255.255.255.252 |
| A3     | 63        | /25    | 10.23.7.0   | 255.255.255.128 |
| A4     | 701       | /22    | 10.23.0.0   | 255.255.252.0   |
| A5     | 2         | /30    | 10.23.7.148 | 255.255.255.252 |
| A6     | 256       | /23    | 10.23.4.0   | 255.255.254.0   |
| A7     | 201       | /24    | 10.23.6.0   | 255.255.255.0   |
| A8     | 3         | /29    | 10.23.7.136 | 255.255.255.248 |
| Total  | 1231      | /21    |             |                 |

#### Tabel IP Node

| Subnet | Node            | IP          | Subnet Mask     |
| ------ | --------------- | ----------- | --------------- |
| A1     | Westalis (eth1) | 10.23.7.129 | 255.255.255.248 |
| A1     | Eden            | 10.23.7.130 | 255.255.255.248 |
| A1     | Wise            | 10.23.7.131 | 255.255.255.248 |
| A2     | Westalis (eth0) | 10.23.7.145 | 255.255.255.252 |
| A2     | Strix (eth1)    | 10.23.7.146 | 255.255.255.252 |
| A3     | Westalis (eth2) | 10.23.7.1   | 255.255.255.128 |
| A3     | Forger          | 10.23.7.2   | 255.255.255.128 |
| A4     | Westalis (eth3) | 10.23.0.1   | 255.255.252.0   |
| A4     | Desmond         | 10.23.0.2   | 255.255.252.0   |
| A5     | Strix (eth2)    | 10.23.7.149 | 255.255.255.252 |
| A5     | Ostania (eth0)  | 10.23.7.150 | 255.255.255.252 |
| A6     | Ostania (eth1)  | 10.23.4.1   | 255.255.254.0   |
| A6     | Blackbell       | 10.23.4.2   | 255.255.254.0   |
| A7     | Ostania (eth2)  | 10.23.6.1   | 255.255.255.0   |
| A7     | Briar           | 10.23.6.2   | 255.255.255.0   |
| A8     | Ostania (eth3)  | 10.23.7.137 | 255.255.255.248 |
| A8     | Garden          | 10.23.7.138 | 255.255.255.248 |
| A8     | SSS             | 10.23.7.139 | 255.255.255.248 |

#### Konfigurasi Node

- Eden

```
auto eth0
iface eth0 inet static
address 10.23.7.130
netmask 255.255.255.248
gateway 10.23.7.129
```

- Wise

```
auto eth0
iface eth0 inet static
address 10.23.7.131
netmask 255.255.255.248
gateway 10.23.7.129
```

- Garden

```
auto eth0
iface eth0 inet static
address 10.23.7.138
netmask 255.255.255.248
gateway 10.23.7.137
```

- SSS

```
auto eth0
iface eth0 inet static
address 10.23.7.139
netmask 255.255.255.248
gateway 10.23.7.137
```

- Strix

```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
address 10.23.7.146
netmask 255.255.255.252

auto eth2
iface eth2 inet static
address 10.23.7.149
netmask 255.255.255.252
```

- Westalis

```
auto eth0
iface eth0 inet static
address 10.23.7.145
netmask 255.255.255.252
gateway 10.23.7.146

auto eth1
iface eth1 inet static
address 10.23.7.129
netmask 255.255.255.248

auto eth2
iface eth2 inet static
address 10.23.7.1
netmask 255.255.255.128

auto eth3
iface eth3 inet static
address 10.23.0.1
netmask 255.255.252.0
```

- Ostania

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.23.7.150
netmask 255.255.255.252
gateway 10.23.7.149

auto eth1
iface eth1 inet static
address 10.23.4.1
netmask 255.255.254.0

auto eth2
iface eth2 inet static
address 10.23.6.1
netmask 255.255.255.0

auto eth3
iface eth3 inet static
address 10.23.7.137
netmask 255.255.255.248
```

- Desmond

```
#auto eth0
#iface eth0 inet static
#address 10.23.0.2
#netmask 255.255.252.0
#gateway 10.23.0.1

auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp
```

- Briar

```
#auto eth0
#iface eth0 inet static
#address 10.23.6.2
#netmask 255.255.255.0
#gateway 10.23.6.1

auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp
```

- Blackbell

```
#auto eth0
#iface eth0 inet static
#address 10.23.4.2
#netmask 255.255.254.0
#gateway 10.23.4.1

auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp
```

- Forger

```
#auto eth0
#face eth0 inet static
#address 10.23.7.2
#netmask 255.255.255.128
#gateway 10.23.7.1

auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp
```

### C. Routing

- Konfigurasi Routing pada Strix
![image](https://user-images.githubusercontent.com/33245436/206869980-1770fc94-489c-42ff-8078-21c12c72e0c5.png)

- Tes ping dari Desmond ke Blackbell
![image](https://user-images.githubusercontent.com/33245436/206870021-0701624f-1b4e-4113-910f-57228381de89.png)

### D. DHCP Server & Relay

- Konfigurasi DHCP Server pada WISE
![image](https://user-images.githubusercontent.com/33245436/206870119-08bd535f-bb5e-4a08-a4ba-abee254e843c.png)
![image](https://user-images.githubusercontent.com/33245436/206870122-00392ac2-551e-4b86-8f7f-aa80f7dd41d3.png)

- Konfigurasi DHCP Relay pada Westalis & Ostania
![image](https://user-images.githubusercontent.com/33245436/206870154-91f9856d-7327-45fc-b5a0-a9bbe408c456.png)

- Lease pada Blackbell
![image](https://user-images.githubusercontent.com/33245436/206870238-27a43473-5fa7-4aa6-af83-7cf4e115615b.png)

### E. Firewall

1. Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi Strix menggunakan iptables, tetapi Loid tidak ingin menggunakan MASQUERADE.
  
  Lakukan pada router Strix :

  ```
  my_eth0_ip=$(/sbin/ifconfig eth0 | grep 'inet addr:' | cut -d: -f2 | awk '{ print $1 }')
  iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source "$my_eth0_ip" -s 10.23.0.0/21
  ```

  `my_eth0_ip` digunakan untuk mengambil ip dari interface eth0 dari `Strix` karena IP eth0 didapatkan dengan DHCP. Kemudian lakukan POSTROUTING Firewall tabel nat untuk mengubah source address dari luar menjadi address Strix
  
  Ping Google.com :
  ![image](https://user-images.githubusercontent.com/33245436/206870532-d124ea94-1898-4696-921d-45ba4ce3319a.png)
  ![image](https://user-images.githubusercontent.com/33245436/206870601-863d11e6-e3f7-4805-a140-02135f509775.png)

2. Kalian diminta untuk melakukan drop semua TCP dan UDP dari luar Topologi kalian pada server yang merupakan DHCP Server demi menjaga keamanan.

  Lakukan script ini pada Strix :

  ```
  iptables -A FORWARD -d 10.23.7.131 -p tcp -i eth0 -j DROP
  iptables -A FORWARD -d 10.23.7.131 -p udp -i eth0 -j DROP
  ```
  
  Testing :
  Dengan menginstall speedtest-cli lakukan `speedtest-cli --simple` pada Server WISE untuk pengecekan firewall

  Sebelum dilakukan Firewall blocking
  
  ![image](https://user-images.githubusercontent.com/33245436/206871904-e2b6ce5a-b58a-4c6f-ba36-0558eb8030dd.png)

  Sesudah dilakukan Firewall Blocking
  
  ![image](https://user-images.githubusercontent.com/33245436/206871946-91dff854-2782-436f-8a83-61b01d400b82.png)

3. Loid meminta kalian untuk membatasi DHCP dan DNS Server hanya boleh menerima maksimal 2 koneksi ICMP secara bersamaan menggunakan iptables, selebihnya didrop.

  Lakukan script ini pada WISE dan Eden :

  ```
  iptables -A INPUT -p icmp -m connlimit --connlimit-above 2 --connlimit-mask 0 -j REJECT
  ```
  
  Testing :
  Lakukan ping ke IP WISE atau Eden pada client Briar, Desmond, dan Forger. Pada saat ping yang ke-3, hasil dari ping akan seperti berikut
  ![image](https://user-images.githubusercontent.com/33245436/206870938-016dd6a7-8ec9-4eae-bf8e-cb239f4ecee6.png)
  ![image](https://user-images.githubusercontent.com/33245436/206870944-e5e3de97-8781-4b16-b42e-d9fb846f17a9.png)
  ![image](https://user-images.githubusercontent.com/33245436/206870955-1f813dae-a26f-4901-8998-217b7afec369.png)
  
4. Akses menuju Web Server hanya diperbolehkan disaat jam kerja yaitu Senin sampai Jumat pada pukul 07.00 - 16.00.
  
  Lakukan Script ini pada SSS dan Garden :

  ```
  iptables -A INPUT -m time --weekdays Mon,Tue,Wed,Thu,Fri --timestart 07:00 --timestop 16:00 -j ACCEPT
  iptabels -A INPUT -j REJECT
  ```
  
  Testing :
  Lakukan ping terhadap sss atau garden
  
  Di luar jam kerja
  ![image](https://user-images.githubusercontent.com/33245436/206871270-39125e32-7369-4bf5-b596-5577597859f2.png)

  Pada saat jam kerja
  ![image](https://user-images.githubusercontent.com/33245436/206871297-75e4755c-e023-4a45-9717-d93c1fa9a15e.png)

5. Karena kita memiliki 2 Web Server, Loid ingin Ostania diatur sehingga setiap request dari client yang mengakses Garden dengan port 80 akan didistribusikan secara bergantian pada SSS dan Garden secara berurutan dan request dari client yang mengakses SSS dengan port 443 akan didistribusikan secara bergantian pada Garden dan SSS secara berurutan.

  Lakukan scipt ini pada Ostania :

  ```
  iptables -A PREROUTING -t nat -p tcp --dport 80 -d 10.23.7.138 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.23.7.139:80
  iptables -A PREROUTING -t nat -p tcp --dport 443 -d 10.23.7.139 -m statistic --mode nth --every 2 --packet 0 -j DNAT --to-destination 10.23.7.138:443
  ```
  
  Testing :

  1. Nyalakan netcat pada SSS dan Garden terlebih dahulu `nc -l -p 80` atau `nc -l -p 443`
  2. Pakai client dan lakukan `nc (ip garden) 80` atau `nc (ip SSS) 443`
  3. Ketik apapun untuk pengetesan keakuratan

  ![image](https://user-images.githubusercontent.com/33245436/206871640-9c04eee8-c5bd-4dc4-a938-7bbe6afc8ea6.png)
  ![image](https://user-images.githubusercontent.com/33245436/206871645-d2627d8e-97a7-4fd9-945d-b9b9268d09b4.png)
  ![image](https://user-images.githubusercontent.com/33245436/206871647-3d8968e4-bc8f-418f-84e7-b5f719d14cb2.png)
  ![image](https://user-images.githubusercontent.com/33245436/206871649-f3c1ffca-f9e5-41d3-bd06-642958a3bcc7.png)  
