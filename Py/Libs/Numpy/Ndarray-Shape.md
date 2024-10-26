# Ndarray Shape

---

> [!faq] Nedir?
> Shape, bir ndarrayın her bir boyutunda bulunan element sayısıdır.

---

## Nasıl Kullanılır?

### Shape

- Bir ndarray üzerinden shape metodunu kullanarak boyutunu tuple
  cinsinde döndürebiliriz.
- Bir shape olması için ndarrayın homojen olması gerekiyor yani
  her boyut kendi içinde eşit elemente sahip olacak.

- Örnek:

```python
from numpy import array

johnny = array(
    [
        [
            [1, 2, 3, 4, 5],
            [6, 7, 8, 9, 10],
        ],
        [
            [11, 12, 13, 14, 15],
            [16, 17, 18, 19, 20],
        ],
    ]
)

print(johnny.shape) # Çıktı (2, 2, 5) olur.
```

- Bu örnekte 5 tane 0 boyutlu, 2 tane 1 boyutlu ve 2 tane 2
  boyutlu ndarray var.
- Ndarrayın kendisi 3 boyutlu ve bu sebepten 3. boyuta kadar olan
  tüm boyutları büyükten küçüğe olacak şekilde sayıyor.

### Reshape 🤫🧏

- Reshape yeniden şekillendirme işlemidir.
- Reshape yapmak için yapılacak ndarrayın element sayısı dönüştürülecek
  shape ile aynı olmalıdır yani 2, 2, 5 şekilli bir ndarrayda 20 element
  var ve biz bunu başka bir şekle dönüştürmek istiyorsak onun da 20
  elementi olması lazım mesela 4, 5 ya da 10, 2 gibi.

- Önceki örneğin üstüne koyarsak:

```python
print(johnny.shape) # (2, 2, 5)

jonathan = johnny.reshape(4, 5)

print(jonathan.shape)  # (4, 5)
```

- Eğer ne kadar element olduğunu bilmiyorsak -1 koyabiliriz.
  -1 geri kalan tarzı bi anlama geliyor.

- Örnek:

```python
from numpy import array

johnny = array(
    [
        [
            [1, 2, 3, 4, 5],
            [6, 7, 8, 9, 10],
        ],
        [
            [11, 12, 13, 14, 15],
            [16, 17, 18, 19, 20],
        ],
    ]
)

jonathan = johnny.reshape(-1)

print(jonathan) # Çıktı 1, 2, 3, 4... 20 olur.
```

- 3 Boyutlu bir ndarrayı burada 1 boyutlya çevirdik.
- Oradaki -1, 20 değerinin görevini yani element sayısını aldı.

---
