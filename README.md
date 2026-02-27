
# CheckPoint 1 — Data Gathering & Business Understanding
**Brendhen Canafaro | A_Brendhen_Canafaro_Lie_033**

---

## 📁 Import Library

```python
import pandas as pd
```

---

## 📂 Memuat Dataset

```python
file = "/content/drive/MyDrive/Tugas-Tugas Praktikum/Tugas AVD/CheckPoint 1: Data Gathering & Business Understanding/Finance_Ecommerce_Dirty_Dataset_csv.csv"

df = pd.read_csv(file)
df.head()
```

---

## 🧠 Business Understanding

### Business Objective

Dataset ini merupakan data-data transaksi keuangan pada platform e-commerce. Dataset ini memiliki 6060 baris x 23 kolom.

Pada dasarnya setiap kebutuhan berbisnis didalam dunia digital diperlukan adanya sebuah analisis terhadap kebutuhan pasar, akan hal tersebut kita perlu melihat dimana dan apa kategori pasar yang cocok untuk terjun kedalam industri tersebut, agar dapat hasil terbaik saat menjalankan bisnis e-commerce.

Dataset ini akan digunakan yaitu, sebagai berikut:
1. Menganalisis tren transaksi dari waktu ke waktu
2. Mengidentifikasi kategori dan subkategori pilihan pasar
3. Menganalisis transaksi berdasarkan lokasi pelanggan

---

### Assess Situation

Platform e-commerce setiap harinya melakukan ribuan transaksi, yang dimana setiap data transaksi menyimpan informasi penting bagi pengambilan keputusan.

Dengan analisis data-data transaksi, perusahaan-perusahaan dapat memahami pola belanja pelanggan, dan akan hal tersebut sangat membantu bisnis memahami kondisi keuangan dan pola pasar konsumen. Berikut merupakan ciri-ciri dari dataset:

**1. Sumber Data**
Dataset Finance_Ecommerce_Dirty_Dataset dari Kaggle.

**2. Kondisi Data**
- 6061 baris
- 23 kolom
- Terdapat data kotor dan nilai kosong

**3. Kendala**
- Data-data ada yang kosong

---

### Analytic Goals & Project Plan

**Tujuan:**
1. Analisis tren transaksi dari waktu ke waktu
2. Analisis kategori dan subkategori pilihan pasar
3. Analisis transaksi berdasarkan lokasi pelanggan

**Rencana Proyek:**
1. Memahami Data
2. Mengelola dan membersihkan data
3. Visualisasi data
4. Menyusun rapi hasil data
5. Membuat ringkasan dan kesimpulan

---

## 🔍 Data Understanding

**Data Understanding** adalah sebuah tahap kedua setelah business understanding. Setelah terbuatnya konsep dasar dari tujuan penggunaan data dan apa hasil yang ingin dicapai, data perlu di **pahami, analisa, diperbaiki, dan dibersihkan** sehingga menjadi data yang dapat digunakan sebagai visualisasi, sesuai keperluan pengguna.

### Memuat Dataset

Dataset yang digunakan adalah file csv yang berjudul **"Finance Ecommerce Dirty Dataset"**, dataset ini berisi data transaksi keuangan dari sebuah platform e-commerce.

Dataset ini mencatat **detail transaksi, perilaku belanja pelanggan, tren transaksi, dan indikasi penipuan.** Informasi utama meliputi **transaksi, nilai uang, saldo, mata uang, serta jenis transaksi.** Dataset juga memuat **data merchant dan data pelanggan**, sehingga analisis pola belanja dan lokasi dapat dilakukan.

Dataset ini memiliki data-data yang cukup besar yaitu, **6060 baris dan 23 kolom.**

```python
file = "/content/drive/MyDrive/Tugas-Tugas Praktikum/Tugas AVD/CheckPoint 1: Data Gathering & Business Understanding/Finance_Ecommerce_Dirty_Dataset_csv.csv"

df = pd.read_csv(file)
df
```

---

## 📊 Deskripsi Data

Dari sebuah dataset terdapat sebuah informasi yang bisa dicari, dengan bagaimana hal tersebut dapat menjelaskan tentang isi dan ciri suatu dataset itu sendiri. Isi dari sebuah informasi deskripsi data dapat mencakup sumber data, jumlah data, jenis variabel, dan lainnya.

### Informasi Dasar

Informasi dasar dari sebuah dataset yang bisa berupa **data type, jumlah baris kolom, data kosong, dan lainnya**. Berdasarkan data yang dibawah ini, dapat diketahui dari dataset ini adalah dataset ini memiliki **6060 baris dan 23 kolom.**

