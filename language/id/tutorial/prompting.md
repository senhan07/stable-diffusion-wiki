---
description: Panduan untuk membuat prompt yang efektif dalam Stable Diffusion.
---

# Prompting

Mari kita langsung saja ke pokok permasalahan: Anda telah memilih salah satu AI, Anda memiliki ide yang ingin ditangkap oleh AI, Anda menulis perintah, Anda menekan tombol dan...

Ini mengerikan.

Apa yang terjadi?

Anda telah merencanakan semuanya di kepala Anda, dan dari gambar-gambar yang Anda lihat, semua orang mendapatkan hasil yang luar biasa. Mengapa anda tidak?

Biar kutebak, Anda telah menulis sesuatu seperti "a green valley with mountains at the back? Anda belum menentukan hal lain. Itu perintah mentah. Sesuatu yang perlu Anda ingat adalah bahwa AI bukanlah pembaca pikiran (masih belum) dan sangat penting bagi AI untuk memahami apa yang Anda coba katakan kepadanya.

Ingat beberapa tahun yang lalu, ketika lagu "Despacito" ada di mana-mana? Dan kecuali Anda adalah orang yang bisa berbahasa Spanyol, liriknya tidak dapat dipahami. Namun, semua orang di seluruh dunia bernyanyi mengikuti lagu tersebut dan memintanya di setiap pub - tidak terlalu peduli atau, pada akhirnya, mendapatkan liriknya dengan benar. Hal serupa juga terjadi saat meminta petunjuk - Anda akan mendapatkan hasil dari AI, namun tidak seakurat yang Anda inginkan karena Anda hampir tidak dapat berkomunikasi dengan AI, dan dialognya tidak dapat dimengerti. Kemudian lagi, Anda akan mendapatkan apa yang Anda coba pada suatu saat, ketika Anda mempelajari apa yang harus dan tidak boleh ditanyakan kepada AI. Beruntung bagi Anda, itulah yang akan dibahas dalam panduan ini.

### **General prompting**

Dalam hal prompting, ada lebih dari satu cara, meskipun ada beberapa trik yang digunakan semua orang.

### **Raw prompt**

Ini adalah cara paling sederhana untuk menggambarkan apa yang ingin Anda hasilkan, seperti:

* A dog
* A knight on a horse
* Hamburger

Ini adalah cara paling dasar untuk membuat  prompt apa pun. Kebanyakan orang baru memulai dengan hanya menggunakan prompt mentah. Namun, ini bisa menjadi kesalahan, karena gambar yang Anda hasilkan dengan cara ini cenderung acak dan kacau. Ini adalah gambar yang saya hasilkan dengan menggunakan petunjuk di atas:



| ![](<../.gitbook/assets/image (4).png>) | ![](<../.gitbook/assets/image (6).png>) | ![](<../.gitbook/assets/image (7).png>) |
| --------------------------------------- | --------------------------------------- | --------------------------------------- |

Seperti yang Anda lihat, gambar-gambar ini memiliki style yang acak dan tidak terlihat sangat estetis, gambar-gambar ini dapat dianggap sebagai konsep dasar seni, tetapi kita tahu bahwa kita dapat melakukan yang lebih baik.

Dan itu membawa saya ke poin berikutnya...

### **Style**

Style adalah salah satu bagian yang paling penting dari prompt. AI, apabila tidak memiliki style tertentu, biasanya memilih style yang paling sering terlihat pada gambar terkait (seperti pada anjing di atas, misalnya). Memiliki style yang dipilih dengan baik + prompt mentah, terkadang sudah cukup, karena style paling memengaruhi gambar setelah prompt mentah.

Berikut ini adalah beberapa style.

| <img src="../.gitbook/assets/image (8).png" alt="" data-size="original"> | <p></p><p><img src="../.gitbook/assets/image (9).png" alt=""></p> |
| :----------------------------------------------------------------------: | :---------------------------------------------------------------: |
|                                 Realistic                                |                            Oil-painting                           |
|                 ![](<../.gitbook/assets/image (10).png>)                 |              ![](<../.gitbook/assets/image (11).png>)             |
|                              Pencil drawing                              |                            Concept Art                            |

Namun demikian, jika ada artis tertentu yang Anda sukai, mengapa tidak menggunakan namanya dalam prompt? Apa salahnya?

