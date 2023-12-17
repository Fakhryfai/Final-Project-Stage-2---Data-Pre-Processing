# Final-Project-Stage-2---Data-Pre-Processing
## A. Handle Missing Value
Tidak terdapat missing values pada dataset, namun untuk fitur poutcome yang memiliki value unknown dilakukan replacement menjadi never yang menunjukkan bahwa customer tidak pernah di hubungi karena memiliki pdays = -.

## B. Handle Duplicate Data
Tidak terdapat duplicated values pada dataset

## C. Handle Outliers
Beberapa fitur numerik pada dataset memiliki sebaran yang right skewed (long right tailed), oleh karena itu dilakukan log transformation terlebih dahulu sebelum me-remove outliers. Log transformation hanya dilakukan pada fitur age dan campaign saja, karena jika semua fitur numerik dilakukan log transformation jumlah data setelah remove outlier akan hilang secara keseluruhan atau berjumlah 0. Setelah log transformation pada fitur age dan campaign, selanjutnya menghapus outliers menggunakan z-scores yang mana jumlah data berkurang dari 45.211 menjadi 44.790.

## D. Feature Transformation
- Sebelum dilakukan feature transformation, dataset dibagi menjadi train data dan test data terlebih dahulu. Yang mana 80% data merupakan train data yang berjumlah 35.835 dan test data sebanyak 20% dari keseluruhan dataset yang berjumlah 8.958
- Selanjutnya dilakukan feature scalling pada train data dan test data dengan standarization untuk fitur numerik. 

## E. Feature Encoding
- Feature Encoding merupakan proses mengubah feature categorical menjadi feature numeric.
- Pada data yang bertipe ordinal dan distinct values = 2 (ya/tidak) diubah menggunakan Label Encoding, sisanya diubah menggunakan one hot encoding

## F. Handle Class Imbalance
- Oversampling SMOTE pada data train yang memiliki ketimpangan pada ditribusi target 

# Feature Engineering
### Delete Unnecessary Columns
Sebab tidak ada feature tanggal yang lengkap, hanya akan didrop ‘day’ sebab korelasinya terhadap y kecil,serta ‘month’ sebab dari apa yang telah disimpulkan pada EDA Multivariate Analysis. Ditambah, day dan month tanpa time series year dan tanpa adanya info kapan campaign dilaksanakan, menjadi sulit untuk menarik kesimpulan dari hal tersebut.

### Delete Redundant Data
Feature ‘previous’ dengan ‘pdays’, ‘status_single’ dengan ‘status_married’, ‘contact_cellular’ dengan ‘contact_unknown’, ‘poutcome_failure’ dengan ‘poutcome_never’, memiliki korelasi di atas 0.7 yang menyebabkan mereka redundant untuk dijadikan feature bersama, sehingga akan digunakan salah satu saja.

### Feature Extraction
Dengan adanya 32 Feature, dirasa telah cukup feature yang dibutuhkan, dengan feature ini memiliki relevansi tersendiri terhadap ‘target’ yang ingin dicapai. Sehingga kami tidak akan mengeluarkan feature baru.

### Ide Feature for future references
- Jumlah anak/tanggungan
- Memiliki produk deposito berjangka pada bank lain (y/n)
- Sudah berapa lama menjadi nasabah bank tersebut
- Memiliki produk investasi lain selain deposito berjangka (y/n)
- Durasi setiap campaign (dengan informasi waktu yang lebih memadai)