```python
df.info()
```

---

### Informasi Lanjutan

```python
dd.info()
```

| No | Kolom | Jumlah Baris | Tipe Data | Deskripsi |
|----|-------|-------------|-----------|-----------|
| 1 | TransactionID | 6057 | object | Kode unik untuk tiap transaksi |
| 2 | Date | 6060 | object | Tanggal transaksi dilakukan |
| 3 | AccountID | 6059 | object | ID unik pemilik akun |
| 4 | AccountName | 6059 | object | Nama pemilik akun |
| 5 | TransactionType | 6058 | object | Jenis transaksi, seperti debit atau kredit |
| 6 | Amount | 6059 | object | Nilai uang pada transaksi |
| 7 | Currency | 6055 | object | Mata uang yang digunakan |
| 8 | ExchangeRate | 6058 | float64 | Nilai tukar mata uang ke mata uang utama |
| 9 | Balance | 5988 | object | Saldo akun setelah transaksi |
| 10 | Merchant | 6058 | object | Nama tempat atau pihak transaksi |
| 11 | MerchantPhone | 4647 | float64 | Nomor telepon merchant |
| 12 | MerchantEmail | 4222 | object | Alamat email merchant |
| 13 | Category | 6058 | object | Kategori utama transaksi |
| 14 | Subcategory | 6055 | object | Rincian kategori transaksi |
| 15 | Country | 6058 | object | Negara tempat transaksi terjadi |
| 16 | City | 6058 | object | Kota tempat transaksi terjadi |
| 17 | PostalCode | 5742 | float64 | Kode pos lokasi transaksi |
| 18 | CardNumber | 5621 | object | Nomor kartu yang digunakan |
| 19 | Email | 5801 | object | Email pemilik akun |
| 20 | Phone | 5732 | float64 | Nomor telepon pemilik akun |
| 21 | IsFraud | 5984 | object | Penanda apakah transaksi penipuan atau bukan |
| 22 | Notes | 5256 | object | Catatan tambahan transaksi |
| 23 | CustomerSince | 6058 | object | Tanggal mulai menjadi nasabah |

---

### Informasi Statistik Deskriptif

```python
df.describe(include='all')
```

**1. Count (Kelengkapan Data)**

Berdasarkan data, total baris transaksi adalah 6060. Maka dapat disimpulkan:

| Kategori | Kolom | Jumlah Data Hilang |
|----------|-------|--------------------|
| 🔴 Tinggi | MerchantEmail | 1838 data hilang |
| 🔴 Tinggi | MerchantPhone | 1413 data hilang |
| 🟡 Sedang | CardNumber | 439 data hilang |
| 🟡 Sedang | Phone | 328 data hilang |
| 🟡 Sedang | PostalCode | 318 data hilang |
| 🟡 Sedang | Email | 259 data hilang |
| 🟡 Sedang | Balance | 72 data hilang |
| 🟢 Rendah | TransactionID | 3 data hilang |
| 🟢 Rendah | Currency | 5 data hilang |
| 🟢 Rendah | Subcategory | 5 data hilang |
| 🟢 Rendah | ExchangeRate | 2 data hilang |
| 🟢 Rendah | Merchant | 2 data hilang |
| 🟢 Rendah | Category | 2 data hilang |
| 🟢 Rendah | Country | 2 data hilang |
| 🟢 Rendah | City | 2 data hilang |
| 🟢 Rendah | AccountID | 1 data hilang |
| 🟢 Rendah | AccountName | 1 data hilang |
| 🟢 Rendah | TransactionType | 1 data hilang |
| 🟢 Rendah | Amount | 1 data hilang |

> **Kesimpulan:** Berdasarkan hasil pengecekan, sebagian besar kolom masih memiliki data yang cukup lengkap. Missing values paling banyak terdapat pada kolom **MerchantPhone** dan **MerchantEmail**, dan juga terdapat kolom-kolom yang memiliki missing values yang cukup besar pada dataset, yaitu **CardNumber, PostalCode, Phone, Email, dan Balance.** Kolom lain seperti **TransactionID, AccountID, Amount, TransactionType, dan lain-lainnya,** hanya kehilangan sedikit data dan masih dapat ditangani dengan mudah. Secara keseluruhan, dataset masih layak digunakan untuk analisis, namun diperlukan proses pembersihan data pada beberapa kolom sebelum visualisasi dan pemodelan dilakukan.

---

**2. Mean vs Median (Distribusi Data)**

