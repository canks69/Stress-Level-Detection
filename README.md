# Stress Level Detection using K-Nearest Neighbors (KNN)

## 📋 Deskripsi Proyek

Proyek ini mengimplementasikan klasifikasi tingkat stress menggunakan algoritma K-Nearest Neighbors (KNN) dengan tiga pendekatan berbeda untuk mengoptimalkan performa model:

1. **KNN Murni** - Implementasi KNN dasar tanpa optimasi tambahan
2. **KNN + SMOTE** - KNN dengan Synthetic Minority Oversampling Technique untuk mengatasi ketidakseimbangan kelas
3. **KNN + GridSearch** - KNN dengan optimasi hyperparameter menggunakan GridSearchCV

## 📊 Dataset

Dataset yang digunakan adalah `fix dataset 1031.csv` yang berisi informasi terkait tingkat stress dengan fitur-fitur:

- **Gender**: Jenis kelamin
- **Age**: Usia
- **Occupation**: Pekerjaan
- **Sleep Duration**: Durasi tidur
- **Quality of Sleep**: Kualitas tidur
- **Physical Activity Level**: Tingkat aktivitas fisik
- **Stress Level**: Tingkat stress
- **BMI Category**: Kategori BMI
- **Blood Pressure**: Tekanan darah (dipisah menjadi Systolic dan Diastolic)
- **Sleep Disorder**: Target klasifikasi (Normal, Insomnia, Sleep Apnea)

## 🗂️ Struktur Proyek

```
Stress Level Detection/
├── README.md                    # Dokumentasi proyek
├── dataset/
│   └── fix dataset 1031.csv    # Dataset utama
├── base_knn.ipynb             # Notebook dasar KNN (referensi)
├── knn_murni.ipynb            # KNN tanpa optimasi
├── knn_smote.ipynb            # KNN dengan SMOTE
└── knn_gridsearch.ipynb       # KNN dengan GridSearch
```

## 🚀 Skenario Implementasi

### ✅ 1. KNN Murni (`knn_murni.ipynb`)

**Tujuan**: Implementasi KNN dasar untuk mendapatkan baseline performance

**Fitur Utama**:
- Preprocessing data standar
- Training KNN dengan parameter default (k=5)
- Testing manual untuk berbagai nilai k (1-20)
- Evaluasi performa model

**Output**:
- Distribusi kelas original
- Akurasi untuk setiap nilai k
- K optimal yang memberikan performa terbaik
- Visualisasi akurasi vs k

### ✅ 2. KNN + SMOTE (`knn_smote.ipynb`)

**Tujuan**: Mengatasi ketidakseimbangan kelas menggunakan SMOTE

**Fitur Utama**:
- Analisis distribusi kelas **BEFORE** dan **AFTER** SMOTE
- Implementasi SMOTE untuk balancing data
- Training KNN dengan data yang sudah di-balance
- Perbandingan performa dengan KNN murni

**Informasi yang Disajikan**:
- **Data before SMOTE**: Jumlah sampel masing-masing kelas
- **Data after SMOTE**: Jumlah sampel setelah balancing
- **Peningkatan data**: Jumlah sampel sintetis yang ditambahkan per kelas
- **K optimal**: Nilai k terbaik untuk KNN+SMOTE
- **Improvement**: Perbandingan akurasi dengan KNN original

### ✅ 3. KNN + GridSearch (`knn_gridsearch.ipynb`)

**Tujuan**: Optimasi hyperparameter KNN menggunakan GridSearchCV

**Fitur Utama**:
- Comprehensive hyperparameter tuning
- Cross-validation dengan 5-fold
- Perbandingan **BEFORE** dan **AFTER** GridSearch
- Top 10 kombinasi parameter terbaik

**Hyperparameter yang Dioptimasi**:
```python
param_grid = {
    'knn__n_neighbors': [3, 5, 7, 9, 11, 13, 15, 17, 19, 21],
    'knn__weights': ['uniform', 'distance'],
    'knn__algorithm': ['auto', 'ball_tree', 'kd_tree', 'brute'],
    'knn__metric': ['euclidean', 'manhattan', 'minkowski'],
    'knn__p': [1, 2]
}
```

