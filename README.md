# CheckPoint 1 (A_Brendhen_Canafaro_Lie_033)
CheckPoint 1: Data Gathering & Business Understanding

# Import Library
import pandas as pd

# Memuat Dataset
file = "/content/drive/MyDrive/Tugas-Tugas Praktikum/Tugas AVD/CheckPoint 1: Data Gathering & Business Understanding/Finance_Ecommerce_Dirty_Dataset_csv.csv"

df = pd.read_csv(file)

df.head()

# Business Understanding

## Business Objective

Dataset ini merupakan data-data transaksi keuangan pada platform e-commerce. Dataset ini memiliki 6060 baris x 23 kolom. 

Pada dasarnya setiap kebutuhan berbisnis didalam dunia digital diperlukan adanya sebuah analisis terhadap kebutuhan pasar, akan hal tersebut kita perlu melihat dimana dan apa kategori pasar yang cocok untuk terjun kedalam industri tersebut, agar dapat hasil terbaik saat menjalankan bisnis e-commerce

Dataset ini akan digunakan yaitu, sebagai berikut:
1. Menganalisis tren transaksi dari waktu ke waktu
2. Mengidentifikasi kategori dan subkategori pilihan pasar
3. Menganalisis transaksi berdasarkan lokasi pelanggan

## Assess Situation
Platform e-commerce setiap harinya melakukan ribuan transaksi, yang dimana setiap data transaksi menyimpan informasi penting bagi pengambilan keputusan

Dengan analisis data-data transaksi, perusahaan-perusahaan dapat memahami pola belanja pelanggan, dan akan hal tersebut sangat membantu bisnis memahami kondisi keuangan dan pola pasar konsumen. Berikut merupakan ciri-ciri dari dataset: 

1. Sumber Data  
Dataset Finance_Ecommerce_Dirty_Dataset dari Kaggle.

2. Kondisi Data 
* 6061 baris  
* 23 kolom  
* Terdapat data kotor dan nilai kosong

3. Kendala 
* Data-data ada yang kosong 

## Analytic Goals & Project Plan

### Tujuan
1. Analisis tren transaksi dari waktu ke waktu
2. Analisis kategori dan subkategori pilihan pasar
3. Analisis transaksi berdasarkan lokasi pelanggan

### Rencana Proyek
1. Memahami Data  
2. Mengelola dan membersihkan data  
3. Visualisasi data 
4. Menyusun rapi hasil data
4. Membuat ringkasan dan kesimpulan

# Data Understanding

**Data Understanding** adalah sebuah tahap kedua setelah business understanding. Setelah terbuatnya konsep dasar dari tujuan penggunaan data dan apa hasil yang ingin dicapai, data perlu di **pahami, analisa, diperbaiki, dan dibersihkan** sehingga menjadi data yang dapat digunakan sebagai visualisasi, sesuai keperluan pengguna.

## Memuat Dataset

Dataset yang digunakan adalah file csv yang berjudul **"Finance Ecommerce Dirty Dataset"**, dataset ini berisikan Dataset ini berisi data transaksi keuangan dari sebuah platform e-commerce.

Dataset ini mencatat **detail transaksi, perilaku belanja pelanggan, tren transaksi, dan indikasi penipuan.** Informasi utama meliputi **transaksi, nilai uang, saldo, mata uang, serta jenis transaksi.**
Dataset juga memuat **data merchant dan data pelanggan, **sehingga analisis pola belanja dan lokasi dapat dilakukan.

Dataset ini memiliki data-data yang cukup besar yaitu, **6060 baris dan 23 kolom.**


```python
file = "/content/drive/MyDrive/Tugas-Tugas Praktikum/Tugas AVD/CheckPoint 1: Data Gathering & Business Understanding/Finance_Ecommerce_Dirty_Dataset_csv.csv"

df = pd.read_csv(file)
df


# Deskripsi Data

Dari sebuah dataset terdapat sebuah informasi yang bisa dicari, dengan bagaimana hal tersebut dapat menjelaskan tentang isi dan ciri suatu dataset itu sendiri. Isi dari sebuah informasi deskripsi data dapat mencakup sumber data, jumlah data, jenis variabel, dan lainnya.

### Informasi Dasar

Informasi dasar dari sebuah dataset yang bisa berupa **data type, jumlah baris kolom, data kosong, dan lainnya**. Berdasarkan data yang dibawah ini, dapat diketahui dari dataset ini adalah dataset ini memiliki **6060 baris dan 23 kolom.**

```python
df.info()


