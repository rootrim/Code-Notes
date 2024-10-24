# Numpy Data Types

---

> [!faq] Nedir?
>
> Bilgisayarlar verileri ham olarak tutamaz bu sebeple
> veri tipi olarak saklar ve kullanır. Mesela "4" değerine
> bir tam sayı der ve ya "a" değerine bir karakter der.
>
> Numpyda veri tipleri C dilindeki veri tiplerine
> benzerlik gösterir. Bunun sebebi C dilinde yazılmış
> olması ve performans odaklı olmasıdır.

## Tam Liste?

İşte tam liste:

| Tip | İsmi                                   |
| --- | -------------------------------------- |
| i   | integer                                |
| b   | boolean                                |
| u   | unsigned integer                       |
| f   | float                                  |
| c   | complex float                          |
| m   | timedelta                              |
| M   | datetime                               |
| O   | object                                 |
| S   | string                                 |
| U   | unicode string                         |
| V   | Ayrılmış alan (Boşluk olarak da geçer) |

---

## Nasıl Kullanılır?

- Numpyda bir veri tipini dtype metodu ile öğrenebiliriz.

- Örnek:

```python
yusuf = numpy.array([1, 4, 7, 1, 5])

print(yusuf.dtype) # Çıktı int64 olur bu da i'ye karşılık gelir.
```

- Numpyda bir ndarrayın tipini oluştururken dtype
  parametresi ile değiştirebiliriz.
- Parametreye veri tipinin kısaltmasını vermemiz teterlidir.

- Örnek:

```python
yusuf = numpy.array([1, 4, 7, 1, 5], dtype="f")

print(yusuf.dtype) # Çıktı float32 olur bu da float değeridir ve kısaltması f'dir.
```

- İstersek i, u, f, S ve U tiplerinin boyutlarını da belirtebiliriz.
- Tipin hemen sağına byte miktarı gireriz ve belirlemiş oluruz.

- Örnek:

```python
yusuf = numpy.array([1, 4, 7, 1, 5], dtype="i4")

print(yusuf.dtype) # Çıktı int32 olur bu da integer veri tipidir ama 4 bytedır.
```

- Daha önceden oluşturulmuş bir ndarrayın tipini değiştirmek için
  onu kopyalayıp başka bir arraya aktarırız.
- Bunuda astype methodu kullanarak yaparız.
- astype metodunda içine kısaltmayı verebiliriz ya da kısaltmasını.

- Basit bir örnek:

```python
import numpy as gyro

tuskAct4 = gyro.array([1.618, 1.414])
tusk = tuskAct4.astype("i")

print(tuskAct4.dtype) # Çıktı float64 olur yani f
print(tusk.dtype) # Çıktı int32 olur yani i
```

---
