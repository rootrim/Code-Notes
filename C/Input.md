# Girdi?!!?!?!

---

## Nedir? Nerelerde Kullanılır?

- input kullanıcıdan veri alır ve onu bir değişkene aktarır.
- İnteraktif olan herşeyde vardır.

---

## Nasıl Kullanılır?

- scanf fonksiyon ile tek parçalı bir veri alabiliriz.
- scanf fonksiyonunu printf syntaxıda kullanırız ama
  string dışındaki bir türde değer alıyorsak değişkenin
  başına & konur.

- Örnek:

```c
char gyro[30];
int ball;

printf("Who are you: ");
scanf("%s", gyro);

printf("How old are you: ");
scanf("%d", &ball);

printf("Hello %s, %d yıllar eskisisin!\n", gyro, ball);
```

- Eğer bu kodu çalıştırıp kimsiniz sorsuna tam isim
  girerseniz kodun adam akıllı çalışmadığını görürsünüz.
- Bunun önüne geçmek için scanf değil de fgets kullanmamız gerekir.
- Bu fonksiyon boşlukları da işin içine katar.
- Önce içine değerin kaydolacağı değişken yazılır sonra
  girdinin alabileceği maksimum boyut ve son olarak girdi tipi yazılır.

- Örnek:

```c
char gyro[30];
int ball;

printf("Who are you: ");
fgets(gyro, sizeof(gyro), stdin);

printf("How old are you: ");
scanf("%d", &ball);

printf("Hello %s%d yıllar eskisisin!\n", gyro, ball);
```

- Bu kodda fgets kısmında şunları yaptık:
  - Önce girdinin nereye kaydolacağını belirttik.
  - Devamında girdinin alabileceği max değeri,
    değişkenin alabileceği max değere sizeof operatörü ile belirttik.
  - Sonrasında inputu klavyeden alacağımız için standart input yani stdin belirttik.
- fgets sadece string tipi verileri alır bunu unutmamak lazım
  ayrıca girdinin sonuna da bir \n ekler.

---
