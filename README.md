# JCBDAAH-006_Gamma

[README_telco_cust_churn.md](https://github.com/user-attachments/files/33140549/README_telco_cust_churn.md)
# Telco Customer Churn Analysis

## Tentang Project

Project ini adalah **Final Project Kelompok Gamma** yang dibuat untuk menganalisis customer churn pada perusahaan telekomunikasi.

Tujuan utama project ini adalah mencari tahu faktor-faktor yang berkaitan dengan pelanggan yang berhenti berlangganan, terutama dari sisi **jenis kontrak, layanan internet, tenure, layanan tambahan, dan metode pembayaran**.

Pada project ini kami melakukan proses mulai dari **Data Understanding, Data Cleaning, Exploratory Data Analysis (EDA), Statistical Testing**, sampai membuat rekomendasi strategi retensi untuk pelanggan.

---

## Anggota Kelompok

- Ayudhia Surya Taufiqa Rahma
- Muhammad Haikal Athallah
- Quaishum Syantini

---

## Gambaran Masalah

Industri telekomunikasi berkembang cukup cepat dan persaingan antar layanan juga semakin tinggi. Salah satu masalah yang dihadapi perusahaan adalah **customer churn**, yaitu ketika pelanggan berhenti menggunakan layanan.

Churn dapat berdampak pada pendapatan perusahaan karena perusahaan perlu mempertahankan pelanggan lama sekaligus mendapatkan pelanggan baru.

Karena itu, pada project ini kami mencoba melihat:

- Faktor apa yang berkaitan dengan churn?
- Kelompok pelanggan mana yang memiliki risiko churn lebih tinggi?
- Bagaimana pengaruh jenis kontrak dan lama berlangganan?
- Layanan apa yang dapat membantu meningkatkan retensi pelanggan?
- Strategi apa yang bisa dilakukan oleh tim **Sales**?

---

## Stakeholder

Stakeholder yang menjadi fokus dalam project ini adalah **tim Sales**.

Analisis ini diharapkan dapat membantu tim Sales dalam melihat:

- Jenis kontrak yang memiliki risiko churn tinggi
- Segmen pelanggan yang perlu diperhatikan
- Penawaran produk dan layanan tambahan
- Strategi untuk meningkatkan loyalitas pelanggan
- Cara mengurangi risiko kehilangan pelanggan

---

## Dataset

Dataset yang digunakan adalah **Telco Customer Churn (IBM Sample Dataset)**.

Detail dataset:

- **7.043 baris**
- **21 kolom**
- 1 baris mewakili 1 pelanggan
- `customerID` digunakan sebagai ID unik pelanggan
- Dataset merupakan snapshot satu waktu dan tidak memiliki data historis berdasarkan tanggal

### Beberapa Kolom yang Digunakan

| Kolom | Keterangan |
|---|---|
| `customerID` | ID unik pelanggan |
| `gender` | Jenis kelamin pelanggan |
| `SeniorCitizen` | Status pelanggan senior |
| `Partner` | Status memiliki pasangan |
| `Dependents` | Status memiliki tanggungan |
| `tenure` | Lama pelanggan menggunakan layanan dalam bulan |
| `PhoneService` | Status layanan telepon |
| `MultipleLines` | Status multiple lines |
| `InternetService` | Jenis layanan internet |
| `OnlineSecurity` | Layanan keamanan online |
| `OnlineBackup` | Layanan backup online |
| `DeviceProtection` | Perlindungan perangkat |
| `TechSupport` | Layanan technical support |
| `StreamingTV` | Layanan streaming TV |
| `StreamingMovies` | Layanan streaming film |
| `Contract` | Jenis kontrak pelanggan |
| `PaperlessBilling` | Status paperless billing |
| `PaymentMethod` | Metode pembayaran |
| `MonthlyCharges` | Biaya bulanan |
| `TotalCharges` | Total biaya selama berlangganan |
| `Churn` | Status pelanggan berhenti atau tidak |

---

## Rumusan Masalah

Beberapa pertanyaan yang ingin kami jawab dalam project ini:

1. Faktor apa saja yang paling berkaitan dengan keputusan pelanggan untuk melakukan churn?
2. Bagaimana hubungan jenis layanan dengan churn?
3. Bagaimana pengaruh jenis kontrak dan tenure terhadap churn rate?
4. Strategi retensi seperti apa yang dapat digunakan untuk mengurangi churn?

---

## Tujuan Analisis

Tujuan dari project ini adalah:

1. Mengidentifikasi faktor utama yang berkaitan dengan churn.
2. Menentukan segmen pelanggan yang memiliki risiko churn lebih tinggi.
3. Melihat hubungan contract dan tenure terhadap keberlangsungan pelanggan.
4. Memberikan rekomendasi strategi retensi yang dapat digunakan oleh bisnis.

---

## Proses Analisis

### 1. Data Understanding

Pada tahap awal kami melihat:

- Struktur dataset
- Jumlah baris dan kolom
- Tipe data
- Missing value
- Unique value
- Distribusi data
- Variabel yang digunakan sebagai target

`Churn` digunakan sebagai **target**, sedangkan kolom lainnya digunakan sebagai faktor yang dianalisis hubungannya dengan churn.

### 2. Data Cleaning

Beberapa proses cleaning yang dilakukan:

- Mengubah `TotalCharges` menjadi tipe numerik.
- Menangani **11 missing value** pada `TotalCharges`.
- Missing value tersebut diisi dengan `0` karena customer tersebut memiliki `tenure = 0`.
- Mengubah `SeniorCitizen` dari `0/1` menjadi `No/Yes`.
- Mengecek kembali missing value setelah cleaning.
- Mengecek duplicate data.

Hasil pengecekan menunjukkan **tidak terdapat duplicate data**.

### 3. Exploratory Data Analysis

Beberapa analisis yang dilakukan:

- Churn rate
- Churn berdasarkan tenure
- Cohort analysis
- Churn berdasarkan contract
- Churn berdasarkan internet service
- Churn berdasarkan OnlineSecurity dan TechSupport
- Churn berdasarkan payment method
- MonthlyCharges dan churn
- TotalCharges dan tenure

### 4. Statistical Testing

Untuk memastikan pola yang ditemukan bukan hanya berdasarkan visualisasi, kami melakukan beberapa statistical test:

- **Chi-Square Test + Cramer's V** untuk variabel kategorikal dengan Churn
- **Mann-Whitney U Test** untuk membandingkan tenure
- **Independent Sample T-Test** untuk membandingkan MonthlyCharges

---

# Hasil Analisis

## 1. Churn Rate

Dari total **7.043 pelanggan**:

- **5.174 pelanggan (73,5%)** masih bertahan
- **1.869 pelanggan (26,5%)** melakukan churn

Jadi, churn rate keseluruhan pada dataset adalah sekitar **26,5%**.

---

## 2. Tenure dan Early Churn

Salah satu temuan utama adalah pelanggan pada masa awal berlangganan memiliki risiko churn yang lebih tinggi.

Pelanggan dengan tenure **0–12 bulan** memiliki churn rate sekitar **47,44%**.

Sedangkan pelanggan dengan tenure **lebih dari 48 bulan** memiliki churn rate sekitar **9,51%**.

Dari hasil ini terlihat bahwa **tahun pertama menjadi periode yang cukup kritis dalam mempertahankan pelanggan**.

Median tenure:

| Status | Median Tenure |
|---|---:|
| Churn | 10 bulan |
| Retained | 38 bulan |

Hasil statistical testing juga menunjukkan bahwa perbedaan tenure antara pelanggan churn dan retained signifikan.

---

## 3. Contract dan Churn

Jenis kontrak menjadi salah satu faktor yang cukup terlihat hubungannya dengan churn.

| Contract | Churn Rate |
|---|---:|
| Month-to-month | 42,71% |
| One year | 11,27% |
| Two year | 2,83% |

Pelanggan **Month-to-month** memiliki churn rate jauh lebih tinggi dibandingkan pelanggan dengan kontrak 1 tahun dan 2 tahun.

Hasil Chi-Square menunjukkan bahwa hubungan antara jenis kontrak dan churn signifikan secara statistik.

---

## 4. Internet Service

Pelanggan yang menggunakan **Fiber Optic** memiliki churn rate yang cukup tinggi.

Churn rate pelanggan Fiber Optic sekitar:

**41,89%**

Hal ini menjadi perhatian karena pelanggan Fiber Optic juga memiliki biaya bulanan yang relatif tinggi.

Salah satu hal yang perlu diperhatikan adalah apakah harga yang dibayarkan sudah sesuai dengan kualitas layanan yang diterima pelanggan.

---

## 5. Online Security dan Tech Support

Kami juga melihat penggunaan layanan tambahan seperti **OnlineSecurity** dan **TechSupport**.

Hasil analisis menunjukkan:

| Bundling | Churn Rate |
|---|---:|
| No Security/Support | 48,96% |
| Partial Bundling | 21,82% |
| Full Bundling | 9,01% |

Pelanggan yang tidak menggunakan layanan Security/Support memiliki churn rate paling tinggi.

Sedangkan pelanggan yang menggunakan **OnlineSecurity + TechSupport** memiliki churn rate yang jauh lebih rendah.

Hal ini dapat menjadi pertimbangan untuk membuat strategi bundling.

---

## 6. Payment Method

Perbedaan churn juga terlihat berdasarkan metode pembayaran.

Salah satu perhatian dalam analisis adalah pelanggan yang menggunakan **Electronic Check**.

Pelanggan dengan metode pembayaran manual dapat memiliki friction yang lebih tinggi dibandingkan metode pembayaran otomatis.

Karena itu, salah satu rekomendasi yang diberikan adalah mendorong pelanggan untuk menggunakan metode pembayaran yang lebih praktis seperti **auto-pay / automatic payment**.

---

## 7. Monthly Charges

Hasil analisis menunjukkan bahwa pelanggan yang churn memiliki biaya bulanan yang lebih tinggi.

Median Monthly Charges:

| Status | Median Monthly Charges |
|---|---:|
| Churn | sekitar $79,65 |
| Retained | sekitar $64,43 |

Hasil Independent Sample T-Test menunjukkan bahwa perbedaan MonthlyCharges antara kelompok churn dan retained signifikan secara statistik.

Hal ini dapat menjadi indikasi adanya **price sensitivity**, terutama pada pelanggan dengan biaya bulanan yang tinggi.

---

## 8. Total Charges

`TotalCharges` memiliki korelasi yang cukup tinggi dengan `tenure`, yaitu sekitar **0,83**.

Hal ini cukup masuk akal karena total biaya pelanggan sangat berkaitan dengan berapa lama pelanggan sudah menggunakan layanan.

Karena itu, `TotalCharges` tidak bisa langsung dianggap sebagai faktor independen baru karena sebagian besar hubungannya berasal dari lama berlangganan.

---

# Insight Utama

Dari hasil analisis, beberapa insight yang paling penting adalah:

### 1. Pelanggan baru memiliki risiko churn yang tinggi

Pelanggan dengan tenure 0–12 bulan memiliki churn rate sekitar **47,44%**.

### 2. Month-to-month adalah kontrak dengan risiko churn paling tinggi

Churn rate:

- Month-to-month: **42,71%**
- One year: **11,27%**
- Two year: **2,83%**

### 3. Fiber Optic perlu mendapatkan perhatian

Churn rate pelanggan Fiber Optic mencapai **41,89%**.

### 4. Security dan Support berpotensi membantu retensi

Churn rate:

- Tanpa Security/Support: **48,96%**
- Partial Bundling: **21,82%**
- Full Bundling: **9,01%**

### 5. Pelanggan churn cenderung memiliki biaya bulanan lebih tinggi

Hal ini menunjukkan bahwa faktor harga atau value yang diterima pelanggan perlu diperhatikan.

---

# Rekomendasi

Berdasarkan hasil analisis, kami membuat beberapa rekomendasi untuk tim Sales.

## 1. Retention & Onboarding untuk 12 Bulan Pertama

Karena churn tinggi pada pelanggan baru, perusahaan dapat memberikan perhatian lebih selama tahun pertama.

Contohnya:

- Loyalty point pada bulan ke-3, ke-6, dan ke-12
- Follow-up pelanggan baru
- Edukasi penggunaan layanan
- Memastikan tidak ada masalah teknis
- Program khusus sebelum renewal

Tujuannya adalah menjaga pelanggan agar melewati periode awal yang memiliki risiko churn tinggi.

---

## 2. Contract Migration

Untuk pelanggan **Month-to-month**, perusahaan dapat memberikan penawaran agar pelanggan berpindah ke kontrak 1 tahun atau 2 tahun.

Contohnya:

- Diskon untuk beberapa bulan pertama
- Gratis 1 bulan
- Tambahan layanan seperti OnlineSecurity atau TechSupport
- Penawaran bundling

---

## 3. Payment Method Optimization

Mendorong pelanggan dari metode pembayaran manual seperti **Electronic Check** ke metode pembayaran otomatis.

Beberapa cara yang dapat dilakukan:

- Cashback atau potongan tagihan satu kali
- Edukasi mengenai auto-pay
- Notifikasi melalui aplikasi, WhatsApp, atau email
- Membuat proses perubahan metode pembayaran lebih mudah

---

## 4. Fiber Optic + Protection Bundling

Untuk pelanggan Fiber Optic, perusahaan dapat mengevaluasi kembali:

- Kualitas jaringan
- Harga layanan
- Keluhan pelanggan
- Customer experience

Kemudian menawarkan bundling seperti:

**Fiber Optic + OnlineSecurity + TechSupport**

Tujuannya adalah meningkatkan value yang dirasakan pelanggan.

---

# Tools yang Digunakan

Project ini dibuat menggunakan:

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab / Jupyter Notebook

---

# Cara Menjalankan Project

1. Download repository/project ini.
2. Pastikan dataset `Telco_Customer_Churn.csv` tersedia.
3. Buka notebook:

```text
telco_cust_churn_Project.ipynb
```

4. Install library yang dibutuhkan:

```bash
pip install pandas numpy matplotlib seaborn
```

5. Jalankan notebook dari awal sampai akhir.

Dataset dibaca menggunakan:

```python
df_telco = pd.read_csv('Telco_Customer_Churn.csv')
```

---

# Kesimpulan

Dari project ini dapat disimpulkan bahwa **customer churn cukup dipengaruhi oleh beberapa faktor seperti tenure, jenis kontrak, layanan internet, layanan tambahan, dan biaya bulanan**.

Risiko churn paling tinggi terlihat pada:

- Pelanggan baru dengan tenure 0–12 bulan
- Pelanggan dengan kontrak Month-to-month
- Pengguna Fiber Optic
- Pelanggan yang tidak menggunakan Security/Support
- Pelanggan dengan biaya bulanan yang relatif tinggi

Dari hasil tersebut, strategi yang kami rekomendasikan adalah fokus pada **retensi pelanggan baru, mendorong perpindahan kontrak ke jangka panjang, meningkatkan value layanan Fiber Optic, menawarkan bundling Security & Support, dan mendorong penggunaan pembayaran otomatis**.

---

## References

- Kaggle – Telco Customer Churn  
  https://www.kaggle.com/datasets/blastchar/telco-customer-churn

- BISA AI Portfolio  
  https://bisa.ai/portofolio/detail/NTM1MA

- Medium – Customer Churn dengan Supervised Machine Learning  
  https://kakazidane2000.medium.com/memprediksi-customer-churn-dengan-menggunakan-supervised-machine-learning-6b7b945d41a3

- Journal JCI  
  https://journal.jci.co.id/jisbt/article/view/527/226
