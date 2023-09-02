# X/Y/Z plot

Membuat beberapa kisi-kisi gambar dengan parameter yang bervariasi. X dan Y digunakan sebagai baris dan kolom, sedangkan kisi Z digunakan sebagai dimensi batch.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Pilih parameter mana yang harus dibagi berdasarkan baris, kolom, dan batch dengan menggunakan bidang Tipe X, Tipe Y, dan Tipe Z, dan masukkan parameter tersebut yang dipisahkan dengan koma ke dalam bidang nilai X/Y/Z. Untuk bilangan bulat, bilangan titik mengambang, dan rentang didukung. Contoh:

* Rentang sederhana:&#x20;
  * `1-5` = 1, 2, 3, 4, 5&#x20;
* Rentang dengan kenaikan dalam tanda kurung:&#x20;
  * `1-5 (+2)` = 1, 3, 5&#x20;
  * `10-5 (-3)` = 10, 7&#x20;
  * `1-3 (+0.5)` = 1, 1.5, 2, 2.5, 3&#x20;
* Rentang dengan hitungan dalam tanda kurung siku:&#x20;
  * `1-10 [5]` = 1, 3, 5, 7, 10&#x20;
  * `0.0-1.0 [6]` = 0.0, 0.2, 0.4, 0.6, 0.8, 1.0
