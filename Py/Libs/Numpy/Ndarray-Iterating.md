# Ndarray Iterating

---

> [!faq] Nedir?
>
> Iterating, bir ndarrayı for döngüsünde kullanarak
> içindeki elementlerde gezmektir.

---

## Nasıl Kullanılır?

- Normal for döngüsünde nasıl liste kullanıyorsan öyle.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array([1, 2, 3, 4, 5, 6])

for i in habbab:
    print(i)
```

- Birden fazla boyutlu arrayları iterate etmek istiyorsak
  iç içe for döngüleri kullanırız.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
    ],
)

for i in habbab:
    for ii in i:
        print(ii)
```

- Numpy iterasyonda kullanmamız için nditer diye yardımcı bir
  fonksiyon oluşturmuş.
- Bu fonksiyon sayesinde ekstra parametreler atayabiliriz.
- Varsayılan olarak tüm listeyi dolaşır.

- Örnek:

```python
iport numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
    ],
)

for i in gyro.nditer(habbab):
    print(i)
```

- Burada sanki listeyi düzlenmiş bir ndarray gibi
  tüm elementleri yazdırır.

- Eğer tüm elementleri başka bir veri tipinde yazdırmak
  istiyorsak **op_dtypes** kullanırız ama bunu kullanırken
  bellekte yer açmamız lazım bu yüzden buffered flagını ekleriz.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
    ],
)

for i in gyro.nditer(habbab, flags=["buffered"], op_dtypes="f8"):
    print(i)
```

- Eğer enumerate ile for kullanmak istiyorsak
  ndenumerate yardımcı fonksiyonunu kullanabiliriz.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
    ],
)

for idx, i in gyro.ndenumerate(habbab):
    print(idx)
```

- idx değişkeni bize hangi değeri döndürdüğünü
  söyleyen bir tuple değeri gönderir.

---
