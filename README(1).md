# Clustering Model

## Pengantar
Dikarenakan belum memiliki strategi yang tepat untuk menawarkan jenis produk yang sesuai dengan segmen calon nasabah yang akan direkrut, maka proyek ini bertujuan untuk membuat model clustering guna mengelompokkan nasabah berdasarkan kepemilikan produk bank dan demografi. Tujuan utama dari clustering ini adalah untuk mengetahui segmen-segmen nasabah yang memiliki karakteristik serupa sehingga dapat digunakan untuk strategi pemasaran yang lebih efektif.

## Objective
Membuat Sebuah Model Clustering untuk mengetahui kepemilikan produk berdasarkan demografi nasabah yang saat ini sudah menggunakan layanan FundFusion dengan Silhouette Score >0.7

## Dataset
Dataset yang digunakan dalam proyek ini berisi informasi demografis dan finansial dari nasabah bank. Kolom-kolom utama dalam dataset meliputi:

1. **GCIF**: Unique Identifier Nasabah
2. **Area**: Lokasi Nasabah (Jakarta, Bogor, Bandung, Surabaya, Jogja, Solo)
3. **Jalur_Pembukaan**: Touch Points Nasabah membuka produk (Cabang, Telemarketing, Aplikasi Digital, Internet Banking)
4. **Vintage**: Durasi Menjadi Nasabah (Sejak membuka akun)
5. **Usia**: Usia Nasabah
6. **Jenis_Kelamin**: Laki-laki (1) & Perempuan (0)
7. **Status_Perkawinan**: Status perkawinan (Belum Menikah, Menikah, Cerai, Janda/Duda)
8. **Jumlah_Anak**: Jumlah Anak Nasabah (numerik)
9. **Pendidikan**: Status pendidikan terakhir (Tidak Memiliki Pendidikan Formal, SD, SMP, SMA, Sarjana, Magister, Doktor)
10. **Produk_Tabungan**: Status Kepemilikan Produk (Yes/1, No/0)
11. **Produk_Deposito**: Status Kepemilikan Produk (Yes/1, No/0)
12. **Produk_Kartu_Kredit**: Status Kepemilikan Produk (Yes/1, No/0)
13. **Produk_Kredit_Rumah**: Status Kepemilikan Produk (Yes/1, No/0)
14. **Produk_Kredit_Kendaraan**: Status Kepemilikan Produk (Yes/1, No/0)
15. **Produk_Kredit_Dana_Tunai**: Status Kepemilikan Produk (Yes/1, No/0)
16. **Total_Kepemilikan_Produk**: Jumlah Produk Yang Dimiliki (Penjumlahan dari Produk)
17. **Pendapatan_Tahunan**: Rata-rata Pendapatan Dalam Setahun
18. **Total_Relationship_Balance**: Total Asset Nasabah dalam Cutoff Bulan Observasi

## Proses Data
1. **Pengecekan Data Duplikat dan Missing Data**:
   - Memeriksa apakah ada nilai yang hilang dan duplikat dalam dataset.
   - Menghapus baris dengan nilai yang hilang dan duplikat.

2. **Pengecekan dan Penanganan Outlier**:
   - Menggunakan metode Z-Score untuk mendeteksi dan menghapus outlier dalam dataset.

3. **Pembagian Dataset untuk Eksperimen**:
   - Dataset dibagi menjadi tiga bagian berdasarkan variabel yang digunakan dalam eksperimen:
     - Eksperimen 0: Semua variabel digunakan.
     - Eksperimen 1: Variabel demografis.
     - Eksperimen 2: Variabel finansial.

4. **Encoding dan Standarisasi Data**:
   - Melakukan encoding pada variabel kategori.
   - Melakukan standarisasi pada variabel numerik.

## Modeling
Modeling dilakukan menggunakan dua algoritma clustering:
1. **K-Means**:
   - Mencoba berbagai jumlah cluster (k=3, 4, 5) dan menghitung Silhouette Score untuk setiap percobaan.
   - Hasil terbaik dengan k=3 yang memiliki Silhouette Score tertinggi.

2. **K-Medoids**:
   - Juga mencoba berbagai jumlah cluster (k=3, 4, 5) dan menghitung Silhouette Score untuk setiap percobaan.
   - Hasil terbaik dengan k=3 untuk sebagian besar eksperimen.

## Hasil Clustering
1. **Eksperimen 0** (Semua Variabel):
   - K-Means k=3: Silhouette Score = 0.4314
   - K-Medoids k=3: Silhouette Score = 0.4329

2. **Eksperimen 1** (Variabel Demografis):
   - K-Means k=3: Silhouette Score = 0.4999
   - K-Medoids k=3: Silhouette Score = 0.0049

3. **Eksperimen 2** (Variabel Finansial):
   - K-Means k=3: Silhouette Score = 0.1841
   - K-Medoids k=3: Silhouette Score = 0.1166

## Kesimpulan
- **K-Means k=3** memberikan hasil clustering terbaik dengan Silhouette Score tertinggi dalam berbagai eksperimen.
- Pelanggan dapat dikelompokkan menjadi tiga cluster dengan karakteristik yang berbeda:
  - Cluster 1: Pelanggan muda dengan total kepemilikan produk yang rendah.
  - Cluster 2: Pelanggan dengan variasi usia dan total kepemilikan produk yang luas.
  - Cluster 3: Pelanggan tua dengan total kepemilikan produk yang tinggi.

## Visualisasi
Visualisasi dilakukan untuk memahami distribusi pelanggan dalam setiap cluster:
- **Scatter Plot**: Menunjukkan hubungan antara usia dan total kepemilikan produk dalam setiap cluster.

## Rekomendasi
- **Edukasi dan Peningkatan Pemahaman**: Untuk pelanggan muda dengan kepemilikan produk rendah, bank dapat mengadakan program edukasi finansial.
- **Penawaran Produk yang Disesuaikan**: Untuk pelanggan dengan variasi kebutuhan yang luas, bank dapat menawarkan produk yang lebih disesuaikan.
- **Program Loyalitas dan Layanan Premium**: Untuk pelanggan setia dengan hubungan yang kuat, bank dapat memperkenalkan program loyalitas dan layanan premium.


Semoga ini membantu! Jika ada pertanyaan lebih lanjut atau bantuan tambahan, jangan ragu untuk menghubungi saya! 😊