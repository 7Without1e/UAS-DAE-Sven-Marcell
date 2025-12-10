Laporan Analisis Workflow KNIME — Toyota Corolla Dataset
1. Tujuan Workflow
Workflow KNIME ini dibuat untuk menganalisis dataset Toyota Corolla dengan fokus pada warna mobil yang paling sering muncul, distribusi masing-masing warna, serta hubungan warna dengan variabel numerik seperti harga, usia mobil, dan kilometer. Analisis dilakukan menggunakan berbagai visualisasi dan preprocessing data sebagai dasar pengambilan insight.
2. Visualisasi dan Interpretasi
2.1 Bar Plot 1 – Frekuensi Warna
(Gambar: https://github.com/user-attachments/assets/c85a4baa-299d-49d9-928d-009109d63a9f)
Bar Plot ini menunjukkan jumlah kemunculan tiap kategori warna dalam dataset. Sumbu X berisi nama warna, dan Sumbu Y menunjukkan jumlah unit mobil. Visualisasi ini memudahkan identifikasi warna dominan dan melihat preferensi pasar Toyota Corolla berdasarkan data historis.
2.2 Bar Plot 2 – Perbandingan Prediksi Fitur
(Gambar: https://github.com/user-attachments/assets/fba612ef-85a3-432b-97cb-21f8343060a1)
Grafik ini membandingkan nilai prediksi model untuk tiga fitur: Price, Age_08_04, dan KM, berdasarkan kategori warna mobil.
Price memiliki nilai prediksi kecil pada semua warna → warna tidak berpengaruh signifikan terhadap harga.
Age_08_04 menunjukkan nilai tinggi dan bervariasi → usia mobil adalah faktor prediktif paling kuat.
KM menunjukkan variasi antar warna → pola penggunaan mobil tampak berbeda berdasarkan warna tertentu.
2.3 Pie Chart – Proporsi Warna Mobil
(Gambar: https://github.com/user-attachments/assets/3ce5672f-68f5-439d-83ce-5f3bfb774971)
Diagram lingkaran ini menggambarkan persentase masing-masing warna dalam dataset. Visualisasi ini memperjelas warna mana yang paling dominan dan membantu memahami komposisi pasar Toyota Corolla.
2.4 Scatter Plot – Hubungan Harga dengan Variabel Lain
(Gambar: https://github.com/user-attachments/assets/a71308f2-beb7-40ed-9199-b8f8727b8b18)
Scatter Plot digunakan untuk melihat hubungan antara dua variabel numerik, misalnya:
Harga vs Umur Mobil
Harga vs Kilometer
Jika titik membentuk pola menurun, berarti terdapat korelasi negatif, yaitu harga turun seiring bertambahnya umur atau kilometer.
2.5 Box Plot – Distribusi Harga di Berbagai Kategori
(Gambar: https://github.com/user-attachments/assets/55475e76-943e-4622-8536-0af18b7f6d48)
Box Plot digunakan untuk membandingkan distribusi harga antar kategori tertentu, misalnya berdasarkan warna atau jenis bahan bakar. Kotak menunjukkan rentang IQR, garis di tengah adalah median, sedangkan titik di luar whiskers merupakan outlier harga.
2.6 Density Plot – Distribusi Variabel Numerik
(Gambar: https://github.com/user-attachments/assets/8a4987ed-32ae-4f5f-b2a8-fc421b9c0d8a)
Density Plot (KDE) menampilkan distribusi probabilitas untuk variabel seperti harga atau kilometer. Puncak kurva menunjukkan nilai yang paling sering muncul, sehingga memudahkan memahami kecenderungan data secara halus.
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
