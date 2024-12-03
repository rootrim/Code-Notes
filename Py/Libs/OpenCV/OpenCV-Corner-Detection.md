# OpenCV Corner Detection

---

> [!faq] Nedir?
> Köşe algılama, bir görseldeki değişimlerin en çok olduğu yeri
> algılamaya denir. Bu yöntemi kullanarak üç boyutlu nesneler gibi
> objeleri algılayabiliriz.

---

## Nasıl Kullanılır?

Köşe algılamak için `cornerHarris()` fonksiyonunu kullanabiliriz.
Bu fonksiyon içine sırasıyla işlenecek görseli, bakılacak komşu sayısını,
çekirdek boyutunu ve hassaslık değerini alır.

İşte bir örnek:

```python
baseImg = cv.imread("Photos/sudokidoki.jpg", 0)
floImg = np.float32(baseImg)

corneredImg = cv.cornerHarris(floImg, blockSize=2, ksize=5, k=0.04)

imshow(baseImg, "gray")
imshow(corneredImg, "jet")
```

Eğer istersek `cornerHarris()` fonksiyonu yerine `goodFeaturesToTrack()`
fonksiyonunu kullanabiliriz.

Bu fonksiyon diğerinden biraz değişiktir. İçine sırasıyla önce işlenecek
görseli, bulunacak köşe sayısını, kalite seviyesi ve minimum yakınlık değerini
alır. Çıktı olarak ise bize köşelerin x ve y değerlerini içeren 3 boyutlu bir
ndarray gönderir.

İşte bir örnek:

```python
baseImg = cv.imread("Photos/sudokidoki.jpg", 0)
floImg = np.float32(baseImg)

corners = cv.goodFeaturesToTrack(floImg, 740, 0.01, 3)
corners = np.int64(corners)

imshow(baseImg, "gray")

for corner in corners:
    x, y = corner.ravel()
    cv.circle(baseImg, (x, y), 3, (125, 125, 125), -1)

imshow(baseImg, "gray")
```

Bu kodda elde ettiğimiz 3 boyutlu listeyi dolaşıp ravel ile 1 boyutluya kadar
boyutunu düşürüp öyle işlem yaptık. Yaptığımız işlemde değişkenlerin integer olmasına
ettik ve her köşeye 3 pixel yarıçaplı içi dolu yuvarlaklar çizdik.
