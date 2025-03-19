# Mlp
# YZM304 Derin Öğrenme Projesi 1: Çok Katmanlı Perceptron Uygulaması

## Proje Özeti
Bu proje, BankNote Authentication veri seti için Çok Katmanlı Perceptron (MLP) sinir ağlarını iki farklı şekilde uygular:
1. **Derin Öğrenme Kütüphaneleri Kullanmadan** - NumPy uygulaması
2. **Keras Kullanarak** - Keras'ı 2-layer için kullanan uygulama

Proje, ikili sınıflandırma için 2-Katmanlı ve 3-Katmanlı sinir ağı mimarilerinin performansını karşılaştırır.


## Uygulama Ayrıntıları

### Her İki Uygulamaya da Ortak
- Veri ön işleme ile rasgele karıştırma (random_state=42)
- 80/20 eğitim/test bölünmesi (sınıflandırma ile)
- Gizli katmanlar için ReLU aktivasyonu
- Çıkış katmanı için sigmoid aktivasyonu
- İkili sınıflandırma görevi

### NumPy Uygulaması (`mlp_wolibs.ipynb`)
- Manuel olarak uygulanması:
  - İleri yayılım
  - Geri yayılım
  - Ağırlık güncellemeleri
  - Maliyet hesabı
- Hem 2-katmanlı hem de 3-katmanlı mimariler, gizli katmanlarda 5 nöron ile
- Özel eşik için tahmin (0.44942162)

### Keras Uygulaması (`mlp_wlibs.ipynb`)
- Sıralı model API'si
- Erken durdurma ve model denetleme noktası
- İkili çapraz entropi kaybı fonksiyonu
- Eğitim sırasında doğrulama bölünmesi
- Test kümesinde performans değerlendirmesi

## Sonuçlar

### NumPy Uygulaması
- **2-Katmanlı Model**:
  - Doğruluk: 0.8691
  - Hassasiyet: 0.8209
  - Geri Çağırma: 0.9016
  - F1 Skoru: 0.8594

- **3-Katmanlı Model**:
  - Doğruluk: 0.7491
  - Hassasiyet: 0.6879
  - Geri Çağırma: 0.7951
  - F1 Skoru: 0.7376

### Keras Uygulaması (2-layer için)
- Doğruluk: 0.8218
- Kayıp: 0.5186

## Ana Bulgular
1. Özel uygulamada 2-katmanlı model, 3-katmanlı modelden daha iyi performans gösterdi, bu da daha basit mimarinin bu problem için yeterli olduğunu gösteriyor.
2. Özel uygulamanın 2-katmanlı modeli, Keras uygulamasından daha iyi performans gösterdi, muhtemelen özel eşik ayarlamasından dolayı.
3. Keras uygulaması, yerleşik düzenleme ve optimizasyon yetenekleri ile daha akıcı bir yaklaşım sağlar.


## Proje Yapısı
- `mlp_wolibs.ipynb`: NumPy kullanarak özel MLP uygulaması
- `mlp_wlibs.ipynb`: Keras kullanarak MLP uygulaması
- `BankNote_Authentication.csv`: Veri seti (depo içinde dahil değildir)
- `README.md`: Proje belgeleri


## Kullanılan Kaynaklar
- https://www.kaggle.com/code/androbomb/simple-nn-with-python-multi-layer-perceptron
