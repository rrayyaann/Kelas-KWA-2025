# More SQLi - PicoCTF

🔗 **Resource Link:** https://play.picoctf.org/practice/challenge/358?category=1&page=1&search=sql

---

## Dokumentasi
<details>
<summary>Tangkapan Layar</summary>
<img width="1500" src="https://github.com/user-attachments/assets/0d20dc45-0e14-4fa3-83aa-bc97d29787ef" />
<img width="1500" src="https://github.com/user-attachments/assets/9d86db27-699a-4074-ba21-41967fabf2c5" />
<img width="1500" src="https://github.com/user-attachments/assets/14cea5c0-efcf-4648-b5da-2824b4589b28" />
<img width="1500" src="https://github.com/user-attachments/assets/a90e20a0-7f55-4219-beb6-04b3606e65fe" />
<img width="1500" src="https://github.com/user-attachments/assets/43d3e9f5-ca83-40e4-a302-7a8af88a1287" />

</details>

---

## Langkah Penyelesaian

1. **Menjelajahi Halaman Login**  
   Saya mulai dengan mencoba kredensial sederhana:  
`Username : test`
`Password : test`


Setelah dikirimkan, respons menampilkan query SQL mentah:  

```sql
SELECT id FROM users WHERE password = 'test' AND username = 'test'
```

2. **Menyuntikkan Kode SQL**
Dengan mengetahui bahwa 1=1 selalu bernilai true, saya mencoba payload berikut pada kolom username maupun password:

3. **Menggunakan Payload**
Setelah login berhasil, rentan terhadap injeksi SQL berbasis Union ! Berikutnya, kita perlu mencari DBMS (Sistem Manajemen Basis Data) mana yang digunakan server web. Setelah beberapa kali coba-coba, saya menemukan bahwa itu menggunakan SQLite:
`' UNION ALL SELECT sqlite_version(),NULL,NULL-- -`
Setelah itu, kita dapat mulai menghitung dan mengekstrak basis data!!
`' UNION SELECT sql,NULL,NULL FROM sqlite_master-- -`
Nama tabel yang ditemukan: hints, more_table, offices,users Pada tabel more_table, kita dapat melihat bahwa ada flagkolom!
`' UNION SELECT id,flag,NULL FROM more_table-- -`
