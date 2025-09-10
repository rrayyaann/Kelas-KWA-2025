# Forbidden Paths - PicoCTF

🔗 **Resource Link:** [PortSwigger Lab - SQL Injection](https://play.picoctf.org/practice/challenge/270?page=1&search=Forbidden%20Paths%20p)

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>

<!-- ![login-test](../assets/login-test.png) -->
<!-- ![payload-success](../assets/payload-success.png) -->
<!-- ![burp-repeater](../assets/burp-repeater.png) -->

</details>

## Langkah Penyelesaian

1. **Informasi Awal**  
   Dari deskripsi lab, diketahui bahwa file **`flag.txt`** berada pada direktori: `/usr/share/nginx/html/`

   Aplikasi memiliki pemfilteran jalur absolut, sehingga langsung mengakses `/usr/share/nginx/html/flag.txt` akan gagal. Oleh karena itu, pendekatan **path traversal** (`../`) digunakan.  

<img width="1500" alt="dir-traversal-test" src="https://github.com/user-attachments/assets/1111111111"/>

---

2. **Percobaan Awal dengan Pola Traversal**  
Beberapa variasi traversal dicoba, seperti:  
path relative dengan cara keluar dari folder satu persatu sampai pada direktori yang sama dengan `flag.txt`nya. Atau sama dengan memberikan path relative flag.txt terhadap path sekarang kita. Dengan begitu kita bisa menginputkan:

```sql
../../../../flag.txt
```

## Kesimpulan
- Aplikasi rentan terhadap **Directory Traversal** meskipun ada filter jalur absolut.  
- Payload `../../../../flag.txt` digunakan untuk keluar dari direktori aplikasi dan mengakses file target.  
