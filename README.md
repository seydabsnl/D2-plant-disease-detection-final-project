# Sürdürülebilir Tarım İçin Derin Öğrenme Destekli Bitki Hastalığı Tespiti

Bu proje, bitki yapraklarındaki hastalıkları tespit etmek amacıyla geliştirilmiş hibrit bir makine öğrenmesi ve derin öğrenme çalışmasıdır. Proje kapsamında gürültülü arka plana sahip gerçek dünya verileri (**PlantDoc**) kullanılarak Klasik ML ve Modern DL mimarileri kıyaslanmıştır.

## 📂 Proje Yapısı

```text
.
├── PlantDoc-Split/          # Eğitim/Test/Val olarak ayrılmış veri seti (Notebook 1 oluşturur)
├── Notebook_1_Veri_Hazirligi.ipynb  # Veri temizleme, birleştirme ve split işlemleri
├── Notebook_2_Klasik_ML.ipynb       # HOG+SVM ve Renk+RF modelleri (Baseline)
├── Notebook_3_ResNet50.ipynb        # PyTorch ile ResNet50 Transfer Learning
├── Notebook_4_YOLOv8.ipynb          # Ultralytics ile YOLOv8 Classification
├── requirements.txt                 # Gerekli kütüphaneler
└── README.md                        # Proje dokümantasyonu