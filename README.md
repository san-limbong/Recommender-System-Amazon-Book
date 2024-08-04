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
   Collaborative Filtering adalah pendekatan yang umum digunakan dalam membuat sistem rekomendasi, yang bekerja memberikan rekomendasi untuk pengguna atau pembaca dengan membandingkan preferensi pengguna lain yang telah menilai produk dengan cara yang sama dengannya.

Berlandaskan hal tersebut, akan dilakukan pengembangan sistem rekomendasi sebagai bahan eksperimen yang berperan untuk meningkatkan kepuasan pembaca, meningkatkan penjualan, dan menumbuhkan budaya membaca Sehingga dapat meningkatkan pengalaman pengguna dengan memudahkan mereka menemukan buku-buku baru dan menarik, ataupun untuk kepentingan penyedia buku tersebut.


## Business Understanding
### Problem Statements
Berdasarkan latar belakang di atas, berikut akan dijabarkan pokok permasalahan yang dibahas dalam proyek sebagai berikut.
- Bagaimana membuat sistem yang dapat memberi rekomendasi buku berdasarkan kesamaan konten atau deskripsi item yang pernah dibaca oleh pengguna sebelumnya?
- Bagaimana membuat sistem yang dapat memberi rekomendasi buku berdasarkan persamaan preferensi pengguna lainnya _(review/score atau rating)_?

### Goals
Tujuan dari proyek ini adalah:
- membuat sistem yang dapat memberi rekomendasi buku berdasarkan kesamaan konten atau deskripsi item yang pernah dibaca oleh pengguna sebelumnya.
- membuat sistem yang dapat memberi rekomendasi buku berdasarkan persamaan preferensi pengguna lainnya _(review/score atau rating)_

### Solution Statements
Berikut adalah beberapa pendekatan yang bisa digunakan untuk membangun sistem rekomendasi buku:

1. Content-Based Filtering (CBF): Pendekatan ini memanfaatkan informasi tentang buku, seperti kategori dan deskripsi isi, untuk memahami preferensi pengguna. Algoritma ini mencocokkan preferensi pengguna dengan atribut-atribut buku dan memberikan rekomendasi buku yang memiliki atribut sesuai dengan preferensi pengguna dalam konteks case ini adalah kategori _(categories)_.

