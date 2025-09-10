# Login Admin

🔗 **Resource Link:** [Juice Shop - Injection Challenges](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>

<!-- ![S1S1](../assets/S1S1.png) -->

</details>

---

## Langkah Penyelesaian

1. **Uji Awal dengan `'`**  
   Saat memasukkan karakter `'` pada kolom *login* maupun *password*, aplikasi menampilkan error.  
   Hal ini mengindikasikan bahwa input pengguna langsung dieksekusi dalam query SQL.  

   <img width="1500" alt="S1S1" src="https://github.com/user-attachments/assets/67ce711c-533a-44c2-8c6c-aa5dc04f19a6"/>">

---

2. **Eksploitasi dengan Payload**  
   Dengan memasukkan payload berikut pada kolom *email*, serta password bebas:  

Payload ini membuat kondisi login selalu bernilai **true**, sementara bagian password diabaikan dengan `--`.  
Akibatnya, sistem akan langsung mengautentikasi pengguna sebagai akun pertama di database, yaitu **admin**.  

<img width="1500" alt="payload-success" src="https://github.com/user-attachments/assets/d1426dfb-5f1c-4dcf-8575-d2d2df158ad1">

---

3. **Hasil Akhir: Login Sebagai Admin**  
Setelah payload dijalankan, login berhasil dilakukan dengan hak akses **admin**.  

<img width="1500" alt="admin-login" src="https://github.com/user-attachments/assets/9f877dbb-866d-4081-81cf-34535525c6b1">


---

## Kesimpulan
- Karakter `'` dapat memicu error yang menandakan adanya *SQL Injection vulnerability*.  
- Dengan memanfaatkan query sederhana (`' OR 1=1--`), autentikasi dapat dilewati tanpa verifikasi password.  
- Hal ini menegaskan pentingnya validasi input serta penggunaan *prepared statement* untuk mencegah serangan serupa.  
