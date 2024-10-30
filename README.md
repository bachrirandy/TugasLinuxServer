**Nama  : Mochammad Randy Surya Bachri**

**NIM   : 09011282328052**

**Kelas : SK3A**

**Dosen Pengampu Mata Kuliah: Adi Hermansyah, S.Kom., M.T**

---


# Akses Base Server dengan Protokol SSH
## 1. Protokol SSH
Secure Shell (SSH) adalah protokol jaringan yang digunakan untuk mengamankan komunikasi antara dua perangkat dalam jaringan, terutama untuk mengakses server secara remote. SSH mengenkripsi data yang dikirimkan, sehingga menjaga kerahasiaan dan integritas informasi selama proses transfer. Protokol ini biasanya berjalan pada port 22.

## 2. Tools yang digunakan
### 2.1 Operating System
#### 2.1.1 Host Side
Host Side Server yang digunakan kali ini merupakan OS yang berbasis server, di sini saya menggunakan Ubuntu Server 24.04.1 LTS. 
![Screenshot 2024-10-30 103557](https://github.com/user-attachments/assets/6b7eb845-0e5f-4ccd-9c8f-b168bdd27730)

#### 2.1.2 Client Side
Client Side OS menggunakan Kali Linux digunakan sebagai sistem operasi pada perangkat klien untuk menjalankan aplikasi atau mengakses layanan dari server. Dalam konteks ini, Kali Linux sebagai Client OS berperan sebagai interface pengguna yang langsung berinteraksi dengan layanan atau aplikasi yang disediakan oleh server.
![Screenshot 2024-10-30 103625](https://github.com/user-attachments/assets/c36cf4e4-d110-485a-8311-48a942075743)

## 3. Pembahasan
### 3.1 Cek IP Adress Host Server 
Lakukan dengan menggunakan command
```
$ ifconfig
```
![Screenshot 2024-10-30 103557](https://github.com/user-attachments/assets/57eb475f-96fc-4282-a84e-f4500a5328a4)

### 3.2 Cek Port pada Host Server dengan tools NMap 
Hal ini bisa dilakukan dengan menggunakan tools NMap pada Kali Linux untuk melihat open port pada Host Server, 

Berikut ini command nya:
```
$ nmap [ip address]
```
![Screenshot 2024-10-30 103832](https://github.com/user-attachments/assets/cedecd84-694c-4dc6-8def-b717d73b3a3f)

### 3.3 Melakukan koneksi pada port menggunakan protokol SSH
Untuk melakukan koneksi pada port menggunakan protokol SSH, dapat dilakukan dengan perintah berikut:
```
$ ssh -p 22 [Hostusername@HostIPAddress]
```
![Screenshot 2024-10-30 103851](https://github.com/user-attachments/assets/f9ec3280-5058-4b7a-91e2-075deb44fcc8)

### 3.4 Melakukan konfigurasi port 40 ke host server
#### 3.4.1 Masuk ke mode super users 
```
$ sudo su
```
![Screenshot 2024-10-30 104112](https://github.com/user-attachments/assets/52da53a9-471f-460c-b685-f2fdad29b7c1)

#### 3.4.2 Lakukan modifikasi pada file sshd_config
Sebelum melakukan modifikasi, lakukan copy terlebih dahulu pada file sshd_config dengan command:

```
cp /etc/ssh/sshd_config /etc/ssh/sshd_config.backup
```
Setelah itu, akses isi file sshd_config dan ubah port 22 ke port 40 dan masukkan Protocol 2 dengan command berikut:
```
nano /etc/sshd_config
```

![Screenshot 2024-10-30 203610](https://github.com/user-attachments/assets/64daa6ca-8a0d-4e5f-914f-5a4d198c4099)
![Screenshot 2024-10-30 110220](https://github.com/user-attachments/assets/bab72a7e-22c4-410f-9469-ec7ac95bafb9)

#### 3.4.3 Aktifkan dan terapkan perubahan port pada sistem
Lakukan konfirmasi dengan ufw agar perubahan dapat diterapkan. Berikut ini command nya:

```
$ ufw allow 40/tcp
$ ufw enable
```
Cek status dengan command:

```
$ ufw status
```
![Screenshot 2024-10-30 105748](https://github.com/user-attachments/assets/eade0ecf-65c0-494d-b6a0-106e233e6be2)

Cek status port dengan tulpn:
```
ss -tulpn | grep ssh
```
![Screenshot 2024-10-30 115854](https://github.com/user-attachments/assets/0f8e4298-5bca-4006-ba1d-1a42b1964eb2)

#### 3.4.4 Lakukan Koneksi pada Port 40
Cek dengan menggunakan port 22:
![Screenshot 2024-10-30 112156](https://github.com/user-attachments/assets/7a81e237-6896-43e7-9d8f-c37458f84127)

di sini dapat kita lihat bahwa port 22 sudah tidak bisa digunakan secara remote.

Lalu, cek dengan port 40
![Screenshot 2024-10-30 111814](https://github.com/user-attachments/assets/e44e83ec-f5cf-4521-bed9-4acda067e5e7)




























