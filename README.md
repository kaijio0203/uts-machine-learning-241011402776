# UTS Machine Learning - Implementasi From Scratch (NumPy)

Repositori ini berisi penyelesaian Ujian Tengah Semester (UTS) mata kuliah Machine Learning, yang mengimplementasikan algoritma **Linear Regression** dan **Logistic Regression** dari nol (*from scratch*) menggunakan bahasa pemrograman Python dan pustaka NumPy.

---

## 📌 Identitas Mahasiswa
* **Nama:** Muhamad Fahim
* **NIM:** 241011402776
* **Program Studi:** S1 Teknik Informatika (Universitas Pamulang)
* **Parameter Global (`RANDOM_STATE`):** 76

---

## 📊 Ringkasan Hasil Eksperimen

### **Bagian A: Linear Regression (`Ads_Data.csv`)**
Model regresi linear dilatih untuk memprediksi nilai penjualan berdasarkan biaya iklan menggunakan metode *Normal Equation* dan *Gradient Descent*.
* **Metrik Evaluasi Data Testing:**
  * **$R^2$ Score:** $\approx 0.838$ (Menunjukkan sekitar $83.8\%$ variasi penjualan dapat dijelaskan oleh variabel biaya iklan).
  * **RMSE (Data Testing):** $\approx 9.59$ juta Rupiah.
* **Eksperimen Gradient Descent:** 
  Pengujian dengan tiga nilai *learning rate* (`0.001`, `0.02`, `0.1`) menunjukkan bahwa *learning rate* `0.02` memberikan konvergensi yang optimal, sedangkan *learning rate* `0.1` terlalu besar sehingga mengalami *overshooting* dan *overflow* (`NaN`).

### **Bagian B: Logistic Regression (`Email_Data.csv`)**
Model klasifikasi biner dilatih untuk menyaring email *Spam* (1) dan *Bukan Spam* (0) berdasarkan jumlah link dan kata promosi menggunakan algoritma *Logistic Regression* berbasis *Gradient Descent*.
* **Metrik Evaluasi Data Testing (Threshold = 0.5):**
  * **Akurasi:** Tinggi / Konsisten pada data uji.
  * **Precision & Recall:** Seimbang, dengan penekanan bahwa *False Positive* ditekan seminimal mungkin agar email penting tidak keliru masuk ke folder spam.
* **Analisis Threshold:**
  * Penurunan *threshold* (misal ke `0.3`) menaikkan *Recall* (lebih sensitif menangkap spam).
  * Kenaikan *threshold* (misal ke `0.7`) menaikkan *Precision* (lebih ketat dan aman dari risiko salah deteksi email penting).

### **Bagian C & Bonus:**
* **Pemahaman Konsep:** Mencakup penjelasan teoretis mengenai perbedaan regresi dan klasifikasi, fungsi sigmoid, fungsi *loss* (MSE vs *Log Loss*), pencegahan *overfitting*, serta faktor penyebab perbedaan hasil antar-individu.
* **Perbandingan Scikit-Learn:** Validasi model manual terhadap pustaka resmi `scikit-learn` menunjukkan hasil parameter yang identik pada Linear Regression, serta perbedaan minor pada Logistic Regression akibat penggunaan regularisasi L2 (*Ridge*) *default* pada *sklearn*.

---

## 🚀 Cara Menjalankan Program
1. Pastikan dependensi pustaka Python berikut telah terinstal:
   ```bash
   pip install numpy pandas matplotlib scikit-learn
