---
description: Bobot kata pada prompt
---

# Attention / Emphasis

## Bobot

Menggunakan `()` pada prompt akan meningkatkan bobot pada kata-kata yang diapit, dan `[]` akan menurunkannya. Anda dapat menggabungkan beberapa pengubah:

<div data-full-width="false">

<figure><img src="../../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

</div>

* `a (word)` - meningkatkan bobot pada `word` dengan faktor 1.1
* `a ((word))` -meningkatkan bobot pada `word` dengan faktor 1.21 (= 1.1 \* 1.1)
* `a [word]` - mengurangi bobot pada `word` dengan faktor 1.1
* `a (word:1.5)` - meningkatkan bobot pada `word` dengan faktor of 1.5
* `a (word:0.25)` - kurangi bobot pada kata dengan faktor 4 (= 1 / 0.25)
* `a \(word\)` - gunakan karakter literal () dalam prompt

Dengan `()`, bobot dapat ditentukan seperti ini: `(text:1.4)`. Jika bobot tidak ditentukan, maka diasumsikan sebagai `1.1`. Menentukan bobot hanya dapat dilakukan dengan `()`, bukan dengan `[]`.

Jika Anda ingin menggunakan salah satu karakter literal `()[]` dalam prompt, gunakan garis miring untuk menghilangkannya: `anime_(character)`.
