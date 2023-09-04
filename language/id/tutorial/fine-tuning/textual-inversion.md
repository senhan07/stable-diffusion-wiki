# Textual Inversion

## Apa itu Textual inversion ?

Textual inversion adalah teknik yang digunakan dalam Stable Diffusion untuk menambahkan gaya atau objek baru ke model text-to-image tanpa mengubah model yang mendasarinya. Teknik ini memungkinkan pembuatan gambar berdasarkan konsep yang diberikan pengguna dengan mendefinisikan kata kunci baru dan menemukan vektor embedding yang sesuai dalam model bahasa.

Berikut adalah poin-poin penting untuk memahami tentang textual inversion dalam Stable Diffusion:

* Textual inversion memungkinkan komposisi kalimat berbahasa alami menggunakan "kata-kata" baru dalam ruang embedding model, yang dapat menangkap konsep yang beragam dan berbeda.
* Biasanya hanya membutuhkan 3-5 gambar contoh untuk mendefinisikan konsep baru dan menghasilkan gambar berdasarkan konsep tersebut.
* Berkas textual inversion, yang berisi embedding, biasanya memiliki ukuran 10-100KB dan memiliki ekstensi file seperti .pt atau .safetensors.
* Prosesnya melibatkan pelatihan model Stable Diffusion menggunakan textual inversion dengan menyediakan sekumpulan gambar yang mewakili konsep yang diinginkan.
* Textual inversion dapat digunakan untuk personalisasi pembangkitan gambar dan menambahkan gaya atau objek baru ke pipa teks-ke-gambar.
