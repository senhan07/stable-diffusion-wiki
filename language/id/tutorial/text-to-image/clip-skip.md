# Clip Skip

Ini adalah slider dalam pengaturan, dan mengontrol seberapa dini pemrosesan prompt oleh jaringan CLIP harus dihentikan.



**Penjelasan yang lebih rinci:**

CLIP adalah jaringan neural yang sangat canggih yang mengubah teks prompt Anda menjadi representasi numerik. Jaringan saraf bekerja sangat baik dengan representasi numerik ini dan itulah mengapa pengembang SD memilih CLIP sebagai salah satu dari 3 model yang terlibat dalam metode difusi stabil untuk menghasilkan gambar. Karena CLIP adalah jaringan saraf, itu berarti CLIP memiliki banyak lapisan. Perintah Anda didigitalkan dengan cara yang sederhana, dan kemudian diumpankan melalui lapisan-lapisan. Anda mendapatkan representasi numerik dari prompt setelah lapisan pertama, Anda memasukkannya ke lapisan kedua, Anda memasukkan hasilnya ke lapisan ketiga, dan seterusnya, hingga Anda mencapai lapisan terakhir, dan itulah output CLIP yang digunakan dalam difusi stabil. Ini adalah nilai slider 1. Tetapi Anda dapat berhenti lebih awal, dan menggunakan output dari lapisan berikutnya ke lapisan terakhir - itu adalah nilai slider 2. Semakin cepat Anda berhenti, semakin sedikit lapisan jaringan saraf yang bekerja pada prompt.

Beberapa model dilatih dengan tweak semacam ini, jadi pengaturan nilai ini membantu menghasilkan hasil yang lebih baik pada model-model tersebut.
