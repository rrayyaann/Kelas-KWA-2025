# SQLiLite - PicoCTF

🔗 **Resource Link:** [PortSwigger Lab - SQL Injection](http://play.picoctf.org/practice/challenge/304?category=1&page=1&search=sql)

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>

<!-- ![login-test](../assets/login-test.png) -->
<!-- ![payload-success](../assets/payload-success.png) -->
<!-- ![burp-repeater](../assets/burp-repeater.png) -->

</details>

## Langkah Penyelesaian

1. **Eksplorasi Awal Halaman Login**  
   Tantangan ini relatif mudah dan memakan waktu sekitar **5–10 menit**.  
   Saat pertama kali masuk ke instance, hanya terlihat halaman login kosong.  

   Saya mencoba berbagai kombinasi kredensial:  
   - Username: `admin`, `administrator`, `root`  
   - Password: varian dari payload `' OR 1=1`  

   Sayangnya, semua usaha tersebut gagal.  

   <img width="1500" alt="login-page" src="https://github.com/user-attachments/assets/67ce711c-533a-44c2-8c6c-aa5dc04f19a6"/>

---

2. **Menemukan Query SQL dari Error**  
   Setelah beberapa kali gagal, aplikasi akhirnya menampilkan query SQL yang digunakan untuk memvalidasi login.  
   Dari sini, terlihat jelas bahwa aplikasi **rawan SQL Injection**.  

   Untuk memperdalam, saya merujuk ke dokumentasi resmi PortSwigger:  
   👉 [SQL Injection - PortSwigger](https://portswigger.net/keamanan-web/injeksi-sql#cara-mendeteksi-kerentanan-injeksi-sql)  

   <img width="1500" alt="portswigger-help" src="https://github.com/user-attachments/assets/d1426dfb-5f1c-4dcf-8575-d2d2df158ad1"/>

---

3. **Payload yang Berhasil**  
   Akhirnya, login berhasil menggunakan payload sederhana berikut:  `Username : admin' --`


Payload ini menutup string username dan mengabaikan bagian validasi password dengan komentar `--`.  

---

4. **Menemukan Flag**  
Meskipun login berhasil, flag **tidak langsung tampil di layar**.  
Setelah membuka **Developer Tools → Inspector**, 

<img width="1500" alt="inspector-flag" src="https://github.com/user-attachments/assets/9f877dbb-866d-4081-81cf-34535525c6b1"/>

---

## Kesimpulan
- Username `'admin' --` dengan password kosong berhasil melewati autentikasi.  
- Flag tidak ditampilkan langsung, tetapi dapat diekstrak melalui **browser inspector**.  
- Tantangan ini lebih condong ke tingkat **mudah**, namun tetap memberikan gambaran jelas tentang **vulnerabilitas SQL Injection**.  