2. Collaborative Filtering (CF). CF dapat diimplementasikan dengan dua varian, yaitu User-Based CF dan Item-Based CF. User-Based CF mencari pengguna serupa dan merekomendasikan buku yang disukai oleh pengguna serupa. Item-Based CF mencari buku serupa dan merekomendasikan buku yang mirip dengan yang sudah disukai oleh pengguna. Pada konteks perancangan diharapkan dapat memprediksi rating atau preferensi pengguna terhadap buku berdasarkan embedding (representasi numerik) dari pengguna dan buku.

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
| Its Only Art If Its Well Hung!                | NaN                                                       | ['Julie Strain']    | ![Image](http://books.google.com/books/content?id=DykPAAAACAAJ&printsec=frontcover&img=1&zoom=1&source=gbs_api)       | [PreviewLink](http://books.google.nl/books?id=DykPAAAACAAJ&dq=...) | NaN         | 1996          | [InfoLink](http://books.google.nl/books?id=DykPAAAACAAJ&dq=...) | ['Comics & Graphic Novels'] | NaN          |
| Dr. Seuss: American Icon                      | Philip Nel takes a fascinating look into the key events... | ['Philip Nel']      | ![Image](http://books.google.com/books/content?id=IjvHQsCn_pgC&printsec=frontcover&img=1&zoom=1&edge=curl&source=gbs_api)       | [PreviewLink](http://books.google.nl/books?id=IjvHQsCn_pgC&pg=...) | A&C Black   | 2005-01-01    | [InfoLink](http://books.google.nl/books?id=IjvHQsCn_pgC&dq=...) | ['Biography & Autobiography'] | NaN          |
| Wonderful Worship in Smaller Churches         | This resource includes twelve principles in unique wors... | ['David R. Ray']    | ![Image](http://books.google.com/books/content?id=2tsDAAAACAAJ&printsec=frontcover&img=1&zoom=1&source=gbs_api)       | [PreviewLink](http://books.google.nl/books?id=2tsDAAAACAAJ&dq=...) | NaN         | 2000          | [InfoLink](http://books.google.nl/books?id=2tsDAAAACAAJ&dq=...) | ['Religion']                 | NaN          |
| Whispers of the Wicked Saints                 | Julia Thomas finds her life spinning out of control whi... | ['Veronica Haddon'] | ![Image](http://books.google.com/books/content?id=aRSIgJlq6JwC&printsec=frontcover&img=1&zoom=1&source=gbs_api)       | [PreviewLink](http://books.google.nl/books?id=aRSIgJlq6JwC&dq=...) | iUniverse   | 2005-02       | [InfoLink](http://books.google.nl/books?id=aRSIgJlq6JwC&dq=...) | ['Fiction']                  | NaN          |
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
1. Melakukan cleaning data meliputi, _missing value_ dan _duplicate_
2. Membentuk ulang kolom pada dataframe, meliputi pemilihan atribut yang dianggap relevan untuk perancangan proyek.
Seperti 'Id', 'Title', 'User_id', 'review/score' untuk dataframe rating, dan
'Title', 'categories' untuk dafaframe details
3. Memilih data yang digunakan dengan jumlah sebesar 0,1 dari dari dataset asli dikarenakan jumlah record dataset asli yang terlalu besar sehingga hal ini diperlukan untuk meningkatkan aksebilitas saat perancangan model.
4. Membersihkan data pada kolom kategori di dataframe details dari tanda kurung siku dan petik.
5. Mengimplementasikan TF-IDF.
   
TF-IDF adalah metode umum yang digunakan dalam sistem pengambilan informasi dan ekstraksi dokumen yang relevan dengan permintaan tertentu. Dalam pendekatan ini, terdapat dua komponen utama, yaitu TF dan IDF. TF (Term Frequency) mengukur seberapa sering sebuah kata atau istilah muncul dalam teks tertentu. Karena panjang dokumen dapat bervariasi, kami melakukan normalisasi dengan membagi frekuensi kemunculan kata dengan panjang dokumen untuk mengakomodasi perbedaan tersebut

Berikut rumus TF:

![tf](https://github.com/user-attachments/assets/4ffd81e6-d67f-4d4e-b239-12c100bc3ffc)

IDF (Inverse Document Frequency) mengukur sejauh mana pentingnya sebuah istilah dalam keseluruhan kumpulan dokumen. Sementara TF memberikan bobot yang sama untuk semua istilah, IDF mengatasi masalah seperti kata-kata umum yang tidak relevan, seperti "is," "are," "am," dan sebagainya. IDF mengurangi bobot istilah yang sering muncul di banyak dokumen dan memberi bobot lebih pada istilah yang jarang ditemukan, sehingga membantu menyoroti istilah yang lebih signifikan.

Rumus IDF:

![idf](https://github.com/user-attachments/assets/8eae16b8-78a0-4e23-9df5-72940d61b6a5)

Rumus perhitungan bobot tf-idf:

![weight](https://github.com/user-attachments/assets/1de3bfcc-4fdd-427c-b670-3b829472e9e4)

Skor TF-IDF digunakan untuk mengidentifikasi istilah-istilah yang menyimpan informasi penting dalam dokumen tertentu. Untuk menerapkan TF-IDF dalam kode, Anda dapat menggunakan fungsi TfidfVectorizer() dari pustaka scikit-learn. Fungsi TfidfVectorizer() akan menangani tokenisasi teks, membangun kosa kata, menghitung bobot frekuensi dokumen secara terbalik, dan memungkinkan Anda untuk melakukan encoding pada teks baru.

Berikut matriks tf-idf untuk beberapa judul buku dan kategori

![matriks](https://github.com/user-attachments/assets/5a50b367-5b35-449d-af66-161144c461ce)


6. Melakukan Encoding
Pada bagian ini, akan dilakukan penyandian (encode) fitur User_id dan Title ke dalam teks integer. 
![encode user](https://github.com/user-attachments/assets/d6d8d857-2b2a-46fc-9569-1daa9558b5fe)

7. Split Data.

Pada pengembangan model menggunakan RecommenderNet, data train dan validasi dibagi dengan komposisi 80:20. Dengan catatan melakukan pemetaan (mapping) data user dan book menjadi satu value terlebih dahulu. Kemudian, membuat rating dalam skala 0 sampai 1 agar mudah dalam melakukan proses training. 


## Modelling

### Content Based Filtering

Pemodelan untuk Content Based Filtering kita menggunakan fungsi cosine_similarity.
Cosine similarity mengukur tingkat kesamaan antara dua vektor dengan menentukan sejauh mana kedua vektor tersebut mengarah ke arah yang sama. Ia menghitung sudut kosinus antara kedua vektor, di mana semakin kecil sudut kosinus, semakin tinggi nilai cosine similarity.

![sudut](https://github.com/user-attachments/assets/142a355b-b53f-47ab-915c-4793e6e1819a)

Di Python, cosine similarity menghitung tingkat kesamaan dengan menggunakan dot product yang dinormalisasi antara dua vektor masukan, X dan Y. Metrik ini sering dipakai untuk mengukur kesamaan dokumen dalam analisis teks. Misalnya, dalam studi kasus ini, cosine similarity digunakan untuk menilai kesamaan antara judul buku dan kategorinya.

Rumusnya sebagai berikut.

![rumus cos](https://github.com/user-attachments/assets/1d6ccef6-8198-4cdb-91e5-0f73b3566e2b)

Berikut hasil penerapannya.

![output cosine](https://github.com/user-attachments/assets/05ce6e29-9988-4d2e-b250-7c73212b40b8)

Setelah memiliki data similarity antar buku (Title), kemudian kita akan memberikan sejumlah rekomendasi terhadap pengguna dengan menggunakan fungsi yakni sebagai berikut.

```
def book_recommendations(nama_buku, similarity_data=cosine_sim_df, items=data[['Title', 'categories']], k=5):
    # Mengambil data dengan menggunakan argpartition untuk melakukan partisi secara tidak langsung sepanjang sumbu yang diberikan
    # Dataframe diubah menjadi numpy
    # Range(start, stop, step)
    index = similarity_data.loc[:,nama_buku].to_numpy().argpartition(
        range(-1, -k, -1))

    # Mengambil data dengan similarity terbesar dari index yang ada
    closest = similarity_data.columns[index[-1:-(k+2):-1]]

    # Drop nama_buku agar nama resto yang dicari tidak muncul dalam daftar rekomendasi
    closest = closest.drop(nama_buku, errors='ignore')

    return pd.DataFrame(closest).merge(items).head(k)
```

Keterangan:
```
    nama_buku : Nama buku (index kemiripan dataframe).
    Similarity_data : Dataframe mengenai similarity yang telah kita definisikan sebelumnya.
    Items : Nama dan fitur yang digunakan untuk mendefinisikan kemiripan, dalam hal ini adalah ‘Title’ dan ‘categories’.
    k : Banyak rekomendasi yang ingin diberikan, dalam hal ini adalah 5.
```

Berikut hasil **mendapatkan top-N recommendation** pada Content Based Filtering atau rekomendasi buku berdasarkan kesamaan konten atau deskripsi item yang pernah dibaca oleh pengguna sebelumnya

![implementasi content based](https://github.com/user-attachments/assets/d7b9cffb-b6a6-44a7-84a3-5f2e1a8cc13f)


### Collaborative Filtering
Pada bagian pembangunan model dengan menggunakan metode Collaborative filtering, digunakan RecommenderNet.
RecommenderNet adalah implementasi dari model pembelajaran mesin yang menggunakan embedding untuk menangkap preferensi pengguna dan fitur item, serta produk titik untuk menghasilkan skor rekomendasi. Model ini sering digunakan dalam sistem rekomendasi untuk meningkatkan pengalaman pengguna dengan menyediakan rekomendasi yang dipersonalisasi.

```
class RecommenderNet(tf.keras.Model):

  # Insialisasi fungsi
  def __init__(self, num_users, num_books, embedding_size, **kwargs):
    super(RecommenderNet, self).__init__(**kwargs)
    self.num_users = num_users
    self.num_books = num_books
    self.embedding_size = embedding_size
    self.user_embedding = layers.Embedding( # layer embedding user
        num_users,
        embedding_size,
        embeddings_initializer = 'he_normal',
        embeddings_regularizer = keras.regularizers.l2(1e-6)
    )
    self.user_bias = layers.Embedding(num_users, 1) # layer embedding user bias
    self.books_embedding = layers.Embedding( # layer embeddings books
        num_books,
        embedding_size,
        embeddings_initializer = 'he_normal',
        embeddings_regularizer = keras.regularizers.l2(1e-6)
    )
    self.books_bias = layers.Embedding(num_books, 1) # layer embedding books bias

  def call(self, inputs):
    user_vector = self.user_embedding(inputs[:,0]) # memanggil layer embedding 1
    user_bias = self.user_bias(inputs[:, 0]) # memanggil layer embedding 2
    books_vector = self.books_embedding(inputs[:, 1]) # memanggil layer embedding 3
    books_bias = self.books_bias(inputs[:, 1]) # memanggil layer embedding 4

    dot_user_books = tf.tensordot(user_vector, books_vector, 2)

    x = dot_user_books + user_bias + books_bias

    return tf.nn.sigmoid(x) # activation sigmoid
```

Komponen-komponen RecommenderNet:

  1. User Embedding:
      self.user_embedding adalah lapisan embedding untuk pengguna. Lapisan ini mengubah ID pengguna menjadi vektor embedding dengan ukuran tertentu (embedding_size). Vektor ini merepresentasikan fitur-fitur pengguna dalam ruang berdimensi lebih rendah.

  2. User Bias:
      self.user_bias adalah lapisan embedding untuk bias pengguna. Bias ini adalah nilai skalar yang terkait dengan setiap pengguna untuk menangkap preferensi umum mereka.

  3. Books Embedding:
      self.books_embedding adalah lapisan embedding untuk buku. Lapisan ini mengubah ID buku menjadi vektor embedding dengan ukuran tertentu (embedding_size). Vektor ini merepresentasikan fitur-fitur buku dalam ruang berdimensi lebih rendah.

  4. Books Bias:
      self.books_bias adalah lapisan embedding untuk bias buku. Bias ini adalah nilai skalar yang terkait dengan setiap buku untuk menangkap popularitas umum mereka.

Fungsi call:

  - Fungsi call adalah fungsi yang dipanggil saat model melakukan forward pass. Fungsi ini menerima input berupa pasangan ID pengguna dan ID buku, lalu menghasilkan prediksi rating.
  - Langkah-langkah dalam call:
      1. Mengambil vektor embedding pengguna berdasarkan ID pengguna (inputs[:, 0]).
      2. Mengambil bias pengguna berdasarkan ID pengguna.
      3. Mengambil vektor embedding buku berdasarkan ID buku (inputs[:, 1]).
      4. Mengambil bias buku berdasarkan ID buku.
      5. Melakukan dot product antara vektor embedding pengguna dan vektor embedding buku untuk mendapatkan interaksi pengguna-buku.
      6. Menambahkan bias pengguna dan bias buku ke hasil dot product.
      7. Menggunakan fungsi aktivasi sigmoid untuk menghasilkan prediksi rating akhir.

Berikut hasil **mendapatkan top-N recommendation** pada Collaborative Filtering atau rekomendasi buku berdasarkan persamaan preferensi pengguna lainnya (review/score atau rating).

![1](https://github.com/user-attachments/assets/ef1db814-c803-4a02-878e-c064b1b87c25)


## Evaluasi
Metrik yang akan kita gunakan pada prediksi ini adalah RMSE atau Root Mean Squared Error. Root Mean Square Error (RMSE) adalah salah satu metrik evaluasi yang sering digunakan dalam pemodelan statistik dan machine learning, Fungsi dari RMSE adalah untuk mengukur seberapa baik suatu model memetakan nilai prediksi ke nilai sebenarnya dengan menghitung akar kuadrat dari rata-rata dari kuadrat kesalahan. RMSE dihitung dengan mengambil akar kuadrat dari rata-rata dari kuadrat selisih antara setiap prediksi individu dan nilai sebenarnya.

![rmse](https://github.com/user-attachments/assets/f0653cde-4aa5-43e9-a51b-e2aba9d58709)

Keterangan:
```
    n adalah jumlah total observasi atau sampel.
    yi adalah nilai aktual atau nilai sebenarnya dari observasi ke-i.
    Ŷi adalah nilai prediksi model untuk observasi ke-i.
```

Berikut hasil evaluasi rmse pada proyek ini.

![rmse](https://github.com/user-attachments/assets/670b8319-1161-43fa-a7f9-f1d6350559f2)

1. Berdasarkan data tersebut, masih terdapat kekurangan dalam bentuk error rate yang cenderung kurang baik, dan overfitting. Hal ini disebabkan keterbatasan sumber daya atau _environtment_ serta kurang lengkapnya kategori bawaan dari dataset yang disediakan. 

2. Berdasarkan hasil keseluruhan diatas, kita telah membuat sistem yang dapat memberi rekomendasi buku berdasarkan kesamaan konten atau deskripsi item yang pernah dibaca oleh pengguna sebelumnya dengan menerapkan Content-Based Filtering (CBF).
4. Berdasarkan hasil keseluruhan diatas, kita telah juga sistem yang dapat memberi rekomendasi buku berdasarkan persamaan preferensi pengguna lainnya _(review/score atau rating)_ dengan menggunakan Collaborative Filtering (CF).


## Deployment

Cobain rekomendasi buku dengan klik [disini ](https://sistemrekomendasibuku.streamlit.app/)

**Content Based Preview**

![contentbased-1](https://github.com/user-attachments/assets/2c6117d6-b733-49c9-8d3b-45428218ba6d)

![contentbased-2](https://github.com/user-attachments/assets/a38c75ee-d191-4281-894c-47cdbb4809ca)


**Collaborative Filtering Preview**

![collaborative-1](https://github.com/user-attachments/assets/2ea1e2e7-185d-464e-9a32-0929502d9bb1)

![collaborative-2](https://github.com/user-attachments/assets/c76d3243-e73c-4cdc-995a-1df2028d2e85)

## Kesimpulan
1. Sistem rekomendasi buku sudah dapat diterima dengan mengimplementasikan Content-Based Filtering dan Collaborative Filtering, sesuai sebagaimana ketentuan perekomendasian masing - masing.
2. Sistem rekomendasi masih memiliki catatan, yakni terkait penggunaan dataset yang lebih lengkap serta pelatihan model yang sebaiknya lebih ditingkatkan guna mendapatkan hasil rekomendasi yang lebih baik lagi.
