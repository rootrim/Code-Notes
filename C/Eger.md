# Eğer Blokları

- Başka bir dilde if else blokları...

---

## Nedir? Nerede Kullanılır?

- if else blokları elimizdeki bool tipindeki verilere
  göre bir işlemin gerçekleşip gerçekleşmeyeceğini belirler.
- Karşılaştırma ve mantık operatörlerinin kankisidir.
  Birbirleri olmadan ikiside işe yaramaz.

---

## Nasıl Kullanılır?

- Kullanması göründüğünün aksine çok kolaydır.
- if else bloklarına üç ana blok vardır. Bunlar:

  - if
  - else
  - if else

### if

- if ana blokdur. Verilen değer boolean true ise çalışır değilse çalışmaz.

- Örnek isteyenler el kaldırsın!

```c
int keremAge = 13;
int trimAge = 13;

if (keremAge == trimAge) {
    printf("Yaşlarımız eşit!?!?!?!?")
}
```

- Yaşlar eşitse ekrana yazdırıyoruz da değilse ne yapacağız?
  İşte o zaman işin içine else de dahil oluyor.

### else

- Else bloğu, if bloğu çalışmadığı zaman etkin olur.

- Örnekler hazır!

```c
int keremAge = 13;
int trimAge = 13;

if (keremAge == trimAge) {
    printf("Yaşlarımız eşit!?!?!?!?")
} else {
    printf("Yaşlarımız eşit değil seni ezik!")
}
```

- Eğer yaşların eşitliği değilde büyüklüğü ile işlem yapmak istersek ne olacak?
  Eğer büyüklüğü hesaba katarsak toplam 3 durum olur, sadece if ve else yetmez.
- İşin içine else if de girer.

### else if

- Else if if çalışmadığı zaman başka bir koşul oluşturur
  yani if çalışmadığı zaman kendisi if gibi davranır.
- if else, if gibi bool tipinde bir veriye ihtiyaç duyar.

- Örnekler yetişti!

```c
int keremAge = 13;
int ysufAge = 15;

if (ysufAge > keremAge) {
    printf("\"Senden çok daha iyiyim\" - Cortex');
} else if (ysufAge == keremAge) {
    printf("Yaşlar eşit!?!?!?!?!?");
} else {
    printf("... and the war begins ...");
}
```

- Buraya kadar çok iyidi dimi?
- Şimdi işler boka dönüyor.
- Şu her dilde olan kısaltmalar vardır ya?
  Şimdi C dilindeki if else kısaltmasına bakacağız.

### Short Hando if else

- Bu jojo referansı kod bloğu ne işe yarıyor diye soracak olursanız cevap basit.
  Güzel olan kodunuzu hacker koduna çevirmeye yarıyor.
  Ayrıca azcık satır eksiltiyor.
- Soldaki boolean değerine göre sağdaki ":"nin solu 1, sağı 0 ise gerçekleşiyor.

- Örnek mi? Sen istedin...

```c
bool doYouUseArchBTW = false;
(doYouUseArchBTW) ? printf("Sigma") : printf("Çık dışarı! Çık dışarı Eşşek!");
```

- Eğer duruma göre bir değer atamak istiyorsan şöyle yapabilirsin:

```c

bool doYouUseArchBTW = false;
bool sigma = (doYouUseArchBTW) ? true : false;
```

---
