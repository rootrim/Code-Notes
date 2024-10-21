# Tekrar Eden Fonksiyonlar

---

## Nedir? Nerelerde Kullanılır?

- Habbab Paşa'nın dediğine göre Recursion sadece gerçek
  sigmaların kullanabildiği bir yazılım tekniğiymiş.
- Habbab Paşa'nın birçok öğrencisi bu yolda sigma tipi
  yazılımdan soğuyarak web developinge geçmiştir.
- Bu teknik bir fonksiyonun kendisini return etmesine dayanıyor.
- Bu tekniği kullanarak kural çerçevesinde sıralı dizeleri yazdırabiliriz.
  ya da kuralı olan başka bir şeyi.

---

## Nasıl Kullanılır?

- Faktoriyel bulan basit bir recursive fonksiyon:

```c
int faktorial(int var) {
  if (var == 0) {
    return 1;
  } else {
    return var * faktorial(var - 1);
  }
}
```

- Bu kodu daha iyi anlamak için 5 sayısını kullandığımızı varsayan
  bir tablo oluşturuyorum.

| Adım | Değer                        |
| ---- | ---------------------------- |
| 1    | 5 x faktorial(4)             |
| 2    | 5 x 4 x faktorial(3)         |
| 3    | 5 x 4 x 3 x faktorial(2)     |
| 4    | 5 x 4 x 3 x 2 x faktorial(1) |
| 5    | 5 x 4 x 3 x 2 x 1            |

- Bu şekilde çalışıyor.

- Bu şekilde çalışıyor.
- Teknik çok karmaşık olduğu için daha fazla örnek veremeyceğim.
- Habbab Paşa bu tekniği nerede kullanmayı planlıyordu acaba?

---
