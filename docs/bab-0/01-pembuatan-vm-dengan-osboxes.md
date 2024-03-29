# Persiapan Lingkungan Praktikum

## Prasyarat

Pastikan kalian sudah memasang virtualbox atau vmware atau vm manager lain pada sistem operasi kalian.

## Unduh Linux Box dari Osboxes

Download image ubuntu dengan DE yang sesuai dengan kemampuan laptop.

Jika RAM kurang dari 8 GB, bisa mencoba menggunakan [Xubuntu](https://www.osboxes.org/xubuntu/) atau [Lubuntu](https://www.osboxes.org/lubuntu/). Jika RAM diatas 8 GB, bisa menggunakan [Ubuntu](https://www.osboxes.org/ubuntu/) GNOME Biasa. Unduh flavor ubuntu yang sesuai di versi 20.04. Box lainnya bisa dilihat di laman resmi [osboxes](https://www.osboxes.org/virtualbox-images/), untuk praktikum KI disarankan memakai Ubuntu GNOME atau Xubuntu. Untuk yang menggunakan vm manager lain bisa menyesuaikan.

![osboxes-web](images/000_01.png)

## Pembuatan Mesin Virtual Baru

Klik ikon New,

![klik-new](images/000_02.png)

Sesuaikan nama dan folder tempat penyimpanan data mesin virtual dan tipe serta jenisnya.

![deskripsi-vm](images/000_03.png)

Alokasikan memori RAM untuk mesin virtual. Untuk Xubuntu, minimal alokasi memori RAM adalah 512 MB namun, disarankan untuk melebihinya seperti di 1024 MB atau 1536 MB. Untuk Ubuntu GNOME, disarankan untuk mengalokasikan memori minimal 4096 MB.

![alokasi-memori](images/000_04.png)

> Jika menggunakan xubuntu, untuk beberapa praktikum yang menggunakan aplikasi berbasis java (ghidra) mungkin tidak bisa dijalankan. Solusinya adalah menjalankan ghidra di OS Host secara langsung.

Klik ikon folder untuk membuka file yang telah didownload tadi.

![open-osboxes](images/000_05.png)

Klik Add,

![klik-add-box](images/000_06.png)

Arahkan ke tempat di mana kalian mengekstrak file vdi dari box yang kalian download pada osboxes. Klik open.

![choose-box](images/000_07.png)

Klik *Choose* untuk memilih file yang kita tambahkan tadi.

> Jangan khawatir dengan virtual size yang sangat besar. Ukuran tersebut tidak akan dialokasikan langsung ke penyimpanan, namun dialokasikan secara dinamis sesuai dengan total ukuran file-file yang ada di mesin virtual.

![choose](images/000_08.png)

Klik create untuk membuat mesin virtual.

![create-vm](images/000_09.png)

Klik start untuk memulai Mesin virtual

![start-vm](images/000_10.png)

Login menggunakan password default osboxes, yaitu `osboxes.org` dan Mesin Virtual sudah jadi.

![login-user-osboxes](images/000_11.png)

> A little tip, ukuran resolusi default vm pada virtualbox adalah 4:3. Untuk mengganti resolusi bisa menuju ke pengaturan display pada **mesin virtual**nya, set ke resolusi atau ukuran yang diinginkan seperti 1280x720 atau 1600x900 dst.

## [Optional] Setup User Baru dan Ubah hostname

Tambahkan user baru dengan username bebas dan password yang aman.

```bash
sudo adduser username
```

![add-user](images/000_18.png)

Tambahkan ke grup sudo agar bisa menjalankan command sudo

```bash
sudo usermod -aG sudo username
```

Lalu, jalankan command berikut untuk membuat user baru tidak perlu memasukkan password setiap kali ingin menjalankan sudo.

```bash
sudo bash -c 'echo "username ALL=(ALL) NOPASSWD:ALL" | tee /etc/sudoers.d/username'
```

![add-to-sudoers](images/000_19.png)

Ganti menjadi user baru,

```bash
su - bob
```

Ganti lagi menjadi user `root` melalui user baru yang dibuat tadi,

```bash
sudo -i
```

![add-sudo-without-pass](images/000_20.png)

Ganti hostname dengan menjalankan 2 perintah berikut dengan user `root`,

```bash
hostname username-praktikum-ki
echo 'username-praktikum-ki' > /etc/hostname
```

![hostname-change](images/000_21.png)

Exit dari `root` dan login menjadi `root` lagi dengan perintah `sudo -i`.

![test-hostname](images/000_22.png)

Reboot mesin virtual,

```bash
sudo shutdown -r now
```

![reboot-vm](images/000_23.png)

Login dengan user baru.

![osboxes-web](images/000_24.png)
