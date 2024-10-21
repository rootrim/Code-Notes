# ndarray

---

## Nedir? Neye Yarar?

- Ndarray, numpyın getirdiği 50 kat hızlı array tipidir.
- Numpyın sigma skilidir.
- Numpyda sıklıkla kullanılır.

---

## Nasıl Kullanılır

- Kullanmak için numpyın _array_ fonksiyonunu kullanırız.

- Örnek:

```python
import numpy as kendirli
birNdarray = kendirli.array([4, 7, 22, 69])
```

### Boyutlar

- Numpyda çeşitli boyutlarda array oluşturabiliriz.

- İşte 0 boyutlu bir array örneği:

```python
sifirBoyut = numpy.array(31)
```

- Bu ise 1 boyutlu:

```python
birBoyutlu = numpy.array([2, 3, 7, 6])
```

- 2 boyutlu:

```python
ikiBoyutlu = numpy.array([[4, 5, 7], [4, 3, 7]])
```

- Bu da 3 boyutlu:

```python
ucBoyutlu = numpy.array([[[4, 5, 7], [4, 3, 7]], [[8, 9, 4], [3, 1, 6]]])
```

- Eğer boyutları kontrol etmek istiyorsanız ndarray sınıfının
  ndim metodunu kullanarak boyutuna bakabilirsiniz.

- Örnek:

```python
boyutTest = ucBoyutlu.ndim

print(boyutTest)
```

- Eğer boyutları belirtmek istiyorsanız array fonksiyonun içine
  ndmin değişkenini belirtebilirsiniz.

- Örnek:

```python
naniBoyutlu = .array([2, 3, 7], ndmin=3)

print(naniBoyutlu)
print(naniBoyutlu.ndim) # Çıktı 3 olur
```

---
