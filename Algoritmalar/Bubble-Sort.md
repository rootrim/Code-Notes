# Bubble Sort Algoritması

---

> [!faq] Nedir?
> Bubble Sort algoritması bir sıralama algoritmasıdır.
> O(n²) karmaşıklığına sahip olduğu için büyük dizilerde çok verimli değildir
> ama bir o kadar da basittir.

---

## Mantığı Nedir?

- Bubble sortun ana mantığı dönüşümlü olarak kıyaslama yapmaktır.
- Daha ayrıntılı bir açıklama istiyorsan şöyle: önce ilk iki
  değişkeni karşılaştırıyor sonra eğer önce gelen değişken daha büyükse
  iki değişkenin de yerini birbirleriyle değiştirir sonra ikinci
  ve üçüncü değişkenle sonra üçüncü... Böyle böyle devam ederek sona
  kadar gelir ve bu bir tur olur. Her turda sadece 1 değişken tam olarak
  yerine oturur bu yüzden bu turları listenin uzunluğu kere tekrarlarız.

### Örneklerle Daha İyi Kavrayalım

- Pythonda basit bir örnek:

```python
def bubbleSort(aList: list[int]):
    n = len(aList)

    for i in range(n - 1):
        for j in range(n - 1 - i):
            if aList[j] > aList[j + 1]:
                aList[j + 1], aList[j] = aList[j], aList[j + 1]

    return aList
```

- Önce listenin uzunluğunu len fonksiyonuyla belirttik
  sonrasında listenin uzunluğuna göre iki tane for döngüsü
  başlattık. Bu döngülerden içerdeki ana olayı yaparken diğeri
  tekrar yapmakta. İçerdeki döngünün n - 1 - i olmasının sebebi
  her döngüden sonra zaten 1 net sayı oturduğu için tekrardan tekrarlamaya
  gerek kalmıyor. Oradaki if ise kaşılaştırmayı yapıyor ve duruma göre
  swap işlemini gerçekleştiriyor.

---
