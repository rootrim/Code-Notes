# Matplotlib Markers

---

> [!faq] Nedir?
> Markerlar aslında grafiğin nasıl görüneceğidir.

---

## Nasıl Kullanılır?

- Marker parametresi ile noktaların nasıl gözükeceğini belirtebiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([8, 3, 9, 2])

meth.plot(ypoints, marker="o")
meth.show()
```

- Bu marker parametresine verebileceğimiz değerler kısıtlıdır ve her değerin kendine
  özel bir sitili vardır.

- İşte tam tablo:

| Marker | Açıklama       |
| ------ | -------------- |
| 'o'    | Halka          |
| '\*'   | Yıldız         |
| '.'    | Nokta          |
| ','    | Pixel          |
| 'x'    | X              |
| 'X'    | X (Kalın)      |
| '+'    | Artı           |
| 'P'    | Artı (Kalın)   |
| 's'    | Kare           |
| 'D'    | Baklava        |
| 'd'    | Baklava (ince) |
| 'p'    | Beşgen         |
| 'H'    | Altıgen        |
| 'h'    | Altıgen        |
| 'v'    | Üçgen Aşağı    |
| '^'    | Üçgen Yukarı   |
| '<'    | Üçgen Sola     |
| '>'    | Üçgen Sağa     |
| '1'    | Üç Kol Aşağı   |
| '2'    | Tri Yukarı     |
| '3'    | Tri Sol        |
| '4'    | Tri Sağ        |
| '\|'   | Dikey Çizgi    |
| '\_'   | Yatay Çizgi    |

- Hani "o" parametresi verip çizgileri kaybediyorduk ya, işte o parametre
  aslında sadece o işe yaramıyor.
- marker|line|color formatında yazılıyor ve fmt olarak karşımıza çıkıyor.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([8, 3, 9, 2])

meth.plot(ypoints, "o:r")
meth.show()
```

- Birden fazla çizgi tipi var.
- İşte tam liste:

| Syntax | Açıklama                           |
| ------ | ---------------------------------- |
| '-'    | Düz çizgi                          |
| ':'    | Noktalı çizgi                      |
| '--'   | Uzun çizgili çizgi                 |
| '-.'   | Hem noktalı hem uzun çizgili çizgi |

- Birden fazla da renk referansı var.
- Tam liste:

| Syntax | Açıklama  |
| ------ | --------- |
| 'r'    | Kırmızı   |
| 'g'    | Yeşil     |
| 'b'    | Mavi      |
| 'c'    | Camgöbeği |
| 'm'    | Mor       |
| 'y'    | Sarı      |
| 'k'    | Siyah     |
| 'w'    | Beyaz     |

- Eğer marker küçük geliyorsa `ms` parametresi ile boytunu belirtebiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([8, 3, 9, 2])

meth.plot(ypoints, "o--r", ms=20)
meth.show()
```

- Ya da istersek markerin kenar rengi için `mec` yüzey rengi için `mfc`
  parametrelerini kullanabilriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([6, 1, 1, 4, 4, 6, 6, 6, 8, 4, 4, 8, 8, 12, 12, 6])
ypoints = np.array([1, 1, 4, 4, 7, 7, 8, 7, 7, 7, 8, 8, 4, 4, 1, 1])

meth.plot(ypoints, xpoints, marker="o", mec="r", mfc="b")
meth.show()
```

- Mec ve mfc içine hex kodu ve ya html renk isimleri yazabiliriz.

---
