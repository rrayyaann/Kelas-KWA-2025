# Login Admin

🔗 **Resource Link:** [Juice Shop - Injection Challenges](https://portswigger.net/web-security/sql-injection/lab-login-bypass)

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
   Untuk melewati pengecekan password, disisipkan komentar setelah username agar klausa password diabaikan.

Payload yang digunakan: ``or 1=1--`
Bagian setelah -- diabaikan oleh server, sehingga login langsung berhasil sebagai **`or 1=1--or**.

<img width="1500" alt="payload-success" src="c:\Users\Muhamad Arrayyan\AppData\Local\Packages\5319275A.WhatsAppDesktop_cv1g1gvanyjgm\TempState\9B1CB2C300EF5FB35CBA2F89C1A36FFD\WhatsApp Image 2025-09-08 at 22.09.59_4ae32206.jpg">

---

3. **Hasil Akhir: Login Sebagai Admin**  
Dengan payload tersebut, autentikasi berhasil dilewati dan akses penuh ke akun administrator diperoleh.


---

## Kesimpulan
- Karakter ' menimbulkan error, mengonfirmasi adanya SQL Injection vulnerability.
- Dengan payload ``or 1=1--`, bagian password diabaikan dan login langsung berhasil.