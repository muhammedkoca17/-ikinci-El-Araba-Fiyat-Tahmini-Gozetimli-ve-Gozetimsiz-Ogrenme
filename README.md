# İkinci-El-Araba-Fiyat-Tahmini-Gözetimli-ve-Gözetimsiz-renme
Colab üzerinden aynı veri seti üzerinden gözetimli öğrenmede GradientBoostingRegressor algoritması gözetimsiz öğrenmede K-Means ile başarı oranları karşılaştırılmıştır.

# Kaggle Proje Linki
https://www.kaggle.com/code/muhammedkoca/arac-fiyat-tahmini

# Projenin Amacı
Bu proje Veri seti, amerika da ikinci el araç fiyatlarının açık arttırma da fiyat tahmini yapmaktadır. İnternet üzerindeki dış kaynaklardan toplanan verilerden oluşmaktadır. Veri seti 2015 yılında toplanmıştır.

# Veri Seti
Kullanılan veri seti, 558811 satırdan oluşmaktadır.
**-year:** araç üretim yılı
**-make:** araç üretici firma
**-model:** aracın modeli
**-trim:** donanım paketi hakkında bilgi vermektedir
**-body:** araç gövdesi hakkında bilgiler vermektedir.
**-transmiision:** sansıman hakkında bilgiler.
**-vin:** benzersiz araç kimlik numarasını vermektedir
**-state:** aracın kayıtlı olduğu eyalet vermektedir.
**-condition:** aracın ilk günkü haliden kalan kondisyon puan üzerinden değeri.
**-odometer:** aracın km sayacı
**-color:** araç dış renk
**-interior:** araç iç renk
**-seller:** aracı satan firma
**-mmr:** aracın piyasa değeri
**-sellingprice:** aracın satış fiyatı
**-saledate:** aracın satıs fiyatı

# Değişekenler
Bağımlı değişken(y) "satış fiyatı" sütunu, bağımsız değişkenler(x) ise "satış fiyatı" sütunu hariç tüm satırlar olarak belirlenmiştir. Çeşitli regresyon algoritmaları denenerek bağımlı değişkeni bulmaya çalışılır. Bu projede kullanılan regresyon algoritmaları:

from sklearn.linear_model import LinearRegression, Ridge, Lasso, ElasticNet, BayesianRidge
from sklearn.neighbors import KNeighborsRegressor
from sklearn.tree import DecisionTreeRegressor
from sklearn.ensemble import RandomForestRegressor, GradientBoostingRegressor
from sklearn.model_selection import cross_validate
from sklearn.metrics import r2_score,mean_squared_error

# Model Seçimi
En iyi performansı veren algoritma seçilir, onun için R-kare, modelinizin veri setindeki değişkenliği ne kadar açıkladığını gösterir. 1.0 değeri mükemmel uyumu, 0.0 değeri ise hiçbir uyumu ifade etmez. hiperparametre optimize edilir ve seçilen algoritmanın değerlendirilmesi yapılır. Bu yüzden cross validationdan sonuc olarak en iyi performansı gösteren model, RANDOM FOREST REGRESSION olarak belirlenmiştir. Daha sonra değerlendirme sürecinde bu projede **Ortalama Karesel Hata(Mean Squared Error)**, **Ortalama Mutlak Hata(Mean Absolute Error)** kullanılmıştır.
