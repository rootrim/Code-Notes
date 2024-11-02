# Matplotlib Grid

---

> [!faq] Nedir?
> Grid, tabloya ızgara eklemektir.

---

## Nasıl Kullanılır?

- Bir tabloya grid eklemek için `grid()` fonksiyonunu kullanırız.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([100, 20])
ypoints = np.array([20, 100])

meth.grid()

meth.plot(xpoints, ypoints)
meth.show()
```

- `grid()` fonksiyonunun içine axis parametresini girerek hangi
  ekseni göstereceğini belirtebiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([100, 20])
ypoints = np.array([20, 100])

meth.grid(axis="x")

meth.plot(xpoints, ypoints)
meth.show()
```

- `color`, `linestyle` ve `linewidth` parametrelerini de verebiliriz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([100, 20])
ypoints = np.array([20, 100])

meth.grid(color="blue", linestyle="--", linewidth=0.5)

meth.plot(xpoints, ypoints)
meth.show()
```

---
