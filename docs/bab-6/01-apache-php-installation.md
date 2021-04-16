# Apache PHP installation

## Install Apache2 dan PHP pada Ubuntu

Instalasi apache2 dan php dapat dilakukan dengan perintah berikut,

```bash
sudo bash -c "apt update && apt install apache2 php libapache2-mod-php"
```

![install php apache](images/01_001.png)

Pastikan apache sudah berjalan dengan perintah,

```bash
sudo systemctl status apache2
```

![get-apache-status](images/01_002.png)

Jika belum memiliki status *running*, jalankan dengan perintah berikut,

```bash
sudo systemctl start apache2
```

Untuk membuat apache selalu berjalan ketika komputer pertama kali dinyalakan, jalankan perintah berikut.

```bash
sudo systemctl enable apache2
```
