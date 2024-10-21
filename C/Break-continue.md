# Break Continue

---

## Nedir? Ne İşe Yarar?

- Break ve Continue ifadeleri, bir döngü sırasında kullanılırlar.
- Break döngüyü kırıp parçalamaya yararken, continue sadece başa sarar.

---

## Nasıl Kullanılır?

- Döngüdeyken yazarsın olur biter.

- Let's doin' some örnek

```c
int i = 31;
while (true) {
    if (i > 15) {
        printf("%d", i);
        i--;
    } else {
        break;
    }
}
```

- Bu örnekte sonsuz bir döngüyü kırdık.
- i değeri 15'e eşitlenince break çalıştı ve döngü kırıldı.

- Hadi başka bir örnek.

```c
for (int i = 1; i <= 50; i++) {
  if (i == 31) {
    continue;
  }
  printf("%d\n", i);
}
```

- Bu kodda ise 1'den 50'ye kadar olan sayıları ekrana yazdırıyoruz ama
  31'e gelince onu atlıyoruz.

---
