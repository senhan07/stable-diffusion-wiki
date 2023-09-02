---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Variational Autoencoder (VAE)

### Introduction

Variational Autoencoder (VAE) is a type of autoencoder, a neural network trained to replicate its input data to its output, often used for dimensionality reduction. However, VAEs incorporate a regularization process during training to prevent overfitting. This ensures that the latent space, the intermediate representation of the data, possesses certain desirable properties that make generative processes more effective [Source 3](https://ambcrypto.com/blog/what-is-vae-in-stable-diffusion-a-comprehensive-guide/).

In Stable Diffusion, the VAE (or encoder-decoder) component is responsible for compressing the input images into a smaller, latent space, which helps to reduce the VRAM requirements for the diffusion process. In practice, it is important to use a decoder that can effectively reconstruct the original image from the latent space representation [Source 2](https://stable-wiki.org/docs/stable-diffusion/VAE).

### What does VAE do in Stable Diffusion?

VAEs work by encoding and decoding images to and from a smaller latent space, speeding up computation and enhancing image quality. The impact of using a VAE is subtle yet powerful. An enhanced VAE improves the decoding process, leading to better image recovery, particularly for fine details such as eyes and text [Source 3](https://ambcrypto.com/blog/what-is-vae-in-stable-diffusion-a-comprehensive-guide/).

Stable Diffusion already comes with a built-in VAE for every model. However, certain scenarios may require the use of external VAEs as they can deliver superior results compared to the built-in options [Source 1](https://stable-diffusion-art.com/how-to-use-vae/), [Source 3](https://ambcrypto.com/blog/what-is-vae-in-stable-diffusion-a-comprehensive-guide/).

### When to use VAE?

The decision to use a VAE depends on your personal preferences and the desired results. If you strive for continuous improvement and seek the best possible outcomes, incorporating a VAE into your workflow can be beneficial. However, if your current results satisfy you, you don’t need to use a VAE [Source 3](https://ambcrypto.com/blog/what-is-vae-in-stable-diffusion-a-comprehensive-guide/).

### Downloading and Installing VAE

To use a VAE in Stable Diffusion, you simply need to download your chosen VAE and place it in the stable-diffusion-webui\models\VAE folder (when using AUTOMATIC1111’s WebUI). Once this is done, you can select your preferred VAE from the “Settings” tab in the AUTOMATIC1111 WebUI [Source 3](https://ambcrypto.com/blog/what-is-vae-in-stable-diffusion-a-comprehensive-guide/).

For Linux and Mac OS, run the commands below in Linux or Mac OS under stable-diffusion-webui’s directory downloads and installs the VAE files [Source 1](https://stable-diffusion-art.com/how-to-use-vae/):

```bash
wget https://huggingface.co/stabilityai/sd-vae-ft-ema-original/resolve/main/vae-ft-ema-560000-ema-pruned.ckpt -O models/VAE/vae-ft-ema-560000-ema-pruned.ckpt
```

### Popular VAEs for Stable Diffusion

There are multiple VAEs available for Stable Diffusion, each offering unique enhancements. Some of the most popular ones include:

* kl-f8-anime (Anything V3): This VAE has been ideally configured for creating anime artwork. The model has been fine-tuned on the SD 1.4 VAE with a large dataset of anime-styled images. It was developed by an artist named Hakurei.
* kl-f8-anime2: This model is an improved version of the kl-f8-anime VAE that specifically targets more vibrant, varied, and accurate colors in the output anime art.
* vae-ft-mse-840000-ema-pruned: StabilityAI created this model, optimized for realistic models or styles, using the mean squared error (mse) loss function for fine-tuning during training [Source 10](https://okuha.com/vae-in-stable-diffusion/).

### Conclusion

In conclusion, VAEs offer an effective way to enhance the visual quality of Stable Diffusion checkpoint models. With their ability to improve image sharpness, color vividness, and the depiction of hands and faces, VAEs can elevate your Stable Diffusion experience \[Source 3
