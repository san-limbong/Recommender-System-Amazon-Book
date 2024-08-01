# Laporan Proyek Machine Learning - San Antonio Limbong
## Domain Proyek
Project Domain (Tags) : **Recommender System** 

Title : Recommender System - Amazon Book

### Latar Belakang

![latar](https://github.com/user-attachments/assets/372ea83e-d56d-4dd3-bc91-694b2dd13682)



## Business Understanding
### Problem Statements
Berdasarkan latar belakang di atas, berikut ini merupakan rincian masalah yang dapat diselesaikan pada proyek ini:


### Goals
Tujuan dari proyek ini adalah:


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

| A_id | Fixed Acidity | Volatile Acidity | Citric Acid | Residual Sugar | Chlorides | Total Sulfur Dioxide | Density | pH | Sulphates | Alcohol | Quality |
|------|---------------|------------------|-------------|----------------|-----------|----------------------|---------|----|-----------|---------|---------|
| 0.0  | 7.4           | 0.70             | 0.00        | 1.9            | 0.076     | 34.0                 | 0.9978  | 3.51 | 0.56      | 9.4     | 5       |
| 1.0  | 7.8           | 0.88             | 0.00        | 2.6            | 0.098     | 67.0                 | 0.9968  | 3.20 | 0.68      | 9.8     | 5       |
| 2.0  | 7.8           | 0.76             | 0.04        | 2.3            | 0.092     | 54.0                 | 0.9970  | 3.26 | 0.65      | 9.8     | 5       |
| 3.0  | 11.2          | 0.28             | 0.56        | 1.9            | 0.075     | 60.0                 | 0.9980  | 3.16 | 0.58      | 9.8     | 6       |


Tabel 1. EDA Deskripsi Variabel

Dilihat dari _Tabel 1. EDA Deskripsi Variabel_ dataset ini telah di *bersihkan* dan *normalisasi* terlebih dahulu oleh pembuat, sehingga mudah digunakan dan ramah bagi pemula. 
- Dataset berupa CSV (Comma-Seperated Values).
- Dataset memiliki 1599 sample dengan 12 fitur.
- Dataset memiliki 11 fitur bertipe float64 dan 1 fitur bertipe int.
- Terdapat 240 duplikat dalam dataset.

### Variable - variable pada dataset

### EDA - Univariate Analysis

### EDA - Multivariate Analysis


## Data Preparation

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

![rmse](https://github.com/user-attachments/assets/a515e9f3-b63d-40ec-89f0-11ca8bf7f280)

## Deployment
[link](https://sistemrekomendasibuku.streamlit.app/)

**Content Based Preview**

![contentbased-1](https://github.com/user-attachments/assets/78871d12-f16d-4602-9836-a9effe71ad3a)

![contentbased-2](https://github.com/user-attachments/assets/e89acb42-c08d-42d1-9f44-ed18d8c48d28)

**Collaborative Filtering Preview**

![collaborative-1](https://github.com/user-attachments/assets/1fab9d76-c199-42db-91e1-015e769debd9)

![collaborative-2](https://github.com/user-attachments/assets/abee646b-5af8-42f3-8879-0c5f6dc888e9)

