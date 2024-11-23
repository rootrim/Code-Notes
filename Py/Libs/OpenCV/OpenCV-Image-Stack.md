# OpenCV Image stack()`

---

> [!faq] Nedir?
> Görüntüleri birbirinin ucuna ekleme işlemidir.

---

## Nasıl Kullanılır?

OpenCV bize bu işlemi gerçekleştirmek için bir fonksiyon sunmaz,
Bu sebeple Numpy'ın bize verdiği `hstack()` ve `vstack()` fonksiyonlarını
kullanırız.

`hstack()` horizontal yani yatay, `vstack()` vertical yani dikey birleştirir.

İşte basit bir örnek:

```python
import cv2 as cv
import numpy as np


def main():
    im = cv.imread("Photos/cat.jpg")

    imHStacked = np.hstack((im, im))
    imVStacked = np.vstack((im, im))

    cv.imshow("Horizontly stacked image", imHStacked)

    cv.waitKey(0)
    cv.destroyAllWindows()

    cv.imshow("Verticly stacked image", imVStacked)

    cv.waitKey(0)
    cv.destroyAllWindows()


if __name__ == "__main__":
    main()
```

Burda unutmamamız gereken iki görselin de aynı boyutta olması aksi durumda hata
alırız.
