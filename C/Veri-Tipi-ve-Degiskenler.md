# C Dilinde Veri Tipleri ve Değişkenler

- C dilinde 4 tane ana veri tipi vardır ve bunlar şunlardır:
  - int
  - float
  - double
  - char
- C dilinde 4 ana veri tipi dışında bazı özel niteleyiciler vardır ve bunlar da şunlardır:
  - short
  - long
  - unsigned
  - const
- Bu niteleyiciler sayesinde değişkenlerin bellekte kapladığı alanı değiştirebiliriz.
- sizeof operatörü ile bir değişkenin kapladığı yeri görebiliriz.

## int

- Tek sayıları belirtirken kullanılır.
- 3 40 998 gibi sayılar bu tipde belirtilir.
- %d ve ya %i ile belirtilebilirler.

## float

- Ondalıklı sayıları belirtmek kullanılır.
- 7 basamak saklamak için yeterlidir.
- %f ile belirtilebilir.

## double

- double, floatın genişletilmiş versiyonudur.
- 16 basamak saklamak için yeterlidir.
- %lf ile belirtilebilir.

## char

- char tek karakterleri, harfleri, sayıları ve ASCII değerlerini tanımlarken kullanılır.
- %c ile belirtilebilir.
- Karakter dizileri yani stringler %s ile belirtilir.

## bool

- stdbool kütüphanesi ile gelen bu tip evet ve hayırı ifade eder.

## Niteleyiciler

- Niteleyiciler değişlenlerin ne kadar yer kaplayacağını belirtmede kullanılır.
- Belirtmek için belirteçlere baş harflerinden ekleme yapılır.
- Örneğin unsigned bir float belirtmek istiyorsan:

```c
printf("%uf", unsignedFloat);
```

### const

- const bir değişkeni değiştirilemez yapar.
  Yani bir kere atarsın ve o öyle kalır.

## Değişkenler

- Değişken oluşturmak c dilinde şöyledir:

```c
niteleyici veriTipi degiskenIsmi = veri;
```

- Eğer karakter dizisi(string) oluşturmak istiyorsan ise şöyle:

```c
char degiskenIsmi[] = "Konodioda!";
```

- Eğer bir değişkeni ekrana yazdırmak istiyorsan onu belirtmelisin
  ve bunu da şöylersen şöyle yaparsın:

```c
printf("%i", anInt);
```
