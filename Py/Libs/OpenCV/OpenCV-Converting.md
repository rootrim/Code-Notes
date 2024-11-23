# OpenCV Converting

---

> [!faq] Nedir?
> Converting, renk formatlarını değiştirmektir.
> Renk formatı BGR, RGB, Grayscale.

---

## Nasıl Kullanılır?

Converting yapmak için `cvtColor()` fonksiyonunu kullanabiliriz.
Bu fonksiyon içine parametre olarak önce işlemin yapılacağı görseli,
ikinci olarak OpenCV'nin bize verdiği bazı yöntemleri yazarız.

OpenCV'nin bize verdiği bu yöntemleri `COLOR_*2*` formatındadır ve ilk kısma
Önceki tipi, ikinci kısma dönüştürülecek tipi yazarız.

İşte BGR2RGB bir örnek:

```python
img = cv.imread("Photos/cats.jpg")

cvdImg = cv.cvtColor(img, cv.COLOR_BGR2RGB)

cv.imshow("Converted image", cvdImg)
```
