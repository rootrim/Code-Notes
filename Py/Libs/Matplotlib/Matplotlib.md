# Matplotlib

---

> [!faq] Nedir?
> Matplotlib bir grafik çizme kütüphanesidir.
> Pythonda çalışır ve birçok diğer kütüphaneyle uyumluluk gösterir.

---

## Nasıl Kullanılır?

- Matplotlibi kullanmak için önce import etmemiz gerek.

- Örnek:

```python
import matplotlib as mpl
```

- Eğer benim gibi terminal sigmasıysanız🤫🧏 matplotlib-backend-kitty
  paketini pip ile indirdikten sonra kodun içinden source ederseniz
  direkt kitty protokolü ile görüntü alabilirsiniz.

- Örnek:

```python
import matplotlib as mpl

mpl.use("module://matplotlib-backend-kitty")
```

- Oluşturduğunuz tabloyu görmek istiyorsanız `matplotlib.pyplot.show()`
  fonksiyonu ile görebilirsiniz.

---
