# Matplotlib Line

---

> [!faq] Nedir?
> Bu bölümde line ayarlarına bakacağız.

---

## Nasıl Kullanılır?

- Linenın stilini değiştirmek için `linestyle` ve ya `ls` parametrelerini kullanabiliriz.
- Bu parametrelin içine dotted, dashed, :, --, gibi değerler gelir.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([6, 1, 1, 4, 4, 6, 6, 6, 8, 4, 4, 8, 8, 12, 12, 6])
xpoints = np.array([1, 1, 4, 4, 7, 7, 8, 7, 7, 7, 8, 8, 4, 4, 1, 1])

meth.plot(xpoints, ypoints, ls=":")
meth.show()
```

- Linenın rengini değiştirmek için `color` ve ya `c` parametrelerini kullanabiliriz.
- Bu parametrelerin içine hex kodu ve ya html renk kodu girebiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([6, 1, 1, 4, 4, 6, 6, 6, 8, 4, 4, 8, 8, 12, 12, 6])
xpoints = np.array([1, 1, 4, 4, 7, 7, 8, 7, 7, 7, 8, 8, 4, 4, 1, 1])

meth.plot(xpoints, ypoints, c="r")
meth.show()
```

- Linenın kalınlığını değiştirmek için `linewidth` ve ya `lw` parametrelerini kullanabiliriz.
- Bu parametrelerin içine sayı girersin.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([6, 1, 1, 4, 4, 6, 6, 6, 8, 4, 4, 8, 8, 12, 12, 6])
xpoints = np.array([1, 1, 4, 4, 7, 7, 8, 7, 7, 7, 8, 8, 4, 4, 1, 1])

meth.plot(xpoints, ypoints, c="r", lw=20)
meth.show()
```

- Birden fazla çizgi çizmek istiyorsak birden fazla plot fonksiyonu kullanabiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([6, 1, 1, 4, 4, 8, 8, 12, 12, 6])
xpoints = np.array([1, 1, 4, 4, 8, 8, 4, 4, 1, 1])
qpoints = np.array([4, 6, 6, 6, 8, 4])
zpoints = np.array([7, 7, 8, 7, 7, 7])

meth.plot(xpoints, ypoints)
meth.plot(zpoints, qpoints)
meth.show()
```

- Ya da tek fonksiyonda yapmak istiyorsak uç uca ekleyebiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

ypoints = np.array([6, 1, 1, 4, 4, 8, 8, 12, 12, 6])
xpoints = np.array([1, 1, 4, 4, 8, 8, 4, 4, 1, 1])
zpoints = np.array([7, 7, 8, 7, 7, 7])
qpoints = np.array([4, 6, 6, 6, 8, 4])

meth.plot(xpoints, ypoints, zpoints, qpoints)
meth.show()
```

---
