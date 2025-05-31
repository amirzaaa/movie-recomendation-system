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

Selanjutnya tahapan ini dilakukan untuk memahami statistika deskriptif pada data yang akan digunakan. tahap ini mengimplementasikan fungsi `.describe()` untuk mendapatkan informasi seperti count, mean, standard deviasi, min, kuartil, dan max. Berikut adalah implementasi kodenya

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

### 1. Membuat Dataframe untuk Model Content-Based Filtering

Selanjutnya, tahapan ini dilakukan agar fitur-fitur yang tidak digunakan pada model content-based filtering dapat dikecualikan terlebih dahulu untuk mengurangi dimensi data yang akan di modelkan. Berikut adalah implementasi kode nya.

![image](https://github.com/user-attachments/assets/bfdf3191-3a16-46dc-942b-99a0de0e5d49)

Dari hasil implementasi kode diatas, peneliti berhasil untuk membuat dataframe baru untuk model content-based filter dengan memilih fitur User ID, Product Name ID, dan Brand sebagai fitur fitur yang akan digunakan ketika pemodelan nanti. Hal pertama yang dilakukan oleh peneliti adalah dengan memnbuat dataframe baru dengan menyalin data-data dari dataframe fashion, kemudian menginisialisasi fitur baru bernama Product Name ID yang memiliki nilai gabungan dari fitur Product Name dan fitur Product ID. Setelah itu, peneliti mengurangi dimensi dari data dengan menyeleksi fitur fitur yang akan digunaka

### 2. Membuat Dataframe untuk model Collaborative Filtering

Setelah membuat dataframe untuk model CBF, peneliti juga membuat dataframe baru khusus untuk digunakan saat pemodelan dengan menggunakan Collaborative Filtering. Berikut adalah hasil dari implementasi kodenya.

![image](https://github.com/user-attachments/assets/7b91c664-fb75-4ad1-b06b-0d321c936874)

Dari hasil tersebut dapat dilihat bahwa peneliti membuat dataframe cf_data. Dataframe tersebut berisi fitur-fitur seperti User ID, Product ID dan Rating. Berbeda dengan model CBF, model Collaborative Filtering sangat membutuhkan fitur rating untuk melakukan pemodelan, karena model tersebut dibuat berdasarkan rating yang diberikan oleh pengguna terhadap suatu item.

## Modeling

Setelah melakukan tahapan Data Understanding dan Data Preparation, tahapan selanjutnya adalah dengan melakukan tahapan modeling sistem rekomendasi. Model yang digunakan dalam proyek kali ini adalah dengan mencoba menerapkan model Content-Based Filtering dan Collaborative Filtering. Berikut adalah tahapan-tahapnnya.

### 1. Content-Based Filtering Model

Content-based filtering adalah teknik rekomendasi yang menyarankan item kepada pengguna berdasarkan karakteristik item yang sebelumnya mereka minati. Dalam konteks produk fashion, sistem ini menganalisis fitur-fitur intrinsik seperti warna, gaya, merek, kategori, harga, dan atribut musiman untuk membentuk profil item dan pengguna. Sistem kemudian menghitung skor kemiripan antara preferensi pengguna dan karakteristik produk untuk merekomendasikan item yang paling relevan. Pendekatan ini sangat cocok untuk rekomendasi fashion karena keputusan pembelian sering dipengaruhi oleh preferensi gaya, kesesuaian warna, loyalitas merek, dan tren musiman.

**Kelebihan**:

- Transparansi tinggi - mudah dijelaskan mengapa suatu produk direkomendasikan
- Mengatasi cold start problem untuk item baru
- Konsistensi dengan preferensi user
- Coverage yang baik untuk produk niche
- Privacy-friendly - tidak perlu data user lain

**Kekurangan**:

- Over-specialization - bisa terjebak dalam "filter bubble"
- Bergantung pada kualitas feature extraction
- Cold start problem untuk user baru
- Sulit menangkap preferensi kompleks
- Kurang adaptif terhadap perubahan preferensi

Setelah mengetahui definisi, kelebihan serta kekurangan dari model content-based filtering, berikut adalah tahapan-tahapan dari pemodelan content-based filtering yang telah dilakukan:

#### 1.1 TF-IDF Vectorizer

TF-IDF (Term Frequency-Inverse Document Frequency) adalah komponen penting dalam sistem content-based filtering yang mengubah deskripsi dan fitur tekstual produk menjadi vektor numerik agar dapat diproses oleh algoritma machine learning. Dalam rekomendasi produk fashion, TF-IDF merepresentasikan atribut seperti deskripsi, kategori, gaya, dan material dengan menilai seberapa sering suatu istilah muncul dalam produk tertentu (TF) dan seberapa unik istilah tersebut dalam seluruh katalog produk (IDF). Proses ini menghasilkan matriks fitur yang memungkinkan perhitungan kemiripan antar produk, sehingga membantu sistem mengenali atribut yang paling relevan dan membedakan satu produk dengan lainnya secara lebih akurat. Berikut adalah contoh hasil dari penerapan TF-IDF pada proyek yang ini.

| Product Name ID | adidas | gucci | zara | nike | ... |
|-----------------|--------|-------|------|------|-----|
| Shoes 395       | 0.0    | 0.0   | 0.0  | 1.0  | ... |
| Jeans 960       | 0.0    | 1.0   | 0.0  | 0.0  | ... |
| Jeans 346       | 1.0    | 0.0   | 0.0  | 0.0  | ... |
| Dress 692       | 0.0    | 0.0   | 0.0  | 1.0  | ... |
| T-shirt 204     | 0.0    | 0.0   | 1.0  | 0.0  | ... |
| Sweater 441     | 1.0    | 0.0   | 0.0  | 0.0  | ... |
| Jeans 362       | 1.0    | 0.0   | 0.0  | 0.0  | ... |
| T-shirt 666     | 0.0    | 0.0   | 0.0  | 0.0  | ... |
| T-shirt 642     | 0.0    | 1.0   | 0.0  | 0.0  | ... |
| Sweater 416     | 0.0    | 0.0   | 0.0  | 0.0  | ... |

Hasil diatas merupakan penerapan dari TF-IDF matrix yang telah di buat. Setelah data diubah ke dalam representasi numerik, matriks tersebut disimpan kedalam bentuk dataframe.

#### 1.2 Cosine Similarity

Cosine similarity adalah metrik utama dalam content-based filtering yang mengukur kemiripan antara dua item atau antara preferensi pengguna dan karakteristik produk berdasarkan sudut antara dua vektor fitur. Nilainya berkisar dari 0 hingga 1 (karena fitur produk biasanya non-negatif), dan dihitung menggunakan rumus: 

![image](https://github.com/user-attachments/assets/bd0af1c8-5652-4f9b-b9da-2b4747d33633) 

Metrik ini efektif untuk rekomendasi fashion karena mempertimbangkan arah vektor dibandingkan besarannya, cocok untuk data yang jarang (sparse), efisien secara komputasi, serta bekerja baik dengan representasi fitur dari TF-IDF, sehingga mampu mengenali produk dengan atribut yang mirip seperti gaya, bahan, atau warna. Berikut adalah hasil dari penerapan cosine similarity tersebut.

| Product Name ID | Jeans 851 | Jeans 727 | Jeans 905 | Shoes 667 | T-shirt 471 |
|-----------------|-----------|-----------|-----------|-----------|--------------|
| Jeans 738       | 0.0       | 0.0       | 0.0       | 0.0       | 0.0          |
| Shoes 902       | 0.0       | 0.0       | 0.0       | 0.0       | 0.0          |
| Jeans 943       | 0.0       | 0.0       | 0.0       | 0.0       | 0.0          |
| Shoes 188       | 1.0       | 0.0       | 1.0       | 1.0       | 1.0          |
| Jeans 809       | 0.0       | 1.0       | 0.0       | 0.0       | 0.0          |
| Shoes 750       | 1.0       | 0.0       | 1.0       | 1.0       | 1.0          |
| T-shirt 726     | 1.0       | 0.0       | 1.0       | 1.0       | 1.0          |
| Dress 841       | 0.0       | 0.0       | 0.0       | 0.0       | 0.0          |
| Sweater 581     | 0.0       | 0.0       | 0.0       | 0.0       | 0.0          |
| Jeans 497       | 0.0       | 0.0       | 0.0       | 0.0       | 0.0          |

Hasil dari cosine similarity diatas ditampilkan dalam bentuk dataframe dengan menggunakan index dan kolom dari Product Name ID. Setelah melakukan penerapan cosine similarity, tahapan selanjutnya adalah dengan membuat fungsi yang dapat memberikan rekomendasi menggunakan model Content-Based Filtering. berikut adalah implementasi kode beserta hasilnya.

**Implementasi Kode**:

```
def cbf_recommendations(nama_product, similarity_data=cosine_sim_df, items=cbf_data[['Product Name ID','Brand']], k=10):
    index = similarity_data.loc[:,nama_product].to_numpy().argpartition(
        range(-1, -k, -1))
    closest = similarity_data.columns[index[-1:-(k+2):-1]]
    closest = closest.drop(nama_product, errors='ignore')
    return pd.DataFrame(closest).merge(items).head(k)
cbf_recommendations('Shoes 996')
```

**Output**:

![image](https://github.com/user-attachments/assets/a0df5050-150f-4281-a317-e223de793626)

Hasil diatas merupakan hasil rekomendasi dari model Content-Based Filtering berdasarakn Product Name ID `Shoes 996` yang meruakan Brand dari Zara. Hasil ditampilkan dalam bentuk dataframe dengan kolom Product Name ID dan Brand sebagai fitur utamanya.

### 2. Collaborative Filtering Model

Collaborative filtering adalah teknik rekomendasi yang memprediksi preferensi pengguna berdasarkan pola interaksi kolektif antar pengguna, tanpa bergantung pada atribut produk. Teknik ini bekerja dengan mengidentifikasi kesamaan perilaku antara pengguna atau item berdasarkan data historis seperti pembelian, penilaian, atau tampilan. Collaborative filtering terbagi menjadi dua jenis utama: memory-based (berbasis pengguna atau item) dan model-based (menggunakan algoritma pembelajaran mesin). Dalam konteks fashion, teknik ini efektif karena preferensi gaya sering dipengaruhi oleh tren sosial dan perilaku pengguna lain, sehingga memungkinkan sistem untuk menangkap hubungan implisit antar produk yang tidak tampak secara eksplisit.

**Kelebihan**

- Tidak memerlukan product attributes yang detail
- Menangkap relasi implisit antar produk
- Identifikasi tren dan produk populer
- Memberikan insights tentang segmen pasar

**Kekurangan**

- Cold start problem - untuk user baru dan produk baru
- Scalability issues - tantangan komputasi saat data membesar
- Popularity bias - produk populer lebih sering direkomendasikan
- Lack of explainability - sulit menjelaskan alasan rekomendasi

#### Singular Value Decomposition (SVD)

Singular Value Decomposition (SVD) adalah teknik faktorisasi matriks yang digunakan dalam model-based collaborative filtering, khususnya melalui library Surprise. SVD memecah matriks interaksi pengguna-item menjadi tiga matriks berdimensi lebih rendah untuk mengungkap faktor laten seperti preferensi gaya, sensitivitas harga, atau afinitas merek. Dengan mereduksi dimensi dan mempertahankan nilai singular paling signifikan, SVD mengurangi noise dan meningkatkan akurasi rekomendasi. Implementasi di Surprise juga mencakup bias dan regularisasi untuk mencegah overfitting dan meningkatkan performa prediksi.

Berikut ini adalah hasil dari penerapan model Collaborative FIltering dengan menggunakan library Surprise.

**Implementasi Kode**:

```
recommend = cf_recommendation_system(cf_data)
recommend.fit()

recommend.recommendation(user_id=10)
```

**Output**:

![image](https://github.com/user-attachments/assets/d9ea3668-2858-48c8-aaaa-301277cfe80d)

Dengan menginisialisasi variabel recommend yang menyimpan nilai dari kelas `cf_recommendation_system` yang berisi model yang telah dibuat, kemudian melakukan `fit()` dan memanggil fungsi `recommendation()` berdasarkan `user_id` dengan nilai 10, model tersebut dapat memberikan 10 saran product berdasarkan rating yang diberikan oleh user_id dengan nilai 10.

## Evaluation

Untuk mengevaluasi model yang telah dibuat, pada proyek ini peneliti menggunakan metode evaluasi Precision@K untuk model CBF dan metode evaluasi cross validation (RMSE dan MAE) untuk model Collaborative Filtering. Berikut adalah hasil evaluasinya.

### Precision@K

Precision\@K adalah metrik evaluasi yang mengukur proporsi item relevan di antara K rekomendasi teratas. Dalam rekomendasi fashion, metrik ini penting karena mencerminkan seberapa akurat sistem menyarankan produk yang sesuai dengan preferensi pengguna dalam daftar terbatas. Berikut adalah hasil dari penerapan evaluasi Precision@K pada model CBF.

![image](https://github.com/user-attachments/assets/bd61c1f7-9bbf-4726-a916-d93366812766)

Hasil evaluasi **Precision@K** 0.1 untuk "Shoes 996" menunjukkan bahwa hanya 10% dari K item teratas yang direkomendasikan relevan, kemungkinan karena dataset dominasi merek "Zara" dengan kategori beragam (Shoes, Sweater, Dress), dan model kurang fokus pada kesamaan kategori, memengaruhi akurasi rekomendasi.

### Cross Validation (RMSE dan MAE)

Cross validation adalah teknik evaluasi yang membagi dataset menjadi beberapa bagian untuk melatih dan menguji model collaborative filtering secara bergantian, sehingga hasil evaluasi lebih andal. Dua metrik yang umum digunakan adalah:

- RMSE (Root Mean Squared Error)

![image](https://github.com/user-attachments/assets/657591ca-132a-4243-a76d-4af68cd8d028)

rumus diatas mengukur rata-rata kesalahan kuadrat antara rating prediksi dengan rating aktual. RMSE sensitif terhadap kesalahan besar.
 
- MAE (Mean Absolute Error)

![image](https://github.com/user-attachments/assets/efb10bc5-5696-415f-aec3-4de8cde585d2)

yang menghitung rata-rata selisih absolut antara rating prediksi dan aktual, memberikan interpretasi yang lebih intuitif terhadap kesalahan prediksi.

Dalam sistem rekomendasi fashion, metrik ini membantu menilai seberapa akurat model memprediksi preferensi pengguna terhadap produk fashion. Berikut ini adalah hasil dari penerapan cross validation RMSE dan MAE pada model collaborative filtering.

![image](https://github.com/user-attachments/assets/8df5818d-be04-43c9-a677-142c387d9407)

- Rata-rata RMSE (Root Mean Square Error) adalah 1.1698 ± 0.0399, artinya rata-rata kesalahan prediksi kuadratnya sekitar 1.17 dengan deviasi kecil, menunjukkan model cukup konsisten.
- Rata-rata MAE (Mean Absolute Error) adalah 1.0032 ± 0.0457, berarti rata-rata kesalahan absolut model dalam memprediksi rating pengguna terhadap produk fashion adalah sekitar 1 poin.
- Waktu pelatihan (fit time) sangat cepat, rata-rata hanya 0.03 detik per fold, dan waktu pengujian (test time) hampir nol, menunjukkan efisiensi komputasi yang tinggi.

Secara keseluruhan, model SVD memberikan prediksi yang cukup akurat dan efisien untuk sistem rekomendasi fashion berdasarkan data interaksi pengguna.

### Kesimpulan Hasil Evaluasi

**---Ini adalah bagian akhir laporan---**

