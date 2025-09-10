# SQLi Portswigger- Menampilkan Produk yang Belum Dirilis

🔗 **Resource Link:** [PortSwigger - SQL Injection Lab](https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data)

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>

<!-- ![category-page](../assets/category-page.png) -->
<!-- ![burp-request](../assets/burp-request.png) -->
<!-- ![sqli-test](../assets/sqli-test.png) -->
<!-- ![payload-result](../assets/payload-result.png) -->

</details>

---

## Langkah Penyelesaian

1. **Menjelajahi Halaman Kategori Produk**  
   Setelah membuka lab, terlihat halaman dengan berbagai kategori produk.  
   Saya memilih kategori **Gifts** untuk pengujian awal dan memeriksa request/response menggunakan **Burp Suite**.  

   <img width="1500" alt="category-page" src="https://github.com/user-attachments/assets/1111111111"/>

---

2. **Menguji Kerentanan SQL Injection**  
   Untuk menguji apakah parameter kategori rentan terhadap SQL Injection, saya menambahkan tanda **koma (',')** di akhir request.  
   Hasilnya, server memberikan **500 Internal Server Error**, menandakan adanya potensi SQLi.  

   Saat saya menambahkan **dua koma (',,')**, respons berubah menjadi **200 OK**.  
   Hal ini mengonfirmasi bahwa aplikasi memang **rentan SQL Injection**.  

   <img width="1500" alt="sqli-test" src="https://github.com/user-attachments/assets/2222222222"/>

---

3. **Analisis Query SQL**  
   Dari perilaku aplikasi, kemungkinan query Payload yang digunakan adalah: `Gifts' OR 1=1 --`

---

## Kesimpulan
- Dengan payload sederhana `' OR 1=1 --`, kita dapat melewati filter released = 1.
- Parameter kategori pada filter produk terbukti rentan SQL Injection.
   
