# Capstone Project Module-3 Customer Lifetime Value

[Sumber data CLV](https://drive.google.com/drive/folders/1GR7l3uWmcOCA2sxx1W-cEkReDxdedoeJ?usp=drive_link)

### **Contents**

1. Business Problem Understanding
2. Data Understanding
3. Data Preprocessing
4. Modeling
5. Conclusion
6. Recommendation

### **1. Business Problem Understanding**

**Background**

Customer lifetime value atau CLV adalah suatu ukuran seberapa penting suatu pelanggan terhadap perusahaan. Dari nilai tersebut, perusahaan dapat menentukan berapa keuntungan yang didapatkan dari suatu pelanggan dan biaya yang dikeluarkan untuk memperoleh pelanggan baru atau mempertahankan pelanggan lama. Angka ini cukup penting diketahui oleh suatu perusahaan jika perusahaan ingin secara efektif mengetahui seberapa besar keuntungan/profit (value) yang dapat diperoleh perusahaan dalam menjalin hubungan bisnis dengan pelanggan tersebut secara keseluruhan (lifetime).

Pada kasus perusahaan asuransi, mengetahui besarnya CLV dapat membantu beberapa kinerja perusahaan, diantaranya sebagai berikut.
* Marketing bisa menggunakan informasi CLV untuk menentukan pelanggan mana yang kemungkinan jarang melakukan klaim dan membayar premi yang tinggi. Marketing dapat memilih pelanggan yang menghasilkan keuntungan besar untuk perusahaan,
* Customer service bisa menentukan bagaimana metode yang tepat digunakan menangani setiap pelanggan, sehingga tidak ada biaya yang tinggi digunakan untuk pelanggan yang memiliki nilai CLV yang rendah
* Risk Management dapat menghitung bagaimana seorang pelanggan dapat memberikan keuntungan dan langkah yang perlu dilakukan ketika pelanggan tersebut pergi.

**Problem Statement**

*Customer Lifetime Value* bisa  dihitung berdasarkan data 2 informasi yaitu Customer Value (rata-rata nilai/value pelanggan) dan Average Customer Lifespan (rata-rata lama hubungan bisnis pelanggan dengan perusahaan). Kedua informasi tersebut dapat dibilang sangat terbatas dan tidak menggambarkan karakteristik pelanggan secara mendetail, sehingga walaupun didapatkan nilai CLV, informasi tersebut tidak dapat digunakan secara luas. Selain itu, dibutuhkan juga waktu yang lebih lama untuk menghitung nilai CLV secara manual dalam lingkup perusahaan yang memiliki berbagai macam pelanggan dengan karakteristik yang berbeda-beda.

Dengan memprediksi *Customer Lifetime Value* perusahaan dapat menentukan mana pelanggan yang mungkin memiliki value yang tinggi dan mana yang tidak. Perusahaan bisa memfokuskan kegiatan marketing pada pelanggan yang memiliki value yang tinggi, tidak pada pelanggan yang memiliki value yang rendah. Hal ini dapat meningkatkan effesiensi perusahaan, sehingga perusahaan memerlukan suatu metode yang cepat dan akurat untuk mengetahui dan memprediksi nilai CLV pelanggan berdasarkan data informasi yang tersedia.

**Goals**

Berdasarkan permasalahan tersebut, perusahaan memerlukan sebuah 'tool' yang dapat memprediksi serta membantu pelanggan mereka untuk dapat menentukan *Customer Lifetime Value* pelanggan berdasarkan fitur-fitur tertentu dengan akurat. Adanya perbedaan pada berbagai informasi data yang dimilik pelanggan, seperti jenis kendaraan, jumlah pendapatan, dan tingkat edukasi dapat menambah keakuratan prediksi nilai pelanggan tersebut.

Dari penggunaan "tool" tersebut, dapat memberikan prediksi *Customer Lifetime Value* secara akurat yang dapat meningkatkan jumlah pelanggan. Sehingga semakin banyak pelanggan yang berarti dapat meningkatkan *revenue* untuk perusahaan.

**Analytic Approach**

*Analytic Approach* perlu dilakukan untuk menganalisis data yang dapat menemukan pola dari karakteristik pelanggan yang ada terhadap nilai CLV yang dihasilkan.

Selanjutnya, kita akan membangun suatu model Machine Learning regresi yang akan membantu perusahaan asuransi untuk dapat menyediakan 'tool' prediksi nilai CLV yang tentunya akan sangat membantu perusahaan dalam mempercepat proses planning dan implementasi yang akurat terkait pelanggan (baik dalam hal marketing, menjalin hubungan, prioritas, dsb), sehingga keuntungan yang diperoleh perusahaan dapat maksimal.

**Metric Evaluation**

*Metric Evaluation* yang akan digunakan adalah sebagai berikut.
* RMSE adalah nilai rataan akar kuadrat dari error
* MAE adalah rataan nilai absolut dari error
* MAPE adalah rataan persentase error yang dihasilkan oleh model regresi

Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi nilai CLV.

Selain itu, kita juga bisa menggunakan nilai R-squared atau adj. R-squared jika model yang nanti terpilih sebagai final model adalah model linear. Nilai R-squared digunakan untuk mengetahui seberapa baik model dapat merepresentasikan varians keseluruhan data. Semakin mendekati 1, maka semakin fit pula modelnya terhadap data observasi. Namun, metrik ini tidak valid untuk model non-linear.

### **2. Data Understanding**

Dataset berisikan informasi data pelanggan beserta nilai CLV-nya masing-masing.

**Features Information**

| **Feature** | **Data Type** | **Description** |
| --- | --- | --- |
| Vehicle Class | Object | Class of Customer Vehicle |
| Coverage | Object | Type of Insurance Policies |
| Renew Offer Type | Object | Type of Renewal Offers |
| Employment Status | Object | Customer Employment Status |
| Marital Status | Object | Customer Marital Status |
| Education | Object | Customer Education Level |
| Number of Policies | Float | Number of Policies Customer Currently Owns |
| Monthly Premium Auto | Float | Amount of customers' monthly insurance payments (in US$)|
| Total Claim Amount | Float | Cumulative Amount of Claims Since Policy Inception|
| Income | Float | Customer Income (in US$)|
| Customer Lifetime Value | Float | Customer Lifetime Value |

[Feature Information Source](https://www.kaggle.com/code/juancarlosventosa/models-to-improve-customer-retention/notebook) 

### **3. Data Preprocessing**

### **4. Modeling**

* Cross Validation
* Hyperparameter Tuning
  1. Hyperparameter tuning untuk gradient boosting
  2. Hyperparameter tuning untuk decision tree

### **5. Conclusion**

Berdasarkan pemodelan yang sudah dilakukan, fitur '*Number of Policies*' menjadi fitur yang paling berpengaruh terhadap '*Customer Lifetime Value*'.

Metrik evaluasi yang digunakan pada model adalah nilai MAPE. Jika ditinjau dari nilai MAPE yang dihasilkan oleh model setelah dilakukan *hyperparameter tuning*, yaitu sebesar 12.90%, kita dapat menyimpulkan bahwa bila nanti model yang kita buat ini digunakan untuk memperkirakan *CLV* pelanggan baru di perusahaan A pada rentang nilai seperti yang dilatih terhadap model (didapat dari function df.describe(include='all') ):
 - *Number of Policies* dari 1 sampai 9
 - *Monthly Premium Auto* dari 61 sampai 249
 - *Total Claim Amount* dari 0.42 sampai 1961.16
 - *Income* dari 10037 sampai 99934
 - *Vehicle Class* dari kelompok Four-Door Car, Two-Door Car, SUV, Sports Car, Luxury Car, dan Luxury SUV
 - *Coverage* tipe Basic, Extended, dan Premium
 - *Renew Offer Type* jenis Offer1, Offer2, Offer3, dan Offer4
 - *Employment Status* dari kelompok Employed, Unemployed, Medical Leave, Disabled, dan Retired
 - *Marital Status* dengan jenis Married, Single, dan Divorced
 - *Education* tingkat edukasi High Schoold or Below, College, Bachelor, Master, dan Doctor
 
 maka perkiraan *CLV*nya rata-rata akan meleset kurang lebih sebesar 12.90% dari nilai *CLV* seharusnya. 
 
 Tetapi, tidak menutup kemungkinan juga prediksinya meleset lebih jauh karena *bias* yang dihasilkan model masih cukup tinggi bila dilihat dari visualisasi antara *CLV* aktual dan prediksi. *Bias* yang dihasilkan oleh model ini dikarenakan oleh terbatasnya fitur pada *dataset* yang bisa merepresentasikan aspek informasi pelanggan, seperti kelas kendaraan, jenis asuransi, status pekerjaan, status pernikahan, tingkat edukasi, dan lain-lain.

 Model ini tentu masih dapat ditingkatkan performanya agar dapat menghasilkan prediksi yang lebih baik lagi. Namun, kita harus mengatasi limitasi model yang akan dijabarkan dibawah ini.
 1. Jumlah fitur yang sedikit. Karena *dataset* yang didapatkan hanya berisi 10 fitur (10 kolom), maka tentu saja hasil prediksi hanya akan belajar dari fitur-fitur yang sedikit itu, sehingga model menjadi "kurang pintar". Ternyata, walaupun kita sudah menggunakan *polynomial feature*, namun hal itu tidak dapat meningkatkan performa model.
2. Jumlah data (dapat dihitung dari jumlah baris pada dataset) yang sangat sedikit. Kita hanya memiliki 5669 data diawal, sehingga model hanya dapat belajar dari rentang data-data tersebut. Apabila model disuruh prediksi data lain yang berada diluar dari rentang *dataset* yang kita miliki, maka hasil prediksi menjadi kurang akurat dan kurang bisa dipercaya.
3. Masih ada *outliers*. Di satu sisi, apabila kita menghilangkan seluruh *outliers*, maka kita akan kehilangan lebih banyak data dari data yang jumlahnya sudah sangat sedikit. Di sisi lainnya, *outliers* dapat mengurangi performa model. Jadi, setiap keputusan yang diambil memang ada kelebihan dan kekurangannya.

### **6. Recommendation**

### Untuk bisnis.
Dikarenakan nilai *error* yang cukup besar dari nilai *CLV* aktual dengan *CLV* prediksi, maka hasil prediksi model ini sebaiknya tidak secara mentah-mentah dipercaya oleh perusahaan untuk memprediksi *CLV* pelanggannya. Hal ini disebabkan oleh limitasi yang telah dijelaskan diatas. Namun, hasil prediksi untuk nilai *CLV* yang rendah masih cukup akurat. Perusahaan masih dapat memercayai hasil prediksi model apabila nilai *CLV* masih sekitar dibawah 8000 (berdasarkan visual dari *scatterplot*).

### Untuk performa model.
Perusahaan dapat memperbaiki performa model melalui beberapa cara, diantaranya:
- Menambah jumlah fitur pelanggan. Hal ini dapat mengurangi risiko model *underfitting*. Namun, tentu saja fitur yang ditambahkan tidak boleh sembarangan. Apabila perusahaan A menambah terlalu banyak fitur, maka model dapat cenderung *overfitting*. Tambahkan fitur-fitur yang berkaitan/berkorelasi kuat dengan *CLV* seseorang, misalkan tingkat retensi pelanggan (semakin lama pelanggan menggunakan produk/jasa perusahaan A, maka semakin tinggi pula nilai *CLV* pelanggan itu), frekuensi pembelian pelanggan (semakin sering pelanggan melakukan pembelian, semakin tinggi nilai *CLV* pelanggan itu), dan demografi pelanggan (segmen pelanggan yang berbeda mungkin memiliki perilaku pembelian (*purchasing behavior*) yang berbeda. Hal ini dapat mempengaruhi *CLV* mereka).
- Menambah jumlah data pelanggan. Hal ini dapat membuat model menjadi semakin "pintar" karena model akan belajar dari data yang lebih heterogen/lebih beragam. Hal ini juga dapat mengurangi kemungkinan *overfitting*.
- Meningkatkan kualitas data. Ada aturan terkenal dalam dunia *machine learning* yaito GIGO (*Garbage In, Garbage Out*). Tidak peduli seberapa canggih dan akurat model yang dipakai, apabila data yang diolah berkualitas rendah, maka hasilnya akan berkualitas rendah juga.
- Menggunakan GridSearch pada saat *hyperparameter tuning* untuk mendapatkan hasil terbaik. Karena keterbatasan waktu dan kemampuan laptop, saya hanya memakai Randomized Search. Hasil *hyperparameter tuning* yang dihasilkan tentu tidak akan sebaik *hyperparameter tuning* hasil GridSearch.
- Mencoba model/algoritma *machine learning* lain yang lebih kompleks seperti *neural network*, *deep learning algorithm*, dan *survival analysis*. Model yang lebih canggih dan kompleks dapat meningkatkan performa model, walaupun belum pasti. Model yang lebih kompleks juga jauh lebih sulit untuk diinterpretasikan.

### Save Model
- Mencoba model yang sudah dibuat kepada seorang pelanggan baru
- Mengecek rentang tiap data/fitur yang sudah dipelajari model.
- Membuat fitur/informasi dari pelanggan baru tersebut.











