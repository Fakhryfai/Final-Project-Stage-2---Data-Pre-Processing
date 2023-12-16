# Final-Project-Stage-2---Data-Pre-Processing
## A. Handle Missing Value
tidak terdapat missing values jika dilihat menggunakan isna.sum namun, terdapat value unknown pada dataset, yang mengindikasikan missing values, oleh karena itu perlu dilakukan replacement pada value unknown pada kolom job, education, contact dan poutcome dengan modusnya  
## B. Handle Duplicate Data
Tidak ada data duplikat
## C. Handle Outliers
Terdapat outliers pada kolom campaign dan balance, selanjutnya outliers dihapus menggunakan IQR pada kolom campaign dan balance. Jumlah data berkurang dari 45211 menjadi 37752.

## D. Feature Transformation
Dilakukan feature transformation pada fitur-fitur dengan skala berbeda menggunakan Standardization. 

## E. Feature Encoding
- Feature Encoding merupakan proses mengubah feature categorical menjadi feature numeric. 
- Pada data yang bertipe ordinal dan distinct values = 2 (ya/tidak) diubah menggunakan Label Encoding, sisanya diubah menggunakan one hot encoding


## F. Handle Class Imbalance
- Data Frame dibagi menjadi train data dan test data dengan test size 0.2 yang mana 80% merupakan train data dan 20% merupakan test data 
- Dilanjutkan dengan oversampling SMOTE 

# Feature Engineering
### Delete Unnecessary Columns
Sebab tidak ada feature tanggal yang lengkap, hanya melibatkan ‘day’ dan ‘month’ saja, tanpa ada year, sehingga akan sulit untuk disimpulkan apabila feature-feature ini dilibatkan.
### Delete Redundant Data
Feature ‘previous’ dengan ‘pdays’, ‘status_single’ dengan ‘status_married’, ‘contact_cellular’ dengan ‘contact_telephone’, ‘poutcome_failure’ dengan ‘poutcome_other’, memiliki korelasi di atas 0.7 yang menyebabkan mereka redundant untuk dijadikan feature bersama, sehingga akan digunakan salah satu saja.
### Feature Extraction
Dengan adanya 27 Feature, dirasa telah cukup feature yang dibutuhkan, dengan feature ini memiliki relevansi tersendiri terhadap ‘target’ yang ingin dicapai. Sehingga kami tidak akan mengeluarkan feature baru.

### Ide Feature for future references
- Jumlah anak/tanggungan
- Memiliki produk deposito berjangka pada bank lain (y/n)
- Sudah berapa lama menjadi nasabah bank tersebut
- Memiliki produk investasi lain selain deposito berjangka (y/n)
- Durasi setiap campaign (dengan informasi waktu yang lebih memadai)
