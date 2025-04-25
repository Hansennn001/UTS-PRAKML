
# Klasifikasi Kelayakan Kredit Komputer Menggunakan Decision Tree

## Alhan Husen
## 1227050015
## Prak ML - E 

## Ringkasan Proyek
Dalam proyek ini, dibangun sebuah model klasifikasi berbasis **Decision Tree** untuk menentukan apakah seseorang dianggap layak memperoleh kredit komputer. Penilaian dilakukan dengan mempertimbangkan beberapa atribut seperti usia, tingkat penghasilan, status sebagai mahasiswa, serta skor kredit.

Dataset yang digunakan merupakan data simulasi yang merepresentasikan kondisi pemohon dan keputusan terkait pemberian kredit komputer (`Buys_Computer` = 1 untuk layak, 0 untuk tidak layak).

---

## Informasi Dataset
Dataset terdiri dari 5 fitur:
- `Age`: Kategori umur (`Muda`, `Paruh Baya`, `Tua`)
- `Income`: Tingkat penghasilan (`Rendah`, `Sedang`, `Tinggi`)
- `Student`: Status mahasiswa (`Ya`, `Tidak`)
- `Credit_Rating`: Penilaian kredit (`Baik`, `Buruk`)
- `Buys_Computer`: Label target klasifikasi (`1 = Layak`, `0 = Tidak Layak`)

---

## Alur Pengerjaan

### 1. **Eksplorasi Data (EDA)**
- Melihat struktur dan isi awal dataset
- Menganalisis distribusi label target
- Memeriksa kategori unik dari setiap fitur

### 2. **Pra-pemrosesan**
- Melakukan encoding terhadap data kategorikal menggunakan `LabelEncoder`
- Membagi data menjadi training set dan test set dengan perbandingan 80:20

### 3. **Pelatihan Model**
Dua model Decision Tree dibangun dan dibandingkan:
1. **Model Default**:
   ```python
   DecisionTreeClassifier(random_state=42)
   ```

2. **Model Entropy**:
   ```python
   DecisionTreeClassifier(criterion='entropy', random_state=42)
   ```

---

### 4. **Evaluasi Model**
Setiap model dievaluasi menggunakan beberapa metrik:
- **Confusion Matrix**
- **Akurasi**
- **Precision**, **Recall**, dan **F1-Score**
- **Feature Importance**
- **Visualisasi Struktur Pohon** dengan `plot_tree()`

---

### 5. **Prediksi Data Baru**
Contoh data yang digunakan untuk pengujian:

```python
{
  'Age': 'Muda',
  'Income': 'Rendah',
  'Student': 'Ya',
  'Credit_Rating': 'Buruk'
}
```

Hasil prediksi dari kedua model (Gini dan Entropy) menunjukkan apakah individu tersebut layak diberikan kredit.

---

## Teknologi dan Library
- Python
- pandas
- scikit-learn
- matplotlib

---

## File Terkait
- `decision_tree_kredit_komputer.ipynb` – Notebook utama yang memuat seluruh proses
- `dataset_buys_comp.csv` – Dataset dummy yang digunakan
