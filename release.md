# Sürüm Notları (Release Notes)

## [v0.2.0] - D2: Uygulama ve Derinleştirme - 2025-12-19
### Eklendi
- **Veri Hattı (Pipeline):** `PlantDoc` veri seti için otomatik temizleme, birleştirme ve train/val/test ayırma scripti (Notebook 1) eklendi.
- **Klasik ML Modelleri:** HOG öznitelikleri ile SVM ve Renk Histogramı ile Random Forest modelleri (Notebook 2) eklendi.
- **YOLOv8 Entegrasyonu:** `ultralytics` kütüphanesi ile sınıflandırma (classification) modu devreye alındı.
- **Veri Artırma (Augmentation):** Eğitim setine RandomRotation ve Flip işlemleri eklendi.

### Değiştirildi
- **Veri Seti:** Proje odağı `PlantVillage` (laboratuvar verisi) yerine `PlantDoc` (tarla verisi) olarak güncellendi.
- **Model Stratejisi:** Tek bir model yerine "2 Klasik + 2 Derin Öğrenme" kıyaslamalı yapıya geçildi.

### Düzeltildi
- `Tomato_two_spotted_spider_mites_leaf` sınıfındaki veri yetersizliği (n=2) tespit edilip veri setinden çıkarıldı.

---

## [v0.1.0] - D1: Proje Ön Teklifi - 2025-11-25
### Eklendi
- Literatür taraması tamamlandı.
- Proje ön teklif raporu hazırlandı.
- Temel gereksinimler belirlendi.