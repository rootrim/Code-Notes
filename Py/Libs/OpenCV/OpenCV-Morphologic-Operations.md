# Morphologic Operations

---

> [!faq] Nedir?
> Morpologic Operations, büyütüp küçülterek yani dönüşüm yaparak
> gerçekleştirdiğimiz işlemlere verilen adlardır.
>
> Şimdi bunlardan bazılarına bakacağız.

---

## Nasıl Kullanır?

OpenCV'de birden fazla morfolojik operasyon vardır. Bunlar: Erozyon,
genişleme, açma, kapatma ve morfolojik gradyandır.

Erozyon işlemi isminden de anlaşılabilineceği üzere resmin üst katmanını
küçültür. İçine sırasıyla işlenecek görseli, kerneli ve iterasyon sayısı
değerlerini alır.

Kernel, 1'lerden oluşan bir görseldir ve büyütme işlemi sırasında resmin
üzerinde gezdirilir. İterasyon sayısı ise ne kadar tekrarlama yapılacağıdır.

İşte basit bir örnek:

```python
img = cv.imread("Photos/sexyvamppire.png")
linux = ones((5, 5), dtype=uint8)

erodedIMG = cv.erode(img, linux, iterations=1)
```

Genişleme de aynı inputlarla çalışıyor. Tek farkı küçültmek yerine genişletmesi.

Örnek:

```python
img = cv.imread("Photos/sexyvamppire.png")
linux = ones((5, 5), dtype=uint8)

dilatedIMG = cv.dilate(img, linux, iterations=1)
```

Buradan sonra işler değişiyor. Açma, kapama ve morfolojik gradyanda
`morphologyEx()` fonksiyonu kullanılır ve işlem ikinci parametrede belirtilir.

Açma işlemi aslında bir görsele önce erozyon sonra da genişletme yapmaktır.
Bu sayede beyaz gürültüyü ortadan kalite eksilmesi minimumda kurtulabiliriz.

Kullanmak için `morphologyEx()` fonksiyonunun içine sırasıyla önce görseli
sonra işlemin kendisini `cv2.MORPH_OPEN` ve en son olarak ise kerneli gireriz.

İşte bir örnek:

```python
img = cv.imread("Photos/sexyvamppire.png")
linux = ones((5, 5), dtype=uint8)

openedIMG = cv.morphologyEx(img, cv.MORPH_OPEN, linux)
```

Kapama işlemi ise açma işleminin aksine görsele önce genişletme sonra da erozyon
uygular. Bu işlem sayesinde de siyah noktaları en az kalite düşüşüyle azaltmış oluruz.

Kapamayı da aynı açma işlemindeki gibi kullanırız tek fark işlemde `cv2.MORPH_CLOSE`
kullanırız.

Örnek:

```python
img = cv.imread("Photos/sexyvamppire.png")
linux = ones((5, 5), dtype=uint8)

closedIMG = cv.morphologyEx(img, cv.MORPH_CLOSE, linux)
```

Morfolojik gradyan, açma ile kapama arasındaki farkı göstererek kenar tespiti yapar.

Kullanması açma ile kapama ile aynıdır ama işlem kısmına `cv2.MORPH_GRADIENT` yazılır.

Örnek:

```python
img = cv.imread("Photos/sexyvamppire.png")
linux = ones((5, 5), dtype=uint8)

gradiatedIMG = cv.morphologyEx(img, cv.MORPH_GRADIENT, linux)
```
