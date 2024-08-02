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

### Model Development dengan Content Based Filtering
#### TF-IDF Vectorizer
TF-IDF adalah metode umum yang digunakan dalam sistem pengambilan informasi dan ekstraksi dokumen yang relevan dengan permintaan tertentu. Dalam pendekatan ini, terdapat dua komponen utama, yaitu TF dan IDF. TF (Term Frequency) mengukur seberapa sering sebuah kata atau istilah muncul dalam teks tertentu. Karena panjang dokumen dapat bervariasi, kami melakukan normalisasi dengan membagi frekuensi kemunculan kata dengan panjang dokumen untuk mengakomodasi perbedaan tersebut

Berikut rumus TF:

![tf](https://github.com/user-attachments/assets/4ffd81e6-d67f-4d4e-b239-12c100bc3ffc)

IDF (Inverse Document Frequency) mengukur sejauh mana pentingnya sebuah istilah dalam keseluruhan kumpulan dokumen. Sementara TF memberikan bobot yang sama untuk semua istilah, IDF mengatasi masalah seperti kata-kata umum yang tidak relevan, seperti "is," "are," "am," dan sebagainya. IDF mengurangi bobot istilah yang sering muncul di banyak dokumen dan memberi bobot lebih pada istilah yang jarang ditemukan, sehingga membantu menyoroti istilah yang lebih signifikan.

Rumus IDF:

![idf](https://github.com/user-attachments/assets/8eae16b8-78a0-4e23-9df5-72940d61b6a5)

Rumus perhitungan bobot tf-idf:

![weight](https://github.com/user-attachments/assets/1de3bfcc-4fdd-427c-b670-3b829472e9e4)

Skor TF-IDF digunakan untuk mengidentifikasi istilah-istilah yang menyimpan informasi penting dalam dokumen tertentu. Untuk menerapkan TF-IDF dalam kode, Anda dapat menggunakan fungsi TfidfVectorizer() dari pustaka scikit-learn. Fungsi TfidfVectorizer() akan menangani tokenisasi teks, membangun kosa kata, menghitung bobot frekuensi dokumen secara terbalik, dan memungkinkan Anda untuk melakukan encoding pada teks baru.

Implementasinya adalah sebagai berikut.

Kode Program

```
from sklearn.feature_extraction.text import TfidfVectorizer

# Inisialisasi TfidfVectorizer
tf = TfidfVectorizer()

# Melakukan perhitungan idf pada data categories
tf.fit(data['categories'])

# Mapping array dari fitur index integer ke fitur nama
tf.get_feature_names_out()
```

Output:
```
array(['1939', '1945', 'ability', 'abnormalities', 'abolitionists',
        ...
       'world', 'writing', 'yoga', 'young', 'your'], dtype=object)
```

Kode Program:
```
# Melakukan fit lalu ditransformasikan ke bentuk matrix
tfidf_matrix = tf.fit_transform(data['categories'])

# Melihat ukuran matrix tfidf
tfidf_matrix.shape
```
Output:
`(4086, 306)`

Kode program:
```
# Mengubah vektor tf-idf dalam bentuk matriks dengan fungsi todense()
tfidf_matrix.todense()
```
Output:
```
matrix([[0., 0., 0., ..., 0., 0., 0.],
        [0., 0., 0., ..., 0., 0., 0.],
        [0., 0., 0., ..., 0., 0., 0.],
        ...,
        [0., 0., 0., ..., 0., 0., 0.],
        [0., 0., 0., ..., 0., 0., 0.],
        [0., 0., 0., ..., 0., 0., 0.]])
```
Matriks tf-idf untuk beberapa judul buku dan kategori

![matriks](https://github.com/user-attachments/assets/5a50b367-5b35-449d-af66-161144c461ce)


#### Cosine Similarity

Cosine similarity mengukur tingkat kesamaan antara dua vektor dengan menentukan sejauh mana kedua vektor tersebut mengarah ke arah yang sama. Ia menghitung sudut kosinus antara kedua vektor, di mana semakin kecil sudut kosinus, semakin tinggi nilai cosine similarity.

![sudut](https://github.com/user-attachments/assets/142a355b-b53f-47ab-915c-4793e6e1819a)

Di Python, cosine similarity menghitung tingkat kesamaan dengan menggunakan dot product yang dinormalisasi antara dua vektor masukan, X dan Y. Metrik ini sering dipakai untuk mengukur kesamaan dokumen dalam analisis teks. Misalnya, dalam studi kasus ini, cosine similarity digunakan untuk menilai kesamaan antara judul buku dan kategorinya.

Rumusnya sebagai berikut.

![rumus cos](https://github.com/user-attachments/assets/1d6ccef6-8198-4cdb-91e5-0f73b3566e2b)

Implementasinya adalah sebagai berikut.

Kode program
```
from sklearn.metrics.pairwise import cosine_similarity

# Menghitung cosine similarity pada matrix tf-idf
cosine_sim = cosine_similarity(tfidf_matrix)
cosine_sim
```
Output:
```
array([[1., 0., 0., ..., 0., 0., 0.],
       [0., 1., 1., ..., 1., 0., 1.],
       [0., 1., 1., ..., 1., 0., 1.],
       ...,
       [0., 1., 1., ..., 1., 0., 1.],
       [0., 0., 0., ..., 0., 1., 0.],
       [0., 1., 1., ..., 1., 0., 1.]])
```

Kode program:
```
# Membuat dataframe dari variabel cosine_sim dengan baris dan kolom berupa nama resto
cosine_sim_df = pd.DataFrame(cosine_sim, index=data['Title'], columns=data['Title'])
print('Shape:', cosine_sim_df.shape)

# Melihat similarity matrix pada setiap resto
cosine_sim_df.sample(5, axis=1).sample(10, axis=0)
```

Output:

![output cosine](https://github.com/user-attachments/assets/05ce6e29-9988-4d2e-b250-7c73212b40b8)




### Mendapatkan Rekomendasi
Berikut implementasi kode penggunaan content based filtering serta outputnya:
Kode program:
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
Output:

![implementasi content based](https://github.com/user-attachments/assets/d207ecbd-65dd-4db5-b107-0d446de8eaea)


### Model Development dengan Collaborative Filtering

#### Encoding
Pada bagian ini, akan dilakukan penyandian (encode) fitur `User_id` dan `Title` ke dalam teks integer. 
Berikut tahapan proses encoding yang dilakukan.

Kode program:
```
# Mengubah User_id menjadi list tanpa nilai yang sama
user_ids = df['User_id'].unique().tolist()
print('list User_id: ', user_ids)

# Melakukan encoding User_id
user_to_user_encoded = {x: i for i, x in enumerate(user_ids)}
print('encoded User_id : ', user_to_user_encoded)

# Melakukan proses encoding angka ke ke User_id
user_encoded_to_user = {i: x for i, x in enumerate(user_ids)}
print('encoded angka ke User_id: ', user_encoded_to_user)

# Mengubah Book menjadi list tanpa nilai yang sama
book_ids = df['Title'].unique().tolist()

# Melakukan proses encoding Book
book_to_book_encoded = {x: i for i, x in enumerate(book_ids)}

# Melakukan proses encoding angka ke Title
book_encoded_to_book = {i: x for i, x in enumerate(book_ids)}
```

Output:

![encode user](https://github.com/user-attachments/assets/737f718d-c6cd-41fd-a143-163736e39fde)

Kemudian akan dilakukan pemetaan `User_id` dan `Title` kedalam dataframe untuk dikelola.
```
# Mapping userID ke dataframe user
df['user'] = df['User_id'].map(user_to_user_encoded)

# Mapping Book ke dataframe resto
df['book'] = df['Title'].map(book_to_book_encoded)
```

Terakhir dalam tahapan encode, melakukan pengecekan jumlah data yang dimiliki, seperti berikut.
Kode program:
```
# Mendapatkan jumlah user
num_users = len(user_to_user_encoded)
print(num_users)

# Mendapatkan jumlah judul
num_books = len(book_to_book_encoded)
print(num_books)

# Nilai minimum rating
min_rating = min(df['review/score'])

# Nilai maksimal rating
max_rating = max(df['review/score'])

print('Number of User: {}, Number of Book: {}, Min Rating: {}, Max Rating: {}'.format(
    num_users, num_books, min_rating, max_rating
))
```

Output:
```
37559
17165
Number of User: 37559, Number of Book: 17165, Min Rating: 1.0, Max Rating: 5.0
```

#### Split Data
Kode program:
```
# Membuat variabel x untuk mencocokkan data user dan resto menjadi satu value
x = df[['user', 'book']].values

# Membuat variabel y untuk membuat rating dari hasil
y = df['review/score'].apply(lambda x: (x - min_rating) / (max_rating - min_rating)).values

# Membagi menjadi 80% data train dan 20% data validasi
train_indices = int(0.8 * df.shape[0])
x_train, x_val, y_train, y_val = (
    x[:train_indices],
    x[train_indices:],
    y[:train_indices],
    y[train_indices:]
)

print(x, y)
```

Output:
```
[[    0     0]
 [    1     1]
 [    2     2]
 ...
 [37558   136]
 [25846  4549]
 [31607   406]] [1.   0.   1.   ... 1.   0.75 1.  ]
```

#### Build Model with RecommenderNet

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



