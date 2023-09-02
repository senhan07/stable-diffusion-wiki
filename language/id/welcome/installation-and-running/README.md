---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Panduan Instalasi

### Google Colab

Tersedia di [colab-web-ui-links.md](colab-web-ui-links.md "mention")

***

Pastikan [dependencies](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Dependencies) yang diperlukan terpenuhi dan ikuti petunjuk yang tersedia untuk:

* [NVidia](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs) (disarankan)
* GPU [AMD](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-AMD-GPUs).
* [CPU Intel, GPU Intel (baik yang terintegrasi maupun yang terpisah)](https://github.com/openvinotoolkit/stable-diffusion-webui/wiki/Installation-on-Intel-Silicon) (halaman wiki eksternal)

### Windows

#### Instalasi pada Windows 10/11 dengan NVidia-GPU menggunakan paket rilis

1. Unduh `sd.webui.zip` dari [v1.0.0-pre](https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.0.0-pre) dan ekstrak isinya.
2. Jalankan `update.bat`.
3. Jalankan `run.bat`.

> Untuk detail lebih lanjut, lihat [Instal-dan-Jalankan-pada-NVidia-GPU](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs)

#### Instalasi Otomatis pada Windows

1. Instal [Python 3.10.6](https://www.python.org/downloads/release/python-3106/) (Versi Python yang lebih baru tidak mendukung torch), dengan mencentang "Add Python to PATH".
2. Instal [git](https://git-scm.com/download/win).
3. Unduh repositori stable-diffusion-webui, misalnya dengan menjalankan `git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git`.
4. Jalankan `webui-user.bat` dari Windows Explorer sebagai pengguna biasa, non-administrator, pengguna.

***

### Linux (Instalasi Otomatis)

1. Instal dependensi:

```bash
# Berbasis Debian:
sudo apt install wget git python3 python3-venv libgl1 libglib2.0-0
# Berbasis Red Hat:
sudo dnf install wget git python3
# Arch-based:
sudo pacman -S wget git python3
```

2. Arahkan ke direktori yang Anda inginkan untuk menginstal webui dan jalankan perintah berikut:

```bash
wget -q https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh
```

3. Jalankan `webui.sh`.
4. Periksa `webui-user.sh` untuk opsi.

***

### Apple Silicon

Temukan petunjuknya [di sini](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon).

***
