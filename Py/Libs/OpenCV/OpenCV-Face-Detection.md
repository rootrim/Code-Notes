# OpenCV Face Detection

---

> [!faq] Nedir?
> Face detection, bir görüntüdeki insan yüzlerini algılayan
> yöntemdir.

---

## Nasıl Kullanılır?

Bu işlemi gerçekleştirebilmek için elimizde yüzün neye benzediğine
dair bir veri gerekiyor. Bu veriyi OpenCV'nin kendi github
sayfasından ya da başka bir yerden bulabiliriz. Ben kendi sitesindeki
veriyi kullanacağım.

Kullanımı basit. Verilerden bir cascasde nesnesi oluşturuyoruz ve
sonrasında bu nesnenin `detectMultiScale()` methodunu kullanıp bir
konum listesi alıyoruz. Bu konum listesinde bulunan değerleri de
bir `for` döngüsü ile itere edip resme yazdırıyoruz.

Örnek:

```python
linuxMaker = cv.imread("Faces/other/linustorvalds.jpg", 0)

faceCascade = cv.CascadeClassifier("Data/haarcascade_frontalface_default.xml")

faceRect = faceCascade.detectMultiScale(linuxMaker)

of.imshow(linuxMaker, "gray")

detectedSigma: np.ndarray

for x, y, w, h in faceRect:
    detectedSigma = cv.rectangle(
        linuxMaker,
        (x, y),
        (x + w, y + h),
        (255, 255, 255),
        3,
    )

of.imshow(detectedSigma, "gray")
```

Peki eğer birden fazla yüz bulmamız gerekirse o zaman ne olacak.
Eğer denersek göreceğimiz hesapsız tutarsız yüze benzeyen herşeyi
bulması olacaktır. Bunu değiştiremek için ise `detectMultiScale()`
fonksiyonuna `minNeighbors` parametresini girmek olacaktır. Bu
parametre iki eşleşme arasındaki minimum boşluğu belirtir. Ne kadar
az olursa o kadar çok eşleşme olur.

Başka bir örnek:

```python
groupOfPeople = cv.imread("Photos/group 2.jpg", 0)

faceCascade = cv.CascadeClassifier("Data/haarcascade_frontalface_default.xml")

faceRect = faceCascade.detectMultiScale(groupOfPeople, minNeighbors=5)

of.imshow(groupOfPeople, "gray")

detectedSigma: np.ndarray

for x, y, w, h in faceRect:
    detectedSigma = cv.rectangle(
        groupOfPeople,
        (x, y),
        (x + w, y + h),
        (255, 255, 255),
        3,
    )

of.imshow(detectedSigma, "gray")
```