***

### **Bagaimana menjadi lebih deskriptif**

Ini bisa menjadi bagian yang paling sulit. Ironis, ya? Tapi memang benar - kita terkadang kesulitan dengan fakta bahwa kita memiliki gambaran ini di kepala kita dan tidak memiliki kata-kata yang cukup atau akurat untuk mendeskripsikannya. Oleh karena itu, AI akan memberikan kita gambar yang mungkin cukup dekat dengan ide kita, tetapi tidak sepenuhnya.

Berikut adalah beberapa tips yang dapat membantu Anda dengan masalah ini:

* <mark style="background-color:orange;">**Urutan itu penting!!!**</mark> Ingatlah bahwa urutan itu penting - kata-kata yang berada di dekat bagian depan atau awal prompt memiliki bobot yang lebih besar dibandingkan dengan kata-kata yang berada di bagian belakang prompt.
* Jika Anda masih menggunakan kata "very" sebelum kata lainnya, <mark style="background-color:orange;">**HENTIKAN.SEGERA**</mark>. Cobalah untuk menemukan kata yang lebih tepat daripada menambahkan kata "very" pada semua kata.&#x20;

Coba ikuti langkah-langkah berikut ini: **content type > description > style > composition**

* **Content type**: Jenis karya seni apa yang ingin Anda capai? Apakah foto, gambar, sketsa, render 3D...?
* **Description**: tentukan subjek, atribut subjek, lingkungan/pemandangan. Semakin deskriptif Anda menggunakan kata sifat, semakin baik hasilnya.
* **Style**: kita telah melihat yang paling umum di atas, tetapi ada juga "sub-kategori" - lightning, detail…
* **Composition**: mengacu pada rasio aspek, tampilan kamera dan resolusi.

***

### **Prompt Tambahan**

Terakhir, ada beberapa kata untuk meningkatkan prompt Anda, dan tentu saja, gambar yang akan Anda dapatkan. Ini bisa dianggap sebagai sentuhan akhir, dan Anda bisa menambahkan sebanyak dan seacak yang Anda inginkan, tetapi berikut ini ada beberapa contohnya:

#### Lighting

{% code overflow="wrap" %}
```
accent lighting, ambient lighting, backlight, blacklight, blinding light, candlelight, concert lighting, crepuscular rays, direct sunlight, dusk, Edison bulb, electric arc, fire, fluorescent, glowing, glowing radioactively, glow-stick, lava glow, moonlight, natural lighting, neon lamp, nightclub lighting, nuclear waste glow, quantum dot display, spotlight, strobe, sunlight, ultraviolet, dramatic lighting, dark lighting, soft lighting, gloomy
```
{% endcode %}

#### Detail

{% code overflow="wrap" %}
```
highly detailed, grainy, realistic, unreal engine, octane render, bokeh, vray, houdini render, quixel megascans, depth of field (or dof), arnold render, 8k uhd, raytracing, cgi, lumen reflections, cgsociety, ultra realistic, volumetric fog, overglaze, analog photo, polaroid, 100mm, film photography, dslr, cinema4d, studio quality
```
{% endcode %}

#### Artistic techniques and materials

{% code overflow="wrap" %}
```
Digital art, digital painting, color page, featured on pixiv (for anime/manga), trending on artstation, precise line-art, tarot card, character design, concept art, symmetry, golden ratio, evocative, award winning, shiny, smooth, surreal, divine, celestial, elegant, oil painting, soft, fascinating, fine art
```
{% endcode %}

#### **Camera view and quality**

{% code overflow="wrap" %}
```
ultra wide-angle, wide-angle, aerial view, massive scale, street level view, landscape, panoramic, bokeh, fisheye, dutch angle, low angle, extreme long-shot, long shot, close-up, extreme close-up, highly detailed, depth of field (or dof), 4k, 8k uhd, ultra realistic, studio quality, octane render,
```
{% endcode %}

#### **Style and composition**

{% code overflow="wrap" %}
```
Surrealism, trending on artstation, matte, elegant, illustration, digital paint, epic composition, beautiful, the most beautiful image ever seen,
```
{% endcode %}

#### **Colours**

```
Triadic colour scheme, washed colour
```

Source: [https://prompthero.com/stable-diffusion-prompt-guide](https://prompthero.com/stable-diffusion-prompt-guide)
