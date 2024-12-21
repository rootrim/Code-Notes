# OpenCV Walker Detection

---

> [!faq] Nedir?
> OpenCV'de hog tanımlayıcısı kullanarak insan tanımlaması
> yapabiliriz.

---

## Nasıl Yapılır?

Önce Hog açıklayıcısı oluşturuyoruz.

```python
hog = cv.HOGDescriptor()
```

Sonra bu nesneye tespit yapabilmesi için SVM katmanı ekliyoruz.

```python
hog.setSVMDetector(cv.HOGDescriptor_getDefaultPeopleDetector())
```

Bu artık kullanabildiğimize göre hadi kullanalım. `detectMultiScale()`
fonksiyonu sayesinde içine görseli vererek insanları bulabiliriz.

```python
(rects, weights) = hog.detectMultiScale(img)
```

Rects değerini kullanarak eşleşmeleri yazdıralım.

```python
for x, y, w, h in rects:
    cv.rectangle(img, (x, y), (x + w, y + h), (0, 255, 0), 2)
```
