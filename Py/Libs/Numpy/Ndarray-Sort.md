# Ndarray Sort

---

> [!CAUTION] Nedir?
> Sort, gerek alfabe gerek büyüklüğe bakarak sıralama yapmaktır.

---

## Nasıl Kullanılır?

- Sırlama yapmak için sort fonksiyonunu kullanılır.
- Gayet basit.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array([5, 7, 43, 8, 45, 7456, 3, 576])

habbabSorted = gyro.sort(habbab)

print(habbabSorted)
```

- Birden fazla boyutlu arrayları sıralarsak herşey sıralanır.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [5, 7, 43, 8],
        [45, 7456, 3, 576],
    ]
)

habbabSorted = gyro.sort(habbab)

print(habbabSorted)
```

---
