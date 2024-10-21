# İç İçe Arraylar

---

## Nedir? Nerelerde Kullanılır?

- İç içe arraylar kısaca bir arrayın aslında başka bir arrayın elemanı olmasıdır.
- Matrix tarızı tablolar oluşturmada kullanılır.

---

## Nasıl Kullanılır?

- Bir arrayın içine başka bir array koy sonra bum! İç içe arrayın hazır.
- Birden fazla köşeli parantez kullanarak daha içteki verilere erişebiliriz.

- Hadi bir çarpan tablosu oluşturalım.

```c
int tablo[3][3] = {
  {12, 18, 24},
  {14, 21, 28},
  {16, 24, 32}
};
// Arrayı oluşturduk şimdi yazdırıyoruz

for (int i = 0; i < 3; i++) {
  for (int i2 = 0; i2 < 3; i2++) {
    printf("%d\n", tablo[i][i2]);
  }
  printf("\n");
}
```

- Bu kod aslında aşağıdaki tabloyu ifade ediyor.

| tablo       | İlk sütun | İkinci sütun | Üçüncü sütun |
| ----------- | --------- | ------------ | ------------ |
| İlk sıra    | 12        | 18           | 24           |
| İkinci sıra | 14        | 21           | 28           |
| Üçüncü sıra | 16        | 24           | 32           |

---
