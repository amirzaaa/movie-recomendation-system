# Laporan Proyek Machine Learning - Amir Hamzah

## Project Overview

### Latar Belakang

Di era digital, platform streaming seperti Netflix dan Disney+ menyediakan ribuan film, tetapi banyaknya pilihan justru menyebabkan masalah baru.  Di tengah katalog yang luas, pengguna sering bingung menemukan konten yang sesuai dengan preferensi mereka.  Seperti yang ditunjukkan oleh studi Nielsen, rata-rata pelanggan menghabiskan 18 menit hanya untuk memilih film, sementara penelitian McKinsey menunjukkan bahwa 80% langganan pelanggan menghentikan pembelian karena rekomendasi yang tidak relevan.  Fenomena overload data ini tidak hanya membuang waktu, tetapi juga membuat pengguna kurang puas dan setia [[1](https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/9163/4159)].

Terbukti bahwa metode rekomendasi konvensional yang bergantung pada kategori umum seperti genre atau film populer tidak cukup.  Metode seperti ini tidak dapat memenuhi kebutuhan khusus setiap orang, seperti ketertarikan aktor tertentu, nuansa cerita, atau preferensi sutradara.  Akibatnya, pengguna menerima rekomendasi yang umum dan tidak personal, yang pada akhirnya menyebabkan mereka kurang terlibat dengan platform [[2](https://jurnal.plb.ac.id/index.php/tematik/article/view/683/400)].

Sistem rekomendasi berbasis AI adalah solusi penting untuk masalah ini. Dengan menggunakan teknik machine learning seperti Collaborative Filtering (menganalisis pola pengguna yang mirip) dan Content Based Filtering (mencari kesamaan atribut film), sistem dapat menghasilkan rekomendasi yang sangat individual [[3](http://ejurnal.umri.ac.id/index.php/coscitech/article/view/5131/2462)]. Misalnya, sistem akan menyarankan film sci-fi seperti "Inception" kepada orang yang menyukainya tanpa mempertimbangkan sutradara (Christopher Nolan) atau kompleksitas alur cerita [[4](https://www.neliti.com/publications/491509/implementasi-metode-collaborative-filtering-untuk-sistem-rekomendasi-penjualan-p)].

Implementasi sistem ini meningkatkan retensi pelanggan dan menghemat waktu pengguna hingga 70% (penelitian MIT).  Platform memiliki kemampuan untuk mengubah ketidakpastian menjadi keputusan cepat sekaligus meningkatkan nilai bisnis melalui peningkatan keterlibatan pengguna.  Pada akhirnya, tujuan proyek ini adalah untuk menjembatani perbedaan antara kebutuhan pengguna untuk menyesuaikan konten dan banyaknya konten yang tersedia.

### Referensi

[[1](https://j-ptiik.ub.ac.id/index.php/j-ptiik/article/view/9163/4159)] Fajriansyah, M., Adikara, P. P., & Widodo, A. W. (2021). Sistem Rekomendasi Film Menggunakan Content Based Filtering. Jurnal Pengembangan Teknologi Informasi dan Ilmu Komputer, 5(6), 2188-2199.

[[2](https://jurnal.plb.ac.id/index.php/tematik/article/view/683/400))] Suharya, Y., Herdiana, Y., Putri, N. I., & Munawar, Z. (2021). Sistem Rekomendasi Untuk Toko Online Kecil Dan Menengah. TEMATIK, 8(2), 176-185.

[[3](http://ejurnal.umri.ac.id/index.php/coscitech/article/view/5131/2462)] Ardiansyah, R., Bianto, M. A., & Saputra, B. D. (2023). Sistem Rekomendasi Buku Perpustakaan Sekolah menggunakan Metode Content-Based Filtering. Jurnal CoSciTech (Computer Science and Information Technology), 4(2), 510-518.

[[4](https://www.neliti.com/publications/491509/implementasi-metode-collaborative-filtering-untuk-sistem-rekomendasi-penjualan-p)] Februariyanti, H., Laksono, A. D., Wibowo, J. S., & Utomo, M. S. (2021). Implementasi Metode Collaborative Filtering Untuk Sistem Rekomendasi Penjualan Pada Toko Mebel. Jurnal Khatulistiwa Informatika, 9(1), 491509.

## Business Understanding

Pada bagian ini, peneliti menggunakan dataset dari [_Movie Recommendation System_](https://www.kaggle.com/datasets/parasharmanas/movie-recommendation-system) untuk mendukung pelaksanaan proyek ini dengan baik. Berikut merupakan beberapa permaasalahan, tujuan, serta pernyataan solusi yang dapat peneliti jabarkan.

### Problem Statements

Adapun agar dapat memberikan tujuan dan solusi yang efektif, berikut merupakan beberapa permasalahan yang telah peneliti angkat.

- Bagaimana cara agar pengguna dapat menerima rekomendasi film berdasarkan preferensi yang mereka miliki?
- Bagaimana cara agar pengguna tidak menghabiskan banyak waktu untuk memilih film yang ingin ditonton?
- Bagaimana cara menerapkan algoritma machine learning yang dapat memberikan rekomendasi yang tepat terhadap pengguna?

### Goals

Berdasarkan problem statements yang ada, berikut adalah beberapa tujuan yang ingin dicapai oleh peneliti.
- Untuk memberikan sistem rekomendasi film terhadap pengguna berdasarkan preferensi yang mereka miliki 
- Untuk mengatasi dan mengurangi waktu pencarian film agar pengguna tidak merasa kebingungan
- Untuk menerapkan algoritma machine learning yang dapat memberikan rekomendasi terhadap pengguna

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution approach (algoritma atau pendekatan sistem rekomendasi).

## Data Understanding
Pada tahapan ini, peneliti melakukan data understanding untuk dapat memahami variabel-variabel, tingkat kebersihan data dari duplikasi dan nilai yang kosong, serta statistika deskriptif yang ada pada dataset [_Movie Recommendation System_](https://www.kaggle.com/datasets/parasharmanas/movie-recommendation-system) yang akan digunakan. berikut adalah beberapa tahapannya.

Pada dataset yang peneliti gunakan, terdapat dua file dalam bentuk csv yang merupakan bagian keseluruhan dari dataset tersebut, berikut adalah informasi mengenai dua file data tersebut.

### Deskripsi Variabel

#### Movies.csv

File ini berisi data terkait `movieId`, `title`, dan `genres`. Berikut adalah informasi lengkap mengenai fitur-fitur tersebut.

| Fitur     | Deskripsi                                                  |
|-----------|------------------------------------------------------------|
| movieId   | Merupakan primary key yang merepresentasikan setiap film dalam dataset              |
| title     | Merupakan judul dari setiap film yang ada                 |
| genres    | Merupakan genre dari setiap film yang ada                 |

#### Ratings.csv

File ini berisi data terkait userId, movieId, rating, dan timestamp. Berikut adalah informasi lengkap mengenai fitur-fitur tersebut.

| Fitur     | Deskripsi                                                                 |
|-----------|--------------------------------------------------------------------------|
| userId    | Merupakan primary key yang merepresentasikan setiap pengguna (user)         |
| movieId   | Merupakan foreign key yang merepresentasikan setiap film dalam dataset      |
| rating    | Nilai penilaian atau skor yang diberikan oleh pengguna terhadap suatu film|
| timestamp | Waktu ketika pengguna memberikan rating, dalam format Unix timestamp     |

### Memahami Informasi pada Data

Tahapan ini dilakukan untuk mengetahui informasi penting yang ada pada dataframe. dengan menggunakan kode `movies.info()` kita bisa mendapatkan informasi seperti jumlah baris dan kolom, jenis tipe data pada setiap fitur, dan jumlah missing value yang ada pada dataframe movies. Berikut adalah implementasi kodenya.

| No | Column   | Non-Null Count | Dtype  |
|----|----------|----------------|--------|
| 1  | movieId  | 62,423         | int64  |
| 2  | title    | 62,423         | object |
| 3  | genres   | 62,423         | object |

Dari hasil implementasi kode tersebut terdapat 3 jumlah kolom dengan total 62423 baris. Pada dataframe tersebut data tergolong bersih dari missing value yang ditandakan dengan non-null. Kemudian, berikut adalah hasil dari implementasi kode yang diterapkan pada variabel rating `rating.info()`.

![image](https://github.com/user-attachments/assets/111c9e10-f19a-48a3-9e6b-d80f067234c1)

Dari hasil implementasi kode tersebut terdapat 4 jumlah kolom dengan total 25000095 baris. Namun pada hasil dari implementasi kode rating.info() tidak dapat menampilkan informasi terkait missing value, dikarenakan terlalu banyaknya jumlah data yang ada.

### Mengecek Missing Value (Rating)

Selanjutnya, karena informasi terkait missing value tidak dapat diketahui dengan menggunakan rating.info(), peneliti menggunakan implementasi kode berikut `rating.isna().sum()` unuk mendapatkan informasi terkait missing value yang ada pada variabel rating.

| Column | Jumlah Missing Value   |
|---------|-----------------------|
| userId  | 0 |
| movieId | 0 |
| rating  |  0  |
| timestamp | 0 |

dari hasil tersebut data dipastikan aman dari missing value yang diindikasikan oleh nilai 0 pada setiap kolom nya

### Mengecek Duplikasi Data

Selanjutnya, tahapan ini dilakukan untuk mendapatkan informasi terkait jumlah dauplikasi data pada dataframe movies dan rating yang telah dibuat. Dengan menggunakan fungsi `duplicated().sum()` kita bisa melihat jumlah duplikasi data yang ada pada kedua variabel yang akan digunakan. Berikut adalah hasil dari implementasi kode nya.

```
Jumlah duplikasi data pada dataframe rating sebanyak:  0
Jumlah duplikasi data pada dataframe rating sebanyak:  0
```

Dari hasil tersebut dapat diketahui bahwa terdapat total 0 data yang terduplikasi. Hal itu mengindikasikan bahwa tidak ada yang terduplikasi pada variabel movies dan rating.

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

Dari hasil tersebut, berikut adalah beberapa insight yang dapat disimpulkan.

- Rata-rata Rating: Rata-rata rating (mean) adalah 3.53 dari skala maksimum 5, menunjukkan bahwa secara umum pengguna cenderung memberikan rating yang cukup positif (di atas netral, yaitu 3).
- Variasi Rating: Standar deviasi rating adalah 1.06, yang berarti ada variasi sedang dalam rating yang diberikan pengguna. Rating tidak terlalu homogen, tetapi juga tidak terlalu bervariasi ekstrem.
- Rentang Rating: Rating minimum adalah 0.5 dan maksimum adalah 5.0, menunjukkan bahwa pengguna memanfaatkan seluruh skala rating yang tersedia, meskipun rating rendah (di bawah 3) lebih jarang terjadi berdasarkan distribusi kuartil.

### Exploratory Data Analysis

Selanjutnya, tahapan ini dilakukan untuk mendapatkan hasil analisis mengenai insight terkait distribusi data, dan lain sebagainya dalam bentuk visualisasi. Berikut adalah beberapa implementasinya

### 1. Analisis Distribusi Rating

Tahapan ini dilakukan untuk mendapatkan insight terkait bagaimana distribusi dari rating yang diberikan oleh pengguna. tahapan ini mengimplementasikan kode sns.countplot() yang tersedia pada library seaborn. berikut adalah hasil dari implementasinya.

![image](https://github.com/user-attachments/assets/bed1670b-61b7-4d20-9d3a-3b36f4e71f57)

Berikut adalah insight yang dapat diambil dari hasil visualisasi diatas.

- Most Rating: pengguna secara keseluruhan memberikan rating sebanyak 4.0 terhadap film yang mereka tonton. Tidak hanya itu, rating 3 dan 5 juga sering diberikan oleh pengguna.
- Less Rating: jumlah rating paling sedikit yang diberikan oleh pengguna berada pada rating 0.5, 1.0, dan 1.5.
 
Dari hasil tersebut, dapat di simpulkan bahwa pengguna merasa puasa terhadap film yang mereka tonton.

### 2. Analisis Disribusi Genres

Tahapan ini dilakukan untuk mendaptkan informasi terkait distribus pada fitur genres. Pada tahapan ini, tidak menerapkan visualisasi dengan menggunakan `sns.countplot()` dikarenakan terlalu banyak jenis genre yang ada pada dataset yang digunakan. berikut adalah hasil dari implementasi kode `movies.genres.value_counts()` yang digunakan.

| Genre                                              | count |
|----------------------------------------------------|--------|
| Drama                                              | 9,056  |
| Comedy                                             | 5,674  |
| (no genres listed)                                 | 5,062  |
| Documentary                                        | 4,731  |
| Comedy\|Drama                                      | 2,386  |
| ...                                                | ...    |
| Action\|Fantasy\|Thriller\|IMAX                    | 1      |
| Action\|Adventure\|Animation\|Children\|Comedy\|... | 1      |
| Action\|Film-Noir\|Thriller                        | 1      |
| Action\|Adventure\|Crime\|Drama\|Sci-Fi            | 1      |
| Mystery\|Sci-Fi\|Thriller\|IMAX                    | 1      |

Dari hasil tersebut, dapat dilihat bahwa pengguna lebih sering menonton film bergenre pure Drama, dan pure Comedy. Hal itu dapat dilihat dari jumlah nilai yang ada pada dataset tersebut, dimana genre pure Drama memeiliki jumlah tontonan sebanyak 9056 kali, dan genre pure comedy memiliki tontonan sebanyak 5674 kali. Dari hasil tersebut juga terdapat genre (no genres listed) yang mengindikasin bahwa tidak ada info spesifik mengenai genre tersebut. genre dengan jenis tersebut akan peneliti hapus pada tahapan data preparation agar tidak mengganggu pada tahap pemodelan.


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

Selanjutnya, tahapan ini dilakukan untuk menggabungkan kedua variabel menjadi 1 dataframe. Hal ini dilakukan agar kedua informasi pada variabel tersebut dapat terintegrasi dengan baik guna mendukung pemodelan yang lebih akurat. berikut adalah implementasi kodenya

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