Perbandingan mean dan median digunakan untuk melihat sebaran data. Dari dataset hanya terdapat satu kolom angka yang bisa kita analisa, yaitu kolom data **ExchangeRate**. Sedangkan kolom lainnya seperti **PostalCode, MerchantPhone dan Phone,** tidak dapat dianalisa dikarenakan tidak memiliki makna statistik yang kuat.

Data kolom numerik seperti **Balance dan Amount** tidak dapat dianalisa dikarenakan hasil program describe menghasilkan di kolom balance dan amount adalah **NaN**.

| Kolom | Mean | Median | Kesimpulan |
|-------|------|--------|------------|
| ExchangeRate | 46,32 | 72,09 | Left-skewed (condong ke kiri) |

> **Kesimpulan:** Distribusi ExchangeRate menunjukkan kecenderungan **left-skewed** (Condong ke kiri). Analisis mean dan median ini tidak dapat menggambarkan sifat keseluruhan data, karena nilai ExchangeRate tidak mempengaruhi variabel utama lainnya.

---

**3. Min dan Max (Validasi Logika)**

**Min dan max** adalah nilai paling kecil dan nilai paling besar dalam suatu data, keduanya dipakai untuk mengecek kewajaran nilai. Sama seperti sebelumnya terdapat kolom data numerik yang seharusnya bisa dianalisa seperti **Balance dan Amount,** tetapi hasil kolom yang dikeluarkan adalah **NaN**.

| Kolom | Min | Max |
|-------|-----|-----|
| ExchangeRate | 1,00 | 109,97 |

> **Kesimpulan:** Nilai **ExchangeRate** menunjukkan nilai minimum transaksi dengan mata uang bernilai setara, sedangkan nilai maksimum menunjukkan adanya transaksi dengan mata uang bernilai tinggi.

---

**4. Standar Deviasi (std) — Variabilitas Data**

Standar deviasi digunakan untuk melihat seberapa jauh data menyebar dari rata-ratanya. Sama seperti sebelumnya pada kolom data numerik **Amount dan Balance** tidak dapat dianalisa karena isi kolom adalah **NaN**.

| Kolom | Mean | Std |
|-------|------|-----|
| ExchangeRate | 46,32 | 40,25 |

> **Kesimpulan:** Pada kolom **ExchangeRate,** nilai standar deviasi yang cukup besar. Hal ini menandakan perbedaan nilai tukar mata uang yang signifikan antar transaksi.

---

## ✅ Verifikasi Kualitas Data

**Verifikasi kualitas data** adalah proses untuk memastikan data layak dianalisis. Proses ini mengecek apakah data sudah lengkap, akurat, dan konsisten. Verifikasi dilakukan dengan **melihat data hilang, tipe data, dan nilai aneh**. Contohnya nilai terlalu besar, terlalu kecil, atau tidak masuk akal. **Tujuannya** agar hasil analisis tidak menyesatkan. Data yang baik menghasilkan kesimpulan yang lebih tepat.

---

### Data Type Check

Disini kita akan melakukan pengecekan tipe data pada setiap kolom, Tujuannya agar analisis dan visual yang dibuat lebih akurat dan tidak menyesatkan.

Dilihat dibawah ini, terdapat beberapa kesalahan tipe data yang diberikan, yaitu sebagai berikut:

| No | Kolom | Tipe Data Saat Ini | Seharusnya | Alasan |
|----|-------|-------------------|------------|--------|
| 1 | Date | object | date | Isi kolom adalah tanggal |
| 2 | Amount | object | float | Bisa berupa angka desimal |
| 3 | Balance | object | float | Bisa berupa angka desimal |
| 4 | IsFraud | object | boolean | Isi kolom adalah Yes/No seperti True/False |
| 5 | CustomerSince | object | date | Isi kolom adalah tanggal |

```python
df.dtypes
```

---

### Inconsistent Value

Pada tahap **inconsistent value** ini, dilakukan pengecekan konsistensi data, terutama pada cara penulisan. Tujuannya agar data yang sebenarnya sama, tidak terbaca sebagai data berbeda akibat perbedaan penulisan.

**1. AccountName**

Dapat dilihat, bahwa pengecekan kolom AccountName memperlihatkan **perbedaan penulisan, seperti huruf besar kecil dan salah ketik.**

Contoh: `Raj Gupta` dan `raj GUPTA` — nama yang sama dengan format berbeda.

```python
print(df['AccountName'].unique())
```

**2. TransactionType**

Dapat dilihat, bahwa pengecekan kolom TransactionType memperlihatkan perbedaan penulisan, seperti **format huruf besar dan kecil.**

Contoh: `Credit` dan `CREDIT` — jenis transaksi yang sama dengan format berbeda.

