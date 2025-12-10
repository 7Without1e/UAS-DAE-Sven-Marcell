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
