# Arraylar

---

## Nedir? Nerelerde Kullanılır?

- Arraylar birden fazla veriyi bir yerde saklamak için kullanılır.
- Yazılarda, listelerde ve daha bir çok yerde kullanılır.
- Bir arrayda sadece aynı tipdeki veriler bulunabilir.

---

## Nasıl Kullanılır?

- Değişken isminin sağına yapışık bir şekilde "[]" konur
  ve eşittirin sağ tarafına "{}" konur ve veriler "," ile ayrılır.
- İçerdeki verilere değişkenin sağındaki köşeli parantezin içine
  index numarasını yazarak erişebilir ve hatta değiştirebiliriz.

- Kono Örnek Da!

```c
int rakamlar[] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
printf("%d\n", rakamlar[6]); // Çıktı 6 olur çünkü 6. indexte 6 değeri var
```

- İstersek bir arraydaki bir değerin kendisini değiştirebiliriz.

- Örnek?

```c
int yaslar[] = {13, 14, 15, 16};
printf("%d", yaslar[3]); // Çıktısı 16 olur

yaslar[3] = 33;
printf("%d", yaslar[3]); // Çıktısı 33 olur
```

### Extra

- Sizeof fonksiyonu ile bir değişkenin boyutunu alabiliyorduk.
  Şimdi bu bildiklerimizi kullanarak bir arrayın uzunluğunu hesaplayacağız.
  Sonra da bunu kullanarak liste üyelerini ekrana yazdıracağız.

- Bir örnekte 3 taş nasıl mı vurulur?

```c
int yaslar[] = {13, 14, 15, 16};
int kaccm = sizeof(yaslar) / sizeof(yaslar[0]);
for (int i = 0; i < kaccm; i++) {
  printf("%d %d\n", i, yaslar[i]);
}
```

- Bu kodda önce yaslar arrayını oluşturuyoruz.
- Sonra arrayın bellekte kapladığı toplam alanı
  arraydaki 0 indexindeki verinin bellekte kapladığı
  alana bölerek eleman sayısını buluyoruz.
- "E bu nasıl oluyor?" diyorsanız anlatayım:
  - Arrayın bellekte kapladığı toplam alan aslında
    içindeki elemanların toplam alanıdır ve biz eğer bunu
    herhangi bir elemanın alanına bölersek elimize eleman sayısı geçer.
  - Matematiksel olarak anlatmak gerekirse; bir integer 4
    byte yer kaplıyor, arrayda 4 tane integer varsa array
    16 byte yer kaplar. Toplam alanı yani arrayın alanını,
    eleman alanı yani herhangi bir elemana bölersek eleman
    sayısını alırız.

---
