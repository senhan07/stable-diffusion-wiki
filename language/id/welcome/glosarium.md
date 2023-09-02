---
description: Apa yang kamu harus tau
---

# Glosarium

## Model

Model pembelajaran mesin, model pembelajaran mendalam, model AI, model statistik... semuanya memiliki arti yang sama. Model hanyalah ekspresi matematika yang mengambil sesuatu sebagai input dan mengeluarkan sesuatu sebagai output. AI hanyalah sebuah model matematika. AI mencoba meniru (yaitu: model) sesuatu di dunia nyata, apakah itu data mentah, gambar, musik, dll. Dalam pembuatan gambar AI, model mengambil teks sebagai input dan mengeluarkan gambar sebagai output.

## Guidance Scale/CFG (Classifier Free Guidance) Scale

Menyesuaikan seberapa banyak gambar akan seperti prompt Anda. Nilai yang lebih tinggi akan membuat gambar Anda semakin mendekati prompt Anda.

## Diffusing

Mekanisme yang digunakan oleh model pembangkitan gambar AI untuk menghasilkan gambar. Singkatnya: AI memulai dengan gambar yang seluruhnya terdiri atas noise acak, dan langkah demi langkah mencoba menghilangkan noise hingga gambar akhir tercipta. Noise yang dihilangkan pada setiap langkah dikondisikan oleh perintah yang diberikan, begitulah cara Anda mendapatkan gambar yang jernih dan bukan hanya noise acak.

## Prompt

Deskripsi gambar yang akan dihasilkan oleh AI.

## Render

Tindakan mengubah representasi abstrak dari suatu gambar menjadi gambar akhir. Dalam pemodelan 3D, jika Anda membuat model 3D, itu hanyalah poligon dan persamaan matematika. Untuk mendapatkan gambar yang sebenarnya dari mereka, Anda perlu merendernya (yang melibatkan perhitungan bayangan secara akurat, menghitung bagaimana cahaya memantul dari permukaan dan warna apa yang dihasilkannya, dll.). Secara teknis, ini bukan yang dilakukan oleh Stable Diffusion. Ini adalah cara lama. Stable Diffusion mendifusikan gambar, bukan merendernya.

## Sampler

Metode pengambilan sampel difusi.

## **Sampling Method**

ini adalah konsep yang cukup teknis. Ini adalah opsi yang bisa Anda pilih ketika menghasilkan gambar dalam Stable Diffusion. Singkatnya: output terlihat kurang lebih sama, apa pun metode pengambilan sampel yang Anda gunakan, perbedaannya sangat halus dan seharusnya tidak terlalu penting, yang mana yang Anda pilih. Beberapa orang mengatakan bahwa ada tiga kelompok: kelompok A (DDIM, Euler, DPM2, HEUN, LMS, DPM\_adaptive dan PLMS) lebih lembut dan berseni; kelompok B (DPM\_fast) memberikan hasil yang lebih bervariasi dan acak; dan kelompok C (DPM2, Euler\_a) memberikan hasil yang sedikit lebih fotorealistik dan jelas. Kesimpulannya: jika Anda menginginkan hasil yang lembut dan berseni, Anda bisa menggunakan DPM\_adaptive atau DDIM; jika Anda menginginkan variasi, pilihlah DPM\_fast; dan jika Anda mencari photorealism, cobalah DPM2 atau Euler\_a. [sampling-method.md](../tutorial/text-to-image/sampling-method.md "mention")

## Seed

Digunakan untuk membatasi keacakan. Generasi dengan prompt, param dan seed yang sama akan menghasilkan gambar yang sama.

## **Steps**

Berapa banyak langkah yang dihabiskan untuk menghasilkan (menyebarkan) gambar Anda. Lebih banyak langkah, lebih banyak kualitas gambar dan waktu untuk menghasilkannya.
