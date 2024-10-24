# Fish Image Classification

1) Kullanılan Kütüphaneler
- Sayısal işlemler için numpy.
- Veri manipülasyonu ve analizi için pandas.
- Veri görselleştirme için matplotlib.pyplot.
- Derin öğrenme modelini oluşturmak ve eğitmek için tensorflow ve keras.
- Veri ön işleme ve değerlendirme metrikleri için sklearn.
- Gelişmiş veri görselleştirme için seaborn.
- Görüntü işleme için PIL.

2) Veri Hazırlama
- Veri Kümesi Yükleme: Veri kümesi her balık türü için dizinler halinde düzenlenmiştir. Görüntü yolları ve etiketler çıkarılır ve bir pandas DataFrame'de saklanır.
- Veri Bölme: Veriler, sınıf dağılımının korunmasını sağlamak için tabakalı örnekleme kullanılarak eğitim ve test kümelerine (%80 eğitim, %20 test) ayrılır.
- Görüntü Ön İşleme: Görüntüler 128x128 piksele yeniden boyutlandırılır ve 0-1 aralığına normalleştirilir.

3) Model Mimari
- CNN modeli, aşağıdaki katmanlarla TensorFlow ve Keras kullanılarak oluşturulmuştur:
  - Maksimum havuzlama ile üç konvolüsyonel katman.
  - 2D matris verilerini bir vektöre dönüştürmek için bir düzleştirme katmanı.
  - 128 birim ve ReLU aktivasyonuna sahip yoğun bir katman.
  - Çok sınıflı sınıflandırma için softmax aktivasyonlu bir çıktı katmanı.
 
4) Eğitim
- Doğrulukve Kayıp : Modelin performansı, doğruluk ve kayıp ölçütleri ile test seti üzerinde değerlendirilir.
- Karışıklık Matrisi: Modelin farklı sınıflardaki performansını görselleştirmek için bir karışıklık matrisi oluşturulur.
- Sınıflandırma Raporu: Her sınıf için ayrıntılı kesinlik ve geri çağırma sağlanır

5) Tahmin
-Örnek bir görüntü yüklenir, önceden işlenir ve balık türlerini tahmin etmek için eğitilmiş modele beslenir. Tahmin matplotlib kullanılarak görselleştirildi.
