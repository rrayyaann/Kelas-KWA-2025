# SQLiLite - PicoCTF

🔗 **Resource Link:** http://play.picoctf.org/practice/challenge/304?category=1&page=1&search=sql

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>
<img width="1500" src="https://github.com/user-attachments/assets/34eaba11-06fd-4093-9644-a9e2ec45c908" />
<img width="1500" src="https://github.com/user-attachments/assets/75f41c93-5f98-4736-b63e-11dfdec5ba20" />
<img width="1500" src="https://github.com/user-attachments/assets/2d5f38e5-5185-43f8-baca-98fff9b6630c" />
</details>

## Langkah Penyelesaian

1. **Eksplorasi Awal Halaman Login**  
   Tantangan ini relatif mudah dan memakan waktu sekitar **5–10 menit**. Saat pertama kali masuk ke instance, hanya terlihat halaman login kosong. mari mencoba berbagai kombinasi kredensial:  
   - Username: `admin`, `administrator`, `root`  
   - Password: varian dari payload `' OR 1=1`  

---

2. **Menemukan Query SQL dari Error**  
   Setelah beberapa kali gagal, aplikasi akhirnya menampilkan query SQL yang digunakan untuk memvalidasi login. Dari sini, terlihat jelas bahwa aplikasi **rawan SQL Injection**.
   
---

3. **Payload yang Berhasil**  
   Akhirnya, login berhasil menggunakan payload sederhana berikut:  `Username : admin' --` Payload ini menutup string username dan mengabaikan bagian validasi password dengan komentar `--`.  

---

4. **Menemukan Flag**  
Meskipun login berhasil, flag **tidak langsung tampil di layar**.  
Setelah membuka **Burpsuite → Inspector**, 

---

## Kesimpulan
- Username `'admin' --` dengan password kosong berhasil melewati autentikasi.  
- Flag tidak ditampilkan langsung, tetapi dapat diekstrak melalui **browser inspector**.  
- Tantangan ini lebih condong ke tingkat **mudah**, namun tetap memberikan gambaran jelas tentang **vulnerabilitas SQL Injection**.  
