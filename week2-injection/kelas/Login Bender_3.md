# Login Bender

🔗 **Resource Link:** [Juice Shop - Injection Challenges](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

---

## Langkah Penyelesaian

1. **Menemukan Email Bender**  
   Untuk dapat login ke akun Bender, terlebih dahulu perlu mencari alamat emailnya.  
   Informasi tersebut dapat ditemukan di bagian *review product*.  

   <img width="1500" alt="review-bender" src="https://github.com/user-attachments/assets/4332b42e-e3c4-4c8b-ae12-2c356d35ce54">

---

2. **Login Sebagai Bender**  
   Setelah memperoleh alamat email, masukkan ke kolom login dengan menambahkan `--` di belakangnya agar password diabaikan.  
   Hasilnya, login berhasil dilakukan sebagai pengguna **Bender**.  

   <img width="1500" alt="login-bender" src="https://github.com/user-attachments/assets/ab4b6ab0-a9c0-496f-89c2-cebf539e6a2f">

---

## Kesimpulan
- Email Bender dapat diidentifikasi dari *product review*.  
- Dengan menambahkan `--` setelah email, autentikasi password dapat dilewati.  
- Teknik ini memperlihatkan kelemahan *SQL Injection* pada sistem login.  
