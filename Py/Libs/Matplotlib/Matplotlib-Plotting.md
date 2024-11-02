# Matplotlib Plotting

---

> [!faq] Nedir?
> Plotting tabloya yazmakdır.
> Matplotlibin en temel şeyidir.

---

## Nasıl? Kullanılır?

- pyplot alt modülündeki `plot()` fonksiyonu tabloda noktalar koymak için kullanılır.
- Varsayılan olarak iki nokta arasına çizgi çizer.
- Aldığı ilk parametre x-ekseni, ikincisi y-eksenindeki noktalardır.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([6, 3])
ypoints = np.array([3, 6])

meth.plot(xpoints, ypoints)
meth.show()
```

- Eğer çizgi çekmek değil de sadece nokta koymak istiyorsak
  "o" parametresini belirtebiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([6, 3])
ypoints = np.array([3, 6])

meth.plot(xpoints, ypoints, "o")
meth.show()
```

- Birden fazla nokta isiyorsak x ve y noktalarının sayısını arttırabiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([6, 1, 1, 4, 4, 6, 6, 6, 8, 4, 4, 8, 8, 12, 12, 6])
ypoints = np.array([1, 1, 4, 4, 7, 7, 8, 7, 7, 7, 8, 8, 4, 4, 1, 1])

meth.plot(xpoints, ypoints)
meth.show()
```

- x-noktalarını belirtmezsek ve sadece y-noktalarını verirsek x 1,2,3,4.. diye gider
  ve y belirttiğin şekilde olur.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

# xpoints = np.array([6, 1, 1, 4, 4, 6, 6, 6, 8, 4, 4, 8, 8, 12, 12, 6])
ypoints = np.array([1, 1, 4, 4, 7, 7, 8, 7, 7, 7, 8, 8, 4, 4, 1, 1])

meth.plot(ypoints)
meth.show()
```

---
