# Ndarray join

---

> [!faq] Nedir?
>
> İki ya da daha fazla arrayı tek arrayda toplamaktır.

---

## Nasıl Kullanılır?

- Join işlemi için birden fazla fonksiyonumuz bulunmakta.
- Bunlar:
  - concatenate
  - stack
  - hstack
  - vstack
  - dstack

### Concatenate

- Verilen axis değerine göre ndarrayları birleştirir.
- Varsayılan olarak axis değeri 0'dır.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array([[1, 2, 3], [4, 5, 6]])
tesla = gyro.array([[7, 8, 9], [-1, 0, 1]])

arr = gyro.concatenate((habbab, tesla))
```

- Bu sefer de axis değeri olan bir örnek:

```python
import numpy as gyro

habbab = gyro.array([[1, 2, 3], [4, 5, 6]])
tesla = gyro.array([[7, 8, 9], [-1, 0, 1]])

arr = gyro.concatenate((habbab, tesla), axis=1)

print(arr)
```

### Stack

- Concatenate'in yeni boyutta yapan hali arada başka fark yok.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
    ],
)
tesla = gyro.array(
    [
        [7, 8, 9],
        [-1, 0, 1],
    ],
)

stand = gyro.stack((habbab, tesla), axis=1)

print(stand) # Çıktı 3 boyutlu olur.
```

### Hstack

- Bu fonksiyon sıralar halinde birleştirme yapar yani birinci
  ndarrayın ilk satırını diğer ndarrayın birinci satırıyla birleştirir.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
    ],
)
tesla = gyro.array(
    [
        [7, 8, 9],
        [-1, 0, 1],
    ],
)

stand = gyro.hstack((habbab, tesla))

print(stand)
```

### Vstack

- Dikey sütünlar halinde birleştirme yapar yani üst üste ekler.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
    ],
)
tesla = gyro.array(
    [
        [7, 8, 9],
        [-1, 0, 1],
    ],
)

stand = gyro.vstack((habbab, tesla))

print(stand)
```

### Dstack

- Bu fonksiyon ndarrayları sütunlar şeklinde baştan sona dikey yazar.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3],
        [4, 5, 6],
        [4, 5, 6],
    ],
)
tesla = gyro.array(
    [
        [7, 8, 9],
        [-1, 0, 1],
        [-1, 0, 1],
    ],
)
edison = gyro.array(
    [
        [7, 8, 9],
        [-1, 0, 1],
        [-1, 0, 1],
    ],
)

stand = gyro.dstack((habbab, tesla, edison))

print(stand)
```

---
