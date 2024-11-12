# OpenCV Resize & Rescale

---

> [!faq] Nedir?
> Resize ve rescale işlemleri görüntünün ve ya videonun fazla büyük olduğu  
> zamanlarda görüntüyü küçülterek bilgisayara binen fazla yükü azaltmada kullanılır.

---

## Nasıl Kullanılır?

Resize ve rescale yapmak için `resize()` fonksiyonunu kullanabiliriz. Bu fonksiyon içine
işlem yapılacak görüntüyü, yeni boyutunu ve opsiyonel olarak interpolasyon yöntemini girebiliriz.

Yeni boyut, genişlik ve uzunluğun olduğu bir tuple demetidir. Genişlik ve uzunluk ise
pixsel sayılarıdır. Gayet basit.

İşte boyutun oran ile hesaplandığı bir fonksiyon örneği:

```python
def imResize(img: ndarray, scale=1.0) -> ndarray:
    width = int(img.shape[1] * scale)
    height = int(img.shape[0] * scale)

    dimension = (width, height)
    return cv.resize(img, dimension)
```

`img.shape[1]` görselin genişliğini, `img.shape[0]` görselin uzunluğunu belirtir.
Bu değerleri `scale` ile ile çarparak oranladık ve bunları kullanarak bir int sayı belirledik.
Bu sayılarla ise bir boyut tuplesi oluşturduk sonrada bunu rescale etmede kullandık.

Videoyu görsellere ayırdıktan sonra kullanırsak videolarda da işe yarar bu teknik.
