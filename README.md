# 🌱 Sürdürülebilir Tarım İçin Derin Öğrenme Destekli Bitki Hastalığı Tespiti

Bu proje, bitki yapraklarındaki hastalıkları tespit etmek amacıyla geliştirilmiş hibrit bir makine öğrenmesi ve derin öğrenme çalışmasıdır. Proje kapsamında gürültülü arka plana sahip gerçek dünya verileri (**PlantDoc**) kullanılarak Klasik ML ve Modern DL mimarileri kıyaslanmıştır.

## 📋 İçindekiler

- [Özellikler](#-özellikler)
- [Gereksinimler](#-gereksinimler)
- [Kurulum](#-kurulum)
- [Kullanım](#-kullanım)
- [Proje Yapısı](#-proje-yapısı)
- [Veri Seti](#-veri-seti)
- [Modeller](#-modeller)
- [Sonuçlar](#-sonuçlar)
- [Lisans](#-lisans)

## ✨ Özellikler

- **Klasik Makine Öğrenmesi Modelleri**: HOG (Histogram of Oriented Gradients) + SVM ve Renk Özellikleri + Random Forest
- **Derin Öğrenme Modelleri**: ResNet50 Transfer Learning ve YOLOv8 Classification
- **Ablation Study**: YOLOv8 için farklı model boyutları ve hiperparametrelerin sistematik testi
- **Gerçek Dünya Verisi**: PlantDoc veri seti ile gürültülü arka plana sahip gerçek görüntüler
- **Kapsamlı Karşılaştırma**: Farklı yaklaşımların performans analizi
- **Jupyter Notebook Tabanlı**: Adım adım açıklamalı ve tekrarlanabilir deneyler

## 🔧 Gereksinimler

### Sistem Gereksinimleri

- Python 3.8 veya üzeri
- CUDA destekli GPU (önerilir, ancak CPU ile de çalışır)
- En az 8GB RAM (16GB önerilir)
- En az 10GB boş disk alanı (veri seti ve model ağırlıkları için)

### Python Kütüphaneleri

Tüm gerekli kütüphaneler `requirements.txt` dosyasında listelenmiştir:

- `numpy` - Sayısal hesaplamalar
- `matplotlib` - Görselleştirme
- `opencv-python` - Görüntü işleme
- `scikit-learn` - Klasik ML algoritmaları
- `scikit-image` - Görüntü işleme yardımcıları
- `torch` - PyTorch derin öğrenme framework'ü
- `torchvision` - PyTorch görüntü işleme araçları
- `ultralytics` - YOLOv8 için
- `pandas` - Veri manipülasyonu
- `jupyter` - Jupyter notebook ortamı
- `notebook` - Jupyter notebook sunucusu

## 🚀 Kurulum

### 1. Repository'yi Klonlayın

```bash
git clone https://github.com/kullanici-adi/Plant-Disease-Detection-Final-Project.git
cd Plant-Disease-Detection-Final-Project
```

### 2. Sanal Ortam Oluşturun (Önerilir)

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**Linux/Mac:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Bağımlılıkları Yükleyin

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

**Not:** PyTorch'u CUDA desteği ile yüklemek için [PyTorch resmi sitesinden](https://pytorch.org/get-started/locally/) uygun komutu kullanabilirsiniz.

### 4. Veri Setini Hazırlayın

Veri seti dosyası çok büyük olduğu için doğrudan repository'ye yüklenmemiştir. Veri setine erişim için:

1. `data/dataset.md` dosyasındaki Google Drive linkini takip edin
2. Veri setini indirin
3. İndirdiğiniz dosyayı `data/` klasörüne çıkarın
4. Veri seti yapısı şu şekilde olmalıdır:
   ```
   data/
   └── PlantDoc-Original/
       ├── Class1/
       │   ├── image1.jpg
       │   └── image2.jpg
       ├── Class2/
       └── ...
   ```

## 📖 Kullanım

### Adım 1: Veri Hazırlama

İlk notebook'u çalıştırarak veri setini train/val/test olarak bölün:

```bash
jupyter notebook src/Notebook_1_Veri_Hazirligi.ipynb
```

Bu notebook:
- Veri setini tarar
- Sınıfları belirler
- Veriyi train (%70), validation (%15) ve test (%15) olarak böler
- `PlantDoc-Split/` klasörünü oluşturur

### Adım 2: Klasik ML Modelleri

```bash
jupyter notebook src/Notebook_2_Klasik_ML.ipynb
```

Bu notebook:
- HOG özellik çıkarımı + SVM modeli eğitir
- Renk histogramı özellikleri + Random Forest modeli eğitir
- Her iki modelin performansını değerlendirir

### Adım 3: ResNet50 Transfer Learning

```bash
jupyter notebook src/Notebook_3_ResNet50.ipynb
```

Bu notebook:
- ImageNet'te önceden eğitilmiş ResNet50 modelini yükler
- Transfer learning ile bitki hastalığı tespiti için fine-tuning yapar
- Model ağırlıklarını `outputs/` klasörüne kaydeder

### Adım 4: YOLOv8 Classification

```bash
jupyter notebook src/Notebook_4_YOLOv8.ipynb
```

Bu notebook:
- YOLOv8n-cls modelini kullanır
- Classification görevi için eğitir
- Eğitim sonuçlarını ve metrikleri görselleştirir

### Adım 5: YOLOv8 Ablation Study

```bash
jupyter notebook src/Notebook_5_ablation.ipynb
```

Bu notebook:
- YOLOv8 için sistematik hiperparametre testi yapar
- Farklı model boyutları (yolov8s-cls, yolov8m-cls) test eder
- Farklı learning rate değerleri (0.001, 0.0001) karşılaştırır
- Sonuçları tablo formatında kaydeder
- En iyi hiperparametre kombinasyonunu belirler

## 📂 Proje Yapısı

```
Plant-Disease-Detection-Final-Project/
├── data/                          # Veri seti klasörü
│   ├── PlantDoc-Original/        # Orijinal veri seti (indirilecek)
│   ├── PlantDoc-Split/           # Bölünmüş veri seti (Notebook 1 oluşturur)
│   └── dataset.md                # Veri seti indirme linki
├── src/                          # Kaynak kodlar
│   ├── Notebook_1_Veri_Hazirligi.ipynb    # Veri hazırlama
│   ├── Notebook_2_Klasik_ML.ipynb         # Klasik ML modelleri
│   ├── Notebook_3_ResNet50.ipynb          # ResNet50 modeli
│   ├── Notebook_4_YOLOv8.ipynb           # YOLOv8 modeli
│   └── Notebook_5_ablation.ipynb         # YOLOv8 ablation study
├── outputs/                      # Model çıktıları
│   ├── resnet50_plantdoc.pth     # Eğitilmiş ResNet50 ağırlıkları
│   ├── yolo11n.pt                # YOLO model ağırlıkları
│   └── PlantDoc_YOLO_Project/    # YOLO eğitim sonuçları
├── reports/                      # Raporlar ve dokümantasyon
│   ├── paper_eng.pdf             # İngilizce makale
│   ├── paper_eng.docx            # İngilizce makale (Word)
│   ├── paper_tr.pdf              # Türkçe makale
│   └── paper_tr.docx             # Türkçe makale (Word)
├── requirements.txt              # Python bağımlılıkları
└── README.md                     # Bu dosya
```

## 📊 Veri Seti

Bu proje **PlantDoc** veri setini kullanmaktadır. Veri seti hakkında detaylı bilgi ve indirme linki için `data/dataset.md` dosyasına bakınız.

**Önemli Not:** Veri seti dosyası çok büyük olduğu için doğrudan repository'ye yüklenmemiştir. Veri setine erişim için `data/dataset.md` dosyasındaki linki kullanın.

## 🤖 Modeller

### 1. Klasik Makine Öğrenmesi

- **HOG + SVM**: Histogram of Oriented Gradients özellik çıkarımı ile Support Vector Machine
- **Renk + Random Forest**: Renk histogramı özellikleri ile Random Forest Classifier

### 2. Derin Öğrenme

- **ResNet50**: ImageNet'te önceden eğitilmiş ResNet50 modeli ile transfer learning
- **YOLOv8 Classification**: Ultralytics YOLOv8 classification modelleri
  - **YOLOv8n-cls**: Nano model (temel eğitim)
  - **YOLOv8s-cls**: Small model (ablation study)
  - **YOLOv8m-cls**: Medium model (ablation study)
- **Ablation Study**: Farklı model boyutları ve learning rate değerlerinin sistematik testi

## 📈 Sonuçlar

Model performans sonuçları ve karşılaştırmalar `reports/` klasöründeki makale dosyalarında detaylı olarak açıklanmıştır.

## 📄 Lisans

Bu proje açık kaynaklıdır ve MIT Lisansı altında lisanslanmıştır. Detaylar için `LICENSE` dosyasına bakınız.

**Lisans Notu:** Bu projeyi kullanırken:
- PlantDoc veri setinin kendi lisans koşullarına dikkat ediniz
- PyTorch, Ultralytics ve diğer kullanılan kütüphanelerin lisans koşullarını kontrol ediniz
- Ticari kullanım için gerekli izinleri alınız


- PlantDoc veri seti oluşturucularına
- PyTorch ve Ultralytics topluluklarına
- Açık kaynak topluluğuna

## 📚 Referanslar

- PlantDoc: [Veri seti referansı]
- ResNet: [ResNet paper referansı]
- YOLOv8: [YOLOv8 dokümantasyonu](https://docs.ultralytics.com/)

---

**Not:** Bu proje akademik/araştırma amaçlı geliştirilmiştir. Ticari kullanım için gerekli lisansları ve izinleri almayı unutmayınız.
