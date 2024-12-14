# OpenCV Feature Pairing

---

> [!faq] Nedir?
> Özellik eşleme, belirtilen bir nesnedeki noktaları belirtilen
> diğer resimdeki noktalarda arayıp nesneyi bulmaktır.

> [!important] Önemli!
> Özellik eşleme sadece bir nesne tespit edebilir.

---

## Nasıl Yapılır?

Bu işlemi gerçekleştirmek için iki tane nokta tespit metodu ve iki
tane de nokta eşleştirme mothodumuz bulunmakta. Tespit metodlarından
ilki orb diğeri sift, eşleştirme metodlarımızdan biri bruteforce diğeri
de k nearest neighboors (knn).

İlk önce görüntüleri içe aktararak başlıyoruz.

```python
thepicture = cv.imread("Photos/cukulatalar.jpg", 0)
chocolata = cv.imread("Photos/cukulata.jpg", 0)
```

İlk olarak orb methodunu bruteforce ile göstereceğim bu yüzden orb nesnesini
oluşturuyoruz.

```python
orb: cv.ORB = cv.ORB_create()
```

Sırada orb nesnesindeki `detectAndCompute()` fonksiyonu ile anahtar noktaları
ve açıklamaları tespit ediyoruz.

```python
kp1, ds1 = orb.detectAndCompute(chocolata, None)
kp2, ds2 = orb.detectAndCompute(thepicture, None)
```

Orb ile işimiz bitti artık bruteforceu ayarlayabiliriz. Bir bf nesnesi oluşturuyoruz.

```python
bf = cv.BFMatcher(cv.NORM_HAMMING)
```

Şimdide bu nesnesindeki `match()` fonksiyonununa görsellerin açılama değerlerini
vererek eşleşmeleri elde ediyoruz sonra da bunları `distance` değerlerine göre
sıralıyoruz.

```python
matches = bf.match(ds1, ds2)
smatchs = sorted(matches, key=lambda x: x.distance)
```

Şimdide son olarak görselleri, anahtar noktaları ve elde edilen eşleşmeleri kullanarak
bir görsel oluşturuyoruz.

```python
imgMatch = cv.drawMatches(
    chocolata,
    kp1,
    thepicture,
    kp2,
    smatchs[:20],   # İlk 20 eşleşme
    None,
    flags=2,        # Ayrıntılı belirtme
)
```

Orb ve bruteforce böyleydi şimdi sıra sift ve knn de.

Önce bir sift ve bf nesnesi oluşturuyoruz.

```python
sift: cv.SIFT = cv.SIFT_create()
bf = cv.BFMatcher()
```

Şimdide anahtar noktalar ve açıklamalar için sift nesnesinin `detectAndCompute()`
fonksiyonunu kullanıyoruz.

```python
kp1, ds1 = sift.detectAndCompute(chocolata, None)
kp2, ds2 = sift.detectAndCompute(thepicture, None)
```

Şimdide bf nesnesinin `knnMatch()` fonksiyonunu kullanarak eşleşmeleri elde
ediyoruz sonra da bu eşleşmeleri stok bir değer kullanarak uzaklıklarına göre
eleyip iyi olan eşleşmeleri alıyoruz.

```python
matches = bf.knnMatch(ds1, ds2, k=2)
nices = [[m for m, n in matches if m.distance < 0.75 * n.distance]]
```

Son olarak ise `drawMatchesKnn()` fonksiyonunu kullanarak eşleşmeleri
görselleştiriyoruz.

```python
siftMatches = cv.drawMatchesKnn(
    chocolata,
    kp1,
    thepicture,
    kp2,
    nices,
    None,
    flags=2,
)
```
