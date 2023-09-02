# Prompt Editing

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Pengeditan prompt memungkinkan Anda untuk mulai mengambil sampel satu gambar, tetapi di tengah-tengah, Anda dapat menukarnya dengan gambar yang lain. Sintaks dasar untuk ini adalah:

`[from:to:when]`

Di mana `from` dan `to` adalah teks sembarang, dan `when` adalah angka yang menentukan seberapa terlambat dalam siklus pengambilan sampel yang harus dilakukan peralihan. Semakin terlambat, semakin sedikit daya yang dimiliki model untuk menggambar teks `to` sebagai pengganti teks `from`. Jika `when` adalah angka antara 0 dan 1, ini adalah sebagian kecil dari jumlah langkah setelahnya untuk melakukan peralihan. Jika bilangan bulat yang lebih besar dari nol, maka itu adalah langkah setelahnya untuk melakukan peralihan.

* `[to:when]` - menambahkan `to` ke prompt setelah jumlah langkah tertentu (`when`)
* `[from::when]` - menghapus `from` dari prompt setelah jumlah langkah tertentu (`when`)

Berikut adalah contoh yang lebih kompleks dengan beberapa pengeditan:

{% code overflow="wrap" %}
```
fantasy landscape with a [mountain:lake:0.25] and [an oak:a christmas tree:0.75][ in foreground::0.6][ in background:0.25] [shoddy:masterful:0.5]
```
{% endcode %}

* di awal, `fantasy landscape with a mountain and an oak in foreground shoddy`
* setelah langkah 25, `fantasy landscape with a lake and an oak in foreground in background shoddy`
* setelah langkah  50, `fantasy landscape with a lake and an oak in foreground in background masterful`
* setelah langkah  60, `fantasy landscape with a lake and an oak in background masterful`
* setelah langkah  75, `fantasy landscape with a lake and a christmas tree in background masterful`

Gambar di bagian atas dibuat dengan prompt:

{% code overflow="wrap" %}
```
Official portrait of a smiling world war ii general, [male:female:0.99], cheerful, happy, detailed face, 20th century, highly detailed, cinematic lighting, digital art painting by Greg Rutkowski
```
{% endcode %}

Dan angka 0,99 diganti dengan apa pun yang Anda lihat dalam label kolom pada gambar.

\
Kolom terakhir pada gambar adalah `[male:female:0.0]`, yang pada dasarnya berarti bahwa Anda meminta model untuk menggambar wanita dari awal, tanpa memulai dengan jenderal pria, dan itulah sebabnya mengapa gambar ini terlihat sangat berbeda dari yang lain.

\
**Catatan**: Sintaks ini tidak bekerja dengan jaringan tambahan, seperti LoRA.
