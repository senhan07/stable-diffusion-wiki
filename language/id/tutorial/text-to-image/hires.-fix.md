# Hires. fix

## Apa itu Hires. fix ?

Berfungsi untuk merender sebagian gambar Anda pada resolusi yang lebih rendah, meningkatkannya, dan kemudian menambahkan detail pada resolusi tinggi. Dengan kata lain, ini setara dengan menghasilkan gambar dalam txt2img, meningkatkannya melalui metode pilihan Anda, dan menjalankan pass kedua pada gambar yang sudah ditingkatkan skalanya di img2img untuk lebih menyempurnakan peningkatan dan menciptakan hasil akhir.

Secara default, model berbasis SD1/2 menghasilkan gambar yang mengerikan pada resolusi yang sangat tinggi, karena model ini hanya dilatih pada 512px atau 768px. Metode ini memungkinkan untuk menghindari masalah ini dengan memanfaatkan komposisi gambar yang kecil dalam proses denoising pada versi yang lebih besar. Diaktifkan dengan mencentang kotak centang "Hires. fix" pada halaman txt2img.

|                                                         Non Aktif                                                         |                                                           Aktif                                                           |
| :-----------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------: |
| ![00262-836728130](https://user-images.githubusercontent.com/20920490/191177752-ad983e62-8e1c-4197-8f3b-3165a6a6c31d.png) | ![00261-836728130](https://user-images.githubusercontent.com/20920490/191177785-395a951e-0d2e-4db7-9645-4c5af9321772.png) |
| ![00345-950170121](https://user-images.githubusercontent.com/20920490/191178018-25dcd98d-6c45-4c31-ab7a-3de6c51c52e3.png) | ![00341-950170121](https://user-images.githubusercontent.com/20920490/191178048-3eba3db4-e5be-4617-9bfe-2cb36cebaafc.png) |

Gambar kecil dirender pada resolusi apa pun yang Anda tetapkan dengan menggunakan slider width/height. Dimensi gambar besar dikontrol oleh tiga penggeser: Pengali "Scale by" (Mengatur skala), "Resize width to" (Mengubah ukuran lebar ke) dan/atau "Resize height to" (Mengubah ukuran tinggi ke).

* Jika "Resize width to" dan "Resize height to" bernilai 0, maka "Scale by" digunakan.&#x20;
* Jika "Resize width to" bernilai 0, "Resize height to" dihitung dari lebar dan tinggi.&#x20;
* Jika "Resize width to" adalah 0, "Resize height to" dihitung dari lebar dan tinggi.&#x20;
* Jika "Resize width to" dan "Resize height to" bukan nol, gambar akan diperbesar setidaknya menjadi dimensi tersebut, dan beberapa bagian akan di crop

Jika "Ubah ukuran lebar ke" dan "Ubah ukuran tinggi ke" bukan nol, gambar akan diperbesar setidaknya menjadi dimensi tersebut, dan beberapa bagian akan dicrop. Pada versi webui yang lebih lama, lebar dan tinggi akhir dimasukkan secara manual (opsi terakhir yang tercantum di atas). Pada versi baru, standarnya yaitu menggunakan faktor "Scale by", yang merupakan standar dan lebih disukai.

***

## Lebih Lanjut

<figure><img src="../../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

**Upscaler:** Pilih upscaler yang akan digunakan

Berbagai opsi Latent upscaler menskalakan gambar dalam ruang laten. Hal ini dilakukan setelah langkah pengambilan sampel dari pembuatan teks-to-image. Prosesnya mirip dengan image-to-image.

**Hires steps:** Ini adalah jumlah langkah pengambilan sampel setelah meningkatkan gambar laten.

**Denoising strength:** Parameter ini memiliki arti yang sama seperti pada image-to-image. Parameter ini mengontrol noise yang ditambahkan ke gambar laten sebelum melakukan langkah pengambilan sampel Hires.

<figure><img src="../../.gitbook/assets/image (33).png" alt="" width="256"><figcaption><p>Original</p></figcaption></figure>

| ![](<../../.gitbook/assets/image (34).png>) | ![](<../../.gitbook/assets/image (35).png>) | ![](<../../.gitbook/assets/image (36).png>) |
| :-----------------------------------------: | :-----------------------------------------: | :-----------------------------------------: |
|                Denoising: 0.4               |               Denoising: 0.65               |                Denoising: 0.9               |

Kekuatan denoising dari latent upscaler harus lebih tinggi dari 0,5. Kalau tidak, Anda akan mendapatkan gambar yang buram.

Entah kenapa, harus lebih besar dari 0,5 untuk mendapatkan gambar yang tajam. Menetapkannya terlalu tinggi akan banyak mengubah gambar.

Manfaat menggunakan upscaler latent adalah kurangnya artefak peningkatan yang mungkin diperkenalkan oleh upscaler lain seperti ESRGAN. Decoder dari Stable Diffusion menghasilkan gambar, memastikan gayanya konsisten. Kekurangannya, ini akan mengubah gambar sampai batas tertentu, tergantung pada nilai kekuatan denoising.

Faktor kelas atas mengontrol berapa kali lebih besar gambar yang akan dihasilkan. Contohnya, menetapkannya ke 2 akan mengubah skala gambar 512x768 pixel menjadi 1024x1536 pixel.

Atau, Anda bisa menentukan nilai "resize width to" dan "resize height to" untuk menetapkan ukuran gambar yang baru.

Anda bisa menghindari masalah dalam menetapkan denoising dengan menggunakan model upscaler ESRGAN
