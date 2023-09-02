# Models

### Canny Edge

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption><p>Prompt: "bird"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption><p>Prompt: "cute dog"</p></figcaption></figure>

### M-LSD Lines

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption><p>Prompt: "room"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption><p>Prompt: "building"</p></figcaption></figure>

### HED Boundary

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption><p>Prompt: "oil painting of handsome old man, masterpiece"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption><p>Prompt: "Cyberpunk robot"</p></figcaption></figure>

### Scribbles

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption><p>Prompt: "turtle"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (22).png" alt=""><figcaption><p>Prompt: "hot air balloon"</p></figcaption></figure>

### Fake Scribbles

<figure><img src="../../.gitbook/assets/image (23).png" alt=""><figcaption><p>Prompt: "bag"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (24).png" alt=""><figcaption><p>Prompt: "shose" (Note that "shose" is a typo; it should be "shoes". But it still seems to work.)</p></figcaption></figure>

### Human Pose

<figure><img src="../../.gitbook/assets/image (25).png" alt=""><figcaption><p>Prompt: "Chief in the kitchen"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption><p>Prompt: "An astronaut on the moon"</p></figcaption></figure>

### Semantic Segmentation

<figure><img src="../../.gitbook/assets/image (27).png" alt=""><figcaption><p>Prompt: "House"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption><p>Prompt: "River"</p></figcaption></figure>

### Depth

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption><p>Prompt: "Stormtrooper's lecture"</p></figcaption></figure>

### Normal Map

Model ini menggunakan peta normal. Saat ini di APP, normal dihitung dari peta kedalaman midas dan ambang batas pengguna (untuk menentukan berapa banyak area yang menjadi latar belakang dengan identitas wajah normal bagi pemirsa, setel "Normal background threshold" di aplikasi gradio untuk mendapatkan perasaan).

<figure><img src="../../.gitbook/assets/image (30).png" alt=""><figcaption><p>Prompt: "Cute toy"</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (31).png" alt=""><figcaption><p>Prompt: "Plaster statue of Abraham Lincoln"</p></figcaption></figure>

Dibandingkan dengan [depth model](models.md#depth), model ini tampaknya sedikit lebih baik dalam mempertahankan geometri. Hal ini bersifat intuitif: detail kecil tidak menonjol dalam [depth model](models.md#depth), tetapi menonjol dalam normal map. Di bawah ini adalah hasil depth dengan masukan yang sama. Anda bisa melihat, bahwa gaya rambut pria pada gambar masukan dimodifikasi oleh model kedalaman, tetapi dipertahankan oleh model normal.
