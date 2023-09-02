# Prompt matrix

Pisahkan beberapa prompt dengan menggunakan karakter `|`, dan sistem akan menghasilkan gambar untuk setiap kombinasinya. Contohnya, jika Anda menggunakan `a busy city street in a modern city|illustration|cinematic lighting`, ada empat kombinasi yang mungkin terjadi (bagian pertama dari prompt selalu dipertahankan):

* `a busy city street in a modern city`
* `a busy city street in a modern city, illustration`
* `a busy city street in a modern city, cinematic lighting`
* `a busy city street in a modern city, illustration, cinematic lighting`

Empat gambar akan dihasilkan, dalam urutan ini, semuanya dengan seed yang sama dan masing-masing dengan prompt yang sesuai:

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Contoh lainnya, kali ini dengan 5 prompt dan 16 variasi:

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Anda bisa menemukan fitur ini di bagian bawah, di bawah Script -> Prompt matrix.
