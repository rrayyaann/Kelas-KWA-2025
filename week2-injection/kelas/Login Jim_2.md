# Login Jim

🔗 **Resource Link:** [Juice Shop - Injection Challenges](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

---

## Langkah Penyelesaian

1. **Menemukan Email Jim**  
   Untuk dapat login ke akun Jim, pertama perlu mencari alamat email yang digunakan.  
   Email Jim dapat ditemukan melalui bagian *review product*.  

   <img width="1500" alt="review-product" src="https://github.com/user-attachments/assets/bffdc144-8584-465d-8a21-2d6158610eac">

---

2. **Eksploitasi Login Jim**  
   Setelah mengetahui alamat email Jim, masukkan email tersebut pada kolom login dan tambahkan tanda `--` di belakangnya.  
   Dengan cara ini, bagian password akan diabaikan sehingga autentikasi selalu dianggap benar.  

   <img width="1500" alt="login-jim" src="https://github.com/user-attachments/assets/b8fccfdf-ac3f-4ba1-aed7-2ce1e59b9503">

---

## Kesimpulan
- Email target dapat diperoleh melalui *product review*.  
- Menambahkan `--` setelah email memungkinkan untuk melewati verifikasi password.  
- Teknik ini menunjukkan kerentanan *SQL Injection* pada sistem login Juice Shop.  
