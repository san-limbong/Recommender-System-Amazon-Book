# Laporan Proyek Machine Learning - San Antonio Limbong
## Domain Proyek
Project Domain (Tags) : **Recommender System** 

Title : Recommender System - Amazon Book

### Project Overview

![latar](https://github.com/user-attachments/assets/98979c0a-4741-49a0-83c4-469a15260b9e)

Di era digital ini, kita sering kali kewalahan dengan banjir informasi. Hal ini membuat menemukan konten yang relevan menjadi sulit, terutama dalam konteks perbukuan di mana volume buku yang tersedia sangat besar. Ada dua tipe pembaca dalam membaca buku, yakni mereka yang tahu persis apa yang mereka cari dan mereka yang mencari rekomendasi tetapi tidak memiliki ide spesifik tentang apa yang ingin mereka baca. Proyek ini bertujuan untuk memenuhi kebutuhan kedua tipe pembaca tersebut dengan mengembangkan sistem rekomendasi buku menggunakan dataset buku Amazon.

Mengapa sistem rekomendasi sangat penting?
  1. Meningkatkan Pengalaman Pembaca: Dengan menyediakan rekomendasi buku yang dipersonalisasi, sistem ini dapat membantu pemabca menemukan buku yang sesuai dengan minat mereka dengan lebih mudah. Ini sangat bermanfaat bagi pembaca buku yang tidak yakin ingin membaca apa selanjutnya.
  2. Meningkatkan Penjualan: Rekomendasi yang efektif dapat mendorong keterlibatan dan rasa penasaran yang lebih tinggi di antara pembaca, yang pada akhirnya meningkatkan penjualan. Ketika calon pelanggan atau pembaca buku disajikan dengan buku yang sesuai dengan preferensi mereka, mereka lebih mungkin untuk melakukan pembelian.
  3. Mendukung Kebiasaan Membaca: Bagi masyarakat dengan tingkat minat baca yang rendah, seperti di Indonesia di mana indeks membaca relatif rendah, sistem rekomendasi dapat mendorong lebih banyak orang untuk membaca dengan lebih sering dengan memudahkan mereka menemukan buku yang menarik. Hal ini dapat membantu meningkatkan literasi dan pengetahuan secara keseluruhan.

Berdasarkan [jurnal penelitian](https://www.academia.edu/download/59762468/10.1.1.695.642820190617-91457-z4s1rf.pdf), terdapat beberapa metode yang digunakan dalam sistem rekomendasi, diantaranya adalah Content-Based Filtering dan Collaborative Filtering. Dengan penjabaran sebagai berikut.

1. Content-Based Filtering
   Content-based filtering adalah pendekatan yang digunakan untuk memberikan rekomendasi terhadap pengguna atau pembaca dengan membandingkan history data dan menyajikan rekomendasi berdasarkan jumlah kesamaan seperti deskripsi item sebelumnya.
2. Collaborative Filtering
   Collaborative Filtering adalah pendekatan yang umum digunakan dalam merancang sistem rekomendasi, yang bekerja memberikan rekomendasi untuk pengguna atau pembaca dengan membandingkan preferensi pengguna lain yang telah menilai produk dengan cara yang sama dengannya.

Berlandaskan hal tersebut, akan dilakukan pengembangan sistem rekomendasi sebagai bahan eksperimen yang berperan untuk meningkatkan kepuasan pembaca, meningkatkan penjualan, dan menumbuhkan budaya membaca Sehingga dapat meningkatkan pengalaman pengguna dengan memudahkan mereka menemukan buku-buku baru dan menarik, ataupun untuk kepentingan penyedia buku tersebut.


## Business Understanding
### Problem Statements
Berdasarkan latar belakang di atas, berikut akan dijabarkan pokok permasalahan yang dibahas dalam proyek sebagai berikut.
- Bagaimana merancang sistem rekomendasi buku berdasarkan kesamaan konten atau deskripsi item terhadap pengguna atau pembaca (Content-Based Filtering)?
- Bagaimana merancang sistem rekomendasi buku berdasarkan kesamaan rating atau review yang diberikan pengguna lainnya terhadap pembaca (Collaborative Filtering)?

### Goals
Tujuan dari proyek ini adalah:
- Merancang sistem rekomendasi buku berdasarkan kesamaan konten atau deskripsi item terhadap pengguna atau pembaca (Content-Based Filtering).
- Merancang sistem rekomendasi buku berdasarkan kesamaan rating atau review yang diberikan pengguna lainnya terhadap pembaca (Collaborative Filtering)

### Solution Statements

## Data Understanding
### EDA - Deskripsi Variabel
**Informasi Datasets**


| Jenis | Keterangan |
| ------ | ------ |
| Title | Amazon Books Reviews |
| Source | [Kaggle](https://www.kaggle.com/datasets/mohamedbakhet/amazon-books-reviews) |
| License | [CC0: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/) |
| Visibility | Public |
| Tags | _Tabular, Text, Ratings and Rewiews, Literature, NLP, Recommender System, Alcohol_ |
| Usability | 10.00 |

Berikut informasi pada dataset: 

books_data.csv 

| Title                                         | Description                                               | Authors             | Image                                                                 | PreviewLink                                                       | Publisher   | PublishedDate | InfoLink                                                       | Categories                   | RatingsCount |
|-----------------------------------------------|-----------------------------------------------------------|---------------------|-----------------------------------------------------------------------|-------------------------------------------------------------------|-------------|---------------|---------------------------------------------------------------|------------------------------|--------------|
| Its Only Art If Its Well Hung!                | NaN                                                       | ['Julie Strain']    | ![Image](http://books.google.com/books/content?id=DykPAAAACAAJ)       | [PreviewLink](http://books.google.nl/books?id=DykPAAAACAAJ&dq=...) | NaN         | 1996          | [InfoLink](http://books.google.nl/books?id=DykPAAAACAAJ&dq=...) | ['Comics & Graphic Novels'] | NaN          |
| Dr. Seuss: American Icon                      | Philip Nel takes a fascinating look into the key events... | ['Philip Nel']      | ![Image](http://books.google.com/books/content?id=IjvHQsCn_pgC)       | [PreviewLink](http://books.google.nl/books?id=IjvHQsCn_pgC&pg=...) | A&C Black   | 2005-01-01    | [InfoLink](http://books.google.nl/books?id=IjvHQsCn_pgC&dq=...) | ['Biography & Autobiography'] | NaN          |
| Wonderful Worship in Smaller Churches         | This resource includes twelve principles in unique wors... | ['David R. Ray']    | ![Image](http://books.google.com/books/content?id=2tsDAAAACAAJ)       | [PreviewLink](http://books.google.nl/books?id=2tsDAAAACAAJ&dq=...) | NaN         | 2000          | [InfoLink](http://books.google.nl/books?id=2tsDAAAACAAJ&dq=...) | ['Religion']                 | NaN          |
| Whispers of the Wicked Saints                 | Julia Thomas finds her life spinning out of control whi... | ['Veronica Haddon'] | ![Image](http://books.google.com/books/content?id=aRSIgJlq6JwC)       | [PreviewLink](http://books.google.nl/books?id=aRSIgJlq6JwC&dq=...) | iUniverse   | 2005-02       | [InfoLink](http://books.google.nl/books?id=aRSIgJlq6JwC&dq=...) | ['Fiction']                  | NaN          |
| Nation Dance: Religion, Identity and Cultural | NaN                                                       | ['Edward Long']     | NaN                                                                   | [PreviewLink](http://books.google.nl/books?id=399SPgAACAAJ&dq=...) | NaN         | 2003-03-01    | [InfoLink](http://books.google.nl/books?id=399SPgAACAAJ&dq=...) | NaN                          | NaN          |


Books_rating.csv 

| Id         | Title                     | Price | User_id          | profileName                      | review/helpfulness | review/score | review/time | review/summary                                  | review/text                                                                                                                                                             |
|------------|---------------------------|-------|------------------|----------------------------------|--------------------|--------------|-------------|------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1882931173 | Its Only Art If Its Well Hung! | NaN   | AVCGYZL8FQQTD    | Jim of Oz "jim-of-oz"            | 7/7                | 4.0          | 940636800   | Nice collection of Julie Strain images          | This is only for Julie Strain fans. It's a collection of images of Julie Strain in various poses. Only for fans of Julie Strain.                                         |
| 0826414346 | Dr. Seuss: American Icon     | NaN   | A30TK6U7DNS82R   | Kevin Killian                     | 10/10              | 5.0          | 1095724800  | Really Enjoyed It                              | I don't care much for Dr. Seuss but after reading this book I gained a new appreciation for him. Philip Nel does an excellent job.                                       |
| 0826414346 | Dr. Seuss: American Icon     | NaN   | A3UH4UZ4RSVO82   | John Granger                      | 10/11              | 5.0          | 1078790400  | Essential for every personal and Public Library | If people become the books they read and if "the best things in life are free," then every personal and public library must have a copy of "Dr. Seuss: American Icon."  |
| 0826414346 | Dr. Seuss: American Icon     | NaN   | A2MVUWT453QH61   | Roy E. Perry "amateur philosopher" | 7/7                | 4.0          | 1090713600  | Phlip Nel gives silly Seuss a serious treatment | Theodore Seuss Geisel (1904-1991), aka "Dr. Seuss", is the subject of Philip Nel's academic study. Nel explores Seuss's life and work in depth.                           |
| 0826414346 | Dr. Seuss: American Icon     | NaN   | A22X4XUPKF66MR   | D. H. Richards "ninthwavestore"   | 3/3                | 4.0          | 1107993600  | Good academic overview                          | Philip Nel - Dr. Seuss: American Icon. This is both an enjoyable and informative academic overview of the life and work of Dr. Seuss.                                   |


Tabel. EDA Deskripsi Variabel

Dilihat dari _Tabel. EDA Deskripsi Variabel_ dataset ini telah di *bersihkan* dan *normalisasi* terlebih dahulu oleh pembuat, sehingga mudah digunakan dan ramah bagi pemula. 
- Dataset terbagi atas dua yakni books_data dan Books_rating dengan format .CSV (Comma-Seperated Values).
- Dataset books_data.csv 212404 sample dan 10 fitur sementara Books_rating.csv memiliki 3000000 sample dengan 10 fitur.
- Terdapat 0 duplikat dalam dataset books_data.csv sementara 8774 duplikat dalam dataset Books_rating.csv

### Variable - variable pada dataset

books_data.csv 

| Features        | Description                                       |
|-----------------|---------------------------------------------------|
| Title           | Book Title                                        |
| Descripe        | Description of book                               |
| Authors         | Name of book authors                              |
| Image           | URL for book cover                                |
| PreviewLink     | Link to access this book on Google Books          |
| Publisher       | Name of the publisher                             |
| PublishedDate   | The date of publish                               |
| InfoLink        | Link to get more information about the book on Google Books |
| Categories      | Genres of books                                   |
| RatingsCount    | Averaging rating for book                         |


Books_rating.csv 

| Features            | Description                                |
|---------------------|--------------------------------------------|
| id                  | The Id of Book                             |
| Title               | Book Title                                 |
| Price               | The price of Book                          |
| User_id             | Id of the user who rates the book          |
| profileName         | Name of the user who rates the book        |
| review/helpfulness  | Helpfulness rating of the review, e.g. 2/3 |
| review/score        | Rating from 0 to 5 for the book            |
| review/time         | Time of given the review                   |
| review/summary      | The summary of a text review               |
| review/text         | The full text of a review                  |



## Data Preparation
1. Membersihkan data, meliputi _missing value_ dan data duplikat.
2. Mengkontruksi data, meliputi pemilihan atribut yang dianggap relevan untuk perancangan proyek.
3. Memilih data, meliputi pemotongan dataset yang digunakan karena jumlah yang terlalu besar sehingga untuk meningkatkan aksebilitas saat perancangan model.
4. Transformasi data, meliputi menyesuaikan data dengan format yang dianggap kurang tepat dan diperbaharui untuk menunjang perancagan model.

## Modelling

## Evaluasi
Metrik yang akan kita gunakan pada prediksi ini adalah MSE atau Mean Squared Error yang menghitung jumlah selisih kuadrat rata-rata nilai sebenarnya dengan nilai prediksi. MSE didefinisikan dalam persamaan berikut.

![mse](https://github.com/user-attachments/assets/759e96bb-886c-419e-b612-b6047e5d9c61)

```
Keterangan:
N = jumlah dataset
yi = nilai sebenarnya
y_pred = nilai prediksi
```

Berikut hasil evaluasi rmse pada proyek ini.

![rmse](https://github.com/user-attachments/assets/670b8319-1161-43fa-a7f9-f1d6350559f2)

## Deployment
[link](https://sistemrekomendasibuku.streamlit.app/)

**Content Based Preview**

![contentbased-1](https://github.com/user-attachments/assets/2c6117d6-b733-49c9-8d3b-45428218ba6d)

![contentbased-2](https://github.com/user-attachments/assets/a38c75ee-d191-4281-894c-47cdbb4809ca)


**Collaborative Filtering Preview**

![collaborative-1](https://github.com/user-attachments/assets/2ea1e2e7-185d-464e-9a32-0929502d9bb1)

![collaborative-2](https://github.com/user-attachments/assets/c76d3243-e73c-4cdc-995a-1df2028d2e85)