```python
print(df['TransactionType'].unique())
```

**3. Currency**

Dapat dilihat, bahwa pengecekan kolom Currency memperlihatkan perbedaan penulisan, seperti **format huruf besar dan kecil.**

Contoh: `usd` dan `USD` — mata uang yang sama dengan format berbeda.

```python
print(df['Currency'].unique())
```

**4. IsFraud**

Dapat dilihat, bahwa pengecekan kolom IsFraud memperlihatkan perbedaan penulisan, seperti **kesalahan pengetikan.**

Contoh: `yes` dan `Yess` — makna yang sama dengan format berbeda.

```python
print(df['IsFraud'].unique())
```

**5. Notes**

Dapat dilihat, bahwa pengecekan kolom Notes memperlihatkan perbedaan penulisan, seperti **dalam format penulisan.**

Contoh: `repeat purchase` dan `suspected fraud -- verify\ncontact support`.

```python
print(df['Notes'].unique())
```

**6. CustomerSince**

Dapat dilihat, bahwa pengecekan kolom CustomerSince memperlihatkan perbedaan penulisan, seperti **dalam format penulisan tanggal.**

Contoh: `16/09/2018` dan `Aug-21` — format tanggal yang berbeda.

```python
print(df['CustomerSince'].unique())
```

---

### Missing Value

Pada tahap ini, kita akan melihat seberapa banyak data yang hilang pada seluruh kolom. Perhitungan **dibawah 1 persen** akan tidak terhitung dan dianggap tidak perlu ditangani atau dihapus.

| Kolom | Missing Value (%) | Tindakan |
|-------|------------------|----------|
| MerchantEmail | 30,33% | Perlu ditangani atau dihapus |
| MerchantPhone | 23,32% | Perlu ditangani atau dihapus |
| Notes | 13,26% | Perlu ditangani atau dihapus |
| CardNumber | 7,24% | Dapat diabaikan atau ditangani |
| Phone | 5,41% | Dapat diabaikan atau ditangani |
| PostalCode | 5,24% | Dapat diabaikan atau ditangani |
| Email | 4,27% | Dapat diabaikan atau ditangani |
| IsFraud | 1,25% | Dapat diabaikan atau dilakukan pengisian data |
| Balance | 1,18% | Dapat diabaikan atau dilakukan pengisian data |
| Date, AccountID, AccountName, TransactionType, Amount, Currency, ExchangeRate, Merchant, Category, Subcategory, Country, City, CustomerSince | < 1% | Dapat diabaikan / tidak signifikan |

```python
pd.DataFrame(df.isna().sum() / len(df) * 100, columns=['Null Ratio in %'])
```

---

### Duplicated Value

Sekarang, kita akan memeriksa adanya data duplikat agar dataset tetap bersih dan hasil analisis lebih akurat.

```python
df[df.duplicated()]
```

Terlihat terdapat **satu baris duplikat** yang terdapat dalam dataset tersebut, maka itu kita akan menjalankan program `df.drop_duplicates()` untuk menghapus baris duplikat tersebut:

```python
df = df.drop_duplicates()
```

Terlihat bahwa dataset yang digunakan telah bersih dari duplikat.

---

### Outliers Values

Pada tahap ini, kita akan meninjau nilai ekstrem (outliers) pada kolom numerik dan kolom penting lain, seperti **MerchantPhone dan Phone**. Tujuannya agar mendapatkan insight yang lebih akurat dan mendukung analisis serta model yang akan dibuat.

Tidak semua kolom harus ditangani; penting untuk memahami fungsi dan tujuan masing-masing kolom dalam dataset.

Dari hasil pengecekan, terlihat:

| Kolom | Persentase Outlier |
|-------|-------------------|
| MerchantPhone | 2,1% |
| Phone | 2,5% |

```python
results = []

cols = df.select_dtypes(include=['float64', 'int64'])

for col in cols:
    q1 = df[col].quantile(0.25)
    q3 = df[col].quantile(0.75)
    iqr = q3 - q1
    lower_bound = q1 - 1.5 * iqr
    upper_bound = q3 + 1.5 * iqr
    outliers = df[(df[col] < lower_bound) | (df[col] > upper_bound)]
    percent_outliers = (len(outliers) / len(df)) * 100
    results.append({'Kolom': col, 'Persentase Outliers': percent_outliers})

results_df = pd.DataFrame(results)
results_df.set_index('Kolom', inplace=True)
results_df = results_df.rename_axis(None, axis=0).rename_axis('Kolom', axis=1)

display(results_df)
```

