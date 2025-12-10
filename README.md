Laporan Analisis Workflow KNIME
<img width="1512" height="982" alt="Screenshot 2025-12-10 at 08 58 36" src="https://github.com/user-attachments/assets/b4bb8e6d-4dec-4a26-98ae-6b39aa0a5468" />
1. Tujuan Workflow
Workflow KNIME ini dibuat untuk menganalisis dataset Toyota Corolla dan menemukan warna mobil yang paling sering muncul serta melakukan eksplorasi data melalui beberapa visualisasi seperti:
2.Visualisasi
Bar Plot 1 (Frekuensi Warna)

<img width="2146" height="516" alt="Bar Chart 1" src="https://github.com/user-attachments/assets/c85a4baa-299d-49d9-928d-009109d63a9f" />
Interpretasi: Grafik Batang (Bar Plot 1) ini menunjukkan frekuensi kemunculan setiap kategori warna mobil dalam dataset. Sumbu X merepresentasikan kategori warna, dan Sumbu Y menunjukkan jumlah (count) mobil untuk setiap warna. Grafik ini mempermudah identifikasi warna dominan, yang sangat penting untuk memahami tren pasar.

Bar Plot 2 (Harga Rata-Rata per Kategori)<img width="2146" height="516" alt="Bar Chart" src="https://github.com/user-attachments/assets/fba612ef-85a3-432b-97cb-21f8343060a1" />


Interpretasi: Grafik tersebut menunjukkan perbandingan nilai prediksi model untuk tiga fitur—Price, Age_08_04, dan KM—berdasarkan warna mobil. Pada fitur Price, seluruh warna memiliki nilai prediksi yang sangat kecil sehingga menunjukkan bahwa warna mobil tidak berpengaruh signifikan terhadap prediksi harga. Sebaliknya, pada fitur Age_08_04, nilai prediksinya tinggi dan bervariasi, menandakan bahwa umur kendaraan menjadi faktor yang kuat dalam prediksi, dengan beberapa warna seperti Black, Red, dan Unknown menunjukkan pola yang lebih tinggi. Pada fitur KM, tinggi bar juga bervariasi antar warna, menggambarkan bahwa jarak tempuh diprediksi berbeda-beda tergantung warna, sehingga model menunjukkan adanya pola tertentu pada prediksi KM berdasarkan warna mobil.

Pie Chart   <img width="2146" height="516" alt="Pie Chart" src="https://github.com/user-attachments/assets/3ce5672f-68f5-439d-83ce-5f3bfb774971" />

Interpretasi: Diagram Lingkaran (Pie Chart) memberikan gambaran proporsi persentase dari setiap kategori warna terhadap total seluruh data. Ini efektif untuk melihat bagian mana (warna mana) yang mendominasi preferensi pembeli Toyota Corolla secara keseluruhan.

Scatter Plot   <img width="2146" height="516" alt="Scatter Plot" src="https://github.com/user-attachments/assets/a71308f2-beb7-40ed-9199-b8f8727b8b18" />

Interpretasi: Scatter Plot (Grafik Sebar) digunakan untuk mengeksplorasi hubungan antara dua variabel numerik, seperti Harga dan Usia Mobil, atau Harga dan Jarak Tempuh. Pola titik yang tersebar menunjukkan korelasi; misalnya, pola menurun menunjukkan hubungan negatif (semakin tinggi satu variabel, semakin rendah yang lain).

Box Plot  <img width="2146" height="516" alt="Box Plot" src="https://github.com/user-attachments/assets/55475e76-943e-4622-8536-0af18b7f6d48" />


Interpretasi: Box Plot (Diagram Kotak) digunakan untuk membandingkan distribusi variabel numerik (seperti Harga) di berbagai kategori (seperti Jenis Bahan Bakar atau Warna). Kotak menunjukkan jangkauan interkuartil (IQR), garis di tengah adalah median, dan titik di luar kumis (whiskers) adalah outlier harga.

Density Plot   <img width="2146" height="516" alt="Density Plot" src="https://github.com/user-attachments/assets/8a4987ed-32ae-4f5f-b2a8-fc421b9c0d8a" />

Interpretasi: Density Plot (Plot Kepadatan) atau Plot Distribusi Kernel Estimasi (KDE) menunjukkan estimasi fungsi kepadatan probabilitas variabel numerik (misalnya, Harga atau Jarak Tempuh). Puncak pada kurva menunjukkan nilai yang paling umum (mode) dalam dataset.

3. Tahapan Workflow (Overview)
Urutan langkah dalam workflow:
CSV Reader – Mengimpor dataset Toyota Corolla.
Column Filter – Memilih kolom yang relevan untuk analisis warna dan numerik.
Missing Value Handling – Mengatasi nilai kosong agar data bersih.
One-to-Many Encoding – Mengubah kolom warna menjadi beberapa kolom biner seperti Silver, Black, White, Grey, Red, Green, Yellow, Violet, dan Beige.
Normalizer – Menormalkan nilai numerik untuk visualisasi dan analisis lebih stabil.
Visualisasi – Menggunakan Bar Chart, Pie Chart, Scatter Plot, Box Plot, dan Density Plot.
Rule Engine – Membuat kolom prediction berdasarkan aturan tertentu, seperti memilih warna dominan dari one-hot encoding.
4. Insight yang Diperoleh
1. Warna Mobil Dominan
Bar Plot 1 dan Pie Chart menunjukkan bahwa warna seperti Silver, Black, dan Grey mendominasi dataset Toyota Corolla, selaras dengan preferensi umum konsumen terhadap warna netral.
2. Warna Tidak Mempengaruhi Harga
Bar Plot 2 menunjukkan bahwa prediksi Price hampir sama untuk semua warna → warna bukan faktor utama dalam penentuan harga mobil.
3. Umur Mobil Menjadi Faktor Paling Penting
Feature Age_08_04 memiliki nilai prediksi tinggi dan stabil → usia mobil adalah variabel paling menentukan dalam analisis nilai mobil.
4. Pola Kilometer Berbeda antar Warna
Prediksi KM yang bervariasi menunjukkan adanya pola penggunaan mobil berdasarkan warna, meski tidak berkaitan langsung dengan harga.
5. One-Hot Encoding Memperbaiki Dekomposisi Fitur
Transformasi kolom warna menjadi kolom biner membantu model memahami atribut kategori secara lebih detail.
6. Kolom Prediction Mempermudah Segmentasi
Rule Engine memungkinkan pembuatan label khusus, misalnya memilih warna dominan, membuat kategori berbasis nilai numerik, atau menandai data tertentu secara otomatis.
5. Kesimpulan
Workflow KNIME ini memberikan gambaran menyeluruh mengenai distribusi warna mobil Toyota Corolla, hubungan antar variabel numerik, serta pola prediksi berdasarkan kategori warna. Visualisasi yang lengkap dan preprocessing yang baik menjadikan workflow ini dasar yang sangat kuat untuk analisis lanjutan seperti prediksi harga, segmentasi pelanggan, atau model klasifikasi.
