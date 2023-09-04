---
description: Perbedaan antara LoRA dan Textual Inversion
---

# Perbandingan

{% hint style="info" %}
### S**ingkatnya**

#### **Textual Inversion**

Sulit untuk dilatih dengan benar, file 4KB+, hasilnya bisa buruk atau sangat bagus

#### LoRA

Mudah dan cepat untuk dilatih dengan benar, file 4MB+, hasilnya bagus tetapi cenderung menghafal hal-hal yang ada di kumpulan data training (yang bisa menjadi hal yang baik atau buruk).
{% endhint %}

## Textual Inversion

* Textual Inversion adalah teknik yang digunakan dalam Stable Diffusion untuk menambahkan gaya atau objek baru ke model text-to-image tanpa mengubah struktur model yang mendasarinya.
* Textual Inversion menggunakan file TI (Textual Inversion) yang merupakan model kecil yang mengkustomisasi hasil dari pembuatan gambar menggunakan Stable Diffusion. File TI ini dapat meningkatkan SD dengan subjek yang spesifik dan gaya artistik tertentu
* File TI memperkenalkan satu atau lebih istilah kosakata ke model SD. Istilah-istilah ini dikenal sebagai "triggers" dan ditandai dengan menggunakan tanda kurung siku seperti "`<trigger-phrase>`". File TI yang paling umum ditemui adalah file dengan format .pt dan .bin

## LoRA

* LoRA (Low-Rank Adaptation) adalah metode yang digunakan untuk mempercepat proses fine-tuning pada model diffusion. Metode ini memungkinkan untuk memodifikasi komponen-komponen model yang ada seperti tokenizer, text encoder, dan Unet untuk mencapai hasil yang diinginkan.
* LoRA memungkinkan untuk menambahkan regularisasi kelas sebelumnya (prior class regularization) yang merupakan penambahan data yang berbeda daripada memodifikasi komponen model yang ada.
* LoRA dapat diterapkan pada text encoder dan Unet, dengan membedakan antara pelatihan layer perhatian transformer atau komponen lain yang bukan perhatian transformer
