# Matematik

---

## Nedir? Nerelerde Kullanılır?

- C dilinde matematik yapmak istiyorsak kullanırız.
- Baya işimize yarar.

---

## Nasıl Kullanılır?

- Önce kodumuzun başına `#include <math.d>` ekleriz.
- Sonrasında içindeki çeşitli fonksiyonları kullanırız.

* Hadi içindek çeşitli fonksiyonlara bir bakalım.

- Karekök nasıl alınır?
  Balabim balabum işte örnek:

```c
float gyro = sqrt(50);
printf("%f\n", gyro);
```

- Peki nasıl yuvarlama yapacağız?
  Cavabı tam burada:

```c
float gyro = sqrt(48);
printf("%f\n", gyro);
gyro = ceil(gyro);
printf("%f\n", gyro);

float ball = sqrt(50);
printf("%f\n", ball);
ball = floor(ball);
printf("%f\n", ball);
```

- Üst sayıya yuvarlamak için ceil,
  alt sayıya yuvarlamak için floor.

* Peki kuvvet nasıl alınır?
  İşte burada:

```c
int taban = 3;
int us = 4;
int zanam = pow(taban, us);

printf("%d\n", zanam); // Çıktı 81
```

- Bu kaynaktaki en havalı kod:

```c
#include <math.h>
#include <stdbool.h>
#include <stdio.h>

bool asalFinder(int num);

int main() {
  int myNum;
  printf("Bir sayı gir: ");
  scanf("%d", &myNum);
  if (asalFinder(myNum)) {
    printf("Sayı asal\n");
  } else {
    printf("Sayı asal değil\n");
  }
  return 0;
}

bool asalFinder(int num) {
  if (num <= 1) {
    return false;
  } else if (num == 2) {
    return true;
  } else if (num % 2 == 0) {
    return false;
  } else {
    int ending = (int)sqrt(num);
    for (int i = 3; i <= ending; i += 2) {
      if (num % i == 0) {
        return false;
      }
    }
    return true;
  }
}
```

- Asal Finder

---
