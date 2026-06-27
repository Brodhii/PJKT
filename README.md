# 🌐 Implementasi Perancangan Jaringan Kampus Terintegrasi

---

## 👥 Anggota Kelompok

| Nama Anggota | NIM |
| :--- | :--- |
| **Azharrodhi Gustiarya** | 2401020048 |
| **Rizka Sufianty** | 2401020053 |
| **Piky Al Piandi** | 2401020062 |
| **Abdal Ghyfran Kh** | 2401020078 |
| **Nurul Aida** | 2401020072 |

---

## 🗺️ Topologi Jaringan

Berikut adalah diagram arsitektur topologi jaringan yang diimplementasikan dalam simulasi ini:

<img width="1390" height="861" alt="Topologi Jaringan GNS3" src="https://github.com/user-attachments/assets/e77f86c3-ed8a-455d-895e-d61430de9462" />

---

## 🎬 Dokumentasi & Berkas Pendukung

* **Video Demo Proyek:** [Klik Video Demo melalui Google Drive](https://drive.google.com/drive/folders/1fOF5-LEBDBDR5VujHOBvXhSbEevjx95v?usp=sharing)

---

## 🛠️ Panduan Instalasi & Konfigurasi Sistem

> ⚠️ **Pemberitahuan Penting:** Simulasi ini mengintegrasikan *node* berbasis VirtualBox. Guna menghindari kendala kegagalan sistem (*VirtualBox node missing/not found*), Anda diharapkan mengikuti tahapan persiapan di bawah ini secara berurutan dari awal hingga akhir sebelum menjalankan berkas konfigurasi utama GNS3.

### 1. Pengunduhan Berkas Master VM dan Repositori
1. Silakan mengunduh berkas master mesin virtual terlebih dahulu melalui tautan berikut: 📦 **[Unduh Berkas OVA Master VM](https://drive.google.com/drive/folders/17y2o1aPE6UT0di-_Bt5n41KY599z9hNS?usp=sharing)**
2. Unduh atau dapatkan berkas repositori proyek GitHub ini pada sistem operasi Linux maupun Windows melalui salah satu metode berikut:
    * **Metode A (Unduh ZIP):** Klik tombol **Code > Download ZIP** di bagian atas halaman GitHub ini, lalu berkas kompresi `.zip` tersebut **wajib diekstrak** ke direktori kerja proyek lokal Anda:
        * **Pengguna Linux:** `/home/nama_user/GNS3/projects/`
        * **Pengguna Windows:** `C:\Users\Nama_User\GNS3\projects\`
    * **Metode B (Git Clone):** Jalankan perintah berikut melalui Terminal (Linux) atau Command Prompt / Git Bash (Windows):
        * **Linux:** `cd ~/GNS3/projects/ && git clone https://github.com/username_anda/nama_repositori_anda.git`
        * **Windows:** `cd C:\Users\Nama_User\GNS3\projects\ && git clone https://github.com/username_anda/nama_repositori_anda.git`

### 2. Impor Berkas Master VM ke VirtualBox
1. Buka aplikasi **VirtualBox** pada komputer Anda.
2. Pilih menu **File > Import Appliance...**.
3. Lakukan impor terhadap ketiga berkas master `.ova` yang telah diunduh hingga selesai:
   * `R1 GEDUNG A`
   * `UBUNTU SERVER DHCP`
   * `Windows Client A`

### 3. Prosedur Kloning VM (Melengkapi Kebutuhan Node Perangkat)
Platform GNS3 mengidentifikasi nama perangkat secara spesifik. Silakan klik kanan pada setiap VM master yang baru diimpor di VirtualBox, pilih opsi **Clone**, lalu buat duplikat perangkat dengan format penamaan yang persis sama sebagai berikut:

* **Komponen Router (MikroTik):**
  * Duplikasi `R1 GEDUNG A` menjadi ➡️ **`R2 GEDUNG B`**
  * Duplikasi `R1 GEDUNG A` kembali menjadi ➡️ **`R3 GEDUNG C`**
* **Komponen Server (Ubuntu):**
  * Duplikasi `UBUNTU SERVER DHCP` menjadi ➡️ **`UBUNTU SERVER DNS`**
* **Komponen Client (Windows):**
  * Duplikasi `Windows Client A` menjadi ➡️ **`Windows Client B`**
  * Duplikasi `Windows Client A` kembali menjadi ➡️ **`Windows Client C`**

### 4. Registrasi Perangkat pada Preferences GNS3
Setelah seluruh komponen mesin virtual (Total 8 VM) tersedia di VirtualBox, masukkan perangkat-perangkat tersebut ke dalam daftar sistem emulator GNS3:
1. Buka aplikasi **GNS3**, lalu masuk ke menu **Edit > Preferences**.
2. Pada panel menu sebelah kiri, pilih **VirtualBox > VirtualBox VMs**.
3. Klik tombol **New** di bagian bawah.
4. Pada opsi *dropdown* **VM List**, pilih dan daftarkan kedelapan perangkat berikut secara bertahap satu per satu:
   * `R1 GEDUNG A`
   * `R2 GEDUNG B`
   * `R3 GEDUNG C`
   * `UBUNTU SERVER DHCP`
   * `UBUNTU SERVER DNS`
   * `Windows Client A`
   * `Windows Client B`
   * `Windows Client C`
5. Klik **Finish** untuk setiap mesin yang baru dimasukkan, lalu simpan konfigurasi dengan mengklik tombol **Apply** dan **OK**.

### 5. Eksekusi Berkas Proyek Utama
Setelah tahapan persiapan di atas selesai dilakukan:
1. Pada aplikasi GNS3, pilih menu **File > Open Project**.
2. Arahkan pada berkas **`PJKT jarkom.gns3`** di dalam folder kerja proyek yang telah Anda unduh/ekstrak dari GitHub.
3. Seluruh komponen jaringan di dalam lembar kerja topologi akan otomatis tersinkronisasi dengan mesin virtual lokal dan siap untuk disimulasikan.

---

## 📌 Ringkasan Proyek

Proyek praktikum ini berfokus pada rancang bangun dan pengujian infrastruktur jaringan komputer berskala lokal yang diimplementasikan pada lingkungan multi-gedung. Cakupan pengerjaan proyek ini meliputi:
* **Simulasi Topologi:** Menggunakan platform GNS3 sebagai lingkungan emulator utama.
* **Manajemen Alokasi IP:** Konfigurasi DHCP Server beserta implementasi **DHCP Relay** antar subnet.
* **Routing Jaringan:** Penerapan *static routing* guna menghubungkan interkoneksi jalur antar gedung.
* **Layanan Resolusi Nama:** Implementasi DNS Server lokal berbasis **BIND9**.
* **Sistem Operasi Router:** Konfigurasi manajemen perangkat menggunakan **MikroTik RouterOS** serta pengujian konektivitas *end-to-end*.

---
