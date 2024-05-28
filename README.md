# Melakukan Proses ETL pada Data Transaksi, Penjualan, Pendapatan dari Dataset Online Retail menggunakan Python.
Pada kali ini dilakukan proses data pipeline ETL (Extract, Tranfer, dan Load)  dengan menggunakan bantuan bahasa pemrograman Python.
Data yang digunakan ada 3 yang merupakan public dataset mengenai online retail yaitu pertama, data aktivitas customer yang berisikan kumpulan data transaksi yang terjadi antara 1 Desember 2009 hingga 9 Desember 2011. Kedua, data penjualan di mana berisi mengenai data transaksi, penjualan produk, pendapatan, dan berfungsi sebagai sumber data penjualan. Ketiga, data produk yang mana merupakan informasi yang didapatkan dari kolom deskripsi. Dalam pengerjaannya, digunakan bantuan google collab untuk mempermudah melakukan pemrograman Python.

## Data Collection
Untuk data yang digunakan bisa contact melalui bilqisaulia38@gmail.com

## Data Extraction menggunakan Python Pandas
Akan dilakukan extraction data online retail. Karena dataset yang digunakan dalam bentuk file excel maka digunakan ``` pandas.read_excel()``` agar dataset terbaca saat melakukan pemrograman. Selain itu, pada langkah ini dilakukan penghilangan nilai yang kosong/ NaN pada dataset.

## Data Tranformation
### Data Customer
Data customer didapatkan dari data lengkap yang sudah dibersihkan sebelumnya, pada data customer terjadinya transformasi perubahan nama kolom “Customer ID” menjadi “CustomerID” dan menambahkan kolom “Pengeluaran” yang didapatkan dari pengalian data “Quantity” dan “Price”.
### Data Penjualan
Proses mendapatkan Data Penjualan dilakukan dengan mentransformasikan penambahan kolom data “Pendapatan” yang didapatkan dari pengalian data “Quantity” dan data “Price” pada Data Customer.
### Data Produk
Data Produk merupakan hasil transformasi data penjualan yang mana hanya mengambil kolom “StockCode” dan “Description” (Data Frame tidak di load ke MySQL karena data frame melebihi kapasitas MySQL yang digunakan. Mungkin dataframe dapat diload menggunakan database yang lain).

## Data Analisis dan Reporting dengan Python Pandas
### Poroduk Terlaris 
Pada proses ini ditampilkan produk terlaris dengan menggabungkan data penjualan dan menyortir berdasarkan kuantitas dan pendapatan serta dalam praktiknya hanya akan ditampilkan 5 produk terlaris. 
### Segmentasi Pelanggan 
Pada proses ini ditampilkan segmentasi pelanggan berdasarkan jumlah pengeluarannya
dan segmentasi negara berdasarkan jumlah pengeluarannya.
1. Segmentasi Pelanggan berdasarkan Jumlah Pengeluarannya
Perhitungan total pengeluaran untuk setiap pelanggan dan membaginya menjadi beberapa segmen seperti pembelanja rendah, menengah ke bawah, menengah ke atas dan tinggi.
2. Segmentasi Negara berdasarkan Jumlah Pengeluarannya
Pada segmentasi negara dilakukan perhitungan total pengeluaran untuk setiap negara dan membaginya menjadi beberapa segmen seperti negara dengan pembelanjaan rendah, menengah ke bawah, menengah ke atas dan tinggi.
### Tren Penjualan
Pada tahap ini disajikan tren penjualan musiman dengan melakukan analisis data penjualan berdasarkan periode waktu seperti hari libur. Langkah pertama yang kami lakukan adalah menghapus jam yang terdapat pada dataset untuk memudahkan program untuk membaca tren dan hari libur nantinya. Selanjutnya untuk mempermudah melihat tren yang terjadi, kami hanya mengambil kolom invoice date dan pendapatan saja. Lalu dilakukan instalasi packages holiday yang mana packages yang digunakan adalah holiday United Kingdom.

## Exporting Reports
Tahap ini dilakukan ekspor dataset yang telah dihasilkan sebelumnya dengan bahasa pemrograman Python pada google collab. Dataset yang diekspor berupa format csv dengan tujuan mempermudah software tableau untuk membaca data dan melakukan visualisasi nantinya. Dengan bantuan fungsi pandas.to_csvl() didownload sebuah dataset dari produk terlaris, segmentasi pelanggan, serta tren penjualan musiman.
