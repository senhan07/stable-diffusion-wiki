# Upscalers

Sebuah menu memungkinkan Anda untuk memilih jenis upscaler yang akan digunakan untuk mengubah ukuran gambar. Selain semua upscaler yang Anda miliki di tab Ekstra, ada opsi untuk meningkatkan ukuran gambar ruang laten, yang digunakan oleh difusi stabil secara internal - untuk gambar RGB 3x512x512, representasi ruang latennya adalah 4x64x64. Untuk melihat apa yang dilakukan oleh setiap peningkat ruang laten, Anda dapat mengatur kekuatan Denoising ke 0 dan langkah Hires ke 1 - Anda akan mendapatkan perkiraan yang sangat baik tentang apa yang akan dilakukan oleh difusi stabil pada gambar yang ditingkatkan.

Di bawah ini adalah contoh tampilan berbagai mode peningkatan ruang laten yang berbeda.

|                                                          Original                                                          |
| :------------------------------------------------------------------------------------------------------------------------: |
| ![00084-2395363541](https://user-images.githubusercontent.com/20920490/210657893-0660c637-9f26-405e-83c9-3030e45fd5b0.png) |

|                                                Latent, Latent (antialiased)                                                |                                       Latent (bicubic), Latent (bicubic, antialiased)                                      |                                                      Latent (nearest)                                                      |
| :------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------: |
| ![00071-2395363541](https://user-images.githubusercontent.com/20920490/210658048-d90ae87d-4534-4ca4-878b-9aaa4f43f901.png) | ![00073-2395363541](https://user-images.githubusercontent.com/20920490/210658501-c6a64c58-9343-470a-9f0b-6ae76c806725.png) | ![00077-2395363541](https://user-images.githubusercontent.com/20920490/210658607-ac5b5f30-af6a-4158-b968-9d1fdd6faf50.png) |
