# Capstone_Project_3

___

# Business Problem Understanding
## 1. Background
Perumahan merupakan kebutuhan pokok semua manusia, semua orang di dunia ingin mempunyai rumah yang nyaman untuk ditinggali. Pertumbuhan penduduk yang semakin meningkat membuat permintaan untuk perumahan semakin meningkat pula. Seperti halnya di salah satu negara bagian di Amerika Serikat, California. Banyaknya penduduk di sini membuka kesempatan yang besar bagi para developer perumahan untuk menyediakan rumah yang dapat menghasilkan keuntungan untuk mereka, tetapi para developer tentunya tidak ingin membuat suatu rumah dengan harga dan value yang kurang tepat yang dapat menyebabkan kurang maksimalnya profit. Banyak faktor yang dapat menentukan harga rumah yang cocok untuk dijual oleh developer, seperti lokasi, detail, dan fitur-fitur yang terdapat pada rumah tersebut. Oleh karena itu, jika ingin menjadi developer perumahan tentu harus tau berapa harga yang dapat ditawarkan dengan fitur-fitur yang ada di rumah tersebut dan dimana lokasi rumah tersebut berada.

## 2. Problem Statement
Problem terbesar bagi developer perumahan adalah menentukan harga yang cocok untuk suatu rumah agar rumah tersebut dapat dijual dengan profit yang maksimal. Perumahan yang sudah ada serta persaingan dengan developer lain membuat developer perumahan harus dapat membuat suatu rumah dengan spesifikasi serta lokasi yang tepat dan menjualnya dengan harga yang tepat untuk dapat bersaing.

## 3. Goals
Berdasarkan permasalah tersebut, developer perlu memiliki 'tool' yang dapat memprediksi dan membantu mereka dalam menentukan harga jual suatu rumah yang tepat. Adanya perbedaan pada berbagai fitur yang terdapat pada suatu rumah, seperti jumlah kamar, jumlah kamar tidur, dan lokasi dapat menambah keakuratan prediksi harga jual, yang mana dapat mendatangkan profit yang maksimal bagi developer dan harga yang sesuai untuk pembeli.

## 4. Analytic Approach
Melihat problem yang ada, kita akan membangun **model machine learning** yang akan menjadi alat untuk memprediksi harga jual rumah, yang mana akan berguna untuk developer dalam menentukan lokasi serta harga rumah di suatu kawasan tertentu.

## 5. Modelling
Menggunakan model **Supervised Machine Learning (Regression)**, antara lain: Linear Regression, KNN, Decision Tree, Random Forest, XGBoost.

## 6. Evaluation Metric
Evaluasi metrik yang akan digunakan adalah RMSE, MAE, dan MAPE, di mana RMSE adalah nilai rataan akar kuadrat dari error, MAE adalah rataan nilai absolut dari error, sedangkan MAPE adalah rataan persentase error yang dihasilkan oleh model regresi. Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi harga jual sesuai dengan limitasi fitur yang digunakan. 

___

# Data Understanding

## 1. Column Description
Berikut Penjelasan kolom pada dataset.

| No | Nama Kolom | Deskripsi & Penjelasan Kolom |
| -- | -- | -- |
| 1 | longitude | Ukuran seberapa jauh barat sebuah rumah; nilai yang lebih besar lebih jauh ke barat |
| 2 | latitude | Ukuran seberapa jauh utara sebuah rumah; nilai yang lebih besar lebih jauh ke utara |
| 3 | housingMedianAge | Usia rata-rata sebuah rumah dalam satu blok; angka yang lebih rendah adalah bangunan yang lebih baru |
| 4 | totalRooms | Jumlah total ruangan dalam satu blok |
| 5 | totalBedrooms | Jumlah total kamar tidur dalam satu blok |
| 6 | population | Jumlah total orang yang tinggal dalam satu blok |
| 7 | households | Jumlah total rumah tangga (Jumlah kepala dalam satu [Kartu Keluarga], sekelompok orang yang tinggal di dalam satu unit rumah, untuk satu blok |
| 8 | medianIncome | Median pendapatan untuk rumah tangga dalam satu blok rumah (diukur dalam puluhan ribu Dolar AS)| |
| 9 | medianHouseValue | Median harga rumah rata-rata untuk rumah tangga dalam satu blok (diukur dalam Dolar AS) |
| 10 | oceanProximity | Jarak rumah ke pesisir pantai atau laut |

## 2. EDA
Dilakukan pada kolom numerikal & kategorikal.

___

# Conclusion & Recommendation

## 1. Conclusion
- Metrik evaluasi yang digunakan pada model adalah nilai RMSE, MAE & MAPE.
- Diantara 5 model regresi, Random Forest merupakan algoritma pemodelan yang paling baik dalam memprediksi nilai median rumah di California dari dataset.
- Berdasarkan pemodelan yang sudah dilakukan, fitur `median_income` dan `ocean_proximity` menjadi fitur yang paling berpengaruh terhadap `median_house_value`.
- Jika ditinjau dari nilai MAPE yang dihasilkan oleh model setelah dilakukan hyperparameter tuning, yaitu sebesar ~25%

## 2. Recommendation
Ada beberapa rekomendasi yang dapat dilakukan untuk mengembangkan model agar lebih baik lagi, seperti :

- Melihat kembali data predict, data mana saja yang memiliki nilai error yang tinggi, lalu membandingkan feature-feature mana saja yang menyebabkan model menghasilkan error tersebut dan aspek apa yang menyebabkan model menghasilkan error yang tinggi, sehingga kita dapat melakukan training ulang dengan penerapan feature engineering lainnya.

- Jika memungkinkan, penambahan fitur yang lebih korelatif dengan target ('median_house_value'), seperti luas tanah & bangunan atau jarak perumahan dengan pusat kota. Selain itu, dataset ini dibuat pada tahun 1990, pembaruan data terkini untuk California Housing Prices dapat mengimprovisasi kapasitas prediksi model ini.

- Menambahkan data atau mengimprovisasi data dapat membuat model menjadi lebih baik.