```python
plt.figure(figsize=(8, 6))
sns.boxplot(y=df['MerchantPhone'])
plt.title('Boxplot of MerchantPhone')
plt.ylabel('MerchantPhone')
plt.show()
```

```python
plt.figure(figsize=(8, 6))
sns.boxplot(y=df['Phone'])
plt.title('Boxplot of Phone')
plt.ylabel('Phone')
plt.show()
```

---

## 📈 Eksplorasi Data (EDA)

**Exploratory Data Analysis (EDA)** adalah tahap awal dalam analisis data yang bertujuan untuk memahami struktur, pola, dan hubungan dalam dataset sebelum melakukan pemodelan lebih lanjut.

---

### 1. Comparison / Perbandingan

- **Aktivitas:** Membandingkan kategori industri pasar dan produk barang.
- **Tujuan:** Mengidentifikasi industri pasar yang paling memiliki transaksi paling banyak dan juga menemukan jenis produk barang apa yang paling diminati.
- **Visualisasi:** Bar Chart (Grafik Batang).

```python
df = df.copy()
df['Amount'] = pd.to_numeric(df['Amount'], errors='coerce')

penjualan_market = df.groupby('Category')['Amount'].sum().sort_values(ascending=False)

plt.figure(figsize=(10, 6))
sns.barplot(x=penjualan_market.index, y=penjualan_market.values, hue=penjualan_market.index, palette='viridis')
plt.title('Industri Pasar Berdasarkan Total Penjualan')
plt.xlabel('Industri Pasar')
plt.ylabel('Total Penjualan')
plt.xticks(rotation=45)
plt.show()
```

> **Insight:**
> - Industri **Automotive** punya total penjualan tertinggi, diikuti Education dan Entertainment.
> - Industri **Health** memiliki penjualan paling rendah.
> - Sebagian besar transaksi terjadi di sektor **otomotif, pendidikan, dan hiburan.**
>
> **Kesimpulan:** Strategi bisnis harus difokuskan pada penguatan penetrasi di sektor dominan seperti **Automotive, Education, dan Entertainment.**

```python
penjualan_market = df.groupby('Subcategory')['Amount'].sum().sort_values(ascending=False)

plt.figure(figsize=(10, 6))
sns.barplot(x=penjualan_market.index, y=penjualan_market.values, hue=penjualan_market.index, palette='viridis')
plt.title('Total Penjualan Berdasarkan Market')
plt.xlabel('Produk')
plt.ylabel('Total Penjualan')
plt.xticks(rotation=45)
plt.show()
```

> **Insight:**
> - Produk seperti Repair, Books, dan Supermarket mendominasi penjualan.
> - Produk seperti Internet dan Hotel memiliki penjualan paling rendah.
>
> **Kesimpulan:** Strategi bisnis harus difokuskan pada penguatan industri dominan (Repair, Books, Supermarket) serta menghindari memasuki industri rendah minat (Internet, Hotel).

---

### 2. Composition / Komposisi

- **Aktivitas:** Menampilkan persentase kontribusi negara terhadap total penjualan.
- **Tujuan:** Mengetahui negara mana yang memiliki tempat pasar industri paling besar.
- **Visualisasi:** Grafik Lingkaran (Pie Chart).

```python
sales_by_category = df.groupby('Country')['Amount'].sum().sort_values(ascending=False)
sales_by_category_top3 = sales_by_category.head(6)

plt.figure(figsize=(10, 8))
sales_by_category_top3.plot(kind='pie', autopct='%1.1f%%', startangle=140, colors=plt.cm.Paired.colors)
plt.title('Top 6 Negara Teratas Berdasarkan Total Penjualan')
plt.ylabel('')
plt.axis('equal')
plt.show()
```

> **Insight:**
> - **India** menyumbang total penjualan tertinggi, yaitu 18,6%, jadi pasar terbesar dari keenam negara.
> - **USA** memiliki proporsi terendah (14,7%), relatif lebih kecil dibanding negara lain.
> - **Australia, Canada, UK, dan UAE** berada di tengah, dengan proporsi antara 15–18%, menandakan kontribusi yang cukup merata.
>
> **Kesimpulan:** Strategi pemasaran bisa fokus pada India untuk pertumbuhan lebih lanjut, tapi juga memperkuat pasar USA untuk meningkatkan kontribusinya.

---

### 3. Distribution / Distribusi

- **Aktivitas:** Menganalisis penyebaran pengeluaran transaksi.
- **Tujuan:** Melihat apakah mayoritas transaksi bernilai kecil atau besar, serta mendeteksi adanya kecondongan (skewness) dalam data penjualan.
- **Visualisasi:** Histogram.

