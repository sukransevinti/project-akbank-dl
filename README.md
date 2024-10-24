# Balık Türlerini Sınıflandırma Projesi

Bu proje, görüntü işleme ve yapay sinir ağları (ANN) kullanarak balık türlerini sınıflandırmayı amaçlamaktadır. Farklı balık türlerine ait .png formatındaki görüntülerden yararlanarak, bu türlerin doğru ve otomatik tanımlanmasını hedefliyoruz.

## İçindekiler
- [Proje Hakkında](#proje-hakkında)
- [Veri Seti](#veri-seti)
- [Ön İşleme](#ön-i̇şleme)
- [Model Mimarisi](#model-mimarisi)
- [Performans Değerlendirme](#performans-değerlendirme)
- [Kurulum](#kurulum)
- [Kullanım](#kullanım)

## Proje Hakkında
Bu projede, balık türlerinin görüntülerden otomatik olarak tanımlanması için bir yapay sinir ağı modeli geliştirilmiştir. Model, eğitilmiş görüntü verilerini analiz ederek her bir balık türünü yüksek bir doğruluk oranıyla sınıflandırır. Bu, balıkçılık ve biyolojik araştırmalarda büyük kolaylık sağlamaktadır.

## Veri Seti
- **Görüntüler:** Veri seti, her biri 128x128 boyutunda olan çok sayıda balık türü görüntüsünü içermektedir. Bu görüntüler, farklı açılardan ve koşullardan çekilmiştir.
- **Organizasyon:** Görüntüler, her tür için ayrı klasörlerde düzenlenmiştir. Bu yapı, etiketleme sürecini kolaylaştırmaktadır.

## Ön İşleme
- **Görüntü Normalizasyonu:** Modelin daha iyi öğrenebilmesi için görüntüler, 0 ile 1 arasında bir değere normalize edilmiştir. Bu işlem, modelin eğitim sürecini hızlandırır.
- **Etiket Dönüşümü:** Balık türlerini temsil eden etiketler, sayısal formatta bir diziye dönüştürülmüştür. Bu, modelin bu etiketlerle çalışmasını kolaylaştırır.

## Model Mimarisi
- **Katman Yapısı:** Model, iki yoğun katman (dense layer) ve dropout katmanları içermektedir. Bu yapı, aşırı öğrenmeyi (overfitting) önlemek için tasarlanmıştır.
  - **Birinci Katman:** 256 nöron içerir ve ReLU aktivasyon fonksiyonu kullanır.
  - **İkinci Katman:** 128 nöron içerir ve yine ReLU aktivasyon fonksiyonu kullanır.
- **Çıkış Katmanı:** Son katman, softmax aktivasyon fonksiyonu ile her bir balık türü için olasılık değerleri üretir.
- **Derleme:** Model, Adam optimizer ve categorical crossentropy kayıp fonksiyonu ile derlenmiştir.

## Performans Değerlendirme
- Modelin eğitim ve doğrulama süreçlerinde elde edilen doğruluk ve kayıp değerleri dikkatlice analiz edilmiştir.
- **Karışıklık Matrisi:** Modelin performansını değerlendirmek için bir karışıklık matrisi oluşturulmuştur. Bu matris, tahmin edilen etiketler ile gerçek etiketler arasındaki ilişkiyi gösterir.
- **Sınıflandırma Raporu:** Modelin sınıflandırma başarısını detaylandıran bir rapor üretilmiştir. Bu rapor, her bir sınıf için doğruluk, hatalar ve diğer metrikleri içerir.


[Kaggle Linki](https://www.kaggle.com/code/baharsevinti/project-dl-akbank)