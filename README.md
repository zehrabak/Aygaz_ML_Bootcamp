# Aygaz ML Bootcamp: Gözetimli ve Gözetimsiz Öğrenme Karşılaştırması

## Proje Açıklaması
Bu proje kapsamında, **gözetimli** ve **gözetimsiz öğrenme** algoritmalarını aynı veri seti üzerinde karşılaştırdık. Amaç, hangi algoritmanın veri seti üzerinde daha iyi performans gösterdiğini analiz etmek ve seçilen veri setinin hangi öğrenme türü için daha uygun olduğunu belirlemektir.

Kullandığımız veri seti insan kaynakları analitiği üzerine olup, çalışanların işten ayrılma oranlarını ve bu durumla ilişkili diğer değişkenleri incelemektedir.

### Veri Seti
Veri seti, çalışanların işten ayrılma (Attrition) durumu, maaş, departman, seyahat sıklığı gibi değişkenleri içermektedir. Hem sınıflandırma hem de kümeleme algoritmalarının uygulanabileceği yapıda hazırlanmıştır.

- **Bağımlı Değişken (Target):** Attrition (Çalışanların işten ayrılma durumu)
- **Bağımsız Değişkenler:** Maaş, Departman, Seyahat Sıklığı, Yıllık Performans vb.

## Algoritmalar

### 1. Gözetimli Öğrenme (Supervised Learning)
Gözetimli öğrenme kapsamında, **Lojistik Regresyon, Random Forest, XGBoost** gibi sınıflandırma algoritmalarını kullandık. Bu algoritmalar, çalışanların işten ayrılma olasılığını tahmin etmeye çalıştı.

#### En İyi Performans Gösteren Model: **XGBoost**
- **Accuracy:** %97.4
- **Precision:** %95.44
- **Recall:** %89.64
- **F1-Score:** %92.37

XGBoost modeli, hem doğruluk oranı hem de diğer değerlendirme metrikleri açısından en iyi performansı gösterdi.

### 2. Gözetimsiz Öğrenme (Unsupervised Learning)
Gözetimsiz öğrenme algoritmalarında ise **K-Means** ve **Hierarchical Clustering** kullandık. Bu algoritmalar, çalışanların özelliklerine göre kümeler oluşturarak belirli paternler tespit etmeye çalıştı.

#### K-Means Sonuçları
Kümeleme işlemi sonucunda, çalışanlar maaşlarına, departmanlarına ve seyahat sıklıklarına göre anlamlı kümeler oluşturdu. Ancak, modelin performansı sınıflandırma algoritmalarına kıyasla daha düşük kaldı ve verideki paternleri net bir şekilde tespit etmek zor oldu.

## Sonuçlar
Veri seti üzerinde yapılan deneyler, gözetimli öğrenme algoritmalarının gözetimsiz öğrenmeye göre daha başarılı olduğunu göstermektedir. Özellikle sınıflandırma problemi olan "işten ayrılma durumu" (Attrition) gibi durumlarda, gözetimli öğrenme daha uygun sonuçlar vermektedir. Gözetimsiz öğrenme algoritmaları ise daha çok kümeler oluşturmak için kullanışlı olsa da, sınıflandırma için yetersiz kalmıştır.

### Hangi Öğrenme Türü Daha Uygun?
Bu veri seti için gözetimli öğrenme algoritmaları (özellikle XGBoost) daha iyi performans göstermiştir. Çünkü veri setindeki hedef değişken (Attrition) ile ilişkili açık ve net bir sınıflandırma yapılması gerekmektedir. Gözetimsiz öğrenme ise belirli paternleri ortaya çıkarmak için kullanılabilir, ancak sınıflandırma performansı düşük kalmıştır.

### XGBoost Öğrenme Algoritması Neden Seçtiğim Veri Seti İçin Daha Uygun?
Bu veri seti çalışanların işten ayrılma (attrition) durumu ve buna etki eden faktörler üzerine kurulu. Bu tür bir veri setinde XGBoost’un en iyi performansı göstermesinin birkaç önemli nedeni var. İlk olarak, veri seti birçok farklı özelliği (maaş, departman, seyahat sıklığı, çalışma süresi gibi) barındırıyor ve XGBoost, bu özellikler arasındaki karmaşık ilişkileri oldukça etkili bir şekilde öğrenebiliyor. Özellikle hedef değişken olan işten ayrılma durumu ile diğer değişkenler arasındaki ince ilişkileri doğru bir şekilde modelleyebiliyor. Bu, veri setinde bulunan çoklu değişkenlerin etkilerini doğru yansıtabilen bir algoritma kullanmanın önemini gösteriyor.

XGBoost’un bu veri setinde öne çıkmasının bir diğer nedeni ise hız ve doğruluk. Hiperparametre optimizasyonuyla daha da geliştirilebilen XGBoost, hızlı bir öğrenme süreci sunarken yüksek doğruluk oranları elde edebiliyor. Ayrıca, işten ayrılma durumu gibi genellikle dengesiz veri setlerinde, yani "evet" ve "hayır" gibi sınıfların dengesiz dağıldığı durumlarda da oldukça başarılı. XGBoost, azınlık sınıfı (işten ayrılanlar) doğru sınıflandırmada etkili olup, precision ve recall gibi önemli ölçütlerde de güçlü sonuçlar veriyor. Bu sebeplerden dolayı, bu veri seti üzerinde en iyi sonuçları sağlayan model XGBoost oldu ve bu modeli seçmem bu güçlü performansından kaynaklanıyor.

## Kaggle Notebook Linki
Proje notebook'uma [buradan ulaşabilirsiniz](https://www.kaggle.com/code/zehrabak/ml-bootcamp2).
