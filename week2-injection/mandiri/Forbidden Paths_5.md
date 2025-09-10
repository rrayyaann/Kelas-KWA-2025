# Forbidden Paths - PicoCTF

🔗 **Resource Link:** https://play.picoctf.org/practice/challenge/270?page=1&search=Forbidden%20Paths%20p

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>
<img width="1500" src="https://github.com/user-attachments/assets/5c7fa279-3fe6-4ed1-94a8-69d5fbb97c1c" />


</details>

## Langkah Penyelesaian

1. **Informasi Awal**  
   Dari deskripsi lab, diketahui bahwa file **`flag.txt`** berada pada direktori: `/usr/share/nginx/html/`

   Aplikasi memiliki pemfilteran jalur absolut, sehingga langsung mengakses `/usr/share/nginx/html/flag.txt` akan gagal. Oleh karena itu, pendekatan **path traversal** (`../`) digunakan.  

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
