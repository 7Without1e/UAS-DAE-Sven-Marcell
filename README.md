# 🚗 Proyek Analisis Prediksi Harga Mobil Toyota Corolla

Proyek ini merupakan analisis eksplorasi data dan pemodelan regresi awal menggunakan dataset `ToyotaCorolla.csv`. Tujuan utamanya adalah memahami faktor-faktor yang mempengaruhi harga jual mobil, dengan fokus pada hubungan antara **Usia Mobil** dan **Jarak Tempuh (KM)**.

## 💾 Dataset

Dataset: `ToyotaCorolla.csv`
Sumber: Data historis penjualan mobil Toyota Corolla.

| Variabel | Deskripsi | Tipe Data |
| :--- | :--- | :--- |
| `Price` | Harga jual mobil (Variabel Target) | Numerik (Integer) |
| `Age_08_04` | Usia mobil dalam bulan pada tanggal penawaran | Numerik (Integer) |
| `KM` | Jarak tempuh mobil dalam kilometer | Numerik (Integer) |
| `HP` | Tenaga kuda (*Horse Power*) | Numerik (Integer) |
| `Weight` | Berat mobil | Numerik (Integer) |
| `Fuel_Type` | Jenis bahan bakar (Petrol, Diesel, CNG) | Kategorikal |

## ⚙️ Diagram Alur Kerja Eksperimen (Workflow)

Berikut adalah representasi diagram alir proses analisis data dan regresi, menggantikan penggunaan *screenshot* atau gambar.

```mermaid

graph TD
    A[Start] --> B(Memuat Data: ToyotaCorolla.csv);
    B --> C{Pemisahan Variabel};
    C --> D[Target: Price];
    C --> E[Fitur: Age, KM, HP, Weight, ...];
    E --> F(Pemodelan: Algoritma Regresi);
    D --> F;
    F --> G(Evaluasi Model: Test and Score);
    G --> H{Metrik Kinerja};
    H --> I[RMSE, MAE, R-squared];
    I --> J(Interpretasi Hasil);
    J --> K[End];
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import os

# --- 1. Pengaturan Awal ---

# Set style for better visualization
sns.set_style("whitegrid")
# Tentukan nama file dataset
DATASET_FILE = 'ToyotaCorolla.csv'
target_variable = 'Price'

# --- 2. Pemuatan Data ---
try:
    df = pd.read_csv(DATASET_FILE)
    print(f"Dataset '{DATASET_FILE}' berhasil dimuat.")
except FileNotFoundError:
    print(f"ERROR: File '{DATASET_FILE}' tidak ditemukan. Pastikan file berada di direktori yang sama.")
    # Keluar dari skrip jika file tidak ditemukan
    exit()

# --- 3. Visualisasi Data ---

print("\n--- Membuat Visualisasi Korelasi ---")

# Plot 1: Korelasi Harga vs Umur (Age_08_04)
# Visualisasi ini akan menunjukkan korelasi negatif: semakin tua mobil, semakin rendah harganya.
plt.figure(figsize=(10, 6))
sns.scatterplot(x='Age_08_04', y=target_variable, data=df, color='skyblue', alpha=0.7)
plt.title('Korelasi: Umur Mobil (Bulan) vs Harga', fontsize=16)
plt.xlabel('Umur Mobil (Age_08_04 - Bulan)', fontsize=12)
plt.ylabel(f'Harga ({target_variable})', fontsize=12)
plt.grid(True, linestyle='--', alpha=0.6)
plt.savefig('visualisasi_umur_vs_harga.png')
plt.close()
print("Visualisasi 'visualisasi_umur_vs_harga.png' berhasil disimpan.")

# Plot 2: Korelasi Harga vs Jarak Tempuh (KM)
# Visualisasi ini akan menunjukkan korelasi negatif: semakin jauh jarak tempuh, semakin rendah harganya.
plt.figure(figsize=(10, 6))
sns.scatterplot(x='KM', y=target_variable, data=df, color='lightcoral', alpha=0.7)
plt.title('Korelasi: Jarak Tempuh (KM) vs Harga', fontsize=16)
plt.xlabel('Jarak Tempuh (KM)', fontsize=12)
plt.ylabel(f'Harga ({target_variable})', fontsize=12)
plt.grid(True, linestyle='--', alpha=0.6)
plt.savefig('visualisasi_km_vs_harga.png')
plt.close()
print("Visualisasi 'visualisasi_km_vs_harga.png' berhasil disimpan.")

print("\nVisualisasi selesai. Unggah kedua file .png hasil ini ke GitHub untuk ditampilkan di README.")
