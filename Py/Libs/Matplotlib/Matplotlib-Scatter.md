# Matplotlib Scatter

---

> [!faq] Nedir?
> Scatter tablosu birbirine bağlı olmayan noktalardan oluşan bir tablo  
> çeşididir.

> [!faq] Nerede Kullanılır?
> Scatter tabloları birbirinden bağımsız, yükseliş gibi değişkenleri olmayan  
> değerleri bulunduran projelerde kullanılır.

---

## Nasıl Kullanılır?

`scatter()` fonksiyonuna normal bir tablo gibi içine x ve y arrayları verilir.  
Devamında isteğe bağlı olarak:

- `alpha` parametresi ile alfa değerleri.
- `c` parametresi ile renk değerleri.
- `s` parametresi ile boyut değerleri.
- `cmap` parametresi ile renk tablosu.

belirtebiliriz.
Bu değerleri belirtirken de istersek hepsine farklı bir değer vermek  
için bir array girebiliriz ya da düz bir değer girerek hepsine aynı değeri  
atayabiliriz. `cmap` parametresi sadece tek bir değer alır bunu unutma.

`cmap` parametresinin alabildiği bir sürü değer var. Bunlar ise şunlar:

- Accent
- Blues
- BrBG
- BuGn
- BuPu
- CMRmap
- Dark2
- GnBu
- Greens
- Greys
- OrRd
- Oranges
- PRGn
- Paired
- Pastel1
- Pastel2
- PiYG
- PuBu
- PuBuGn
- PuOr
- PuRd
- Purples
- RdBu
- RdGy
- RdPu
- RdYlBu
- RdYlGn
- Reds
- Set1
- Set2
- Set3
- Spectral
- Wistia
- YlGn
- YlGnBu
- YlOrBr
- YlOrRd
- afmhot
- autumn
- binary
- bone
- brg
- bwr
- cividis
- cool
- coolwarm
- copper
- cubehelix
- flag
- gist_earth
- gist_gray
- gist_heat
- gist_ncar
- gist_rainbow
- gist_stern
- gist_yarg
- gnuplot
- gnuplot2
- gray
- hot
- hsv
- inferno
- jet
- magma
- nipy_spectral
- ocean
- pink
- plasma
- prism
- rainbow
- seismic
- spring
- summer
- tab10
- tab20
- tab20b
- tab20c
- terrain
- twilight
- twilight_shifted
- viridis
- winter

Eğer `cmap` parametresini belirtirsek tablonun sağında bir  
renk haritası sütunu ortaya çıkar.

İşte tüm bunları içeren bir örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

arrSize = 100
numofElements = 100

xpoints = np.random.randint(numofElements, size=arrSize)
ypoints = np.random.randint(numofElements, size=arrSize)
colors = np.random.randint(numofElements, size=arrSize)
sizes = 30 * np.random.randint(numofElements, size=arrSize)


meth.scatter(xpoints, ypoints, cmap="nipy_spectral", c=colors, alpha=0.5, s=sizes)
meth.colorbar()
meth.show()
```
