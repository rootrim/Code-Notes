# Matplotlib Labels and Title

---

> [!faq] Nedir?
> Labeller x ve y doğrusunun ismidir.
> Title ise tablonun ismidir

---

## Nasıl Kullanılır?

- Label kullanmak için `xlabel()` ve `ylabel()` fonksiyonlarını kullanırız.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([100, 20])
ypoints = np.array([20, 100])

meth.xlabel("Potansiyel Enerji")
meth.ylabel("Kinetik Enerji")

meth.plot(xpoints, ypoints)
meth.show()
```

- Title kullanmak için ise `title()` fonksiyonunu kullanırız.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([100, 20])
ypoints = np.array([20, 100])

meth.xlabel("Potansiyel Enerji")
meth.ylabel("Kinetik Enerji")

meth.title("Potansiyel-Kinetik Enerji Dönüşümü")

meth.plot(xpoints, ypoints)
meth.show()
```

- Titlenin pozisyonunu değiştirmek için `loc` parametresini kullanabiliriz.
- Bu parametreye left, right ve center yazılabilir.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

xpoints = np.array([100, 20])
ypoints = np.array([20, 100])

meth.xlabel("Potansiyel Enerji")
meth.ylabel("Kinetik Enerji")

meth.title("Potansiyel-Kinetik Enerji Dönüşümü", loc="left")

meth.plot(xpoints, ypoints)
meth.show()
```

- Eğer title ve labellerin yazılarının özelliklerini belirtmek istiyorsak
  `fontdict` parametresini kullanabiliriz.
- Bu parametreye `{'family':'serif','color':'blue','size':20}` bu tarz bir
  dictionary veririz.

- Örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

font = {"family": "serif", "color": "blue", "size": 16}

xpoints = np.array([100, 20])
ypoints = np.array([20, 100])

meth.xlabel("Potansiyel Enerji")
meth.ylabel("Kinetik Enerji")

meth.title("Potansiyel-Kinetik Enerji Dönüşümü", loc="left", fontdict=font)

meth.plot(xpoints, ypoints)
meth.show()
```

---
