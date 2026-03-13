# Linear-Regression
# Brain Weight Prediction (Beyin Ağırlığı Tahmini) 🧠

Bu proje, bireylerin baş çevresi hacmine (cm³) bakarak **beyin ağırlıklarını (gr) tahmin etmeyi** amaçlayan, **Basit Doğrusal Regresyon (Simple Linear Regression)** kullanılarak geliştirilmiş bir makine öğrenmesi modelidir. Proje Google Colab ortamında Python kullanılarak yazılmıştır.

## 📌 Proje Hakkında
Baş çevresi büyüklüğü ile beynin ağırlığı arasında doğru orantılı bir ilişki bulunmaktadır. Bu çalışmada makine öğrenmesi algoritmalarından Lineer Regresyon kullanılarak, eldeki veriler üzerinden bu ilişki matematiksel bir denkleme (y = ax + b) dönüştürülmüş ve yeni ölçümler için tahmin yapabilen bir sistem kurulmuştur.

## 📊 Veri Seti (`Bascevuz.csv`)
Veri setinde 237 gözlem (satır) bulunmaktadır. Modelin eğitimi sırasında sadece aşağıdaki iki kolon kullanılmıştır:
* **Bağımsız Değişken (X):** `Bas_cevresi(cm^3)` - Bireyin baş çevresi hacmi.
* **Bağımlı / Hedef Değişken (y):** `Beyin_agirligi(gr)` - Bireyin beyin ağırlığı.

## 🛠️ Kullanılan Teknolojiler ve Kütüphaneler
* **Programlama Dili:** Python 3.x
* **Veri İşleme:** Pandas, NumPy
* **Makine Öğrenmesi Modeli:** Scikit-Learn (`LinearRegression`)
* **Veri Görselleştirme:** Matplotlib

## ⚙️ Modelin Çalışma Mantığı
1. **Veri Hazırlığı:** Veri seti bağımlı (y) ve bağımsız (X) değişkenler olarak ayrılmıştır.
2. **Eğitim/Test Bölünmesi:** Modelin ne kadar iyi öğrendiğini test edebilmek için veri %70 Eğitim (Train) ve %30 Test olarak ikiye bölünmüştür (`test_size=0.3`).
3. **Model Eğitimi:** `LinearRegression` algoritması eğitim verisi üzerinde uygulanarak en uygun doğru uydurulmuştur.
4. **Grafik Çizimi:** Hem eğitim hem de test veri setleri için, gerçek değerler ve modelin oluşturduğu regresyon doğrusu Matplotlib ile görselleştirilmiştir.

## 🚀 Model Denklemi
Eğitilen Lineer Regresyon modelinin katsayıları (eğim ve kesen) hesaplanarak aşağıdaki formül elde edilmiştir:

* **Eğim (Q1 - Coef):** 0.255
* **Kesen (Q0 - Intercept):** 354.84

**Regresyon Denklemi:** `y = 0.25x + 354.84`  
*(Burada x baş çevresi hacmini, y ise tahmini beyin ağırlığını ifade eder.)*

## 📈 Model Performansı ve Sonuçlar
Test verisi (%30) üzerinden yapılan değerlendirmede modelin hata ve başarı metrikleri aşağıdaki gibi hesaplanmıştır:

* **R-Kare (R² Score):** 0.658 
  *(Modelin bağımlı değişkendeki varyansın yaklaşık %66'sını açıklayabildiğini gösterir.)*
* **Ortalama Mutlak Hata (MAE):** 59.16 gr
* **Ortalama Kare Hata (MSE):** 5337.94
* **Ortalama Kare Hatanın Karekökü (RMSE):** 73.06 gr
* **Medyan Mutlak Hata:** 47.69 gr
* **Ortalama Mutlak Yüzde Hatası (MAPE):** %4.64

**Sonuç:** Modelimiz, ortalama %4.6'lık bir yanılma payı ile beyin ağırlığını başarılı bir şekilde tahmin etmektedir. Hata payının (RMSE) yaklaşık 73 gram olması, tıp ve biyoloji alanlarındaki basit tahminler için kabul edilebilir düzeydedir.
