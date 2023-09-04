---
description: Low-Rank Adaptation
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# LoRA

## Apa itu LoRA ?

LoRA (Low-Rank Adaptation) adalah teknik pelatihan yang digunakan untuk memperbaiki model Stable Diffusion. LoRA dikembangkan oleh Microsoft Research sebagai cara yang lebih cepat dan efisien untuk memperbaiki model bahasa yang besar. LoRA juga telah diadaptasi untuk model difusi dalam pembuatan gambar . Model LoRA lebih kecil ukurannya dibandingkan dengan model checkpoint, sehingga lebih mudah untuk dibagikan dan diunduh . Model LoRA ini digunakan untuk memperkenalkan konsep-konsep baru ke dalam model, sehingga model dapat menghasilkan gambar-gambar dengan konsep tersebut . Model LoRA ini dapat dilatih di atas model dasar seperti Stable Diffusion v1.5 atau NAI Diffusion, tergantung pada gaya atau subjek yang diinginkan.

Berikut adalah poin-poin penting yang perlu dipahami tentang LoRA di Stable Diffusion:

* Model LoRA memiliki ukuran yang lebih kecil dibandingkan dengan model checkpoint, sehingga lebih mudah untuk dibagikan dan diunduh .
* Model LoRA biasanya memiliki ukuran yang lebih kecil hingga 100 kali lipat dibandingkan dengan model checkpoint .
* Model LoRA digunakan untuk memperkenalkan konsep-konsep baru ke dalam model, seperti subjek (karakter, ekspresi wajah, objek) dan gaya (estetika visual, gaya seni) .
* Model LoRA bekerja dengan melakukan perubahan kecil pada lapisan cross-attention dari model Stable Diffusion, yang penting untuk interseksi gambar dan prompt .
* Bobot lapisan cross-attention pada model LoRA diatur dalam matriks low-rank, sehingga ukuran file model menjadi lebih kecil .
* Terdapat berbagai jenis model LoRA yang tersedia tergantung pada konsep yang dilatih, seperti Pixel Art, Ghosts, Barbicore, Cyborg, dan Greg Rutkowski-inspired .

Melatih model Stable Diffusion dengan menggunakan LoRA dapat menjadi cara yang kuat untuk menghasilkan gambar-gambar berkualitas tinggi dengan gaya atau tema tertentu. Dengan memahami cara kerja model LoRA dan cara menginstal dan menggunakannya dengan benar, Anda dapat meningkatkan gambar-gambar yang dihasilkan oleh kecerdasan buatan dan mengeksplorasi berbagai gaya dan efek yang beragam .

## Cara Menggunakan LoRA

Untuk menggunakan model LoRA dengan efektif, Anda dapat mengunduhnya dan menempatkannya di folder `stable-diffusion-webui/models/Lora`, kemudian tambahkan `<lora:FILENAME:WEIGHT>` pada prompt Anda, di mana `FILENAME` adalah nama file LoRA tanpa ekstensi file dan `WEIGHT` adalah kekuatan dari LoRA tersebut dari nilai 0 hingga 1 .

## Batasan penggunaan LoRA

terdapat beberapa batasan dalam penggunaan LoRA untuk mengurangi jumlah parameter pada fine-tuning, serta situasi atau jenis model tertentu di mana LoRA tidak efektif:

* LoRA hanya dapat digunakan pada lapisan perhatian (attention layers) dari model Stable Diffusion. Hal ini berarti LoRA tidak dapat digunakan pada seluruh model atau lapisan-lapisan lain di luar lapisan perhatian.
* LoRA tidak cocok untuk model dengan arsitektur yang berbeda, terutama jika lapisan perhatian tidak ada dalam model tersebut. Sebagai contoh, pada model UNet2DConditionModel, LoRA hanya mendukung lapisan perhatian (attention layers).
* Meskipun LoRA dapat mengurangi jumlah parameter yang dilatih, hasil fine-tuning dengan LoRA masih membutuhkan eksperimen dengan hiperparameter tertentu untuk mendapatkan kualitas generasi yang diinginkan. Beberapa hiperparameter yang perlu dieksperimenkan antara lain learning rate, jumlah langkah pelatihan (training steps), dan lain-lain.
* LoRA tidak selalu menjamin hasil fine-tuning yang lebih baik dibandingkan dengan fine-tuning penuh (full fine-tuning). Meskipun LoRA dapat mempercepat proses pelatihan dan mengurangi biaya komputasi, hasil fine-tuning dengan LoRA tidak selalu setara dengan hasil fine-tuning penuh. Namun, dalam beberapa kasus, LoRA dapat mencapai kualitas fine-tuning yang setara dengan fine-tuning penuh.
