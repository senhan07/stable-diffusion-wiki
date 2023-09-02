---
description: Let us control diffusion models!
---

# ControlNet

ControlNet adalah model Stable Diffusion yang memungkinkan Anda menyalin komposisi atau pose manusia dari gambar referensi.

Pengguna Stable Diffusion yang berpengalaman tahu betapa sulitnya menghasilkan komposisi yang tepat seperti yang Anda inginkan. Gambar-gambarnya agak acak. Yang bisa Anda lakukan adalah memainkan permainan angka: Hasilkan sejumlah besar gambar dan pilih salah satu yang Anda sukai.

Dengan ControlNet, pengguna Stable Diffusion akhirnya memiliki cara untuk mengontrol di mana subjek berada dan bagaimana penampilan mereka dengan presisi!

## Apa itu ControlNet?&#x20;

ControlNet adalah model jaringan saraf untuk mengendalikan model Difusi Stabil. Anda dapat menggunakan ControlNet bersama dengan model Stable Diffusion apa pun.

Bentuk paling dasar dalam menggunakan model Stable Diffusion adalah teks-ke-gambar. Model ini menggunakan perintah teks sebagai pengkondisian untuk mengarahkan pembuatan gambar sehingga Anda menghasilkan gambar yang sesuai dengan perintah teks.

ControlNet menambahkan satu pengkondisian lagi sebagai tambahan dari perintah teks. Pengkondisian ekstra dapat mengambil banyak bentuk dalam ControlNet.

Mari saya tunjukkan dua contoh apa yang dapat dilakukan ControlNet: Mengontrol pembuatan gambar dengan (1) edge detection and (2) human pose detection.

### Edge detection example

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption><p>Stable Diffusion ControlNet with Canny edge conditioning.</p></figcaption></figure>

Proses mengekstraksi informasi spesifik (tepi dalam kasus ini) dari gambar input disebut anotasi atau prapemrosesan (dalam ekstensi ControlNet).

### Human pose detection example

Deteksi tepi bukan satu-satunya cara untuk memproses gambar. Openpose adalah model pendeteksian titik kunci manusia yang cepat yang dapat mengekstrak pose manusia seperti posisi tangan, kaki, dan kepala. Lihat contoh di bawah ini.\


<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption><p>Input image annotated with human pose detection using Openpose.</p></figcaption></figure>

Di bawah ini adalah alur kerja ControlNet menggunakan OpenPose. Titik-titik kunci diekstraksi dari gambar input menggunakan OpenPose, dan disimpan sebagai peta kontrol yang berisi posisi titik-titik kunci. Peta ini kemudian diumpankan ke Stable Diffusion sebagai pengkondisian tambahan bersama dengan prompt teks. Gambar dihasilkan berdasarkan dua pengkondisian ini.

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

Apa perbedaan antara menggunakan pendeteksian tepi Canny dan Openpose? Detektor tepi Canny mengekstrak tepi subjek dan latar belakang. Hal ini cenderung menerjemahkan pemandangan secara lebih tepat. Anda bisa melihat pria yang sedang menari menjadi seorang wanita, tetapi garis bentuk dan gaya rambutnya tetap dipertahankan.

OpenPose hanya mendeteksi titik-titik penting manusia, seperti posisi kepala, lengan, dll. Pembuatan gambar lebih leluasa, tetapi mengikuti pose aslinya.

Contoh di atas menghasilkan gambar seorang wanita yang melompat dengan kaki kiri mengarah ke samping, berbeda dari gambar asli dan gambar dalam contoh Canny Edge. Alasannya adalah karena deteksi keypoint OpenPose tidak menentukan orientasi kaki.
