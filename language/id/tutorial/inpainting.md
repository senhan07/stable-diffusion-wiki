# Inpainting

### Masked content

Menentukan konten yang ditempatkan untuk dimasukkan ke dalam area masking sebelum diwarnai. Ini bukan merupakan hasil akhir, ini hanya melihat apa yang terjadi pada pertengahan proses.

| mask                                                                                                         | fill                                                                                                         | original                                                                                                         | latent noise                                                                                                         | latent nothing                                                                                                         |
| ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpainting-initial-content-mask.png) | ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpainting-initial-content-fill.png) | ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpainting-initial-content-original.png) | ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpainting-initial-content-latent-noise.png) | ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpainting-initial-content-latent-nothing.png) |

### Inpaint area

Biasanya, inpainting mengubah ukuran gambar ke resolusi target yang ditentukan dalam UI. Dengan `Inpaint area: Only masked` yang diaktifkan, hanya area masking yang diubah ukurannya, dan setelah diproses, disisipkan kembali ke gambar aslinya. Hal ini memungkinkan Anda bekerja dengan gambar besar (resolusi tinggi) dan merender objek yang diberi warna pada resolusi yang jauh lebih besar.

|                                              Input                                              |                                  Inpaint area: Whole picture                                  |                                    Inpaint area: Only masked                                   |
| :---------------------------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------: |
| ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpaint-whole-mask.png) | ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpaint-whole-no.png) | ![](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/images/inpaint-whole-yes.png) |

### Masking mode

Ada dua opsi untuk mode masking:

* Inpaint masked - merubah area yang di masking
* Inpaint not masked - merubah area yang tidak di masking
