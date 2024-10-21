# Ndarray Slicing

---

## Nedir? Ne işe yarar?

- Slicing işlemini bir aralıktan değer almak için kullanırız.
- 4'ten 7. indexe kadar olan değerleri al tarzı.
- Pythonun normal slicing işlemine çok benzerdir.

---

## Nasıl Uygulanır?

- Uygulamak için "[]" içine baş:son:adım şeklinde değer gireriz.
- Baş girmezsek en baştan, son girmezsek sona kadar ve adım girmezsek
  tekli tekli devam eder. Hiçbirşey girmeyip sadece "::" yazarsak
  hepsine ulaşırız.

- Basit bir örnek:

```python
dorray = numpy.array([0, 1, 2, 3, 4, 5, 6, 7])
rst = dorray[2:6]
print(rst) # Çıktı 2 3 4 5 olur
```

- Adım içeren bir örnek:

```python
sayilar = numpy.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ,11, 12 ,13, 14 ,15, 16 ,17, 18, 19, 20])
ciftSayilar = sayilar[1::2]
print(ciftSayilar) # Çıktı 2 4 6 8 10... olur
```

- Slicing yaparken "-" kullanarak sondan da başlayabiliriz.

```python
nadaray = numpy.array([3, 67, 2, 61, 89, 21])
eksiSlicing = nadaray[-3:-1]
print(eksiSlicing) # Çıktı 61 89 olur
```

- İstersek birden fazla boyutlu ndarraylarıda dilimleyebiliriz.
- Slicing işleminden önce konumu belirtiriz.

- Örnek:

```python
sayilar = numpy.array([[1, 2, 3, 4, 5, 6, 7, 8, 9, 10], [11, 12 ,13, 14 ,15, 16 ,17, 18, 19, 20]])
ciftSayilar = sayilar[1, 1::2]
print(ciftSayilar) # Çıktı 12 14 16 18 20 olur
```

- Eğer iki ndarray belirtisek ve bir indexi alırsak
  iki boyuttan da değer alırız.

- Örnek:

```python
nadaray = numpy.array([[1, 2, 3, 4, 5, 6, 7, 8, 9, 10], [11, 12 ,13, 14 ,15, 16 ,17, 18, 19, 20]])
sayis = nadaray[::, 2]
print(sayis) # Çıktı 3 13 olur.
```
