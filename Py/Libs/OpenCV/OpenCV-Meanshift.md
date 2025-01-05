# OpenCV Meanshift

---

> [!faq] Nedir?
> Meanshift algoritması nesnelerin youğunluğunu kullanan
> bir kümeleme ve mod arama algoritmasıdır.
>
> Hareket eden nesnelerin kümelenmesinde etkilidir.

---

## Nasıl Kullanılır?

Meanshift metodunu kullanmak için `meanShift()` fonksiyonunu
kullanırız. Ama bu fonksiyonu kullanmak için belirli birkaç
değişkene ihtiyacımız var. Önce elimizde bulacağımız nesnenin bir
örneği lazım bu örnekte kasket kullanarak bulduğumuz bir yüz
kullanacağım.

```python
faceKO = kaskad.detectMultiScale(frame)
```

Şimdi de bundan x,y, weight ve height değerlerini çekmemiz lazım.

```python
(x, y, w, h) = tuple(faceKO[0])
track = (x, y, w, h)
```

Sonra bu değerleri kullanarak `meanShift()` fonksiyonunda kullacağımız
yoğunlukları bulmamız lazım sonrasında ise onu HSV değere çevirmemiz.

```python
manofinterest = frame[y : y + h, x : x + w]
haisenberginterest = cv.cvtColor(manofinterest, cv.COLOR_BGR2HSV)
```

Şimdi de bize bu HSV görselin histogramı lazım. Normalize edilmişi.

```python
thesis = cv.calcHist([haisenberginterest], [0], None, [180], [0, 180])
cv.normalize(haisenberginterest, haisenberginterest, 0, 255, cv.NORM_MINMAX)
```

Şimdide bize en önemli değer olan kriterler lazım.

```python
criticalDamange = (cv.TERM_CRITERIA_EPS | cv.TERM_CRITERIA_COUNT, 5, 1)
```

`calcBackProject()` fonksiyonunu kullanarak dst değerini de buldukmu
artık hazırız.

```python
destination = cv.calcBackProject([haisenburger], [0], thesis, [0, 180], 1)
```

Şimdi de `meanShift()` zamanı.

```python
ret, track = cv.meanShift(destination, track, criticalDamange)
```

Son olarak bu track değerini yazdırdıkmı iş bitti.

```python
x, y, w, h = track
zamuc = cv.rectangle(frame, (x, y), (x + w, y + h), (0, 0, 255), 5)
```
