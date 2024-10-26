# Numpy View and Copy

---

> [!faq] Nedir? Ne İşe Yarar?
>
> View ve Copy ikiside bir ndarrayı başka bir ndarraya taşımak
> için kullanılar yöntemlerdir.
>
> Birbirlerinden farkı ise copy kopyalayarak aktarırken, view
> konumunu aktarır yani copy yeni bir array oluştururken view
> kısayol atar.

---

## Nasıl Kullanılır?

- Bir ndarray üzerinden copy metodunu kullanarak bir kopya
  döndürebiliriz.

- Örnek:

```python
import numpy as jojo

habbab = jojo.array([1, 2, 3, 4, 81])
edison = habbab.copy()

edison[-1] = 5

print(edison) # Çıktı 1, 2, 3, 4, 5 olur.
print(habbab) # Çıktı 1, 2, 3, 4, 81 olur.
```

- İki çıktı da farklı olduğundan da anlayabiliriyoruz ki habbabı
  kopyaladık.

- View için view metodunu kullanırız.

- Örnek:

```python
import numpy as jojo

habbab = jojo.array([1, 2, 3, 4, 81])
edison = habbab.view()

edison[-1] = 5

print(habbab) # Çıktı 1, 2, 3, 4, 5 olur
print(edison) # Çıktı 1, 2, 3, 4, 5 olur
```

- İki çıktıda aynı oldu çünkü viewdeki değeri değiştirmek
  kök değişkenin diskteki konumu ile ilişkili olduğundan
  iki tarafada etki ediyor.

- Ndarray üzerinden base metodunu kullanarak kök değer varsa onu
  yoksa None değerini görebiliriz.

- Önceki örneğin üzerine eklenen iki satır:

```python
print(habbab.base) # Çıktı None olur yani tabansızdır.
print(edison.base) # Çıktı 1, 2, 3, 4, 5 olur yani tabanlıdır.
```

---
