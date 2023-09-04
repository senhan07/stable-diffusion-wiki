# Clip Skip

## Apa itu Clip Skip ?

* Memungkinkan Anda melewatkan sebagian lapisan model CLIP apabila menghasilkan gambar. Hal ini bisa berguna untuk mendapatkan hasil yang lebih kreatif, karena model CLIP terkadang terlalu spesifik dalam deskripsinya.
* Dapat mempercepat proses pembuatan gambar, karena algoritme tidak perlu memproses banyak lapisan model CLIP.

Jumlah Clip Skip yang Anda gunakan, akan bergantung pada gambar spesifik yang ingin Anda hasilkan dan hasil yang Anda inginkan. Jika Anda ingin mendapatkan hasil yang sangat spesifik, maka Anda dapat menggunakan nilai Clip Skip yang lebih rendah. Jika Anda ingin mendapatkan hasil yang lebih kreatif, maka Anda dapat menggunakan nilai Clip Skip yang lebih tinggi.

<figure><img src="../../.gitbook/assets/image (37).png" alt=""><figcaption></figcaption></figure>

Berikut ini ada beberapa contoh, bagaimana Clip Skip dapat mempengaruhi hasil pembuatan gambar:

* Dengan nilai Clip Skip 1, algoritma hanya akan menggunakan lapisan pertama model CLIP. Hal ini akan memberi Anda gambar yang sangat spesifik, yang sangat selaras dengan prompt teks.
* Dengan nilai Clip Skip 2, algoritma akan menggunakan dua lapisan pertama model CLIP. Ini akan memberi Anda gambar yang lebih abstrak yang masih selaras dengan prompt teks, tetapi akan memiliki lebih banyak kebebasan berkreasi.
* Dengan nilai Clip Skip 3, algoritma akan menggunakan tiga lapisan pertama dari model CLIP. Ini akan memberikan Anda gambar yang lebih abstrak yang mungkin tidak selaras dengan prompt teks, tetapi akan memiliki lebih banyak kebebasan berkreasi.

Pada akhirnya, cara terbaik untuk menemukan nilai Clip Skip yang tepat untuk gambar Anda yaitu, bereksperimen. Cobalah nilai yang berbeda-beda dan lihat hasil yang Anda dapatkan.

\
Berikut ini ada beberapa hal tambahan yang perlu diingat apabila menggunakan Clip Skip:

* Semakin tinggi nilai Clip Skip, semakin abstrak gambarnya.
* Semakin tinggi nilai Clip Skip, semakin lama proses pembuatan gambar.
* Sebagian model mungkin tidak berfungsi dengan baik dengan nilai Clip Skip yang tinggi.

## Menentukan Clip Skip

Pada umumnya, nilai 1 atau 2 pada Clip Skip dapat menghasilkan hasil yang memuaskan. Namun demikian, secara berlebihan dapat menyebabkan gambar yang dihasilkan tidak menyerupai dengan prompt.

## Kompatibilitas yang tidak konsisten

Clip Skip dapat menjadi tidak dapat diprediksi ketika digunakan dengan teknologi lain, seperti LoRA. Pengguna harus mengingat hal ini ketika bereksperimen dengan kombinasi ini.

## Implikasi untuk model yang lebih baru

Model Stable Diffusion 2.1 yang lebih baru menggunakan teknologi CLIP yang berbeda (OpenClip), sehingga Clip Skip tidak relevan untuk versi ini.

## Classifier-free guidance (CFG) vs. Clip Skip

Skala CFG dan Clip Skip berinteraksi secara berbeda dengan model. Sementara CFG menentukan bagaimana secara spesifik AI menavigasi dalam model, Clip Skip menentukan bagaimana model dinavigasi. Memahami perbedaan ini dapat membantu mengoptimalkan penggunaan fitur-fitur ini untuk menghasilkan gambar yang lebih tepat dan kreatif.
