# Prompts from file or textbox

Dengan skrip ini, Anda dapat membuat daftar pekerjaan yang akan dieksekusi secara berurutan.

Contoh masukan:

```
--prompt "photo of sunset" 
--prompt "photo of sunset" --negative_prompt "orange, pink, red, sea, water, lake" --width 1024 --height 768 --sampler_name "DPM++ 2M Karras" --steps 10 --batch_size 2 --cfg_scale 3 --seed 9
--prompt "photo of winter mountains" --steps 7 --sampler_name "DDIM"
--prompt "photo of winter mountains" --width 1024
```

Contoh keluar:

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
