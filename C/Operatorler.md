# Operatörler

---

## Nedir? Ne işe yarar?

- Operatörler gerek toplama, çıkarma, mod alma gibi aritmetik işlemlerde,
  gerek büyüktür küçüktür gibi karşılaştırma işlemlerinde,
  gerek AND OR gibi mantıksal işlemlerde,
  gerek atama işlemlerinde kullanılır.
- Bunlar yazılımda hep kullandığımız şeylerdir ve herzaman ihtiyacımız olur.
- C dilinde operatörlerin 4 tipi vardır. Bunlar şunlardır:
  - Aritmetik operatörler.
  - Atama operatörleri.
  - Karşılaştırma operatörleri.
  - Mantıksal operatörler.

---

## Nasıl Kullanılır?

### Aritmetik Operatörler

- Aritmetik operatörler aslında toplama çıkarma gibi
  matematik işlemlerinden başka bir şey değildir.

| İşlem | İsmi     | Açıklama                                      | Örnek  |
| ----- | -------- | --------------------------------------------- | ------ |
| +     | Toplama  | Değerleri birleştirmek                        | x + y  |
| -     | Çıkarma  | İlk değerden diğerini çıkarmak                | x - y  |
| \*    | Çarpma   | Bir değer kadar diğerini toplamak             | x \* y |
| /     | Bölme    | İlk değeri diğerine bölmek                    | x / y  |
| %     | Mod      | İlk değerin diğerine bölümünden kalanı bulmak | x % y  |
| ++    | Arttırma | Bir değerin üstüne 1 eklemek                  | ++x    |
| --    | Azaltma  | Bir değerden 1 eksiltmek                      | --x    |

- Kullanıldığı bir örnek:

```c
const int joestar = 43;
const int zeppeli = 7;

int habbab = joestar * zeppeli;
printf("%d", habbab); // Çıktı joestar ve zeppelinin çarpımı olur
```

### Atama Operatörleri

- Atama operatörleri = ve türevlerinden oluşur.
- Misal bir değişkene bir şey atamada kullanılırlar.

| Sembol | İsmi           | Açıklama                                | Örnek   |
| ------ | -------------- | --------------------------------------- | ------- |
| =      | Atama          | Sağdaki değeri sola atamak              | x = y   |
| +=     | Toplayıp atama | Değerleri topladıktan sonra sola atamak | x += y  |
| -=     | Çıkarıp atama  | Değerleri çıkardıktan sonra sola atamak | x -= y  |
| \*=    | Çarpıp atama   | Değerleri çarptıktan sonra sola atamak  | x \*= y |
| /=     | Bölüp atama    | Değerleri böldükten sonra sola atamak   | x /= y  |
| %=     | Mod alıp atama | Kalanı hesaplayıp sola atamak           | x %= y  |

- İşte bir örnek:

```c
const int ysuf = 15;
int josuke = 17;

josuke -= ysuf;

printf("%d\n", josuke) // Çıktı 2 olur.
```

### Karşılaştırma Operatörleri

- Karşılaştırma operatörleri soldaki ve sağdaki değeri
  karşılaştırıp boolian - 1 ve ya 0 - değer döndürür.
- Boolian değer isteyen heryerde kullanılırlar.

| İşlem | İsmi                | Açıklama                                                            | Örnek  |
| ----- | ------------------- | ------------------------------------------------------------------- | ------ |
| ==    | Eşit mi?            | İki değerin birbirine eşit olup olmadığını kontrol eder             | x == y |
| !=    | Eşit değil mi?      | İki değerin birbirine eşit olmadığını kontrol eder                  | x != y |
| >     | Büyük mü?           | Sol değerin sağ değerden büyük olup olmadığını kontrol eder         | x > y  |
| <     | Küçük mü?           | Sol değerin sağ değerden küçük olup olmadığını kontrol eder         | x < y  |
| >=    | Büyük veya eşit mi? | Sol değerin sağ değere büyük veya eşit olup olmadığını kontrol eder | x >= y |
| <=    | Küçük veya eşit mi? | Sol değerin sağ değere küçük veya eşit olup olmadığını kontrol eder | x <= y |

- Ne bir örnek mi?

```c
const int king = 5;
int seccondo = 3;

printf("%d\n", king == seccondo) // Çıktı 0 yani false olur.
```

- Burada dikkat edilmesi gereken bir şey daha var.
  char listelerini karşılaştırmaya çalıştığımızda
  aslında değerleri değil bellekteki konumlarını karşılaştırır.
  Bu da herzaman false yani 0 değerini verir.
- Bunun önüne geçmek için string.h kütüphanesinden **_strcmp_** fonksiyonunu kullanırız.

#### strcmp

- Bu fonksiyon iki string veriyi karşılaştırır ve eğer ikiside aynı ise 0 değerini döndürür.
- Eğer değilse alfabetik sıraya göre 0'dan farklı bir değer döndürür.

- Birisi string karşılaştıran bir örnek mi dedi?

```c
const char king[] = "Habbab";
char seccondo[] = "Melih";

const int nani = strcmp(king, seccondo) == 0;

printf("%b\n", nani); // Sonuç false yani 0 olur.
```

### Mantıksal Operatörler

- Mantıksal operatörler üniversitedeki bilgisayar bölümümde öğretilen
  AND, OR ve NOT gibi terimleri karşılar :].

| İşlem | İsmi          | Açıklama                                                      | Örnek  |
| ----- | ------------- | ------------------------------------------------------------- | ------ |
| &&    | Mantıksal AND | İki koşulun da doğru olup olmadığını kontrol eder             | x && y |
| \\    | Mantıksal OR  | İki koşuldan en az birinin doğru olup olmadığını kontrol eder | x \\ y |
| !     | Mantıksal NOT | Bir koşulun tersini alır                                      | !x     |

> \\ yorum satırı yapmak için kullanılır aslında.
> Burda onu || diye kabul edin. Markdown tablosu yaparken
> sıkıntı yaptı, o yüzden böyle yazdım.

- Habbab zorla bir örnek yazdırmak istiyor galiba.

```c
int keremAge = 19;
const char keremNationality[] = "afgan";

char nationBorder[] = "afgan";
const int ageBarrage = 18;

const int yakismadi = strcmp(keremNationality, nationBorder) == 0;

int nani = keremAge >= ageBarrage && !yakismadi;

printf("%d\n", nani);
```

---
