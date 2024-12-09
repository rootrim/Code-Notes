# OpenCV Scheme Pairing

---

> [!faq] Nedir?
> Şablon eşleme, bir şablon görüntünün konumunu başka bir
> görselde aramak ve bulmaktır.
>
> Ana görselin üzerine şemayı kaydırır ve karşılaştırma yapar.

---

## Nasıl Yapılır?

Şema eşleme yapmak için bir görsele ve bir maske görsele ihtiyacımız
var. Bu maske görselini ana görselden kesmiş olmamız lazım.

Bundan sonra ise bir OpenCV'nin bize sunduğu algoritmalardan birini
seçmemiz lazım. Bunlar şunlardır:

- TM_CCOEFF
- TM_CCOEFF_NORMED
- TM_CCORR
- TM_CCORR_NORMED
- TM_SQDIFF
- TM_SQDIFF_NORMED

Bu algoritmaları `matchTemplate()` fonksiyonu ile birlikte kullanarak
bir tane tespit görseli alırız. Bu fonksiyon içine sırasıyla görseli,
şemayı ve algoritmayı alır.

Bu fonksiyonun çıktısını kullanabilmek için `minMaxLoc()` fonksiyonunu
kullanırız. Bu fonksiyon içine sadece tespit görselini alır ama çıktı
olarak sırasıyla minimum değer, maxsimum değer, minimum lokasyon ve
maxsimum lokasyon değerlerini alır.

Bu değerleri de sol üst ve sağ alt köşeleri bulmak için kullanırız.
TM_SQDIFF algoritmaları dışında sol üst köşeye maxsimum lokasyon
değerini aksi taktide minimum lokasyon değerini gireriz. Alt sağ
köşeyi bulmak içinse sol üst köşenin 0. indexini maskenin genişliği
ile toplayıp 1. indexinin maske uzunluğu kadar fazlası ile birlikte bir
tuple değeri olarak atarız.

Tüm köşeleri bulduğumuza göre artık çizim yapabiliriz.

Örnek:

```python
img: np.ndarray = cv.imread("Photos/cat.jpg", 0)
msk: np.ndarray = cv.imread("Photos/catface.jpg", 0)
h, w = msk.shape

methods = [
    cv.TM_CCOEFF,
    cv.TM_CCOEFF_NORMED,
    cv.TM_CCORR,
    cv.TM_CCORR_NORMED,
    cv.TM_SQDIFF,
    cv.TM_SQDIFF_NORMED,
]

for method in methods:
    res = cv.matchTemplate(img, msk, method)

    minVal, maxVal, minLoc, maxLoc = cv.minMaxLoc(res)

    if method in [cv.TM_SQDIFF, cv.TM_SQDIFF_NORMED]:
        topLeft = minLoc
    else:
        topLeft = maxLoc

    bottomRight = (topLeft[0] + w, topLeft[1] + h)

    cv.rectangle(img, topLeft, bottomRight, 255, 2)

    of.imshow(res, "gray")
    of.imshow(img, "gray")
```
