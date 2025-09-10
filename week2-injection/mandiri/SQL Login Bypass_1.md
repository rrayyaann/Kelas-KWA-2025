# SQL Login Bypass

🔗 **Resource Link:** https://portswigger.net/web-security/sql-injection/lab-login-bypass

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>
<img width="1500" alt="S1S1" src="https://github.com/user-attachments/assets/0d852f06-ef28-4be6-a131-1be21f9f4874">
</details>

---

## Langkah Penyelesaian

1. **Uji Awal dengan `'`**  
   Saat memasukkan karakter `'` pada kolom *login* maupun *password*, aplikasi menampilkan error.  
   Hal ini mengindikasikan bahwa input pengguna langsung dieksekusi dalam query SQL.  

---

2. **Eksploitasi dengan Payload**  
   Untuk melewati pengecekan password, disisipkan komentar setelah username agar klausa password diabaikan.

Payload yang digunakan: ``or 1=1--`
Bagian setelah -- diabaikan oleh server, sehingga login langsung berhasil sebagai **`or 1=1--or**.

---

3. **Hasil Akhir: Login Sebagai Admin**  
Dengan payload tersebut, autentikasi berhasil dilewati dan akses penuh ke akun administrator diperoleh.

---

## Kesimpulan
- Karakter ' menimbulkan error, mengonfirmasi adanya SQL Injection vulnerability.
- Dengan payload ``or 1=1--`, bagian password diabaikan dan login langsung berhasil.
