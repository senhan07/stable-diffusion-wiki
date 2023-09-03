---
description: Apa yang kamu harus tau
---

# Istilah Dasar

## Diffusing

Mekanisme yang digunakan oleh model pembangkitan gambar AI untuk menghasilkan gambar.&#x20;

Singkatnya: AI memulai dengan gambar yang seluruhnya terdiri atas noise acak, dan langkah demi langkah mencoba menghilangkan noise hingga gambar akhir tercipta. Noise yang dihilangkan pada setiap langkah dikondisikan oleh perintah yang diberikan, begitulah cara Anda mendapatkan gambar yang jernih dan bukan hanya noise acak.

## Render

Tindakan mengubah representasi abstrak dari suatu gambar menjadi gambar akhir. Dalam pemodelan 3D, jika Anda membuat model 3D, itu hanyalah poligon dan persamaan matematika. Untuk mendapatkan gambar yang sebenarnya dari mereka, Anda perlu merendernya (yang melibatkan perhitungan bayangan secara akurat, menghitung bagaimana cahaya memantul dari permukaan dan warna apa yang dihasilkannya, dll.). Secara teknis, ini bukan yang dilakukan oleh Stable Diffusion. Stable Diffusion mendifusikan gambar, bukan merendernya.

## Guidance Scale/CFG (Classifier Free Guidance) Scale

Menyesuaikan seberapa banyak gambar akan mengikuti prompt Anda. Nilai yang lebih tinggi akan membuat gambar yang dihasilkan semakin mendekati prompt Anda dan nilai lebih rendah akan menghasilkan gambar lebih kreatif.

## Positive Prompt

Deskripsi gambar yang akan dihasilkan oleh AI.

## Negative Prompt

Masukkan apa yang tidak ingin Anda lihat. \
Lebih lanjut [negative-prompt.md](../tutorial/prompting/negative-prompt.md "mention")

## Sampler

Metode pengambilan sampel difusi.

## **Sampling Method**

ini adalah konsep yang cukup teknis. Ini adalah opsi yang bisa Anda pilih ketika menghasilkan gambar dalam Stable Diffusion.&#x20;

Singkatnya: output terlihat kurang lebih sama, apa pun metode pengambilan sampel yang Anda gunakan, perbedaannya sangat halus dan seharusnya tidak terlalu penting, yang mana yang Anda pilih. Beberapa orang mengatakan bahwa ada tiga kelompok: kelompok A (DDIM, Euler, DPM2, HEUN, LMS, DPM\_adaptive dan PLMS) lebih lembut dan berseni; kelompok B (DPM\_fast) memberikan hasil yang lebih bervariasi dan acak; dan kelompok C (DPM2, Euler\_a) memberikan hasil yang sedikit lebih fotorealistik dan jelas.&#x20;

Lebih lanjut [sampling-method.md](../tutorial/text-to-image/sampling-method.md "mention")

## Seed

Digunakan untuk membatasi keacakan. Generasi dengan prompt, parameter dan seed yang sama akan menghasilkan gambar yang sama.

Merubah ke `-1` berarti menggunakan angka acak setiap generate. Hal ini berguna apabila Anda ingin menghasilkan gambar baru.&#x20;

## **Steps**

Berapa banyak langkah yang dihabiskan untuk menghasilkan (menyebarkan) gambar Anda. Lebih banyak langkah, lebih bagus kualitas gambar dan waktu untuk menghasilkannya.

## Batch size <a href="#batch-size" id="batch-size"></a>

Jumlah gambar yang dihasilkan setiap kali generate. Karena gambar akhir sangat bergantung pada seed acak, maka, sebaiknya Anda menghasilkan beberapa gambar sekaligus. Dengan cara ini, Anda bisa mendapatkan gambaran yang baik mengenai apa yang bisa dilakukan oleh prompt saat ini.

\
