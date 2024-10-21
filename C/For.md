# for

---

## Nedir? Ne İşe Yarar?

- For döngüsü c dilinde while'ın daha kontrollü bir biçimidir.
- Tekrar isteyen yerlerde kullanılır.

---

## Nasıl? Kullanılır?

- For döngüsünde içine direkt boolean değer atılmaz.
  Onun yerine başlangıç, koşul, artış olmak üzere
  üç farklı fonksiyon atılır.

- Örnek gözükmediği yerden kod çıkmaz.

```c
for (int i = 2; i <= 512; i *= 2) {
  printf("%d\n", i);
}
```

---
