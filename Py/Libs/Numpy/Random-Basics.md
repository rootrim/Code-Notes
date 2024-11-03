# Random Basics

---

> [!note] Nedir?
> Random, mantık tarafından tahmin edilemez demektir.
> Gerçek ve çakma olmak üzere 2 tane random tipimiz var.
> Biz gerçek random için fakir olduğumuz için çakmasını kullanacağız.

---

## Nasıl Kullanılır?

- Öncelikle `from numpy import random` ile randomu içeri aktaralım.

- Bir aralıkta random integer oluşturmak için randint fonksiyonunu kullanırız.

- 0 ile 100 arasında sayı tutan bir örnek:

```python
randomSayi = random.randint(100)
```

- Eğer random bir float oluşturmak istiyorsak rand fonksiyonunu kullanırız.

- Örnek:

```python
shd = randorandomm.rand()
```

- Eğer bir ndarray oluşturmak istiyorsan randinte size parametresi aracılığıyla
  ndarrayın şeklini belirtebiliriz.

- Örnek:

```python
from numpy import random as rd

shd = rd.randint(100, size=(3, 3, 3))

print(shd)
```

- Aynısını rand fonksiyonu için de yapabiliriz.

- Örnek:

```python
from numpy import random as rd

shd = rd.rand(3, 3, 3)

print(shd)
```

- İstersek bir listeden random değer seçebiliriz.
- Bunu da choice fonksiyonuyla yaparız.

- Örnek:

```python
from numpy import random as rd

ayakNumaraları = [36, 36.5, 38, 39, 40, 41, 42, 43, 44, 45]

yusufunAyakNumarası = rd.choice(ayakNumaraları)

print(yusufunAyakNumarası)
```

- Ya da şeklini belirtip boyutlu şekildede alabiliriz.

- Örnek:

```python
from numpy import random as rd

ayakNumaraları = [36, 36.5, 38, 39, 40, 41, 42, 43, 44, 45]

yusufunAyakNumarasıSkalası = rd.choice(ayakNumaraları, size=(2))

print(yusufunAyakNumarasıSkalası)
```