```python
plt.figure(figsize=(10, 6))
sns.histplot(df['Amount'], bins=20, kde=True)
plt.title('Total Pengeluaran')
plt.xlabel('Pengeluaran')
plt.ylabel('Jumlah Pengeluaran')
plt.show()
```

> **Insight:**
> - Sebagian besar transaksi memiliki nominal pengeluaran yang sangat rendah, berpusat di area mendekati angka 0, dengan frekuensi (jumlah transaksi) mencapai titik tertinggi di atas 3.000.
> - Distribusi data menunjukkan kemiringan positif yang ekstrem (positive Skewness), di mana volume transaksi menurun drastis seiring bertambahnya nominal pengeluaran.
> - **Mayoritas aktivitas ekonomi** dalam data ini didominasi oleh transaksi berskala kecil dengan volume yang sangat tinggi.
>
> **Kesimpulan:** Model bisnis saat ini sangat bergantung pada volume transaksi kecil yang tinggi, sehingga strategi yang tepat adalah fokus kepada barang produk yang memiliki nilai jual murah dan berkualitas sesuai dengan pengeluaran terjangkau pembeli.

---

### 4. Relationship / Hubungan

- **Aktivitas:** Menganalisis korelasi antara nilai pengeluaran (Amount) dengan nilai tukar (ExchangeRate).
- **Tujuan:** Mengetahui apakah perubahan nilai tukar mempengaruhi besaran pengeluaran transaksi, serta mengukur kekuatan hubungan antar keduanya.
- **Visualisasi:** Heatmap.

```python
plt.figure(figsize=(8, 6))
sns.heatmap(data=df[['ExchangeRate', 'Amount']].corr(),
            annot=True,
            cmap='viridis',
            fmt='.2f')
plt.title('Korelasi antara Amount dan ExchangeRate')
plt.show()
```

> **Insight:**
> - **Korelasi Sangat Lemah** — angka korelasi antara ExchangeRate dan Amount hanya sebesar 0.02, yang menunjukkan hampir tidak ada hubungan antara keduanya.
> - **Independensi Variabel** — pergerakan naik atau turunnya nilai tukar tidak diikuti oleh perubahan yang signifikan pada jumlah pengeluaran transaksi.
> - Pengguna cenderung melakukan transaksi dengan nominal yang konsisten tanpa terlalu mempedulikan nilai tukar mata uang.
>
> **Kesimpulan:** Besaran pengeluaran transaksi bersifat independen terhadap nilai tukar, sehingga **nilai tukar mata uang yang tinggi maupun kecil**, tidak menjadi faktor yang terlalu berpengaruh bagi pengguna dalam menentukan nominal belanja mereka di platform ini.

---

## 💾 Menyimpan Dataset

```python
df.to_csv('Finance_Ecommerce_Dirty_Dataset.csv', index=False)


---

```
# CheckPoint 3 — Data Preparation
**Brendhen Canafaro | A_Brendhen_Canafaro_Lie_033**

---

## 📁 Import Library

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import plotly.express as px
import numpy as np
from sklearn.impute import KNNImputer
```

---

## 📂 Memuat Dataset

```python
file = "/content/drive/MyDrive/Tugas-Tugas Praktikum/Tugas AVD/CheckPoint 2:  Data Understanding/Finance_Ecommerce_Dirty_Dataset_csv.csv"

