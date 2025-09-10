# NoSQL Manipulation

Link Resource: https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false

### Jawaban

1. Pada saat menambahkan ulasan, metode request diubah dari `PUT` menjadi `PATCH`. Selanjutnya, tambahkan `{"$ne":-1}` agar semua review yang ada dapat dimodifikasi menjadi pesan yang kita tentukan.
<img width="1500" alt="image" src="https://github.com/user-attachments/assets/2da64aeb-02d9-4bb4-babf-4a8400f38e15" />

2. Hasilnya, seluruh review berhasil diganti sesuai dengan input yang diberikan.
<img width="1500" alt="image" src="https://github.com/user-attachments/assets/26ed31ea-a46b-4232-9029-750f6d027fb0" />