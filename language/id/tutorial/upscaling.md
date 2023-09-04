---
description: AI Upscaling models
---

# Upscaling

"Upscaling" (juga dikenal sebagai "Super Resolution", "Upresing", "Upsampling", atau "Upsizing") adalah tindakan meningkatkan resolusi (dimensi lebar & tinggi) dari sebuah gambar (sering disebut sebagai "Single Image Super Resolution" atau "SISR") atau video (Video Super Resolution" atau "VSR").

Di sini, "Peningkatan" biasanya mengacu pada apa yang dilakukan dengan Pembelajaran Mesin/AI. Hal ini sering disebut sebagai "Peningkatan AI". Untuk bentuk peningkatan ini, Model Pembelajaran Mesin dilatih pada pasangan gambar (disebut kumpulan data) dari resolusi rendah dan versi resolusi tinggi dari gambar yang sama. Model ini mempelajari cara yang paling mungkin secara statistik untuk meningkatkan skala gambar untuk menghasilkan hasil seperti data yang dilatih. Mengubah set data ini memungkinkan model untuk mempelajari metode peningkatan yang berbeda.

## Model Upscaler

* [https://openmodeldb.info/](https://openmodeldb.info/)
* [https://nmkd.de/shared/?dir=ESRGAN/Models](https://nmkd.de/shared/?dir=ESRGAN/Models)

## Bagaimana cara meningkatkan resolusi gambar?

Ada banyak program yang dapat melakukan peningkatan menggunakan AI seperti berikut:

* **chaiNNer** (open-source | free)\
  chaiNNer adalah GUI pemrosesan gambar berbasis node yang juga dapat digunakan untuk peningkatan gambar dan dapat dijalankan dengan PyTorch (CUDA), ONNX (CUDA), dan NCNN (AMD/Intel). Karena berbasis node, ini memungkinkan Anda untuk memproses gambar Anda dengan lebih banyak kontrol, dengan biaya yang sedikit lebih kompleks. Selain meningkatkan skala, chaiNNer juga memiliki berbagai kasus penggunaan lain dan merupakan program yang sangat serbaguna.\
  [GitHub](https://github.com/chaiNNer-org/chaiNNer) | [Website](https://chainner.app/)
* **enhancr** (open-source | paid)\
  Dimaksudkan untuk peningkatan dan interpolasi frame video yang cepat, enhancr memanfaatkan TensorRT Nvidia untuk memberikan pemrosesan cepat pada video. Ini mendukung berbagai model, termasuk model ESRGAN\
  [GitHub](https://github.com/mafiosnik777/enhancr)
* **VSGAN-TensorRT-docker** (open-source | free)\
  Alternatif yang lebih rumit tetapi gratis untuk peningkatan video yang cepat dengan TensorRT. Mendukung jumlah model yang sangat banyak, tetapi memerlukan pemilihan parameter secara manual.\
  [GitHub](https://github.com/styler00dollar/VSGAN-tensorrt-docker)
* **Upscayl** (open-source | free)\
  Upscayl adalah GUI peningkatan AI yang ditargetkan untuk digunakan di Linux. Tidak seperti GUI lainnya, Upscayl menawarkan GUI gaya "tombol peningkatan" yang sederhana. Sejauh yang saya ketahui, aplikasi ini hanya bekerja dengan model yang disediakan, tetapi jika Anda menginginkan sesuatu yang sangat mudah digunakan, ini tidak akan lebih mudah lagi.\
  [GitHub](https://github.com/upscayl/upscayl) | [Website](https://www.upscayl.org/)
* **Topaz Gigapixel** (closed-source | paid)\
  Gigapixel adalah produk berbayar dari Topaz Labs. Ini tidak mendukung model apa pun selain milik Topaz Labs, namun sangat terkenal di ruang peningkatan AI untuk model milik mereka.\
  [Website](https://www.topazlabs.com/gigapixel-ai)
* **ComfyUI** (open-source | free)\
  ComfyUI adalah Stable Diffusion UI berbasis node, tetapi juga dapat digunakan untuk peningkatan. Kode untuk peningkatan skala dipinjam dari chaiNNer. Namun, karena lebih fokus pada Stable Diffusion, mungkin tidak akan semudah GUI lainnya.