### Informasi Lanjutan

```python
dd.info()


**1. TransactionID:**
         
        Jumlah baris: 6057
        Tipe data: object
        Deskripsi: Kode unik untuk tiap transaksi

**2. Date:**

        Jumlah baris: 6060
        Tipe data: object
        Deskripsi: Tanggal transaksi dilakukan

**3. AccountID:**

        Jumlah baris: 6059
        Tipe data: object
        Deskripsi: ID unik pemilik akun

**4. AccountName:**

        Jumlah baris: 6059
        Tipe data: object
        Deskripsi: Nama pemilik akun

**5. TransactionType:**

        Jumlah baris: 6058
        Tipe data: object
        Deskripsi: Jenis transaksi, seperti debit atau kredit

**6. Amount:**

        Jumlah baris: 6059
        Tipe data: object
        Deskripsi: Nilai uang pada transaksi

**7. Currency:**

        Jumlah baris: 6055
        Tipe data: object
        Deskripsi: Mata uang yang digunakan

**8. ExchangeRate:**

        Jumlah baris: 6058
        Tipe data: float64
        Deskripsi: Nilai tukar mata uang ke mata uang utama

**9. Balance:**

        Jumlah baris: 5988
        Tipe data: object
        Deskripsi: Saldo akun setelah transaksi

**10. Merchant:**

        Jumlah baris: 6058
        Tipe data: object
        Deskripsi: Nama tempat atau pihak transaksi

**11. MerchantPhone:**

        Jumlah baris: 4647
        Tipe data: float64
        Deskripsi: Nomor telepon merchant

**12. MerchantEmail:**

        Jumlah baris: 4222
        Tipe data: object
        Deskripsi: Alamat email merchant

**13. Category:**

        Jumlah baris: 6058
        Tipe data: object
        Deskripsi: Kategori utama transaksi

**14. Subcategory:**

        Jumlah baris: 6055
        Tipe data: object
        Deskripsi: Rincian kategori transaksi

**15. Country:**

        Jumlah baris: 6058
        Tipe data: object
        Deskripsi: Negara tempat transaksi terjadi

**16. City:**

        Jumlah baris: 6058
        Tipe data: object
        Deskripsi: Kota tempat transaksi terjadi

**17. PostalCode:**

        Jumlah baris: 5742
        Tipe data: float64
        Deskripsi: Kode pos lokasi transaksi

**18. CardNumber:**

        Jumlah baris: 5621
        Tipe data: object
        Deskripsi: Nomor kartu yang digunakan

**19. Email:**

        Jumlah baris: 5801
        Tipe data: object
        Deskripsi: Email pemilik akun

**20. Phone:**

        Jumlah baris: 5732
        Tipe data: float64
        Deskripsi: Nomor telepon pemilik akun

**21. IsFraud:**

        Jumlah baris: 5984
        Tipe data: object
        Deskripsi: Penanda apakah transaksi penipuan atau bukan

**22. Notes:**

        Jumlah baris: 5256
        Tipe data: object
        Deskripsi: Catatan tambahan transaksi

**23. CustomerSince:**

        Jumlah baris: 6058
        Tipe data: object
        Deskripsi: Tanggal mulai menjadi nasabah


### Informasi Statistik Deskriptif

```python
df.describe(include='all')



1. **Count (Kelengkapan Data)**

Berdasarkan data, total baris transaksi adalah 6060. Maka dapat disimpulkan:

* **TransactionID**: hilang **3 data** (6060 - 6057)

