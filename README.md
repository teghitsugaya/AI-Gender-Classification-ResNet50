# AI - Gender Classification with ResNet50

## Introduction
### Background
Pengenalan wajah (face recognition) adalah teknologi AI yang digunakan di bidang keamanan, pemasaran, dan interaksi manusia-komputer. Salah satu penerapannya adalah klasifikasi gender berdasarkan citra wajah.
Manfaat klasifikasi gender antara lain untuk analisis demografi, rekomendasi produk atau iklan, statistik pengguna, sistem keamanan, dan smart surveillance. Contoh penerapan seperti pada e-commerce, media sosial, dan survei data pengguna pria/Wanita. 

### Problem Statement
Meskipun klasifikasi gender tampak sederhana bagi manusia, sistem komputer sering kali menghadapi tantangan seperti pencahayaan tidak konsisten, ekspresi wajah, pose, dan kemiripan visual antar gender. 


## Objectives & Scope
### 🎯 Objectives
- Membangun model klasifikasi gender (laki-laki & perempuan) menggunakan algoritma deep learning populer ResNet50
- Melakukan tuning hyperparameter, evaluasi pada algoritma tesebut.
### Scope
- Mengimplementasikan arsitektur CNN ResNet50 sebagai model klasifikasi.
- Melatih dan menguji model untuk dua kelas saja: laki-laki dan perempuan.
- Tidak mencakup klasifikasi usia, ekspresi wajah, atau identifikasi individu (face recognition berdasarkan identitas unik).

## Data
### DataSet
Sumber DataSet berasal dari **Large-scale CelebFaces Attributes (CelebA)**.
https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html

![image](https://github.com/user-attachments/assets/02ce7651-8498-483e-aa99-df22f9a040e7)

#### Format Data
- Data Set terdiri dari 202.599 jumlah gambar wajah dengan 40 anotasi atribut biner per gambar.
- Dari 202.599 jumlah gambar wajah, diambil 5000 sample jumlah gambar. https://drive.google.com/drive/folders/1BMcCUkpRA99ULUMWYUOboL19Yph2k3Vs

#### Pembagia Data
- Dataset dibagi menjadi 2 bagian utama untuk keperluan pelatihan dan pengujian model. (4000 Train Data | 1000 Test Data)

### Data Atribute
DataSet Memiliki 40 Data Atribute, dan untuk project Gender Classification kita hanya akan menggunakan atribute Male.

![image](https://github.com/user-attachments/assets/17d0daa6-be6b-4d27-a13e-13b1675bc4e5)

### Data Distribution
DataSet yang digunakan, memiliki 5000 total sample, dimana 2047 adalah Male dan 2953 adalah 2953. Dimana jika dipersentase kan menjadi 41% Untuk Male dan 59% Untuk Female.
#### Gender Distribution Table
![image](https://github.com/user-attachments/assets/5a004979-5d2d-4709-94d3-9bfd31313b44)
#### Gender Distribution Chart
![image](https://github.com/user-attachments/assets/49cadd7f-1e41-4785-8f8e-0f472fe4ea49)

### Data Preparation
#### Ekstrak Label
1. Ambil Image Atribute Male, ubah label Male dari -1/1 menjadi 0/1. (Male = 1 dan Female = 0).
2. Simpan ke dalam format CSV.
3. Filter Label Data dengan total Image yang ada (5000 images)

#### Split Data
- Split data menjadi 2 bagian, train_data dan test_data.
- Dengan komposisi 80% train_data dan 20% test_data.
  
![image](https://github.com/user-attachments/assets/0afa5809-583b-4874-9df5-0d000c7ebd5d)

### Data Preprocessing
- Augmentation Data
  
![image](https://github.com/user-attachments/assets/5ba9cb15-2e5d-451b-bf99-7981401b3776)
- Preview Images Augmentation Data
  
![image](https://github.com/user-attachments/assets/976eaf15-56ba-4160-8b5b-ce360d1047f0)

## Model 
### Model Development
- Model Architecture
  
![image](https://github.com/user-attachments/assets/f9ac3540-732d-437e-8d6c-be34f4123655)
- Hyperparameter Tuning
  
![image](https://github.com/user-attachments/assets/56ad19bb-9846-461d-ac71-fb595448d96e)

### Model Evaluation
- Convolution Matrix
  
![image](https://github.com/user-attachments/assets/c8eed8a6-3170-4cb3-b6f3-960ff165dc2d)

- Accuracy, Precision, Recall & F1-Score
  
![image](https://github.com/user-attachments/assets/e8f3a750-d5a8-4ea5-abf4-b171b690b5ae)

- Accuracy per Epoch
  
![image](https://github.com/user-attachments/assets/1924ec5a-390d-416a-b695-40cccad3e870)

### Model Comparison
![image](https://github.com/user-attachments/assets/6741aebc-02b4-4745-ac81-2ab0cc1a83c8)

- ResNet50 menunjukkan performa terbaik, dengan akurasi tertinggi (98%) dan f1-score rata-rata mendekati 0.97–0.99.
- GoogLeNet memiliki akurasi yang baik (95%), tetapi recall untuk male relatif lebih rendah (0.90).
- ResNet18 memiliki akurasi (94%) dengan precision tinggi pada female (0.96), tetapi recall dan f1-score untuk male sedikit lebih rendah (0.90–0.92).
- VGG19 memberikan hasil yang cukup baik (92% akurasi), tetapi lebih rendah dibanding model lainnya, dengan f1-score rata-rata 0.90–0.94.
  
## Real-World Application
![image](https://github.com/user-attachments/assets/1ce5479c-4568-4f4c-a330-282fbe71b54a)

## Conclusion
- ResNet50 menjadi pilihan model terbaik dalam eksperimen ini, menunjukkan kemampuan generalisasi yang baik untuk klasifikasi gender.
- Meskipun ResNet18, GoogLeNet dan VGG19 dapat digunakan, mereka menunjukkan keterbatasan dalam recall untuk male dan overall accuracy terhadap data test.

## Future Deveopment
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

## Contact Us
LinkedIn: Teguh Imanto





