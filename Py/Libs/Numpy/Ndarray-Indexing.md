# Ndarray Indexleme

---

## Nedir? Nerelerde Uygulanır?

- Indexleme, basitçe verilere ulaşmaktır.
- Numpyın index sistemi, pythonun varsayılan index
  sisteminin neredeyse aynısıdır.
- Indexleme elindeki tablodan veri çekerken kullanırsın.

---

## Nasıl Kullanılır?

- Aynı pythondaki gibi kullanıyoruz ama birden fazla "[]" yerine
  "," ile ayırıyoruz.

- Örnek:

```python
ikiBoyutlu = numpy.array([[4, 5, 7], [1, 3, 9]])
rst = ikiBoyutlu[1,1]
print(rst) # Çıktı 3 olur.
```

- İstersek normalde olduğu gibi "-" kullanarak sondan da
  başlayabiliriz.

- Örnek:

```python
ikiBoyutlu = numpy.array([[4, 5, 7], [1, 3, 9]])
rst = ikiBoyutlu[-1,-3]
print(rst) # Çıktı 1 olur.
```
