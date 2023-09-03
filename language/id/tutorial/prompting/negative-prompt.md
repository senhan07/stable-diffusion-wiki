---
description: Penggunaan Negative Prompt dalam Stable Diffusion
---

# Negative Prompt

Negative Prompt adalah parameter yang memberi tahu Stable Diffusion tentang apa yang tidak ingin Anda lihat dalam gambar yang dihasilkan. Apabila ditentukan, ini akan memandu proses pembuatan gambar untuk tidak menyertakan berbagai hal dalam gambar menurut teks yang diberikan.

Negative Prompt dapat mencegah menghasilkan hal-hal tertentu, gaya, memperbaiki beberapa kelainan gambar, dan sangat meningkatkan kualitas. Mari kita cermati contoh yang membandingkan gambar yang sama dengan dan tanpa prompt negatif:

Memperbaiki kualitas secara keseluruhan dan proporsi tubuh sewaktu menciptakan '**portrait**':

| ![](<../../.gitbook/assets/image (38).png>) |      ![](<../../.gitbook/assets/image (39).png>)     |
| :-----------------------------------------: | :--------------------------------------------------: |
|           Without negative prompt           | Negative prompt: 'Disfigured, cartoon, blurry, nude' |



Menghilangkan fitur visual, misalnya '**lumut**' dari '**hutan**':

| ![](<../../.gitbook/assets/image (41).png>) | ![](<../../.gitbook/assets/image (43).png>) |
| :-----------------------------------------: | :-----------------------------------------: |
|           Without negative prompt           |           Negative prompt: 'moss'           |



Mengubah pencahayaan gambar dan membuatnya terlihat lebih tajam dengan menghilangkan kabut:

| ![](<../../.gitbook/assets/image (44).png>) | ![](<../../.gitbook/assets/image (45).png>) |
| :-----------------------------------------: | :-----------------------------------------: |
|           Without negative prompt           |       Negative prompt: 'darkness, fog'      |
