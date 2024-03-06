# **California Housing Price**

Sumber data California Housing Price : [here](https://www.kaggle.com/datasets/camnugent/california-housing-prices)

### **Contents**

1. Business Problem Understanding
2. Data Understanding & EDA
3. Data Preprocessing
4. Modeling
5. Kesimpulan
6. Rekomendasi

****

## **BUSINESS PROBLEM UNDERSTANDING**

### **Context**

California adalah sebuah negara bagian di Amerika Serikat bagian barat. California berbatasan dengan Oregon di utara, Nevada dan Arizona di timur, negara bagian Baja California di Meksiko ke arah selatan; dan memiliki garis pantai sepanjang Samudra Pasifik ke arah barat. Dengan jumlah penduduk lebih dari 39,2 juta jiwa[5] dalam wilayah dengan total area sekitar 163.696 mil persegi (423.970 km2), California merupakan negara bagian Amerika Serikat yang terpadat menurut kepadatan penduduk dan terbesar ketiga berdasarkan wilayah.

Perekonomian yang maju menjadikan California sebagai kota dengan market properti yang paling mahal di Amerika Serikat.

### **Problem Statement**

Berdasarkan data dari [redfin](https://www.redfin.com/state/California/housing-market), harga median sebuah rumah sekarang di California sudah mencapai 739k USD, lebih dari dua kali harga nasional (370k USD). California memiliki empat dari lima pasar perumahan termahal di AS, yaitu Silicon Valley, San Francisco, Orange County, dan San Diego. Namun, tingkat kemiskinan, jika disesuaikan dengan biaya hidup, adalah yang terburuk di negara ini. California menyumbang 12% dari dari total populasi AS, tetapi seperempatnya merupakan tunawisma.

Perusahaan properti di California menghadapi tantangan serius dalam mengantisipasi dan menyesuaikan diri dengan fluktuasi harga rumah yang terus meningkat di pasar yang sangat kompetitif. Dengan populasi yang melebihi 39 juta jiwa, California merupakan salah satu pasar properti paling mahal di Amerika Serikat, dengan harga rata-rata mencapai $739 ribu USD. Ketidakseimbangan antara penawaran perumahan yang menurun dan permintaan yang terus meningkat telah menciptakan ketidakpastian yang signifikan dalam memprediksi harga rumah yang akan mereka bangun. Perusahaan memerlukan solusi yang dapat memberikan prediksi harga yang akurat serta wawasan mendalam mengenai faktor-faktor apa saja yang memengaruhi harga rumah di berbagai daerah California. Solusi ini diharapkan akan memungkinkan perusahaan untuk membuat keputusan yang lebih tepat dan efisien dalam pengembangan properti mereka.

Selanjutnya, untuk menangani masalah ini sebuah perusahaan properti membuat plan untuk membangun perumahan baru untuk menambah *supply* di pasar. **Perusahaan ingin mendapatkan prediksi harga dari rumah yang akan dibangun sebagai pertimbangan untuk perencanaan biaya pembangunan dan perhitungan revenue yang didapat**.

### **Goal**

Berdasarkan problem tersebut, perusahaan ingin membuat `Model` yang membantu dalam perhitungan prediksi harga yang nantinya akan membantu mereka untuk mengambil keputusan. dan juga dapat memberikan wawasan terkait faktor apa saja yang dapat mempengaruhi harga rumah di setiap daerah.

### **Algoritma Pembelajaran Mesin yang akan digunakan **(mungkin cocok)** untuk memprediksi harga perumahan:**

1. **Decision Tree Regression**:Decision Tree Regression cocok untuk masalah yang melibatkan pemodelan struktur data non-linear. Hal ini memungkinkan untuk membangun model yang lebih kompleks dan menangkap hubungan non-linear antara fitur dan variabel target.

2. **Random Forest Regression** : Random forest adalah pengembangan dari pohon keputusan yang menggabungkan beberapa pohon keputusan untuk meningkatkan akurasi dan mengurangi overfitting. Ini sering digunakan untuk masalah regresi yang kompleks.

3. **Support Vector Regression (SVR)**: SVR cocok untuk tugas-tugas regresi ketika berhadapan dengan set data yang lebih kecil. SVR bekerja dengan baik di ruang dimensi tinggi dan efektif ketika jumlah fitur lebih besar daripada jumlah sampel. SVR bertujuan untuk menemukan hyperplane optimal yang memaksimalkan margin, sehingga memungkinkan generalisasi yang lebih baik untuk data yang tidak terlihat.

4. **K-Nearest Neighbors Regressor** : akan memprediksi jumlah sepeda yang akan disewa berdasarkan k tetangga terdekat dari titik yang akan diprediksi. Cocok digunakan jika pola dalam data dapat dijelaskan oleh tetangga terdekat.

5. **XGBoost Regressor dan AdaBoost Regresso**r: XGBoost dan AdaBoost adalah model ensemble yang kuat yang cocok untuk digunakan ketika ada kompleksitas yang tinggi dalam data dan kinerja tinggi dalam prediksi yang diperlukan. Model-model ini akan menangkap pola yang kompleks dalam data dan dapat memberikan prediksi yang akurat dalam berbagai skenario.


**Mean Absolute Percentage Error (MAPE)** dipilih sebagai **metrik evaluasi** karena alasan berikut:

- MAPE memberikan kesalahan rata-rata dalam persentase, yang mudah dipahami dan ditafsirkan. Hal ini memungkinkan kita untuk mengetahui seberapa akurat model tersebut dalam memprediksi jumlah sepeda yang disewa dalam bentuk persentase dari nilai aktual.
- MAPE tidak terpengaruh oleh nilai ekstrim atau pencilan. Hal ini memungkinkan kita untuk memahami kesalahan prediksi secara keseluruhan tanpa terlalu dipengaruhi oleh data yang tidak biasa atau tidak representatif.

## Kesimpulan
- Maka dapat disimpulkan bahwa:

1. Diantara 5 model regresi yang diujikan, **XGBoost** adalah algoritma pemodelan yang paling baik dalam memprediksi nilai rumah dari dataset *california_housing_price.csv*

2. Berdasarkan evaluasi model menggunakan metrik Mean Absolute Percentage Error (MAPE), ditemukan bahwa setelah melakukan hyperparameter tuning, terjadi peningkatan kinerja pada semua model yang dievaluasi, yaitu KNN, Random Forest, dan XGBoost. Berikut adalah kesimpulan dari hasil evaluasi tersebut:

    - KNN: Setelah dilakukan tuning, model KNN mengalami penurunan MAPE sebesar 0.84%, dari sebelumnya 20.63% menjadi 19.79%. Meskipun penurunan ini tidak terlalu signifikan secara visual, namun menunjukkan adanya peningkatan kinerja model dalam memprediksi harga listing.

    - Random Forest: Model Random Forest juga mengalami peningkatan kinerja setelah tuning, dengan penurunan MAPE sebesar 0.16%, dari 18.59% menjadi 18.43%. Meskipun perbaikan ini kecil, namun menunjukkan bahwa tuning parameter dapat memberikan efek positif terhadap kinerja model.

    - XGBoost: Model XGBoost menunjukkan peningkatan kinerja yang paling signifikan setelah dilakukan tuning. Terjadi penurunan MAPE sebesar 0.86%, dari 17.28% menjadi 16.42%. Penurunan MAPE yang cukup besar ini menunjukkan bahwa tuning parameter telah berhasil mengoptimalkan model XGBoost secara efektif.

3. Feature Importance yang paling mempengaruhi hasil prediksi:
    - Median Income Penduduk di kawasan tersebut.
    - Lokasi (Terutama rumah di daerah Daratan/Jauh dari Pesisir pantai) **INLAND**.
4. Model **XGBoost Regressor dengan parameter('regressor__subsample': 0.8, 'regressor__n_estimators': 300, 'regressor__min_child_weight': 5, 'regressor__max_depth': 9, 'regressor__learning_rate': 0.05, 'regressor__gamma': 0.3, 'regressor__colsample_bytree': 0.8)** menunjukan hasil `MAPE` lebih kecil dibandingkan 4 model lainnya.
