# Christmas Special

🔗 **Resource Link:** [Juice Shop - Injection Challenges](https://juice-shop.herokuapp.com/#/score-board?categories=Injection&showDisabledChallenges=false)

---

## Langkah Penyelesaian

1. **Menemukan Produk yang Sudah Dihapus**  
   Produk *Christmas-Super-Surprise-Box* yang sebelumnya telah dihapus dapat ditemukan menggunakan payload berikut: `test')) UNION SELECT * FROM PRODUCTS WHERE deletedAt IS NOT NULL--`

   
Payload ini menampilkan produk yang sudah tidak aktif (*deletedAt IS NOT NULL*).  

<img width="1500" alt="find-deleted-product" src="https://github.com/user-attachments/assets/2abde6bb-62fe-4d1d-b612-5810a0988c40">

---

2. **Melakukan Pembelian Produk**  
Setelah menemukan produk tersebut, lakukan pembelian dengan menggunakan `ProductId = 10`.  

<img width="1500" alt="purchase-product-1" src="https://github.com/user-attachments/assets/ff8475df-ebd3-4eeb-af4a-aed7ad8dbea0">

<img width="1500" alt="purchase-product-2" src="https://github.com/user-attachments/assets/347b6c9f-40bb-4288-b6dd-1a1cacd141b0">

---

3. **Checkout Produk**  
Setelah produk berhasil dimasukkan ke keranjang, lakukan *checkout*.  
Challenge pun terselesaikan.  

<!-- <img width="1500" alt="checkout-success" src="https://github.com/user-attachments/assets/d0149540-8786-4214-a1ea-9b8b74d69614"> -->

---

## Kesimpulan
- Produk yang dihapus tetap dapat ditemukan melalui *SQL Injection*.  
- Dengan `ProductId = 10`, pembelian terhadap produk tersembunyi dapat dilakukan.  
- Checkout produk tersebut menyelesaikan challenge *Christmas Special*.  
 

