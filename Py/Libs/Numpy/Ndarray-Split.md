# Ndarray Split

---

> [!question] Nedir?
>
> Split, joinin tam tersidir.
> ndarrayları ayırmada kullanılır.

---

## Nasıl Kullanılıır?

- array_split fonksiyonunu kullanırız.
- Join ile aynı şekilde kullanılır ama küçük farlar vardır.
- Döndürdüğü değer bir python listesidir ve içinde tipinden şekline
  çeşitli bilgiler vardır ama bizim istediğimiz ayrılmış ndarraylar ilk
  elemanlardır.

- Örnek:

```python
import numpy as gyro

habbab = gyro.array(
    [
        [1, 2, 3, 7, 8, 9],
        [4, 5, 6, -1, 0, 1],
    ],
)

arr = gyro.array_split(habbab, 2, axis=1)

print(arr[0])
```

- Bu kodda array_split fonksiyonuna önce hangi ndarrayı split edeceğimizi
  sonra kaç parçaya böleceğimizi sonrada axisi belirttik.
- Döndürülen listeden de ilk elementi seçip yazdırdık.

- Bunun dışında hstack ve vstacka rakip olarak hsplit ve vsplit
  fonksiyonlarını kullanabiliriz.

---
