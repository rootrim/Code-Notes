# OpenCV Detection with Color

---

> [!faq] Nedir?
> Renkleri kullanarak basit nesne tespiti.

---

## Nasıl Yapılır?

Bu işlemi gerçekleştirmek için birden fazla adım uygulamamız gerekiyor.
Bu adımlar sırasıyla:

1. Görseldeki gereksiz detayları silmek.

2. Görüntüyü HSV hale çevirmek.

3. Belirli bir renk aralığına maske uygulamak.

4. Maskedeki gereksiz detayları silmek.

5. Maskedeki kontorleri bulmak.

6. Bu kontorlerden belirli bir/kaç tanesini içine alacak bir
   dikdörtgen oluşturmak.

7. Ve bu şekli ekrana çizdirmek.

---

Birinci adım için `GaussianBlur()` fonksiyonunu ve ikinci adım
için `cvtColor()` fonksiyonunu kullanabiliriz.

```python
blurFrame = cv.GaussianBlur(frame, kernel_size, 0)

hsv = cv.cvtColor(blurFrame, cv.COLOR_BGR2HSV)
```

Üçüncü adım için bize bir renk skalası lazım. Ben bu örnekte
mavi ve tonlarını seçtim. `inRange()` fonksiyonu ile belirli
bir aralıktaki renkleri maskeyelebiliyoruz.

```python
lower = (90, 100, 50)  # Alt sınır
upper = (140, 255, 255)  # Üst sınır

mask = cv.inRange(hsv, lower, upper)
```

Dördüncü adım için erozyon ve genişletme kullanırız.

```python
mask_eroded = cv.erode(mask, None, iterations=2)
mask_dilated = cv.dilate(mask_eroded, None, iterations=2)
```

Beşinci adım için ise `findContours()` methodunu kullanırız.

```python
contours, _ = cv.findContours(
    mask.copy(),
    cv.RETR_EXTERNAL,
    cv.CHAIN_APPROX_SIMPLE,
)
```

Altıncı adım biraz karmaşık gözüküyor ama çok da zor değil.
Sadece bir dörtgen oluşturup onu çizdiriyoruz.

```python
color = (0, 255, 0)

if len(contours) > 0:

    c = max(contours, key=cv.contourArea)       # En büyük kontürü al

    rect = cv.minAreaRect(c)                    # Kontürden en küçük dörtgenin noktalarını oluştur

    theBox = cv.boxPoints(rect)                 # Noktalardan dörtgen yap
    theBox = np.int64(theBox)                   # int64 tip dönüşümü yap

    cv.drawContours(
        frame,                                  # İşlenecek görüntü
        [theBox],                               # Kontürler listesi
        0,                                      # 0. indexteki kontür
        color,                                  # Renk
        2,                                      # Thickness
    )
```

Bu kadar.
