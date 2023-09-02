# Hires. fix

Pilihan untuk merender sebagian gambar Anda pada resolusi yang lebih rendah, meningkatkannya, dan kemudian menambahkan detail pada resolusi tinggi. Dengan kata lain, ini setara dengan menghasilkan gambar dalam txt2img, meningkatkannya melalui metode pilihan Anda, dan menjalankan pass kedua pada gambar yang sudah ditingkatkan skalanya di img2img untuk lebih menyempurnakan peningkatan dan menciptakan hasil akhir.

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
