# Laporan Analisis Workflow KNIME

## 1. Tujuan Workflow<img width="1512" height="982" alt="Screenshot 2025-12-10 at 08 58 36" src="https://github.com/user-attachments/assets/d4b358fc-ba84-41cd-95d0-4bcb4eb74ed7" />


Workflow KNIME ini dibuat untuk menganalisis dataset **Toyota Corolla** dan menemukan **warna mobil yang paling sering muncul** serta melakukan eksplorasi data melalui beberapa visualisasi seperti:

* Bar Plot
<img width="2146" height="516" alt="Bar Chart 1" src="https://github.com/user-attachments/assets/c85a4baa-299d-49d9-928d-009109d63a9f" />

  
* Pie Chart
  <img width="2146" height="516" alt="Pie Chart" src="https://github.com/user-attachments/assets/3ce5672f-68f5-439d-83ce-5f3bfb774971" />

* Scatter Plot
  <img width="2146" height="516" alt="Scatter Plot" src="https://github.com/user-attachments/assets/a71308f2-beb7-40ed-9199-b8f8727b8b18" />

  
* Box Plot
  <img width="2146" height="516" alt="Box Plot" src="https://github.com/user-attachments/assets/99bf1bcf-b04f-4547-9556-e23948bfbd3e" />

* Density Plot
  <img width="2146" height="516" alt="Density Plot" src="https://github.com/user-attachments/assets/8a4987ed-32ae-4f5f-b2a8-fc421b9c0d8a" />


Workflow juga mencakup proses preprocessing seperti:

* Missing value handling
* One-to-many encoding (one hot encoding) pada kolom warna
* Normalisasi
* Rule Engine untuk menghasilkan kolom *prediction*

---

## 2. Alur Kerja (Workflow Overview)

Berikut langkah utama workflow:

### **1. CSV Reader**

Mengimpor dataset Toyota Corolla.

### **2. Column Filter**

Memilih kolom-kolom yang relevan untuk analisis warna.

### **3. Missing Value**

Membersihkan data dari nilai hilang.

### **4. One to Many (One Hot Encoding)**

Mengubah kolom warna menjadi 10 kolom biner:

* Silver
* Black
* White
* Grey
* Red
* Green
* Yellow
* Violet
* Beige
* ... (opsional jika ada kategori tambahan)

### **5. Normalizer**

Menormalkan nilai numerik untuk keperluan visualisasi.

### **6. Visualisasi**

Menggunakan Box Plot, Density Plot, Pie Chart, Bar Chart untuk melihat persebaran dan frekuensi.

### **7. Rule Engine**

Membuat kolom baru bernama **prediction** berdasarkan aturan yang ditentukan.
Aturan dapat berupa pemilihan warna berdasarkan nilai tertinggi.

---

## 3. Insight yang Diperoleh

Dari workflow ini, beberapa insight penting dapat ditemukan:

### **1. Warna Mobil yang Paling Sering Muncul**

Dengan melihat kolom hasil one-hot encoding serta pie chart/bar chart, kita bisa mengetahui warna dominan dari seluruh dataset.

Biasanya untuk dataset Toyota Corolla, warna yang sering muncul adalah **Silver**, **Black**, dan **Grey**.

### **2. Distribusi Warna Mobil**

Pie Chart membantu menunjukkan proporsi setiap warna. Ini memberikan gambaran preferensi warna untuk model Toyota Corolla.

### **3. Pola Distribusi Harga & Variabel Lain**

Dengan Scatter Plot dan Box Plot, kita dapat melihat hubungan antara:

* harga dan umur mobil
* harga dan kilometer
* harga dan warna (jika dikaitkan)

### **4. Penyederhanaan Kolom Warna**

One-hot encoding memungkinkan model prediksi di masa depan dilakukan lebih akurat.

### **5. Kolom Prediction dari Rule Engine**

Rule Engine digunakan untuk menentukan kategori tertentu — misalnya:

* Memilih warna dominan per baris (jika digunakan max rule)
* Memberi label tertentu berdasarkan kombinasi fitur

---

## 4. Kesimpulan

Workflow KNIME ini memberikan gambaran menyeluruh mengenai data Toyota Corolla, khususnya dari sisi **warna mobil** dan bagaimana warna tersebut berdistribusi dalam dataset. Penggunaan berbagai node visualisasi membantu mendapatkan insight visual yang mudah dipahami. Workflow ini juga siap digunakan sebagai dasar untuk analisis lanjutan seperti model prediksi harga.

---