**Informasi yang Disajikan**:
- **Before GridSearch**: Hyperparameter default dan performanya
- **After GridSearch**: Hyperparameter optimal dan peningkatan performa
- **K optimal**: Nilai k terbaik dari comprehensive search
- **Waktu eksekusi**: Durasi proses GridSearch

## 📈 Hasil dan Analisis

### Perbandingan Metode

| Metode | K Optimal | Akurasi | Keterangan |
|--------|-----------|---------|------------|
| KNN Murni | Akan ditentukan | Baseline | Manual testing k=1-20 |
| KNN + SMOTE | Akan ditentukan | Improvement expected | Balanced data |
| KNN + GridSearch | Akan ditentukan | Best performance | Optimized hyperparameters |

### Insights yang Diperoleh

1. **Distribusi Kelas**: Analisis ketidakseimbangan data original
2. **Efek SMOTE**: Dampak balancing terhadap performa model
3. **Optimasi Parameter**: Hyperparameter mana yang paling berpengaruh
4. **K Optimal**: Nilai k terbaik untuk setiap skenario

## 🛠️ Instalasi dan Penggunaan

### Prerequisites

```bash
pip install pandas
pip install scikit-learn
pip install imbalanced-learn
pip install matplotlib
pip install seaborn
pip install numpy
```

### Menjalankan Notebook

1. **KNN Murni**:
   ```bash
   jupyter notebook knn_murni.ipynb
   ```

2. **KNN + SMOTE**:
   ```bash
   jupyter notebook knn_smote.ipynb
   ```

3. **KNN + GridSearch**:
   ```bash
   jupyter notebook knn_gridsearch.ipynb
   ```

### Urutan Eksekusi yang Disarankan

1. Jalankan `knn_murni.ipynb` untuk mendapatkan baseline
2. Jalankan `knn_smote.ipynb` untuk melihat efek balancing
3. Jalankan `knn_gridsearch.ipynb` untuk optimasi maksimal

## 📊 Evaluasi Model

Setiap notebook menyediakan evaluasi komprehensif:

- **Accuracy Score**: Akurasi keseluruhan model
- **Classification Report**: Precision, Recall, F1-score per kelas
- **Confusion Matrix**: Visualisasi prediksi vs actual
- **Cross-validation**: Validasi dengan k-fold CV (untuk GridSearch)

## 🔍 Fitur Analisis

### Data Analysis
- Missing value handling
- Feature preprocessing
- Outlier detection
- Data distribution visualization

### Model Comparison
- Performance metrics comparison
- Hyperparameter impact analysis
- K-value optimization curves
- Before/after improvement analysis

### Visualization
- Class distribution plots
- Accuracy vs K plots
- Confusion matrix heatmaps
- Performance comparison charts

## 📋 Checklist Skenario

- [x] **KNN Murni**: Implementasi dasar dan testing manual k-values
- [x] **KNN + SMOTE**: Balancing data dan analisis before/after SMOTE
- [x] **KNN + GridSearch**: Optimasi hyperparameter dan analisis before/after

## 🎯 Key Findings

Setiap notebook akan menghasilkan findings berikut:

1. **Distribusi Data**: 
   - Jumlah sampel per kelas before SMOTE
   - Jumlah sampel per kelas after SMOTE
   - Peningkatan data sintetis per kelas

2. **Hyperparameter Optimization**:
   - Parameter default vs optimal
   - K optimal untuk setiap metode
   - Improvement percentage

3. **Performance Comparison**:
   - KNN Murni vs KNN+SMOTE vs KNN+GridSearch
   - Metode mana yang memberikan hasil terbaik
   - Trade-off antara kompleksitas dan performa

## 👨‍💻 Author

Proyek ini dibuat untuk analisis perbandingan metode KNN dalam klasifikasi tingkat stress dengan fokus pada:
- Handling imbalanced data
- Hyperparameter optimization  
- Performance improvement analysis

## 📝 License

This project is for educational and research purposes.

---

**Note**: Jalankan setiap notebook secara berurutan untuk mendapatkan pemahaman yang komprehensif tentang perbandingan ketiga metode KNN.