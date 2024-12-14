# OpenCV Baas Algorithym

---

> [!faq] Nedir?
> Havza algoritması, bir görüntüdeki farklı nesneleri
> ayırmak için kullanılır.

---

## Nasıl Kullanılır?

Bunu yapmak için. Önce bir görselimiz olması lazım.

```python
img = cv.imread("Photos/coins.jpg")
```

Şimdide ayrıntıları azaltmak lazım.

```python
blur = cv.medianBlur(img, 13)
```

Grayscale olmazsa olmaz.

```python
gray = cv.cvtColor(blur, cv.COLOR_BGR2GRAY)
```

İşlemi gerçekleştirmek için bir de threshold yapmamız lazım ki
arkaplan ile önplanı ayırabilelim.

```python
_, threshed = cv.threshold(gray, 65, 255, cv.THRESH_BINARY)
```

Şimdi görseldeki nesneler ile arkaplanı ayırdık eğer sıkıntı varsa `dilate`
gibi yöntemlerle azaltabiliriz.

Bundan sonra ise nesneleri ayırmamız lazım bu sebeple `distanceTransform()`
uygularız.

```python
dist = cv.distanceTransform(threshed, cv.DIST_L2, 5)
```

Görselimiz tekrar farklı renklere ayrıldı bu sebeple tekrar threshold uygularız.
Ama bu sefer maksimum değerin 4 katını minimum değer olarak gireriz ve çıktı olarak
önplan değerini alırız.

```python
_, foreg = cv.threshold(dist, 0.4 * np.max(dist), 255, 0)
```

Arkaplan değerini de önplanı açarak alırız. En son bunları uint8 olarak ayarlarız.

```python
linux = np.ones((3, 3), np.uint8)

backg = cv.dilate(foreg, linux, iterations=1)
foreg = np.uint8(foreg)
```

Bu aşamada ise arkaplandan önplanı çıkararak nesneleri buluruz.

```python
known = cv.subtract(backg, foreg, dtype=0)
```

Şimdi ise havza algoritması için marker değerini bulmamız lazım, bunun için de
`connectedComponents()` fonksiyonunu kullanırız. Bu değere bir ekleriz ve önceden
bulduğumuz known değerinin kullanarak değişik bir işlem yaparız.

```python
_, marker = cv.connectedComponents(foreg)
marker += 1
marker[known == 255] = 0
```

Sırada asıl havza algoritması var. `watershed()` fonksiyonunu kullanarız.

```python
marker = cv.watershed(img, marker)
```

Son olarak kontorleri markeri kullanarak buluruz ve dış kontürleri yazdırırız.

```python
contours, hierarchy = cv.findContours(
    marker.copy(),
    cv.RETR_CCOMP,
    cv.CHAIN_APPROX_SIMPLE,
)

for i in range(len(contours)):
    if hierarchy[0][i][3] == -1:
        cv.drawContours(img, contours, i, (0, 255, 0), 2)
```
