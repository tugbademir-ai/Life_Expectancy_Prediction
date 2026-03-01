# Makine Öğrenmesi ile Beklenen Yaşam Süresi Analizi
Bu proje, Dünya Sağlık Örgütü (WHO) verilerini kullanarak ülkelerin beklenen yaşam sürelerini (Life Expectancy) tahmin etmeyi amaçlayan bir veri bilimi ve makine öğrenmesi çalışmasıdır. 

## Projenin Özellikleri
* **Data Leakage (Veri Sızıntısı) Önlemi:** Eksik veriler (NaN) doldurulurken, modelin geleceği görmesini engellemek adına veri seti *önce* Train ve Test olarak ikiye bölünmüştür. Test verisindeki boşluklar, gerçek hayat senaryosuna sadık kalınarak Train verisinin istatistikleriyle doldurulmuştur.
* **Gelişmiş Eksik Veri İşleme (Imputation):** Yıllara göre değişen verilerdeki boşluklar, düz bir ortalama yerine `interpolate` (enterpolasyon) yöntemiyle doldurularak zaman serisi yapısı korunmuştur.
* **Keşifsel Veri Analizi (EDA) ve Görselleştirme:**Hedef değişkenin dağılımı ve model tahmin başarıları Matplotlib ve Seaborn kullanılarak görselleştirilmiştir.
* **Çoklu Doğrusallık (Multicollinearity) Kontrolü:** Korelasyon matrisi incelenerek birbirini gereksiz tekrar eden bağımsız değişkenler veri setinden çıkarılmıştır.
* **Düzenlileştirme ve Optimizasyon:** Lasso, Ridge ve ElasticNet gibi cezalandırıcı modellerin yanı sıra, Karar Ağacı (Decision Tree) modeli için `GridSearchCV` kullanılarak hiperparametre optimizasyonu (`max_depth`, `min_samples_leaf` vb.) gerçekleştirilmiştir.

## Kullanılan Teknolojiler
* **Dil:** Python
* **Veri İşleme:** Pandas, NumPy
* **Görselleştirme:** Matplotlib, Seaborn
* **Makine Öğrenmesi:** Scikit-Learn (Linear Regression, Ridge, Lasso, ElasticNet, Decision Tree, GridSearchCV, StandardScaler)

## Sonuçlar
Optimizasyon işlemleri sonucunda, model test veri seti üzerinde başarılı bir tahmin performansı sergilemiş ve beklenen yaşam süresindeki değişimleri yüksek oranda açıklayabilmiştir (R2 Score: ~0.916). Karar Ağacı modelinin tahmin başarısı ve hedef değişkenin dağılımı görselleştirilerek analiz edilmiştir.
