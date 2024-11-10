# Matplotlib Bars

---

> [!faq] Nedir?
> Bars tablosu, birbirinden bağımsız sütünlardan oluşan tek eksen odaklı  
> bir tablo çeşididir.

> [!faq] Nerede Kullanılır?
> Dağılım tablolarında, anket sonuçlarında, zaman içindeki değişiklikleri  
> göstermek gibi birçok alanda kullanılır.

---

## Nasıl Kullanılır?

`bar()` fonksiyonuna normal bir tablo oluşturuyor gibi x ve y değerlerini veririz.  
Girdiğimiz eksenlerden hangisinden barların uzamasını istiyorsak ona sayıdan başka birşey veririz.  
Diğerine ise sayıları gireriz. Mesela x ekseninden uzayan sütunlar istiyorsak x arrayı `["a", "b", "c"]`  
gibi birşey olur.

Ayrıca isteğe bağlı olarak `height` / `weight`, `color` gibi parametreler verebiliriz.

İşte bir örnek:

```python
import matplotlib
import matplotlib.pyplot as meth
import numpy as np

matplotlib.use("module://matplotlib-backend-kitty")

sizes = 4
numofCars = 10

colors = np.array(["Red", "Black", "lightgray", "Gray"])
x = np.array(["Red Car", "Black Car", "W. White Car", "Gray Car"])
y = np.random.randint(numofCars, size=sizes)

meth.bar(x, y, color=colors)
meth.show()
```
