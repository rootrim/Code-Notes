# Veri Tipi Dönüşümleri

---

## Nedir? Ne işimize yarar?

- Veri Tipi Dönüşümleri tamsayıları ondalıklara, ondalıkları
  charliste ve ya char bir veriyi inte çevirmekte kullanılır.
- Bu da birden fazla veri tipiyle senkronize çalışmamıza olanak tanır.
- Mesela 5'i 2'ye bölmeye çalışırsak 2 cevabını alırız.
  Neden? Çünkü sonuç int tipinde bir veri. Onu float tipi yapmalıyız.

---

## Nasıl kullanırız?

- C dilinde 2 tane tür dönüşümü vardır. Bunlardan biri otomatik
  diğeri ise manueldir.

### Otomatik dönüşüm.

- Otomatik olan dönüşüm derleyici tarafından gerçekleştirilir.
- Kullanması risklidir çünkü kontrol sende değil ve işler kötüye gidebilir.

- İşte bir örnek:

```c
float gyro = 9;

printf("%f\n", gyro); // Çıktı 9.000000 olur
```

- Burada derleyici integer bir değeri floata çevirdi.

- Şimdi başka bir örnek:

```c
int zeppeli = 9.99;

printf("%d\n", zeppeli); // Çıktı 9 olur.
```

- Burada zeppeli değişkenine float bir değer vermemize rağmen
  bize integer bir veri döndürdü ve .99'lu olan kısmı kaybettik.
- Gördüğünüz gibi bazı veriler kayboldu ve artık kullanılamaz haldeler.
  Bu yüzden bu yöntemi kullanmak risklidir.

- Şimdi daha da başka bir örnek:

```c
float kira = 5 / 2;

printf("%f\n", kira) // Çıktı 2 olur.
```

- Burda çıktının 2.500000 olmasını beklememize rağmen çıktı 2 oldu.
  Peki neden? Çünkü içerdeki 5 ve 2 değerleri hala integer tipinde.
  E nasıl floata çevireceğiz o zaman dediğinizi duyar gibiyim.
  Basit manuel dönüşüm yapacağız.

### Manuel dönüşüm.

- Manuel dönüşüm yapmak için ='in sağına parantezler içine tipi belirtiriz.

- İşte bir örnek

```c
float kawajiri = (float) 5 / 2;

printf("%f\n", kawajiri) // Sonuç 2.500000 olur.
```

- Burada içerdeki 5 ve 2 değerini floata çevirip öyle işlem yapıyoruz.

---
