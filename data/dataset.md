# 📦 Veri Seti Bilgileri

## PlantDoc Veri Seti

Bu proje **PlantDoc** veri setini kullanmaktadır. Veri seti bitki yapraklarındaki hastalıkları tespit etmek için kullanılan gerçek dünya görüntülerinden oluşmaktadır.

## 📥 İndirme

Veri seti dosyası çok büyük olduğu için doğrudan repository'ye yüklenememiştir. Veri setini indirmek için aşağıdaki Google Drive linkini kullanabilirsiniz:

**https://drive.google.com/drive/folders/1TtqrnHW8uzxpF993yuUbOufDWBtjGxaT?usp=sharing**

## 📋 Veri Seti Yapısı

### Orijinal Veri Seti (PlantDoc-Original)

İndirdiğiniz veri setini `data/` klasörüne çıkardıktan sonra yapı şu şekilde olmalıdır:

```
data/
└── PlantDoc-Original/
    ├── train/
    │   ├── Apple_leaf/
    │   │   ├── image1.jpg
    │   │   ├── image2.jpg
    │   │   └── ...
    │   ├── Raspberry_leaf/
    │   │   ├── image1.jpg
    │   │   └── ...
    │   ├── Tomato_mold_leaf/
    │   │   └── ...
    │   └── ... (diğer sınıflar)
    └── test/
        ├── Apple_leaf/
        │   ├── image1.jpg
        │   └── ...
        ├── Raspberry_leaf/
        │   └── ...
        └── ... (diğer sınıflar)
```

### Bölünmüş Veri Seti (PlantDoc-Split)

`Notebook_1_Veri_Hazirligi.ipynb` çalıştırıldıktan sonra oluşan yapı:

```
data/
└── PlantDoc-Split/
    ├── train/
    │   ├── Apple_leaf/
    │   │   ├── image1.jpg
    │   │   └── ...
    │   ├── Raspberry_leaf/
    │   │   └── ...
    │   └── ... (diğer sınıflar)
    ├── val/
    │   ├── Apple_leaf/
    │   │   └── ...
    │   ├── Raspberry_leaf/
    │   │   └── ...
    │   └── ... (diğer sınıflar)
    └── test/
        ├── Apple_leaf/
        │   └── ...
        ├── Raspberry_leaf/
        │   └── ...
        └── ... (diğer sınıflar)
```

## 🔧 Kurulum Adımları

1. Yukarıdaki Google Drive linkinden veri setini indirin
2. İndirdiğiniz zip/rar dosyasını `data/` klasörüne çıkarın
3. Çıkarılan klasörün adının `PlantDoc-Original` olduğundan emin olun
4. Orijinal veri seti yapısını kontrol edin: `train/` ve `test/` klasörleri altında sınıf klasörleri (örn: `Apple_leaf/`, `Raspberry_leaf/`) olmalıdır
5. `src/Notebook_1_Veri_Hazirligi.ipynb` notebook'unu çalıştırarak veri setini train/val/test olarak bölün
6. Notebook çalıştıktan sonra `data/PlantDoc-Split/` klasörü oluşacak ve içinde `train/`, `val/`, `test/` klasörleri bulunacaktır

## ⚠️ Önemli Notlar

- Veri seti dosyası büyük olabilir, indirme süresi internet hızınıza bağlıdır
- Veri setini indirdikten sonra `Notebook_1_Veri_Hazirligi.ipynb` notebook'unu mutlaka çalıştırın
- Veri seti lisans koşullarına dikkat ediniz
- **Çıkarılan Sınıf**: `Tomato_two_spotted_spider_mites_leaf` sınıfı yeterli görüntü sayısına sahip olmadığı için veri setinden çıkarılmıştır. Bu sınıf orijinal veri setinde bulunabilir ancak model eğitimi için kullanılmamıştır.

## 📊 Veri Seti İstatistikleri

- **Toplam Görüntü Sayısı**: [Veri seti indirildikten sonra güncellenecek]
- **Sınıf Sayısı**: [Veri seti indirildikten sonra güncellenecek]
- **Görüntü Formatı**: JPG, PNG
- **Çözünürlük**: Değişken

## 🔗 Alternatif Kaynaklar

Eğer Google Drive linki çalışmıyorsa veya alternatif bir kaynak arıyorsanız:

- https://www.kaggle.com/datasets/nirmalsankalana/plantdoc-dataset