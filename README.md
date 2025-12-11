# Eksperimen Machine Learning – Muhamad Razif

## 📊 Project Overview  
Repositori ini berisi eksperimen awal untuk **submission Machine Learning System and MLOps (MSML)**.  
Pada tahap ini fokusnya adalah **eksplorasi dan preprocessing dataset Drug Classification** untuk memprediksi jenis obat yang tepat berdasarkan kondisi medis pasien.

## 🎯 Objective  
- Melakukan **EDA (Exploratory Data Analysis)** pada dataset `drug200`.  
- Melakukan **preprocessing & splitting data** sehingga siap dipakai pada tahap berikutnya (membangun model & MLOps).  
- Mendokumentasikan hasil eksperimen di satu repo terpisah sesuai kriteria MSML (Kriteria 1).

---

## 📁 Struktur Repository

```text
Eksperimen_SML_RAZIF/
├── README.md
├── drug200.csv                     # raw dataset (jika di-commit)
└── preprocessing/
    ├── Template_Eksperimen_Muhamad_Razif.ipynb
    └── drug_preprocessing/
        ├── drug200_processed.csv   # data hasil preprocessing
        ├── X_train.csv
        ├── X_test.csv
        ├── y_train.csv
        └── y_test.csv

📚 Informasi Dataset
Nama dataset : Drug Classification (drug200.csv)

Sumber : Dataset latihan dari kelas MSML (asalnya dari Kaggle – Pratham Tripathi)

Jumlah baris : ± 200 sampel pasien

Fitur utama :

Age – usia pasien (numerik)

Sex – jenis kelamin (M/F)

BP – tekanan darah (LOW / NORMAL / HIGH)

Cholesterol – kadar kolesterol (NORMAL / HIGH)

Na_to_K – rasio sodium terhadap potassium

Target: Drug – jenis obat (DrugY, drugX, drugA, drugB, drugC)

Dataset sedikit imbalanced (kelas DrugY lebih dominan), sehingga perlu perhatian saat split dan saat nanti membangun model.

🔬 Ringkasan Eksperimen
Data Loading

Load drug200.csv dengan pandas.

Cek dimensi, tipe data, dan nilai unik setiap kolom.

Cek missing values (hasil: tidak ada nilai hilang pada dataset ini).

Exploratory Data Analysis (EDA)

Distribusi target Drug (5 kelas obat).

Distribusi fitur numerik (Age, Na_to_K) dengan histogram.

Distribusi fitur kategorikal (Sex, BP, Cholesterol).

Analisis hubungan fitur vs target (misal: obat apa yang sering muncul pada tekanan darah tinggi, dll).

Preprocessing

Encoding fitur kategorikal:

Sex → Label Encoding (mis. F=0, M=1).

BP → Label Encoding (LOW=0, NORMAL=1, HIGH=2).

Cholesterol → Label Encoding (NORMAL=0, HIGH=1).

Train–Test Split:

Train: 80%

Test : 20%

stratify=Drug untuk menjaga proporsi kelas.

Menyimpan hasil preprocessing ke file:

drug200_processed.csv, X_train.csv, X_test.csv, y_train.csv, y_test.csv.

🛠️ Tools & Library
Python 3.12

pandas, numpy – data wrangling

matplotlib, seaborn – visualisasi EDA

scikit-learn – preprocessing & train–test split

Jupyter Notebook / Google Colab untuk eksperimen

🚀 Cara Menjalankan
Clone repo

bash
Salin kode
git clone https://github.com/Raziffff/Eksperimen_SML_RAZIF.git
cd Eksperimen_SML_RAZIF
Install dependencies dasar

(Bisa juga pakai requirements.txt kalau nanti sudah dibuat.)

bash
Salin kode
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
Letakkan dataset

Simpan file drug200.csv di root folder repositori (sejajar dengan README.md), atau sesuaikan path di notebook.

Jalankan notebook eksperimen

bash
Salin kode
cd preprocessing
jupyter notebook Template_Eksperimen_Muhamad_Razif.ipynb
Run semua sel

Jalankan sel dari atas ke bawah.

File hasil preprocessing (X_train.csv, dll.) akan tersimpan di folder drug_preprocessing/.

👤 Author
Nama : Muhamad Razif

Kelas : Machine Learning System and MLOps – Dicoding

Repo ini digunakan khusus untuk Kriteria 1 – Eksperimen Dataset & Preprocessing sebelum melanjutkan ke repo utama untuk membangun model, workflow CI, serta monitoring dan logging.
