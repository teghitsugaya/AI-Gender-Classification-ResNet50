# 🤖 AI - Gender Classification with ResNet50

![image](https://github.com/user-attachments/assets/36a12543-4beb-47ec-8290-3c7cfcf97fe6)

## 📌 Introduction
### 📚 Background
Pengenalan wajah (face recognition) adalah teknologi AI yang digunakan di bidang keamanan, pemasaran, dan interaksi manusia-komputer. Salah satu penerapannya adalah klasifikasi gender berdasarkan citra wajah.
Manfaat klasifikasi gender antara lain untuk analisis demografi, rekomendasi produk atau iklan, statistik pengguna, sistem keamanan, dan smart surveillance. Contoh penerapan seperti pada e-commerce, media sosial, dan survei data pengguna pria/Wanita. 

### ❓ Problem Statement
Meskipun klasifikasi gender tampak sederhana bagi manusia, sistem komputer sering kali menghadapi tantangan seperti pencahayaan tidak konsisten, ekspresi wajah, pose, dan kemiripan visual antar gender. 

<br />

## 💡 Objectives & Scope
### 🎯 Objectives
- Membangun model klasifikasi gender (laki-laki & perempuan) menggunakan algoritma deep learning populer ResNet50
- Melakukan tuning hyperparameter, evaluasi pada algoritma tesebut.
### 📦 Scope
- Mengimplementasikan arsitektur CNN ResNet50 sebagai model klasifikasi.
- Melatih dan menguji model untuk dua kelas saja: laki-laki dan perempuan.
- Tidak mencakup klasifikasi usia, ekspresi wajah, atau identifikasi individu (face recognition berdasarkan identitas unik).
  
<br />

## 🗃️ DataSet
Sumber DataSet berasal dari **Large-scale CelebFaces Attributes (CelebA)**.
https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html

![image](https://github.com/user-attachments/assets/02ce7651-8498-483e-aa99-df22f9a040e7)

#### 📄 Format Data
- Data Set terdiri dari 202.599 jumlah gambar wajah dengan 40 anotasi atribut biner per gambar.
- Dari 202.599 jumlah gambar wajah, diambil 5000 sample jumlah gambar. https://drive.google.com/drive/folders/1BMcCUkpRA99ULUMWYUOboL19Yph2k3Vs

#### ✂️ Pembagian Data
- Dataset dibagi menjadi 2 bagian utama untuk keperluan pelatihan dan pengujian model. (4000 Train Data | 1000 Test Data)

<br />

## 🏷️ Data Atribute
DataSet Memiliki 40 Data Atribute, dan untuk project Gender Classification kita hanya akan menggunakan atribute Male.

![image](https://github.com/user-attachments/assets/17d0daa6-be6b-4d27-a13e-13b1675bc4e5)

<br />

## 📊 Data Distribution
DataSet yang digunakan, memiliki 5000 total sample, dimana 2047 adalah **Male** dan 2953 adalah **Female**. Jika dipersentase kan menjadi 41% Untuk Male dan 59% Untuk Female.
#### 📋 Gender Distribution Table
<img src="https://github.com/user-attachments/assets/a346659f-63fb-4f07-9b2a-541e5acbba07" width=30% height=30%>

#### 📈 Gender Distribution Chart
<img src="https://github.com/user-attachments/assets/49cadd7f-1e41-4785-8f8e-0f472fe4ea49" width=30% height=30%>

<br />

## 🧹 Data Preparation
#### 🔎 Check Data
1. Check Duplicated Data using hashlib (images hash)
2. Delete Duplicated Data

<img src="https://github.com/user-attachments/assets/f9332761-9b6e-4da3-8505-68677b640b3a" width=80% height=80%>

#### 🏷️ Ekstrak Label
1. Ambil Image Atribute Male, ubah label Male dari -1/1 menjadi 0/1. (Male = 1 dan Female = 0).
2. Simpan ke dalam format CSV.
3. Filter Label Data dengan total Image yang ada (5000 images)

<img src="https://github.com/user-attachments/assets/280f6fcd-5cad-4dcb-9858-e6e1b74beae2" width=80% height=80%>

#### ✂️ Split Data
- Split data menjadi 2 bagian, train_data dan test_data.
- Dengan komposisi 80% train_data dan 20% test_data.
  
![image](https://github.com/user-attachments/assets/0afa5809-583b-4874-9df5-0d000c7ebd5d)

<br />

## 🔧 Data Preprocessing
- Augmentation Data
  
![image](https://github.com/user-attachments/assets/5ba9cb15-2e5d-451b-bf99-7981401b3776)
- Preview Images Augmentation Data
  
![image](https://github.com/user-attachments/assets/976eaf15-56ba-4160-8b5b-ce360d1047f0)

<br />

## 🏗️ Model Development
- 🧱 Model Architecture
  
![image](https://github.com/user-attachments/assets/f9ac3540-732d-437e-8d6c-be34f4123655)
- 🎛️ Hyperparameter Tuning
  
![image](https://github.com/user-attachments/assets/56ad19bb-9846-461d-ac71-fb595448d96e)

<br />

## 📈 Model Evaluation
### 🔍 Confusion Matrix

<img src="https://github.com/user-attachments/assets/c8eed8a6-3170-4cb3-b6f3-960ff165dc2d" width=50% height=50%>

Gambar di atas menunjukkan gambar confusion matrix dari hasil klasifikasi jenis kelamin (female dan male).
- Dari total 596 gambar perempuan, sebanyak 590 diklasifikasikan dengan benar sebagai female, sedangkan 6 gambar salah diklasifikasikan sebagai male.
- Dari total 404 gambar laki-laki, sebanyak 388 diklasifikasikan dengan benar sebagai male, sementara 16 gambar salah diklasifikasikan sebagai female.

Secara keseluruhan, model menunjukkan performa klasifikasi yang baik dengan mayoritas prediksi tepat sesuai label sebenarnya.

### 📝 Classification Report
  
![image](https://github.com/user-attachments/assets/e8f3a750-d5a8-4ea5-abf4-b171b690b5ae)

Gambar di atas menunjukkan classification report yang merangkum metrik evaluasi model klasifikasi untuk dua kelas: female dan male. Model klasifikasi menghasilkan akurasi keseluruhan sebesar 0.98 (98%) pada 1.000 data pengujian.

- Kelas female memiliki nilai:
  - Precision: 0.97 → dari semua prediksi "female", 97% benar.
  - Recall: 0.99 → dari semua data sebenarnya "female", 99% berhasil dikenali dengan benar.
  - F1-score: 0.98 → harmonisasi antara precision dan recall menunjukkan performa sangat baik.

- Kelas male memiliki nilai:
  - Precision: 0.98 → dari semua prediksi "male", 98% benar.
  - Recall: 0.96 → dari semua data sebenarnya "male", 96% dikenali dengan benar.
  - F1-score: 0.97 → menunjukkan performa yang juga sangat baik.

Model menunjukkan performa klasifikasi yang sangat baik untuk kedua kelas, dengan akurasi tinggi dan keseimbangan yang baik antara precision dan recall. 

### 📊 Accuracy per Epoch
  
![image](https://github.com/user-attachments/assets/1924ec5a-390d-416a-b695-40cccad3e870)

Gambar di atas merupakan grafik akurasi per epoch untuk data pelatihan (Train Accuracy) dan data pengujian (Test Accuracy).
- Akurasi pelatihan (Train Accuracy) meningkat tajam pada awal pelatihan dan mencapai hampir 100% setelah epoch ke-2, kemudian stabil di angka maksimum hingga epoch ke-9. Hal ini menunjukkan bahwa model mampu belajar sangat baik dari data pelatihan.
- Akurasi pengujian (Test Accuracy) juga mengalami peningkatan pada awal pelatihan, mencapai sekitar 97.9% pada epoch ke-8, namun tidak setinggi akurasi pelatihan dan mengalami sedikit fluktuasi antar epoch.

Model menunjukkan performa yang sangat baik pada data pelatihan, tetapi ada indikasi awal terjadinya overfitting, karena akurasi pada data pengujian cenderung stagnan dan tidak mengikuti peningkatan akurasi pelatihan secara penuh. Meskipun demikian, performa model pada data pengujian tetap tinggi, yang berarti generalisasi model masih cukup baik.

<br />

## ⚖️ Model Comparison
![image](https://github.com/user-attachments/assets/6741aebc-02b4-4745-ac81-2ab0cc1a83c8)

Pada Project ini, saya membandingkan hasil model ResNet50 dengan beberapa model lainnya yang dikerjakan oleh satu tim project, yaitu ResNet18, GoogLeNet, dan VGG19. Didapatkan bahwa:  

- ResNet50 menunjukkan performa terbaik, dengan akurasi tertinggi (98%) dan f1-score rata-rata mendekati 0.97–0.99.
- GoogLeNet memiliki akurasi yang baik (95%), tetapi recall untuk male relatif lebih rendah (0.90).
- ResNet18 memiliki akurasi (94%) dengan precision tinggi pada female (0.96), tetapi recall dan f1-score untuk male sedikit lebih rendah (0.90–0.92).
- VGG19 memberikan hasil yang cukup baik (92% akurasi), tetapi lebih rendah dibanding model lainnya, dengan f1-score rata-rata 0.90–0.94.

<br />
  
## 🌍 Real-World Application
![image](https://github.com/user-attachments/assets/1ce5479c-4568-4f4c-a330-282fbe71b54a)

Gambar di atas menunjukkan contoh penerapan model klasifikasi jenis kelamin di dunia nyata (Real-World Application).
- Gambar sebelah kiri memperlihatkan hasil prediksi terhadap seorang pria, dengan label terprediksi male dan tingkat kepercayaan (confidence) sebesar 0.64.
- Gambar sebelah kanan memperlihatkan hasil prediksi terhadap seorang wanita, dengan label terprediksi female dan tingkat kepercayaan sebesar 0.53.

Meskipun confidence-nya tidak terlalu tinggi, model tetap mampu mengklasifikasikan kedua gambar sesuai dengan jenis kelamin yang benar, menunjukkan kemampuannya untuk digunakan dalam skenario nyata.


<br />

## ✅ Conclusion
ResNet50 menjadi pilihan model terbaik dalam eksperimen ini, menunjukkan kemampuan generalisasi yang baik untuk klasifikasi gender.

## 🔭 Future Deveopment
- Menggunakan Full Dataset Images pada Dataset CelebA (202.599 Data)
- DataSet displit jadi 3 (train, valid, test)
- Eksperimen dengan arsitektur baru
  - EfficientNet
  - Vision Transformer (ViT)
  - ConvNeXt
- Augmentasi tambahan u/ variasi citra (pose, pencahayaan, ekspresi)
  - RandomRotation
  - RandomHorizontalFlip
  - ColorJitter
  - RandomErasing

## 📬 Contact Us
LinkedIn: Teguh Imanto





