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
import numpy as gyro

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
- 
