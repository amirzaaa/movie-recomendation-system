# Laporan Proyek Machine Learning - Amir Hamzah

## Project Overview

### Latar Belakang

Pertumbuhan pesat platform e-commerce dan ritel online telah mengubah secara fundamental cara konsumen menemukan dan membeli produk fashion. Dengan jutaan produk fashion yang tersedia di berbagai platform online, konsumen seringkali dihadapkan pada tantangan kelebihan informasi, sehingga semakin sulit untuk menemukan produk yang sesuai dengan preferensi pribadi, gaya, dan kebutuhan mereka. Fenomena ini telah menciptakan kesenjangan yang signifikan antara ekspektasi konsumen dan kemampuan mereka untuk menavigasi katalog produk yang luas dengan efisien. Akibatnya, pengembangan sistem rekomendasi cerdas menjadi krusial untuk meningkatkan pengalaman pengguna, meningkatkan kepuasan pelanggan, dan mendorong pertumbuhan bisnis di industri fashion yang kompetitif [[1](https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/9163/4159)].

Sistem rekomendasi telah muncul sebagai alat yang kuat yang memanfaatkan algoritma pembelajaran mesin dan analisis data untuk memberikan saran produk yang dipersonalisasi kepada pengguna berdasarkan perilaku historis, preferensi, dan karakteristik mereka. Dalam konteks ritel fashion, sistem ini memainkan peran penting dalam membantu pelanggan menemukan produk baru, mengurangi waktu pengambilan keputusan, dan pada akhirnya meningkatkan pengalaman berbelanja mereka. Implementasi algoritma rekomendasi yang efektif dapat berdampak signifikan pada metrik bisnis kunci seperti tingkat konversi, nilai pesanan rata-rata, dan retensi pelanggan. Selain itu, rekomendasi yang dipersonalisasi membantu pengecer fashion memahami preferensi dan pola pembelian pelanggan mereka dengan lebih baik, memungkinkan mereka untuk mengoptimalkan manajemen inventaris dan strategi pemasaran [[2](https://jurnal.plb.ac.id/index.php/tematik/article/view/683/400)].


Di antara berbagai teknik rekomendasi yang tersedia, Content-Based Filtering dan Collaborative Filtering mewakili dua pendekatan fundamental yang telah terbukti sangat efektif dalam skenario rekomendasi produk fashion [[3](http://ejurnal.umri.ac.id/index.php/coscitech/article/view/5131/2462)]. Content-Based Filtering berfokus pada analisis karakteristik dan atribut intrinsik produk fashion, seperti warna, gaya, bahan, merek, dan kategori, untuk merekomendasikan barang yang serupa dengan yang sebelumnya disukai atau dibeli oleh pengguna. Pendekatan ini sangat berharga dalam ritel fashion karena dapat menangkap preferensi gaya spesifik dan pilihan estetika yang krusial dalam pemilihan pakaian dan aksesori. Di sisi lain, penyaringan kolaboratif memanfaatkan perilaku dan preferensi kolektif pengguna yang serupa untuk menghasilkan rekomendasi, beroperasi berdasarkan prinsip bahwa pengguna dengan selera serupa di masa lalu akan terus memiliki preferensi serupa di masa depan [[4](https://www.neliti.com/publications/491509/implementasi-metode-collaborative-filtering-untuk-sistem-rekomendasi-penjualan-p)].

Proyek ini bertujuan untuk mengembangkan dan mengimplementasikan sistem rekomendasi produk fashion yang komprehensif dengan menggabungkan teknik Content-Based Filtering dan Collaborative Filtering menggunakan dataset [_Fashion Product_](https://www.kaggle.com/datasets/bhanupratapbiswas/fashion-products). Dengan mengintegrasikan kedua pendekatan komplementer ini, sistem akan mampu mengatasi keterbatasan yang melekat pada masing-masing metode individu sambil memaksimalkan kekuatan masing-masing. Komponen berbasis konten akan memastikan bahwa rekomendasi tetap relevan dengan atribut produk spesifik dan preferensi gaya pengguna, sementara komponen filtrasi kolaboratif akan memperkenalkan keragaman dan membantu pengguna menemukan tren dan produk fashion baru yang mungkin tidak mereka pertimbangkan sebelumnya. Melalui implementasi ini, proyek ini bertujuan untuk menunjukkan efektivitas pendekatan rekomendasi hibrida dalam mengatasi tantangan nyata dalam e-commerce fashion dan memberikan wawasan tentang pertimbangan praktis yang terlibat dalam pengembangan sistem semacam itu.

### Referensi

[[1](https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/9163/4159)] Fajriansyah, M., Adikara, P. P., & Widodo, A. W. (2021). Sistem Rekomendasi Film Menggunakan Content Based Filtering. Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer, 5(6), 2188-2199.

[[2](https://jurnal.plb.ac.id/index.php/tematik/article/view/683/400))] Suharya, Y., Herdiana, Y., Putri, N. I., & Munawar, Z. (2021). Sistem Rekomendasi Untuk Toko Online Kecil Dan Menengah. TEMATIK, 8(2), 176-185.

[[3](http://ejurnal.umri.ac.id/index.php/coscitech/article/view/5131/2462)] Ardiansyah, R., Bianto, M. A., & Saputra, B. D. (2023). Sistem Rekomendasi Buku Perpustakaan Sekolah menggunakan Metode Content-Based Filtering. Jurnal CoSciTech (Computer Science and Information Technology), 4(2), 510-518.

[[4](https://www.neliti.com/publications/491509/implementasi-metode-collaborative-filtering-untuk-sistem-rekomendasi-penjualan-p)] Februariyanti, H., Laksono, A. D., Wibowo, J. S., & Utomo, M. S. (2021). Implementasi Metode Collaborative Filtering Untuk Sistem Rekomendasi Penjualan Pada Toko Mebel. Jurnal Khatulistiwa Informatika, 9(1), 491509.

## Business Understanding

Pada bagian ini, peneliti menggunakan dataset dari [_Fashion Product_](https://www.kaggle.com/datasets/bhanupratapbiswas/fashion-products) untuk mendukung pelaksanaan proyek ini dengan baik. Berikut merupakan beberapa permasalahan, tujuan, serta pernyataan solusi yang dapat peneliti jabarkan.

### Problem Statements

Adapun agar dapat memberikan tujuan dan solusi yang efektif, berikut merupakan beberapa permasalahan yang telah peneliti angkat.

- Bagaimana cara agar pengguna dapat menerima rekomendasi produk berdasarkan preferensi yang mereka miliki?
- Bagaimana cara agar pengguna tidak menghabiskan banyak waktu untuk memilih produk yang ingin mereka beli?
- Bagaimana cara menerapkan algoritma machine learning yang dapat memberikan rekomendasi yang tepat terhadap pengguna?

### Goals

Berdasarkan problem statements yang ada, berikut adalah beberapa tujuan yang ingin dicapai oleh peneliti.
- Untuk memberikan sistem rekomendasi produk terhadap pengguna berdasarkan preferensi yang mereka miliki 
- Untuk mengatasi dan mengurangi waktu pencarian produk agar pengguna tidak merasa kebingungan
- Untuk menerapkan algoritma machine learning yang dapat memberikan rekomendasi terhadap pengguna

### Solution statements
- Menggunakan Teknik Content-Based Filtering untuk memberikan rekomendasi berdasarkan item yang disukai oleh pengguna
- Menggunakan Teknik Collaborative Filtering untuk memberikan rekomendasi berdasarkan rating terhadap item yang diberikan oleh pengguna

## Data Understanding
Pada tahapan ini, peneliti melakukan data understanding untuk dapat memahami variabel-variabel, tingkat kebersihan data dari duplikasi dan nilai yang kosong, serta statistika deskriptif yang ada pada dataset [_Fashion Product_](https://www.kaggle.com/datasets/bhanupratapbiswas/fashion-products) yang akan digunakan. Berikut adalah beberapa tahapannya.

### Deskripsi Variabel

Pada tahapan ini, peneliti akan menjabarkan terkait fitur dan deskripsi fitur pada dataset yang digunakan. Berikut ini adalah penjabarannya yang disusun dalam bentuk tabel.

| Fitur     | Deskripsi                                                  |
|-----------|------------------------------------------------------------|
|User ID|Merupakan ID unik yang merepresentasikan id pengguna|
|Product ID|Merupakan ID unik yang merepresentasikan id produk|
|Product Name|Merupakan nama produk|                 |
|Brand|Merupakan brand dari produk|
|Category|Merupakan Kategori dari produk|
|Price|Merupakan harga dari produk|
|Rating|Merupakan rating yang diberikan pengguna terhadap produk yang di beli|
|Color|Merupakan representasi warna dari produk|
|Size|Merupakan representasi ukuran dari produk|

### Memahami Informasi pada Data

Tahapan ini dilakukan untuk mengetahui informasi penting yang ada pada dataframe. Dengan menggunakan kode `fashion.head(5)` dan `fashion.info()` kita dapat menampilkan 5 baris awal pada dataframe yang digunakan dan juga bisa mendapatkan informasi seperti jumlah baris dan kolom, jenis tipe data pada setiap fitur, dan jumlah missing value yang ada pada dataframe fashion. Berikut adalah implementasi kodenya.

| User ID | Product ID | Product Name | Brand  | Category        | Price | Rating    | Color  | Size |
|---------|------------|---------------|--------|------------------|--------|-----------|--------|------|
| 19      | 1          | Dress         | Adidas | Men's Fashion    | 40     | 1.043159  | Black  | XL   |
| 97      | 2          | Shoes         | H&M    | Women's Fashion  | 82     | 4.026416  | Black  | L    |
| 25      | 3          | Dress         | Adidas | Women's Fashion  | 44     | 3.337938  | Yellow | XL   |
| 57      | 4          | Shoes         | Zara   | Men's Fashion    | 23     | 1.049523  | White  | S    |
| 79      | 5          | T-shirt       | Adidas | Men's Fashion    | 79     | 4.302773  | Black  | M    |


| No | Column        | Count | Non-Null Count| Dtype   |
|----|---------------|----------------|---------|---------|
| 0  | User ID       | 1000           | Non-Null|int64   |
| 1  | Product ID    | 1000           | Non-Null|int64   |
| 2  | Product Name  | 1000           | Non-Null|object  |
| 3  | Brand         | 1000           | Non-Null |object  |
| 4  | Category      | 1000           |Non-Null  |object  |
| 5  | Price         | 1000           | Non-Null   |int64   |
| 6  | Rating        | 1000           | Non-Null |float64 |
| 7  | Color         | 1000           | Non-Null  |object  |
| 8  | Size          | 1000           | Non-Null  |object  |

Dari hasil implementasi kode tersebut terdapat 9 jumlah kolom dengan total 1000 baris. Pada dataframe tersebut data tergolong bersih dari missing value yang ditandakan dengan non-null

### Mengecek Duplikasi Data

Selanjutnya, tahapan ini dilakukan untuk mendapatkan informasi terkait jumlah duplikasi data yang ada pada data fashion. Dengan menggunakan fungsi `duplicated().sum()` kita bisa melihat jumlah duplikasi data pada data yang akan digunakan. Berikut adalah hasil dari implementasi kode nya.

```
Jumlah duplikasi data pada dataframe sebanyak:  0
```

Dari hasil tersebut dapat diketahui bahwa terdapat total 0 data yang terduplikasi. Hal tersebut mengindikasikan bahwa tidak ada yang terduplikasi pada data fashion product.

### Memahami Statistika Deskriptif pada Data

Selanjutnya tahapan ini dilakukan untuk memahami statistika deskriptif pada data yang akan digunakan. tahap ini mengimplementasikan fungsi `.describe()` untuk mendapatkan informasi seperti count, mean, standard deviasi, min, kuartil, dan max. fungsi tersebut akan diimplementasikan hanya pada dataframe rating, karena pada dataframe movies tidak ada informasi penting yang dapat diambil terkait statistika deskriptif. berikut adalah implementasi kodenya.

| Statistik | userId        | movieId       | rating     | timestamp     |
|-----------|---------------|---------------|------------|---------------|
| count     | 25,000,100    | 25,000,100    | 25,000,100 | 25,000,100    |
| mean      | 81,189.28     | 21,387.98     | 3.53       | 1,215,601,000 |
| std       | 46,791.72     | 39,198.86     | 1.06       | 226,875,800   |
| min       | 1             | 1             | 0.5        | 789,652,000   |
| 25%       | 40,510        | 1,196         | 3.0        | 1,011,747,000 |
| 50%       | 80,914        | 2,947         | 3.5        | 1,198,868,000 |
| 75%       | 121,557       | 8,623         | 4.0        | 1,447,205,000 |
| max       | 162,541       | 209,171       | 5.0        | 1,574,328,000 |

Berikut adalah insight singkat terkait kolom **Price** dan **Rating** dari statistik deskriptif dataset:

- **Price**:
  - Rata-rata harga produk adalah 55.78, dengan rentang harga dari 10 hingga 100, menunjukkan variasi harga yang cukup lebar.
  - Median harga (57) hampir sama dengan rata-rata, mengindikasikan distribusi harga yang cukup simetris.
  - Sebagian besar harga (50%) berada antara 33 (Q1) dan 78.25 (Q3), menunjukkan bahwa mayoritas produk memiliki harga menengah.
  - Standar deviasi harga (26.29) menunjukkan adanya variasi yang moderat dalam harga produk.

- **Rating**:
  - Rata-rata rating adalah 2.99 dari skala maksimum 5, menunjukkan bahwa pengguna cenderung memberikan rating yang sedikit di bawah rata-rata (netral).
  - Median rating (2.98) sangat dekat dengan rata-rata, mengindikasikan distribusi rating yang cukup simetris.
  - Sebagian besar rating (50%) berada antara 1.99 (Q1) dan 3.99 (Q3), menunjukkan bahwa rating cenderung berkisar dari rendah hingga tinggi, dengan sedikit kecenderungan ke arah rating sedang.
  - Standar deviasi rating (1.15) menunjukkan variasi yang cukup besar dalam penilaian pengguna, dari 1.00 hingga 4.99.

### Exploratory Data Analysis

Selanjutnya, tahapan ini dilakukan untuk mendapatkan hasil analisis mengenai insight terkait distribusi data, dan lain sebagainya dalam bentuk visualisasi. Berikut adalah beberapa implementasinya

### 1. Analisis Distribusi Brand

Tahapan ini dilakukan untuk mendapatkan insight terkait bagaimana distribusi dari brand yang dibeli oleh pengguna. tahapan ini mengimplementasikan kode sns.countplot() yang tersedia pada library seaborn. Berikut adalah hasil dari implementasinya.

![image](https://github.com/user-attachments/assets/659aa4d1-8270-4685-840a-d0ed76f71a9d)

Adidas, H&M, Zara, Gucci, dan Nike semuanya terwakili secara relatif merata dalam dataset, menurut grafik distribusi merek, dengan setiap merek muncul dalam jumlah yang berkisar antara 175 hingga 200.  Mendekati angka 200, Nike menonjol sebagai merek yang paling banyak terwakili, menunjukkan kemungkinan peningkatan ketersediaan atau popularitas dalam dataset.  Gucci tampaknya memiliki jumlah terendah di antara kelima merek, berkisar sekitar 175, sementara Adidas, H&M, dan Zara mengikuti dengan jumlah antara 175 dan 190, menunjukkan kehadiran yang stabil.

### 2. Analisis Rata-Rata Rating Berdasarkan Brand

Tahapan ini dilakukan untuk mendaptkan informasi terkait bagaimana rata-rata distribusi rating pada tiap brand nya. Dengan melakukan `groupby()` terhadap brand kemudian menghitung rata-rata rating menggunakan fungsi `mean()` dan di visualisasikan menggunaka library matplotlib, peneliti mengharapkan dapat gambaran terkait analisis tersebut. Berikut adalah implementasi kode serta hasilnya.

![image](https://github.com/user-attachments/assets/66401aec-d85e-419a-b0f1-957993d91b8f)


Dari hasil tersebut, brand yang memiliki rata-rata rating paling tinggi adalah brand Gucci. Sedangkan brand Nike dengan distribusi data paling banyak memiliki rata-rata rating paling rendah. Hal ini mengindikasin bahwa, terdapat kemungkinan jika semakin banyak data yang terjual (mendapatkan rating) semakin tinggi terjadinya penurunan rata-rata rating secara kumulatif.


## Data Preparation

### 1. Menghapus Data Genre yang TIdak Valid

Selanjutnya, tahapan ini dilakukan untuk menghapus genre yang tidak memberikan informasi secara spesifik. Genres tersebut terdapat pada dataframe movies dengan genre (no genres listed). Berikut adalah implementasi kodenya.

```
print("Jumlah baris sebelum menghapus (no genres listed): " , len(movies))
movies = movies.drop(movies[movies['genres'] == '(no genres listed)'].index)
print("Jumlah baris setelah menghapus (no genres listed): " , len(movies))
```

Output:

```
Jumlah baris sebelum menghapus (no genres listed):  62423
Jumlah baris setelah menghapus (no genres listed):  57361
```

Berdasarkan hasil dari analisis distribusi genres, genres dengen genre (no genres listed) memiliki jumlah sebanyak data sebanyak 5062. Hal itu menandakan bahwa data genres tersebut berhasil dihapus dengan baik jika dilihat dari jumlah data sebelum dan setelah dihapus.

### 2. Menghapus Kolom Tidak Diperlukan

Selanjutnya, pada tahapan ini peneliti akan melakukan penghapusan pada fitur yang tidak diperlukan. Hal ini dilakukan agar pada tahap pemodelan nanti variabel yang akan digunakan hanyalah variabel yang penting saja. Berikut adalah implementasi kodenya.

```
rating = rating.drop('timestamp', axis=1)
rating
```

Dengan mengimplementasikan kode tersebut, fitur timestamp telah berhasil dihapus pada variabel rating.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
