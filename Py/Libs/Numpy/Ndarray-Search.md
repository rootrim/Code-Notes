# Ndarray Search

---

> [!NOTE] Nedir?
>
> Numpyda arama yapabiliriz.

---

## Nasıl Kullanılır?

- Arama yapmak için where fonksiyonunu kullanabiliriz.
- Where fonksiyonunda parametre olarak içeri bir ndarray
  ile yapılan matematik işlemilerini yazarız. Evet, kulağa
  biraz tuhaf geliyor biliyorum ama öyle, mesela dnar ndarrayında
  5 değerini taşıyan elementleri ayıryoruz; o zaman where
  fonksiyonunun içine dnar == 5 yazarız ya da tek sayıları aramak
  istiyorsak ndar % 2 == 1 yazabiliriz. Sanki normal bir sayıymış gibi.
  Ayrıca sadece integer değerlerle kısıtlı değiliz herhangi bir değerde de
  arama yapabiliriz.
- Tamam fonksiyona verdiğimiz inputu çözdük, peki output ne? Çıktı bulunan
  değerlerin index değerlerinin olduğu ndarrayı içeren bir tupledır ve bu tuple
  copydir yani orjinal ndarrayla alakası yoktur. Eğer bu tupleden bulunan
  indexlere ulaşmak istiyorsak 0. indexe bakarız.

- Hadi bir örnek yapalım:

```python
import numpy as gyro

andarray = gyro.array([4, 56, 7, 34, 6, 2, 6, 34])
altilar = gyro.where(andarray == 6)


print(altilar[1]) # Çıktı 4, 6 olur.
```

- Bu örnekte andarraydaki 6 değerini içeren elementleri aradık ve bulunan değerleri
  altilar değişkenine atadık. Sonrada bu değeri ekrana yazdırdık.

- İstesek bu yöntemle iki ve ya daha fazla boyutlu olan ndarraylarda da arama yapabiliriz
  ama çıktı bu durumda biraz tuhaf oluyor; Mesela iki boyutlu bir arrayda arama yaptığımız
  zaman çıktı aslında bulunan elementleri kordinatları oluyor.

- Hadi bir örnek yapalım:

```python
import numpy as gyro

andarray = gyro.array(
    [
        [4, 56, 7],
        [32, 0, 8],
        [34, 567, 9],
    ]
)
smalls = gyro.where(andarray < 10)

print(smalls)  # Çıktı (array([0, 0, 1, 1, 2]), array([0, 2, 1, 2, 2])) Olur
```

- Çıktıya bakarsak 0'a 0'da yani ilk satırın ilk sütununda
  10'dan küçük bir element var.

- Where fonksiyonunun dışında sıralı listelerde bir değerin nereye ekleneceğini  
  belirten searchsorted fonksiyonumuz var.
- Bu fonksiyon içine girilen sıralı listeye, girilen değerin nereye koyulacağını
  söyler yani 1,3,4,5 diye bir ndarrayın varsa buna 2 sayısını nereye sokacağını söyler.

- Örnek:

```python
import numpy as gyro

andarray = gyro.array([1, 2, 3, 5, 6])
ndndarray = gyro.searchsorted(andarray, 4)

print(ndndarray)  # Çıktı 3 olur.
```

- İstersek birden fazla değer de girebiliriz.

- Örnek:

```python
import numpy as gyro

andarray = gyro.array([1, 3, 5, 7])
ndndarray = gyro.searchsorted(andarray, [2, 4, 6])

print(ndndarray)  # Çıktı 1, 2, 3 olur.
```

- İstersek sağ yada soldan başlamasını side parametresi ile belirtebiliriz.

- Örnek:

```python
import numpy as gyro

andarray = gyro.array([1, 2, 3, 4, 5, 6])
ndndarray = gyro.searchsorted(andarray, 2, side="right")

print(ndndarray)  # Çıktı 2 olur.
```

---
