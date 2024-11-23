# OpenCV Threshold

---

> [!faq] Nedir?
> Threshold eşik değeridir ve görüntüden detayları çıkarmamıza yarar.

---

## Nasıl Kullanılır?

Bu işlemi `threshold()` fonksiyonu ile gerçekleştirebiliriz.
Bu fonksiyon içine parametre olarak önce işlenecek görseli alır,
devamında `thresh` yani minimum değer sonra `maxval` yani maximum değer
ve son olarak ise `type` yani değer aralığını gireriz.

İşte basit bir örnek:

```python
img = cv.imread("Photos/cats.jpg")
imgGray = cv.cvtColor(img, cv.COLOR_BGR2GRAY)

_, imgThreshed = cv.threshold(imgGray, 100, 255, cv.THRESH_BINARY_INV)
```

Şimdi bu eşik işlemini yaptık ama bir sorun var bu eşikleme sadece piksel
değerlerine baktığı için bazen çok tuhaf çıktılar alabiliyoruz bu sebeple
daha karmaşık bir algoritması olan `adaptiveThreshold()` fonksiyonunu
kullanabiliriz.

Bu fonksiyon içine parametre olarak önce işlenecek görseli alır, devamında
maksimum değeri gireriz, daha sonra ise içine fonksiyonun kullanacağı algoritmayı
alır, dördüncü olarak ise eşik aralığını gireriz, en son olarak ise algoritmaya göre
pixel oranı ve ortalama aralık girilebilir.

İşte ADAPTIVE_THRESH_MEAN_C algoritmasını kullanan bir örnek:

```python
img = cv.imread("Photos/cat.jpg")
imgGray = cv.cvtColor(img, cv.COLOR_BGR2GRAY)

imgThreshed = cv.adaptiveThreshold(
    imgGray,                    # İşlencek resim
    255,                        # Üst sınır
    cv.ADAPTIVE_THRESH_MEAN_C,  # Adaptiv thresh algoritması
    cv.THRESH_BINARY,           # Thresh skalası
    11,                         # Blok skalası
    8,                          # Ortalama C degeri
)
```
