# OpenCV Gradians

---

> [!faq] Nedir?
> Gradyanlar kenar tespitinde kullanılan bir yöntemdir.
>
> Görüntü gradyanı, görüntüdeki yoğunluk veya renkteki yönlü
> bir değişikliktir.

---

## Nasıl Kullanılır?

Gradyan yapmak için `Sobel()` ve ya `Laplacian()` fonksiyonları kullanılır.
`Sobel()` fonksiyonunda x ve ya y eksenine özel gradyan yapabilirken `Laplacian()`
fonksiyonunda tüm eksenlere yapar.

Sırayla önce işlenecek görseli sonra algoliratmalarda kullanılacak derinlik değerini
devamında da kernel boyutunu ve isteğe bağlı parametreleri alır.

İşte iki fonksiyonada bir örnek:

```python
img = cv.imread("Photos/sudokidoki.jpg", 0)

sobIMG = cv.Sobel(img, cv.CV_16S, dx=0, dy=1, ksize=5) # Sadece Y eksenindeki kenarlar
lapIMG = cv.Laplacian(img, cv.CV_16S, ksize=5) # Tüm açılar
```
