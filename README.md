## 📚 Informasi Dataset

- **Nama dataset** : Drug Classification (`drug200.csv`)  
- **Sumber**       : Dataset latihan kelas MSML (asalnya dari Kaggle – Pratham Tripathi)  
- **Jumlah baris** : ± 200 sampel pasien  
- **Fitur utama**  :
  - `Age` – usia pasien (numerik)  
  - `Sex` – jenis kelamin (M/F)  
  - `BP` – tekanan darah (LOW / NORMAL / HIGH)  
  - `Cholesterol` – kadar kolesterol (NORMAL / HIGH)  
  - `Na_to_K` – rasio sodium terhadap potassium dalam darah  
- **Target**       : `Drug` – jenis obat (`DrugY`, `drugX`, `drugA`, `drugB`, `drugC`)

Dataset ini sedikit **imbalanced** (kelas `DrugY` lebih dominan), sehingga perlu perhatian saat melakukan split data dan ketika nanti membangun model.

---

## 🔬 Ringkasan Eksperimen

### 1. Data Loading
- Load `drug200.csv` menggunakan `pandas`.  
- Mengecek dimensi dataset, tipe data setiap kolom, dan jumlah nilai unik.  
- Mengecek missing values (hasil: **tidak ada nilai hilang**).

### 2. Exploratory Data Analysis (EDA)
- Distribusi target `Drug` (5 kelas obat).  
- Distribusi fitur numerik (`Age`, `Na_to_K`) dengan histogram.  
- Distribusi fitur kategorikal (`Sex`, `BP`, `Cholesterol`).  
- Analisis hubungan fitur terhadap target (misalnya: jenis obat yang sering muncul pada tekanan darah tinggi, kolesterol tinggi, dan kombinasi fitur lainnya).

### 3. Preprocessing

**Encoding fitur kategorikal:**

- `Sex` → Label Encoding (contoh: F = 0, M = 1).  
- `BP` → Label Encoding (LOW = 0, NORMAL = 1, HIGH = 2).  
- `Cholesterol` → Label Encoding (NORMAL = 0, HIGH = 1).

**Train–Test Split:**

- Train : 80%  
- Test  : 20%  
- Menggunakan `stratify=Drug` untuk menjaga proporsi kelas pada data train dan test.

**Menyimpan hasil preprocessing ke file:**

- `drug200_processed.csv`  
- `X_train.csv`  
- `X_test.csv`  
- `y_train.csv`  
- `y_test.csv`  

Seluruh file ini disimpan di dalam folder `preprocessing/drug_preprocessing/`.

---

## 🛠️ Tools & Library

- Python **3.12**  
- `pandas`, `numpy` – data wrangling & manipulasi data  
- `matplotlib`, `seaborn` – visualisasi EDA  
- `scikit-learn` – preprocessing & train–test split  
- Jupyter Notebook / Google Colab – lingkungan eksperimen

---

## 🚀 Cara Menjalankan

### 1. Clone repo

```bash
git clone https://github.com/Raziffff/Eksperimen_SML_RAZIF.git
cd Eksperimen_SML_RAZIF
