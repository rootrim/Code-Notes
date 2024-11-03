# Ufuncs Basic

---

> [!faq] Nedir?
> Ufunclar, ndarraylar üzerinde işlem yapmamızı sağlayan fonksiyonlardır.

---

## Nasıl Kullanılır?

- Basit bir ufunc içine girilien iki ndarraydaki aynı index numarasına sahip olan
  değerler üzerinde işlem yapar.

- Örnek:

```python
import numpy as gyro
from numpy import array as arr

numSt = arr(
    [4, 5, 6],
)

numNd = arr(
    [1, 2, 3],
)

numS = gyro.add(numSt, numNd)

print(numS) # Çıktı 5, 7, 9 olur.
```

- Sıfırıncı indextekileri birbiriyle birinci indextekileri birbiriyle toplayarak devam etti
  ve bu Çıktıyı verdi.

- Add gibi bir sürü ufunc var. Bunlardan bazılarını aşağıdaki tabloda belirtilmekte:

| Ufunc    | Neye Yarar?                                                                        | Input     | Output    |
| -------- | ---------------------------------------------------------------------------------- | --------- | --------- |
| add      | Toplama                                                                            | 2 Ndarray | 1 Ndarray |
| Subtract | Çıkarma                                                                            | 2 Ndarray | 1 Ndarray |
| Multiply | Çarpma                                                                             | 2 Ndarray | 1 Ndarray |
| Divide   | Bölme                                                                              | 2 Ndarray | 1 Ndarray |
| Power    | Kuvvet Alma                                                                        | 2 Ndarray | 1 Ndarray |
| Mod      | Kalan Alma                                                                         | 2 Ndarray | 1 Ndarray |
| divmod   | Bölüm ve Kuvvet Alma                                                               | 2 Ndarray | 2 Ndarray |
| Absolute | Mutlak Değer Alma                                                                  | 1 Ndarray | 1 Ndarray |
| Fix      | "."dan Sonrasını Atma                                                              | 1 Ndarray | 1 Ndarray |
| Floor    | Alt Tam Sayıya Yuvarlama                                                           | 1 Ndarray | 1 Ndarray |
| Ceil     | Üst Tam Sayıya Yuvarlama                                                           | 1 Ndarray | 1 Ndarray |
| Around   | Tam Sayıya Yuvarlama                                                               | 1 Ndarray | 1 Ndarray |
| Diff     | Kendini Kendinden Sonraki Indexten Çıkarma                                         | 1 Ndarray | 1 Ndarray |
| Prod     | Ndarraydaki Değerleri Çarpma                                                       | 1 Ndarray | 1 Değer   |
| Cumprod  | Prod ama Her Aşama İçin Ayrı Bir Değer                                             | 1 Ndarray | 1 Ndarray |
| Sum      | Ndarraydaki Değerleri Toplama                                                      | 1 Ndarray | 1 Değer   |
| Cumsum   | Sum ama Her Aşama İçin Ayrı Bir Değer                                              | 1 Ndarray | 1 Ndarray |
| lcm      | Ekoku Bulmak                                                                       | 2 Değer   | 1 Değer   |
| gcd      | Ebobu Bulmak                                                                       | 2 Değer   | 1 Değer   |
| reduce   | lcm ve gcd Gibi Değer Alan Fonksiyonların Index Üzerinden İşlem Yapmasını Sağlamak | 2 Ndarray | 1 Ndarray |

---
