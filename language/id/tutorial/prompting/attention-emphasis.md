---
description: Penekanan kata pada prompt
---

# Attention / Emphasis

## Emphasis / Penekanan

Menggunakan `()` pada prompt akan meningkatkan penekanan pada kata-kata yang diapit, dan `[]` akan menurunkannya. Anda dapat menggabungkan beberapa pengubah:

<div data-full-width="false">

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>

</div>

* `a (word)` - meningkatkan penekanan pada `word` dengan faktor 1.1
* `a ((word))` -meningkatkan penekanan pada `word` dengan faktor 1.21 (= 1.1 \* 1.1)
* `a [word]` - mengurangi penekanan pada `word` dengan faktor 1.1
* `a (word:1.5)` - meningkatkan perhatian pada `word` dengan faktor of 1.5
* `a (word:0.25)` - kurangi perhatian pada kata dengan faktor 4 (= 1 / 0.25)
* `a \(word\)` - gunakan karakter literal () dalam prompt

Dengan `()`, bobot dapat ditentukan seperti ini: `(text:1.4)`. Jika bobot tidak ditentukan, maka diasumsikan sebagai `1.1`. Menentukan bobot hanya dapat dilakukan dengan `()`, bukan dengan `[]`.

Jika Anda ingin menggunakan salah satu karakter literal `()[]` dalam prompt, gunakan garis miring untuk menghilangkannya: `anime_(character)`.
