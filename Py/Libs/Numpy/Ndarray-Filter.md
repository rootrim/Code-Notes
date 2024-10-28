# Ndarray Filter

---

> [!note] Nedir?
> Bir ndarrayı, başka bir bool tipi ndarray ile filtrelemektir.

---

## Nasıl Kullanılır?

- Bir ndarrayın index kısmına bir bool ndarrayı yazarsak
  ilk ndarrayı filtrelemiş oluruz.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array([5, 7, 43, 8])

filteKahve = gyro.array([True, False, True, False])

sudo = habbab[filteKahve]

print(sudo)  # Çıktı 5, 43 olur
```

- Çok basit dimi?
- Bunu bu şekilde kullanmak biraz gereksiz bu sebeple bu
  olayı mantık operatörleriyle kullanıyoruz ve bunu yapmanın
  birkaç yolu var.
- Biri filtre listesi oluşturup bir döngü sayesinde terbiye etmek.

- Örnek:

```python
import numpy as gyro

filtreKahve = []

habbab = gyro.array([12, 29, 7, 43, 25, 9, 34, 18, 2, 47, 20, 39, 11, 6, 50])

for atom in habbab:
    if atom > 25:
        filtreKahve.append(True)
    else:
        filtreKahve.append(False)

edison = habbab[filtreKahve]

print(edison)
```

- Basit ama daha basiti var.
- Filtre olan listeye direkt atama yapabiliyoruz.

- Örnek:

```python
habbab = gyro.array([12, 29, 7, 43, 25, 9, 34, 18, 2, 47, 20, 39, 11, 6, 50])

filtreKahve = habbab < 25

edison = habbab[filtreKahve]

print(edison)
```

---
