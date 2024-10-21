# İşaretleyiciler

---

## Nedir? Nerelerde Kullanılır?

- İşaretleyiciler sistem belleğinde işlem yapabilmemizi
  sağlayan yegane şeylerdir.
- Belleğe referans vermemizi ve referansları ters
  çevirip kullanabilmemizi sağlarlar.
- C dilinde büyük bir esneklik sağlayan pointerlar,
  çok önemli bir yer tutar.
- Kodunun havalı gözükmesini istiyorsan kullanırsın.

---

## Nasıl Kullanılır?

- Pointerları kullanabilmek için öncelikle bellekteki
  konumları nasıl görebileceğimizi öğrenmemiz gerek.
- Pointerları %p ile belirtebiliriz.
- Bunu da değişkenin başına & koyarak yapıyoruz.

- Örnek:

```c
int ball;

printf("Your Ball's address is %p\n", &ball);
```

- Peki konumları görmeyi öğrendiğimize göre şimdi
  pointer oluşturma zamanı.
- Pointer oluşturmak için oluşturulan değişkenin soluna
  ve ya tip kısmının sağına \* koyulur ayrıca eşitliğin sağına
  bir adres yazılır.

- Örnek:

```c
int ball;
int *iAMpointer = &ball; // ya da int* iAMpointer = &ball; hangisini istersen

printf("Your Ball's address is %p\n", iAMpointer);
```

- Bu örnekte bir pointer oluşturup ona ball değişkeninin
  bellekteki adresini kaydettik sonra ekrana yazdırdık.

- "E ekrana yazdırdık ta ne oldu?" diyecek olabilirsiniz. Haklısınız
  bu veriyi kullanmamız lazım. Bunu da pointeri kullanacağımız zaman
  onun hemen soluna \* ekleyerek yaparız.

- Örnek:

```c
int ball = 31;
int *iAMpointer = &ball;

printf("Your Ball's address is %p,\n", iAMpointer);
printf("and your Ball's value is %d.\n", *iAMpointer);
```

- Bu örnekte ise pointerin soluna \* koyarak dereferans
  yaptık ve adresteki değere ulaştık.

- Arrayların pointerlarla yakın bir ilişkisi olduğunu biliyormuydun?
- Aslıda bir array içinde bulunan verilerin başını yani 0. indexini
  ifade eden pointerlardır.

- Deneyelim:

```c
int balls[] = {31, 33, 69, 24};

printf("%p\n", balls);

printf("%p\n", &balls[0]);
```

- Bu örnekte iki printfin çıktısı da aynı olur. Bu da arraylar
  ve pointerlar arasındaki bağdır.
- "E tamam da bu bağ benim ne işime yarıyacak?" dediğinnizi duyar gibiyim.
- Şimdi array hani başı çekiyor ya. Ha işte bu yüzden
  adresin bir fazlası da diğer veriyi gösterir.

- Hiç anlamışa benzemiyorsunuz o yüzen hadi bir örnek:

```c
int balls[] = {31, 33, 69, 24};

printf("%d\n", *(balls)); // 0. indexteki integer

printf("%d\n", *(balls + 1)); // 1. indexteki integer

printf("%d\n", *(balls + 2)); // 2. indexteki integer
```

- Bu örnekte \*(balls + 2) kısmında balls pointerına 2 birim
  ekleriz ve iki birim sonrasına doğru pointer kayar
  ve 2. indexteki elemanı gösterir.
- Diyebilirsiniz ki "Toplama yapıyorsun da direkt adresin üzerine eklersen böyle olmaz ki"
  Doğrudur, aslında burada bir olay var. O da ben aslında 1 ile topladığımda
  1 artmaz 1 üye boyutu artar - bu durumda int yani 4 byte oluyor - bu şekilde diğer
  elemanlara da erişebiliriz.
- Bu sayede array elemanları arasında dolaşabiliriz.

---
