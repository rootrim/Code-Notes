# While

---

## Nedir? Ne işe yarar?

- Bir şeyi sürekli yazmak yerine bir kere yaz sonra tekrar et.
- Tekrar isteyen yerlerde kullanılır.
- while ve do-while olmak üzere 2 tipi vardır.
- Break döngüyü kırar parçalar yok eder.

### While

- Whileın sağıda boolian bir değer yazılır ve o
  değer true olduğu sürece kod tekrarlanır.

- Örnek: Toki wa tomare

```c
int i = 0;
while (i <= 10) {
    printf("%d\n", i);
    i++;
}
```

- Döngü i'nin değeri 10'dan fazla olana kadar devam eder ve sonra durur.

### Do-while

- Do-while da while'a çok benzer. Tek fark while'ın ve girilen değerin konumudur.

- Örneksiz yaşanamaz.

```c
int i == 0;
do {
    printf("%d\n", i);
    i++;
} while (i <= 10);
```

- Aynı kodun laciverti.

---
