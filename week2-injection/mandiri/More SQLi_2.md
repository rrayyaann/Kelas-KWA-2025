# More SQLi - PicoCTF

🔗 **Resource Link:** [PortSwigger Lab - SQL Injection](https://play.picoctf.org/practice/challenge/358?category=1&page=1&search=sql)

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>

<!-- ![login-test](../assets/login-test.png) -->
<!-- ![payload-success](../assets/payload-success.png) -->
<!-- ![burp-repeater](../assets/burp-repeater.png) -->

</details>

---

## Langkah Penyelesaian

1. **Menjelajahi Halaman Login**  
   Saya mulai dengan mencoba kredensial sederhana:  
`Username : uji`
`Password : uji`


Setelah dikirimkan, respons menampilkan query SQL mentah:  

```sql
SELECT id FROM users WHERE password = 'uji' AND username = 'uji'
```

2. **Menyuntikkan Kode SQL**
Dengan mengetahui bahwa 1=1 selalu bernilai true, saya mencoba payload berikut pada kolom username maupun password:

3. **Menggunakan Burp Suite untuk Mengekstrak Bendera**
Setelah login berhasil, saya mencegat permintaan dengan Burp Suite dan mengirimkannya ke tab Repeater.
Dengan mengulangi payload yang sama:
`' OR 1=1; -- //`