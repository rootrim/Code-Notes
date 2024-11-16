# OpenCV Skech

---

> [!faq] Nedir?
> Skech, görsel üzerinde bir şeyler çizmek, yazmaktır.

> [!faq] Nerede Kullanılır?
> Skechi görsel üzerinde bir şey belirtmek için kullanırız.

---

## Nasıl Kullanılır?

OpenCV'de skech yapmak oldukça basittir. Sadece uygun şeklin fonksiyonunu bilmen gerekiyor.
Bunlar: kare için `rectangle()`, daire için `circle()`, çizgi için `line()` ve yazı yazmak
için ise `putText()` fonksiyonlarıdır.

`rectangle()` ve `line()` fonksiyonları aynı parametreleri alırlar. Bunlar: çizim yapılacak
görsel, başlangıç konumu, bitiş konumu, renk ve kalınlıktır. Renk parametresini BGR formatında
bir tuple olarak veririz. Kalınlık pixel değeridir ve -1 verirsek içini de doldurur.

`circle()` fonksiyonu `rectangle()` ve `line()`'ın aksine başlangıç noktası ve bitiş noktası
yerine merkez konumu ve çap değeri alır.

`putText()` foksiyonu diğer fonksiyonların aksine parametre sıralaması şöyledir: yazılacak
görsel, yazılacak yazı, başlangıç noktası, font yüzü, font boyutu, renk ve kalınlık. Font
yüzü olarak OpenCV kütüphanesi bize `FONT_HERSLEY_TRIPLEX` tarzı değerler sunuyor. Font boyutu
kısmına punto falan değil de oran yazıyoruz.

İşte bunları içeren bir örnek:

```python
import cv2 as cv
from numpy import zeros, ndarray

def main():
blank = zeros((500, 500, 3), dtype="uint8") # uint8 yani resim formatında bir boş ndarray
imshow(blank)

    # Blank görselinin ortasının konumu ile ilgili 2 değişken
    blankMidW = blank.shape[1] // 2
    blankMidH = blank.shape[0] // 2

    # renk
    green = (0, 255, 0)

    cv.rectangle(
        blank,
        (blankMidW - 50, blankMidH - 50),
        (blankMidW + 50, blankMidH + 50),
        green,
        thickness=2,
    )
    imshow(blank)

    cv.line(
        blank,
        (blankMidW - 50, blankMidH - 50),
        (blankMidW + 50, blankMidH + 50),
        green,
        thickness=2,
    )
    imshow(blank)

    cv.circle(blank, (blankMidW, blankMidH), 40, green, thickness=2)
    imshow(blank)

    cv.putText(
        blank,
        "Kono DIO da!!!",
        (blankMidW - 50, blankMidH + 70),
        cv.FONT_HERSHEY_TRIPLEX,
        0.75,
        green,
    )
    imshow(blank)

def imshow(img: ndarray, name="Image", ms=0):
cv.imshow(name, img)
cv.waitKey(ms)

if __name__ == "__main__":
    main()
```

Gayet basit.