* **AccountID**: hilang **1 data** (6060 - 6059)  
* **AccountName**: hilang **1 data** (6060 - 6059)  
* **TransactionType**: hilang **1 data** (6060 - 6059)
* **Amount**: hilang **1 data** (6060 - 6059)  
* **Currency**: hilang **5 data** (6060 - 6055)  
* **ExchangeRate**: hilang **2 data** (6060 - 6058)  
* **Balance**: hilang **72 data** (6060 - 5988)  
* **Merchant**: hilang **2 data** (6060 - 6058)  
* **MerchantPhone**: hilang **1413 data** (6060 - 4647)
* **MerchantEmail**: hilang **1838 data** (6060 - 4222)  
* **Category**: hilang **2 data** (6060 - 6058)  
* **Subcategory**: hilang **5 data** (6060 - 6055)  
* **Country**: hilang **2 data** (6060 - 6058)  
* **City**: hilang **2 data** (6060 - 6058)  
* **PostalCode**: hilang **318 data** (6060 - 5742)  
* **CardNumber**: hilang **439 data** (6060 - 5621)  
* **Email**: hilang **259 data** (6060 - 5801)  
* **Phone**: hilang **328 data** (6060 - 5732)  


Kesimpulan:

Berdasarkan hasil pengecekan, sebagian besar kolom masih memiliki data yang cukup lengkap.
Missing values paling banyak terdapat pada kolom **MerchantPhone **dan **MerchantEmail**, dan juga terdapat kolom-kolom yang memiliki missing values yang cukup besar pada dataset, yaitu **CardNumber, PostalCode, Phone, Email, dan Balance.**

Kolom lain seperti **TransactionID, AccountID, Amount, TransactionType, dan lain-lainnya,** hanya kehilangan sedikit data dan masih dapat ditangani dengan mudah.

Secara keseluruhan, dataset masih layak digunakan untuk analisis, namun diperlukan proses pembersihan data pada beberapa kolom sebelum visualisasi dan pemodelan dilakukan.

Berdasarkan jumlah data hilang, missing values dapat dikelompokkan sebagai berikut:

**Kategori Tinggi**
Kolom dengan jumlah data hilang besar dan perlu perhatian khusus.
* **MerchantEmail**: 1838 data hilang  
* **MerchantPhone**: 1413 data hilang  

**Kategori Sedang**
Kolom dengan jumlah data hilang sedang dan masih dapat ditangani.
* **CardNumber**: 439 data hilang  
* **PostalCode**: 318 data hilang  
* **Phone**: 328 data hilang  
* **Email**: 259 data hilang  
* **Balance**: 72 data hilang  

**Kategori Rendah**
Kolom dengan jumlah data hilang sedikit dan dampaknya kecil.
* **TransactionID**: 3 data hilang  
* **AccountID**: 1 data hilang  
* **AccountName**: 1 data hilang  
* **TransactionType**: 1 data hilang  
* **Amount**: 1 data hilang  
* **Currency**: 5 data hilang  
* **ExchangeRate**: 2 data hilang  
* **Merchant**: 2 data hilang  
* **Category**: 2 data hilang  
* **Subcategory**: 5 data hilang  
* **Country**: 2 data hilang  
* **City**: 2 data hilang  


---



**2. Mean vs Median (Distribusi Data)**

Perbandingan mean dan median digunakan untuk melihat sebaran data. Dari dataset hanya terdapat satu kolom angka yang bisa kita analisa, yaitu kolom data **ExchangeRate** . Sedangkan kolom lainnya seperti **PostalCode, MerchantPhone dan Phone,** tidak dapat dianalisa dikarenakan tidak memiliki makna stastistik yang kuat.

Data kolom numerik seperti **Balance dan Amount** tidak dapat dianalisa dikarenakan hasil program describe menghasilkan dikolom balance dan amount adalah **NaN**

* Kolom ExchangeRate  
  * Mean = 46,32  
  * Median = 72,09 - Nilai rata-rata lebih kecil dari median

  Ini menunjukkan data cenderung condong ke kiri.  
  Terdapat beberapa nilai rendah yang menarik rata-rata ke bawah.

Kesimpulan:  
Distribusi ExchangeRate menunjukkan kecenderungan **left-skewed** (Condong ke kiri). Analisis mean dan median ini tidak dapat menggambabarkan sifat keseluruhan data, karena nilai ExchangeRate tidak mempengaruhi variabel utama lainnya.


---



**3. Min dan Max (Validasi Logika)**

**Min dan max** adalah nilai paling kecil dan nilai paling besar dalam suatu data, keduanya dipakai untuk mengecek kewajaran nilai. Sama seperti sebelumnya terdapat kolom data numerik yang seharusnya bisa dianalisa seperti **Balance dan Amount,** tetapi hasil kolom yang dikeluarkan adalah **NaN**

