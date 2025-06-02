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
Sumber DataSet berasal dari **Large-scale CelebFaces Attributes (CelebA)**
https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html

![image](https://github.com/user-attachments/assets/02ce7651-8498-483e-aa99-df22f9a040e7)

#### Format Data
- Data Set terdiri dari 202.599 jumlah gambar wajah dengan 40 anotasi atribut biner per gambar.
- Dari 202.599 jumlah gambar wajah, diambil 5000 sample jumlah gambar. https://drive.google.com/drive/folders/1BMcCUkpRA99ULUMWYUOboL19Yph2k3Vs

#### Pembagia Data
- Dataset dibagi menjadi 2 bagian utama untuk keperluan pelatihan dan pengujian model. (4000 Train Data | 1000 Test Data)

### Data Atribute
DataSet Memiliki 40 Data Atribute :
![image](https://github.com/user-attachments/assets/17d0daa6-be6b-4d27-a13e-13b1675bc4e5)
- untuk project Gender Classification, Kita hanya akan menggunakan atribute Male

### Data Distribution
DataSet yang digunakan, memiliki 5000 total sample, dimana 2047 adalah Male dan 2953 adalah 2953
#### Gender Distribution Table
![image](https://github.com/user-attachments/assets/5a004979-5d2d-4709-94d3-9bfd31313b44)
Dimana jika dipersentase kan menjadi 41% Untuk Male dan 59% Untuk Female
#### Gender Distribution Chart
![image](https://github.com/user-attachments/assets/49cadd7f-1e41-4785-8f8e-0f472fe4ea49)

### Data Preparation
### Data Preprocessing






## Model 
### Model Development
### Model Evaluation
### Model Comparison

## Real-World Application

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





