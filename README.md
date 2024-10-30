**Nama: Mochammad Randy Surya Bachri**

**NIM: 09011282328052**

**Kelas: SK3A**

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
$ ifconfig
![Screenshot 2024-10-30 103557](https://github.com/user-attachments/assets/57eb475f-96fc-4282-a84e-f4500a5328a4)

### 3.2 Cek Port pada Host Server dengan tools NMap 
Hal ini bisa dilakukan dengan menggunakan tools NMap pada Kali Linux untuk melihat open port pada Host Server, Berikut ini command nya:
$ nmap [ip address]
![Screenshot 2024-10-30 103832](https://github.com/user-attachments/assets/cedecd84-694c-4dc6-8def-b717d73b3a3f)

### 3.3 Melakukan koneksi pada port menggunakan protokol SSH
Untuk melakukan koneksi pada port menggunakan protokol SSH, dapat dilakukan dengan perintah berikut:
$ ssh -p 22 [Hostusername@HostIPAddress]
![Screenshot 2024-10-30 103851](https://github.com/user-attachments/assets/f9ec3280-5058-4b7a-91e2-075deb44fcc8)

### 3.4 


