df = pd.read_csv(file)
df
```

---

## 🧹 Data Preparation

**Data Preparation** adalah tahap pembersihan dan transformasi data agar siap digunakan untuk analisis. Tahap ini mencakup perbaikan tipe data, penanganan nilai tidak konsisten, penanganan missing values, duplikasi, outliers, konstruksi fitur baru, dan reduksi data.

---

## 🔧 Perbaikan Tipe Data

Beberapa kolom memiliki tipe data yang tidak sesuai dengan isinya. Berikut kolom-kolom yang diperbaiki:

| No | Kolom | Tipe Data Saat Ini | Seharusnya | Alasan |
|----|-------|-------------------|------------|--------|
| 1 | Date | object | datetime64[ns] | Isi kolom adalah tanggal |
| 2 | Amount | object | Float64 | Bisa berupa angka desimal |
| 3 | Balance | object | Float64 | Bisa berupa angka desimal |
| 4 | IsFraud | object | bool | Isi kolom adalah Yes/No seperti True/False |
| 5 | CustomerSince | object | datetime64[ns] | Isi kolom adalah tanggal |

**1. Kolom Date**

```python
df['Date'] = pd.to_datetime(df['Date'], errors='coerce')
```

**2. Kolom Amount**

Tahap ke-1, ubah ke numerik terlebih dahulu:

```python
df['Amount'] = pd.to_numeric(df['Amount'], errors='coerce')
```

Tahap ke-2, ubah ke tipe data Float64:

```python
df['Amount'] = df['Amount'].astype('Float64')
```

**3. Kolom Balance**

Tahap ke-1, ubah ke numerik terlebih dahulu:

```python
df['Balance'] = pd.to_numeric(df['Balance'], errors='coerce')
```

Tahap ke-2, ubah ke tipe data Float64:

```python
df['Balance'] = df['Balance'].astype('Float64')
```

**4. Kolom IsFraud**

```python
df['IsFraud'] = df['IsFraud'].astype(bool)
```

**5. Kolom CustomerSince**

```python
df['CustomerSince'] = pd.to_datetime(df['CustomerSince'], errors='coerce')
```

---

## ⚠️ Inconsistent Values

Pada tahap ini kita menangani ketidakkonsistenan data pada kolom-kolom berikut: AccountName, TransactionType, Currency, Notes, dan CustomerSince.

**1. Kolom AccountName**

Terdapat perbedaan penulisan huruf besar kecil dan salah ketik. Diseragamkan menjadi huruf kapital semua.

```python
df['AccountName'] = df['AccountName'].str.upper()
print(df['AccountName'].unique())
```

**2. Kolom TransactionType**

Terdapat perbedaan format huruf besar dan kecil. Diseragamkan ke format Title Case.

```python
df['TransactionType'] = df['TransactionType'].str.strip().str.title()
print(df['TransactionType'].unique())
```

**3. Kolom Currency**

Terdapat perbedaan format huruf besar dan kecil. Diseragamkan ke huruf kapital semua.

```python
df['Currency'] = df['Currency'].str.strip().str.upper()
print(df['Currency'].unique())
```

**4. Kolom IsFraud**

Terdapat perbedaan penulisan YES/NO. Dipetakan ke nilai yang seragam.

```python
df['IsFraud'] = df['IsFraud'].replace({
    'YES': 'True',
    'NO': 'False'
})

for col in ['IsFraud']:
    print(df[col].unique())
```

**5. Kolom Notes**

Terdapat perbedaan format penulisan dan teks tambahan `-- VERIFY\nCONTACT SUPPORT`. Dibersihkan dan diseragamkan ke huruf kapital.

```python
df['Notes'] = df['Notes'].str.upper()
df['Notes'] = df['Notes'].str.replace(r'\s*--  VERIFY.*', '', regex=True)

for col in ['Notes']:
    print(df[col].unique())
```

**6. Kolom CustomerSince**

Terdapat berbagai format tanggal yang tidak seragam (misal: `16/09/2018`, `Aug-21`, `2024`). Karena setiap data dipastikan memiliki tahun, maka hanya tahunnya saja yang diambil.

```python
import re

def extract_year(val):
    if pd.isna(val):
        return np.nan
    val = str(val).strip()

    match = re.match(r'^[A-Za-z]{3}-(\d{2})$', val)
    if match:
        yr = int(match.group(1))
        return 2000 + yr

    match = re.match(r'^(20\d{2})$', val)
    if match:
        return int(match.group(1))

    match = re.search(r'(20\d{2})', val)
    if match:
        return int(match.group(1))

    return np.nan

df["CustomerSince"] = df["CustomerSince"].apply(extract_year)
```

**7. Kolom Amount**

Terdapat nilai negatif yang merupakan kesalahan input. Semua nilai diubah menjadi positif.

```python
df['Amount'] = df['Amount'].abs()
```

---

## 🕳️ Missing Values

Pada tahap ini kita menangani data yang hilang. Kolom non-numerik dengan missing value tinggi akan diabaikan atau dihapus, sedangkan kolom numerik ditangani dengan imputasi.

```python
print((df.isna().sum() / len(df)) * 100)
```

| Kolom | Missing Value (%) |
|-------|------------------|
| CustomerSince | 66.40% |
| MerchantEmail | 30.33% |
| MerchantPhone | 23.32% |
| Balance | 20.38% |
| Amount | 20.18% |
| Notes | 13.27% |
| CardNumber | 7.24% |
| Phone | 5.41% |
| PostalCode | 5.25% |
| Email | 4.27% |

**1. Amount (20.1%)**

Diimputasi menggunakan **median** karena distribusi data bersifat *right-skewed* dengan outlier yang signifikan, sehingga mean tidak dapat mewakili data dengan baik.

```python
plt.figure(figsize=(10, 6))
sns.histplot(df['Amount'], bins=20, kde=True)
plt.title('Total Transaksi')
plt.xlabel('Transaksi')
plt.ylabel('Jumlah Transaksi')
plt.show()
```

```python
df['Amount'] = df['Amount'].fillna(df['Amount'].median())
```

**2. Balance (20.4%)**

Diimputasi menggunakan **KNN Imputer** karena saldo memiliki hubungan dengan kolom numerik lainnya.

```python
imputer = KNNImputer(n_neighbors=5)
df[['Balance']] = imputer.fit_transform(df[['Balance']])
```

---

## 🔁 Duplicated Values

Menangani baris yang mengalami duplikasi dengan menghapusnya.

```python
df = df.drop_duplicates()
```

---

## 📈 Outliers Values

Deteksi outlier menggunakan metode **IQR (Interquartile Range)** pada kolom numerik.

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

results_df = pd.DataFrame(results)
results_df.set_index('Kolom', inplace=True)
results_df = results_df.rename_axis(None, axis=0).rename_axis('Kolom', axis=1)

display(results_df)
```

