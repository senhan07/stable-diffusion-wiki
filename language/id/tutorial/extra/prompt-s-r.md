# Prompt S/R

Prompt S/R adalah salah satu mode operasi yang lebih sulit untuk dipahami untuk X/Y Plot. S/R adalah singkatan dari search/replace, dan itulah yang dilakukannya - Anda memasukkan daftar kata atau frasa, ia mengambil yang pertama dari daftar dan memperlakukannya sebagai kata kunci, dan mengganti semua contoh dari kata kunci tersebut dengan entri lain dari daftar.

Misalnya, dengan prompt `a man holding an apple, 8k clean` dan Prompt S/R `an apple, a watermelon, a gun` Anda akan mendapatkan tiga prompt:

* `a man holding an apple, 8k clean`
* `a man holding a watermelon, 8k clean`
* `a man holding a gun, 8k clean`

Daftar ini menggunakan sintaks yang sama dengan baris dalam file CSV, jadi jika Anda ingin memasukkan koma ke dalam entri Anda, Anda harus meletakkan teks dalam tanda kutip dan memastikan tidak ada spasi di antara tanda kutip dan tanda koma pemisah:

* `darkness, light, green, heat` - 4 items - `darkness`, `light`, `green`, `heat`
* `darkness, "light, green", heat` - <mark style="background-color:red;">SALAH</mark> - 4 items - `darkness`, `"light`, `green"`, `heat`
* `darkness,"light, green",heat` - <mark style="background-color:green;">BENAR</mark> - 3 items - `darkness`, `light, green`, `heat`
