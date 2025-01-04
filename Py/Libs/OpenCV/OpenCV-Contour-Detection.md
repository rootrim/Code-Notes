# OpenCV Contour Detection

---

> [!faq] Nedir?
> Kontür tespiti, aynı renk veya yoğunluğa sahip tüm kesintisiz
> noktaları birleştirmeye yarayan bir yöntemdir.
>
> Bu yontem şekil algılama ve nesne tespiti için kullanılır.

---

## Nasıl Kullanılır?

Kontürleri bulmak için `findContours()` fonksiyonunu kullanabiliriz.

Bu fonksiyon içine sırasıyla işlenecek görseli, modu ve methodu alır.

Mod kısmına OpenCV'nin bize verdiği `RETR_CCOMP` gibi modları yazarız.

Method kısmına ise OpenCV'nin bize verdiği `CHAIN_APPROX_SIMPLE` gibi
methodları yazarız.

Bu fonksiyon çıktı olarak ise conturlerin olduğu bir liste ve son
olarak bir hiyerarşi gönderir.

İşte bir örnek:

```python
img = cv.imread("Photos/sexyvamppire.png")
contours, hierarchy = cv.findContours(
    img,
    cv.RETR_CCOMP,
    cv.CHAIN_APPROX_SIMPLE,
)
```

Şimdi bu kontürleri görmemiz lazım. Bunun için de iç ve dış kontürler olmak
üzere iki tane boş görsel oluştururuz ve onların üzerinde `drawContours()`
uygularız.

Bu fonksiyon içine sırasıyla şu parametreleri alır: işlenecek görsel,
kontürlerin olduğu liste, kontürün idsi, renk ve kalınlık.

Kontorün idsini almak için hierarchide dolaşmamız falan gerekiyor.
Anlatması güç o yüzden direkt örnek gösteriyorum:

```python
img = cv.imread("Photos/symbols.jpg", 0)
contours, hierarch = cv.findContours(
    img,
    cv.RETR_CCOMP,
    cv.CHAIN_APPROX_SIMPLE,
)

interCont = np.zeros(img.shape)
exterCont = np.zeros(img.shape)

for i in range(len(contours)):
    # External kontürlerin hiyerarşideki konumu:
    if hierarch[0][i][3] == -1:
        cv.drawContours(exterCont, contours, i, 255, cv.FILLED)
    # External olmayan kontürler internaldir
    else:
        cv.drawContours(interCont, contours, i, 255, cv.FILLED)

of.imshow(exterCont, "gray")
of.imshow(interCont, "gray")
```
