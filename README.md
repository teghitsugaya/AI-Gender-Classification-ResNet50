# AI - Gender Classification with ResNet50
## Background & Problem Statement
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
Teguh Imanto
LinkedIn: Teguh Imanto





