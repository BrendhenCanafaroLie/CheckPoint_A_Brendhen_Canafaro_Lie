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
