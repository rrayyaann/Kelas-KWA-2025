# Database Schema

🔗 **Resource Link:** [Juice Shop - Injection Challenges](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

---

## Langkah Penyelesaian

1. **Menggunakan Fitur Search**  
   Pencarian pada aplikasi akan menampilkan produk yang memiliki nama atau deskripsi sesuai dengan *keyword* yang dimasukkan.  

   <img width="1500" alt="search-result-1" src="https://github.com/user-attachments/assets/727a4f55-60a6-48d3-86ff-d9b0bc854530">

   <img width="1500" alt="search-result-2" src="https://github.com/user-attachments/assets/b1521654-8049-47b2-8e0f-acec7b92c22f">

   <img width="1500" alt="search-result-3" src="https://github.com/user-attachments/assets/3715e2d2-a1e3-45ec-94c6-722a119caf43">

---

2. **Identifikasi Struktur Database**  
   Dari eksplorasi query terlihat bahwa terdapat **9 kolom** dalam tabel database.  

   <img width="1500" alt="columns-detected" src="https://github.com/user-attachments/assets/2903a0f7-94f3-4f61-9834-6b9d8b1897eb">

---

3. **Menggunakan Payload SQL Injection**  
   Dengan memasukkan payload berikut: `'))+UNION+SELECT+sql,2,3,4,5,6,7,8,9+FROM+sqlite_master--`

Query ini memanfaatkan UNION SELECT untuk menampilkan *schema* dari tabel yang ada di database.  
Hasilnya, struktur database berhasil diungkap.  

<img width="1500" alt="schema-result-1" src="https://github.com/user-attachments/assets/fdecfda6-e1a5-473c-9c92-1b6d206e9041">

<img width="1500" alt="schema-result-2" src="https://github.com/user-attachments/assets/d4e60d8e-f751-4573-977a-06b7b3f1ad33">

---

## Kesimpulan
- Fitur *search* rawan terhadap *SQL Injection*.  
- Database memiliki **9 kolom** yang dapat digunakan untuk eksploitasi query.  
- Payload UNION SELECT memungkinkan penyerang mengekstrak *database schema*.  