| Kolom | Persentase Outlier |
|-------|-------------------|
| Amount | 11.44% |
| MerchantPhone | 2.13% |
| Phone | 2.51% |
| ExchangeRate | 0.00% |
| Balance | 0.00% |
| PostalCode | 0.00% |
| CustomerSince | 0.00% |

---

## 🏗️ Construct Data

Tahap Construct Data adalah proses membuat kolom baru dari data yang sudah ada untuk memperkaya analisis.

**1. Membuat Kolom Baru `Amount_IDR`**

Dataset memiliki transaksi dari berbagai mata uang (USD, GBP, AED, INR). Kolom ExchangeRate berfungsi sebagai kurs konversi ke INR, lalu dikonversi ke IDR dengan kurs statis 1 INR ≈ Rp190.

- Langkah 1: `Amount × ExchangeRate` → menyamakan ke INR
- Langkah 2: `Amount_INR × 190` → konversi ke IDR

```python
INR_TO_IDR = 190
df['Amount_INR'] = df['Amount'] * df['ExchangeRate']
df['Amount_IDR'] = df['Amount_INR'] * INR_TO_IDR

df = df.drop('Amount_INR', axis=1)
```

**2. Membuat Kolom Baru `BalanceCategory`**

Mengubah nilai numerik Balance menjadi label kategorik agar lebih mudah dianalisis.

- `Positive` → Balance > 0
- `Zero` → Balance = 0
- `Negative` → Balance < 0
- `Unknown` → Balance = NaN

```python
def balance_category(bal):
    if pd.isna(bal):
        return 'Unknown'
    elif bal > 0:
        return 'Positive'
    elif bal == 0:
        return 'Zero'
    else:
        return 'Negative'

df['BalanceCategory'] = df['Balance'].apply(balance_category)
```

Mengecek kolom baru yang sudah tersedia:

```python
print(df.columns)
```

---

## ✂️ Data Reduction

Tahap Data Reduction bertujuan menyederhanakan dataset tanpa menghilangkan informasi penting. Terdapat 9 kolom yang dihapus:

| Kolom | Alasan Penghapusan |
|-------|-------------------|
| `TransactionID` | Tidak merepresentasikan pola atau perilaku transaksi |
| `AccountID` | Tidak digunakan untuk join antar tabel |
| `AccountName` | Identitas pribadi, tidak relevan untuk analisis pola |
| `MerchantPhone` | Tidak memiliki hubungan logis dengan pola transaksi |
| `MerchantEmail` | Hanya mengidentifikasi entitas, bukan perilaku |
| `PostalCode` | Sudah diwakili oleh kolom Country dan City |
| `CardNumber` | Tidak mengandung pola analitik yang berguna |
| `Email` | Hanya pengidentifikasi, tidak bisa digunakan untuk analisis |
| `Phone` | Tidak relevan untuk analisis e-commerce dan keuangan |

```python
df = df.drop('TransactionID', axis=1)
df = df.drop('AccountID', axis=1)
df = df.drop('AccountName', axis=1)
df = df.drop('MerchantPhone', axis=1)
df = df.drop('MerchantEmail', axis=1)
df = df.drop('PostalCode', axis=1)
df = df.drop('CardNumber', axis=1)
df = df.drop('Email', axis=1)
df = df.drop('Phone', axis=1)
```

---

## 💾 Menyimpan Dataset Bersih

```python
df.to_csv('Finance_Ecommerce_Dirty_Dataset.csv', index=False)
```
```

