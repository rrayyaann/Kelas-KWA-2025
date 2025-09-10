# SQLi Portswigger- Menampilkan Produk yang Belum Dirilis

🔗 **Resource Link:** https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>
<img width="1500" src="https://github.com/user-attachments/assets/bfa93b08-96ef-4eed-8f7d-17712ce89682" />
<img width="1500" src="https://github.com/user-attachments/assets/97c164d8-8dd9-4759-8b97-f8e23365883b" />
<img width="1500" src="https://github.com/user-attachments/assets/6e68b9a7-42ab-4859-b34c-303fd0f192d6" />
</details>

---

## Langkah Penyelesaian

1. **Menjelajahi Halaman Kategori Produk**  
   Setelah membuka lab, terlihat halaman dengan berbagai kategori produk. Saya memilih kategori **Gifts** untuk pengujian awal dan memeriksa request/response menggunakan **Burp Suite**.  

---

2. **Menguji Kerentanan SQL Injection**  
   Untuk menguji apakah parameter kategori rentan terhadap SQL Injection, saya menambahkan tanda **koma (',')** di akhir request. Hasilnya, server memberikan **500 Internal Server Error**, menandakan adanya potensi SQLi. Saat saya menambahkan **dua koma (',,')**, respons berubah menjadi **200 OK**. Hal ini mengonfirmasi bahwa aplikasi memang **rentan SQL Injection**.

---

3. **Analisis Query SQL**  
   Dari perilaku aplikasi, kemungkinan query Payload yang digunakan adalah: `Gifts' OR 1=1 --`

---

## Kesimpulan
- Dengan payload sederhana `' OR 1=1 --`, kita dapat melewati filter released = 1.
- Parameter kategori pada filter produk terbukti rentan SQL Injection.
   
