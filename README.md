# README - Analisis Clustering dengan KMeans

## Deskripsi
Proyek ini bertujuan untuk melakukan analisis clustering menggunakan algoritma KMeans pada dataset yang telah diproses. Data telah melalui tahap preprocessing, normalisasi, dan transformasi sebelum diterapkan metode clustering. Hasil akhir dari analisis ini diekspor ke dalam format CSV untuk keperluan lebih lanjut.

## Tahapan Proses
1. **Data Preprocessing**  
   - Menangani nilai yang hilang (missing values)
   - Menghapus data duplikat
   - Normalisasi atau standarisasi fitur numerik
   - Encoding fitur kategorikal

2. **Clustering dengan KMeans**  
   - Menentukan jumlah cluster yang optimal
   - Menerapkan model KMeans
   - Menambahkan hasil cluster ke dalam dataset

3. **Inverse Transform Data**  
   - Mengembalikan data yang telah dinormalisasi ke skala aslinya
   - Melakukan inverse transform pada fitur kategorikal yang telah diencoding

4. **Analisis dan Interpretasi Hasil**  
   - Menganalisis karakteristik masing-masing cluster berdasarkan fitur yang tersedia
   - Menyajikan hasil dalam bentuk visualisasi, seperti boxplot dan distribusi cluster

5. **Mengekspor Hasil**  
   - Menyimpan hasil akhir clustering ke dalam file CSV

## Cara Menggunakan
1. Pastikan semua dependensi sudah terinstal:
   ```bash
   pip install pandas numpy scikit-learn seaborn matplotlib
   ```
2. Jalankan skrip Python yang telah disiapkan.
3. File hasil clustering akan disimpan dalam format CSV di direktori kerja.

## Output File
- **hasil_clustering.csv**: Berisi dataset yang sudah dikelompokkan berdasarkan hasil clustering.
- **visualisasi_cluster.png**: Gambar yang menunjukkan distribusi data dalam setiap cluster.

## Kontak
Jika ada pertanyaan, silakan hubungi Rahmat Hidayat, mahasiswa Statistika Universitas Terbuka semester 6.