* ExchangeRate
  * Min = 1,00
  * Max = 109.97

Kesimpulan:

Nilai **ExchangeRate** menunjukkan nilai minimum transaksi dengan mata uang bernilai setara, sedangkan nilai maksimum menunjukkan adanya transaksi dengan mata uang bernilai tinggi.




---



**4. Standar Deviasi (std) - Variabilitas Data**

Standar deviasi digunakan untuk melihat seberapa jauh data menyebar dari rata-ratanya. Sama seperti sebelumnya pada kolom data numerik **Amount dan Balance** tidak dapat dianalisa karena isi kolom adalah **NaN**

* ExchangeRate
  * Mean = 46,32
  * Std = 40.25


Kesimpulan:

Pada kolom **ExhangeRate,** nilai standar deviasi yang cukup besar. Hal ini menandakan perbedaan nilai tukar mata uang yang signifikan antar transaksi.


## Verifikasi Kualitas Data

**Verifikasi kualitas data** adalah proses untuk memastikan data layak dianalisis.
Proses ini mengecek apakah data sudah lengkap, akurat, dan konsisten. Verifikasi dilakukan dengan **melihat data hilang, tipe data, dan nilai aneh**.
Contohnya nilai terlalu besar, terlalu kecil, atau tidak masuk akal. **Tujuannya** agar hasil analisis tidak menyesatkan.
Data yang baik menghasilkan kesimpulan yang lebih tepat.


### Data Type Check

Disini kita akan melakukan pengecekan tipe data pada setiap kolom, Tujuannya agar analisis dan visual yang dibuat lebih akurat dan tidak menyesatkan.

Dilihat dibawah ini, terdapat beberapa kesalahan tipe data yang diberikan, yaitu sebagai berikut:
1. Date, kolom ini diberikan tipe data object, seharusnya kolom ini bertipe data kan date, karena isi kolom tersebut adalah tanggal.
2. Amount, kolom ini diberikan tipe data object, seharusnya kolom ini bertipe data kan float, karena bisa ber angka desimal.
3. Balance, kolom ini diberikan tipe data object, seharusnya kolom ini bertipe data kan float, karena bisa ber angka desimal.
4. IsFraud, kolom ini diberikan tipe data object, seharusnya kolom ini bertipe data kan boolean, karena isi dari kolom sendiri adalah No atau Yes seperti boolean yang True atau False.
5. CostumerSince, kolom ini diberikan tipe data object, seharusnya kolom ini bertipe data kan date, karena isi kolom tersebut adalah tanggal.

```python
df.dtypes


### Incosistent Value

Pada tahap **incosistent value** ini, dilakukan pengecekan konsistensi data, terutama pada cara penulisan.
Tujuannya agar data yang sebenarnya sama, tidak terbaca sebagai data berbeda akibat perbedaan penulisan.


1. AccountName

Dapat dilihat, bahwa pengecekkan kolom AccountName memperlihatkan **perbedaan penulisan, seperti huruf besar kecil dan salah ketik.**

Contoh kalimatnya adalah **Raj Gupta dan raj GUPTA**. Kedua nama tersebut memiliki nama yang sama tapi dengan format yang berbeda

```python
print(df['AccountName'].unique())



2. TransactionType

Dapat dilihat, bahwa pengecekkan kolom TransactionType memperlihatkan perbedaan penulisan, seperti **format huruf besar dan kecil.**

Contoh kalimatnya adalah **Credit dan CREDIT**. Kedua jenis transaksi tersebut memiliki nama yang sama tapi dengan format yang berbeda.

```python
print(df['TransactionType'].unique())



3. Currency

Dapat dilihat, bahwa pengecekkan kolom Currency memperlihatkan perbedaan penulisan, seperti **format huruf besar dan kecil.**

Contoh kalimatnya adalah **usd dan USD**. Kedua jenis mata uang tersebut memiliki nama yang sama tapi dengan format yang berbeda.

```python
print(df['Currency'].unique())



4.IsFraud

Dapat dilihat, bahwa pengecekkan kolom IsFraud memperlihatkan perbedaan penulisan, seperti **kesalahan pengetikan.**

Contoh kalimatnya adalah **yes dan Yess**. Kedua jenis perkataan tersebut memiliki makna yang sama tapi dengan format yang berbeda.

```python
print(df['IsFraud'].unique())



5. Notes

Dapat dilihat, bahwa pengecekkan kolom Notes memperlihatkan perbedaan penulisan, seperti **dalam format penulisan.**

Contoh kalimatnya adalah **repeat purchase dan suspected fraud -- verify\ncontact support**. Kedua notes tersebut memiliki nama yang sama tapi dengan format yang berbeda.

```python
print(df['Notes'].unique())



6. CustomerSince

Dapat dilihat, bahwa pengecekkan kolom Notes memperlihatkan perbedaan penulisan, seperti **dalam format penulisan tanggal.**

Contoh kalimatnya adalah **16/09/2018 dan Aug-21**. Kedua tanggal tersebut memiliki format yang berbeda.

'''python
print(df['CustomerSince'].unique())



### Missing Value

Pada tahap ini, kita akan melihat seberapa banyak data yang hilang pada seluruh kolom. Dan juga perhitungan **dibawah 1 persen seperti 0.0182 % sekian**, akan tidak terhitung dan dianggap tidak perlu ditangani atau dihapus. Maka terlihat bahwa kolom:


* **Balance (1.18%)**

Memiliki missing values sekitar 1%, yang dimana ini nilai yang kecil sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut dapat diabaikan atau dilakukan pengisian data.

* **MerchantPhone (23.32%)**

Memiliki missing values sekitar 23%, yang dimana ini nilai yang cukup besar sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut perlu ditangani atau dihapus.

* **MerchantEmail (30.33%)**

Memiliki missing values sekitar 30%, yang dimana ini nilai yang cukup besar sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut perlu ditangani atau dihapus.

* **PostalCode (5.24%)**

Memiliki missing values sekitar 5%, yang dimana ini nilai yang lumayan kecil sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut dapat diabaikan atau ditangani.

* **CardNumber (7.24%)**

Memiliki missing values sekitar 7%, yang dimana ini nilai yang lumayan kecil sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut dapat diabaikan atau ditangani.

* **Email (4.27%)**

Memiliki missing values sekitar 4%, yang dimana ini nilai yang lumayan kecil sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut dapat diabaikan atau ditangani.

* **Phone (5.41%)**

Memiliki missing values sekitar 5%, yang dimana ini nilai yang lumayan kecil sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut dapat diabaikan atau ditangani.

* **IsFraud (1.25%)**

Memiliki missing values sekitar 1%, yang dimana ini nilai yang kecil sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut dapat diabaikan atau dilakukan pengisian data.

* **Notes (13.26)**

Memiliki missing values sekitar 23%, yang dimana ini nilai yang lumayan besar sebagai indikasi hilang nya data pada kolom tersebut. Sehingga kolom tersebut perlu ditangani atau dihapus.

* **Date, AccountID, AccountName, TransactionType, Amount, Currency, ExchangeRate, Merchant, Category, Subcategory, Country, City, CustomerSince dan lainnya**

Memiliki Missing value di bawah 1% (0.0000% - 0.0825%), bisa diabaikan atau dianggap tidak signifikan.

```python
pd.DataFrame(df.isna().sum() / len(df) * 100, columns=['Null Ratio in %'])



### Duplicated Value

Sekarang, kita akan memeriksa adanya data duplikat agar dataset tetap bersih dan hasil analisis lebih akurat.

```python
df[df.duplicated()]



Terlihat terdapat **satu baris duplikat** yang terdapat dalam dataset tersebut, maka itu kita akan menjalankan program df = df.drop_duplicates() untuk menghapus baris duplikat tersebut.:


```python
df = df.drop_duplicates()


Terlihat bahwa dataset yang digunakan telah bersih dari duplikat

### Outliers Values
Pada tahap ini, kita akan meninjau nilai ekstrem (outliers) pada kolom numerik dan kolom penting lain, seperti **MerchantPhone dan Phone**. Tujuannya agar mendapatkan insight yang lebih akurat dan mendukung analisis serta model yang akan dibuat.

Tidak semua kolom harus ditangani; penting untuk memahami fungsi dan tujuan masing-masing kolom dalam dataset.

Dari hasil pengecekan, terlihat:

* **MerchantPhone** - presentase outlier **2,1%**

* **Phone** - presentase outlier **2,5%**


```python
results = []

cols = df.select_dtypes(include=['float64', 'int64'])

for col in cols:
  q1 = df[col].quantile(0.25)
  q3 = df[col].quantile(0.75)
  iqr = q3 - q1
  lower_bound = q1 - 1.5*iqr
  upper_bound = q3 + 1.5*iqr
  outliers = df[(df[col] < lower_bound) | (df[col] > upper_bound)]
  percent_outliers = (len(outliers)/len(df))*100
  results.append({'Kolom': col, 'Persentase Outliers': percent_outliers})

# Dataframe dari list hasil
results_df = pd.DataFrame(results)
results_df.set_index('Kolom', inplace=True)
results_df = results_df.rename_axis(None, axis=0).rename_axis('Kolom', axis=1)

# Tampilkan dataframe
display(results_df)


```python
plt.figure(figsize=(8, 6))
sns.boxplot(y=df['MerchantPhone'])
plt.title('Boxplot of MerchantPhone')
plt.ylabel('MerchantPhone')
plt.show()



```python
plt.figure(figsize=(8, 6))
sns.boxplot(y=df['Phone'])
plt.title('Boxplot of Phone')
plt.ylabel('Phone')
plt.show()



## Eksplorasi Data (EDA)

**Exploratory Data Analysis (EDA)** adalah tahap awal dalam analisis data yang bertujuan untuk memahami struktur, pola, dan hubungan dalam dataset sebelum melakukan pemodelan lebih lanjut.

### Comprarison/Perbandingan

**Aktivitas**: Membandingkan kategori industri pasar dan produk barang.

**Tujuan**: Mengidentifikasi industri pasar yang mana paling memiliki transaksi paling banyak dan juga menemuka jenis produk barang apa yang paling diminati

**Visualisasi**: Bar Chart (Grafik Batang).


```python
df = df.copy()
df['Amount'] = pd.to_numeric(df['Amount'], errors='coerce')

penjualan_market = df.groupby('Category')['Amount'].sum().sort_values(ascending=False)

plt.figure(figsize=(10,6))
sns.barplot(x=penjualan_market.index, y=penjualan_market.values, hue=penjualan_market.index, palette='viridis')
plt.title('Industri Pasar Berdasarkan Total Penjualan')
plt.xlabel('Industri Pasar')
plt.ylabel('Total Penjualan')
plt.xticks(rotation=45)
plt.show()



**Insight**

Dari visualisasi data di atas, dapat disimpulkan bahwa:

* Industri **Automotive** punya total penjualan tertinggi, diikuti Education dan Entertainment.

* Industri **Health** memiliki penjualan paling rendah.

* Sebagian besar transaksi terjadi di sektor **otomotif, pendidikan, dan hiburan.**

**Kesimpulan:**

Strategi bisnis harus difokuskan pada penguatan penetrasi di sektor dominan seperti **Automotive, Education, dan Entertainment.**


```python
penjualan_market = df.groupby('Subcategory')['Amount'].sum().sort_values(ascending=False)

plt.figure(figsize=(10,6))
sns.barplot(x=penjualan_market.index, y=penjualan_market.values, hue=penjualan_market.index, palette='viridis')
plt.title('Total Penjualan Berdasarkan Market')
plt.xlabel('Produk')
plt.ylabel('Total Penjualan')
plt.xticks(rotation=45)
plt.show()



**Insight**

Dari visualisasi data di atas, dapat disimpulkan bahwa:

* Produk seperti Repair, Books, dan Supermarket mendominasi penjualan.

* Produk seperti Internet dan Hotel memiliki penjualan paling rendah.


**Kesimpulan:**

Strategi bisnis harus difokuskan pada penguatan industri dominan (Repair, Books, Supermarket) serta menghindari memasukki industri rendah minat(Internet, Hotel)


### Composition/Komposisi

**Aktivitas**: Menampilkan persentase kontribusi negara terhadap total penjualan

**Tujuan**: Mengetahui negara mana yang memiliki tempat pasar industri paling besar.

**Visualisasi**: Grafik lingkaran (Pie Chart).


```python
sales_by_category = df.groupby('Country')['Amount'].sum().sort_values(ascending=False)
sales_by_category_top3 = sales_by_category.head(6)

plt.figure(figsize=(10, 8))
sales_by_category_top3.plot(kind='pie', autopct='%1.1f%%', startangle=140, colors=plt.cm.Paired.colors)
plt.title('Top 6 Negara Teratas Berdasarkan Total Penjualan')
plt.ylabel('')
plt.axis('equal')
plt.show()



**Insight**

* **India** menyumbang total penjualan tertinggi, yaitu 18,6%, jadi pasar terbesar dari keenam negara.

* **USA** memiliki proporsi terendah (14,7%), relatif lebih kecil dibanding negara lain.

* **Australia, Canada, UK, dan UAE** berada di tengah, dengan proporsi antara 15-18%, menandakan kontribusi yang cukup merata.

**Kesimpulan:**

Strategi pemasaran bisa fokus pada India untuk pertumbuhan lebih lanjut, tapi juga memperkuat pasar USA untuk meningkatkan kontribusinya.



### Distribution/Distribusi

**Aktivitas**: Menganalisis penyebaran pengeluaran transaksi.

**Tujuan**: Melihat apakah mayoritas transaksi bernilai kecil atau besar, serta mendeteksi adanya kecondongan (skewness) dalam data penjualan.

**Visualisasi**: Histogram.


```python
plt.figure(figsize=(10, 6))
sns.histplot(df['Amount'], bins=20, kde=True)
plt.title('Total Pengeluaran')
plt.xlabel('Pengeluaran')
plt.ylabel('Jumlah Pengeluaran')
plt.show()



**Insight**

Dari data visualisasi di atas ditunjukkan, membawa kesimpulan bahwa:

* Sebagian besar transaksi memiliki nominal pengeluaran yang sangat rendah, berpusat di area mendekati angka 0, dengan frekuensi (jumlah transaksi) mencapai titik tertinggi di atas 3.000.

* Distribusi data menunjukkan kemiringan positif yang ekstrem (positive Skewness), di mana volume transaksi menurun drastis seiring bertambahnya nominal pengeluaran.

* **Mayoritas aktivitas ekonomi** dalam data ini didominasi oleh transaksi berskala kecil dengan volume yang sangat tinggi.

**Kesimpulan:**

Model bisnis saat ini sangat bergantung pada volume transaksi kecil yang tinggi, sehingga strategi yang tepat adalah fokus kepada barang produk yang memiliki nilai jual murah dan berkualitas sesuai dengan pengeluaran terjangkau pembeli.


### Relationship/Hubungan
**Aktivita**s: Menganalisis korelasi antara nilai pengeluaran (Amount) dengan nilai tukar (ExchangeRate).

**Tujuan**: Mengetahui apakah perubahan nilai tukar mempengaruhi besaran pengeluaran transaksi, serta mengukur kekuatan hubungan antar keduanya.

**Visualisasi**: Heatmap

```python
plt.figure(figsize=(8, 6))
sns.heatmap(data=df[['ExchangeRate', 'Amount']].corr(),
            annot=True,
            cmap='viridis',
            fmt='.2f')
plt.title('Korelasi antara Amount dan ExchangeRate')
plt.show()



**Insight**

Dari data visualisasi di atas ditunjukkan, membawa kesimpulan bahwa:

* **Korelasi Sangat Lemah**, angka korelasi antara ExchangeRate dan Amount hanya sebesar 0.02, yang menunjukkan hampir tidak ada hubungan antara keduanya.

* **Independensi Variabel**, pergerakan naik atau turunnya nilai tukar tidak diikuti oleh perubahan yang signifikan pada jumlah pengeluaran transaksi.

* Pengguna cenderung melakukan transaksi dengan nominal yang konsisten tanpa terlalu mempedulikan nilai tukar mata uang.

**Kesimpulan:**

Besaran pengeluaran transaksi bersifat independen terhadap nilai tukar, sehingga **nilai tukar mata uang yang tinggi maupun kecil**, tidak menjadi faktor yang terlalu berpengaruh bagi pengguna dalam menentukan nominal belanja mereka di platform ini.


## Menyimpan Dataset
```python
df.to_csv('[Finance_Ecommerce_Dirty_Dataset.csv', index=False)