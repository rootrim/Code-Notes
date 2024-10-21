# Scope

---

## Nedir?

- Scope değişkenlerin etki alanıdır.
- A fonksiyonundaki değişken, B fonksiyonunda doğrudan kullanılamaz.

---

## Örnekler

```c
void jojo() {
  printf("JoJo");
  int degisken = 31;
}

int main() {
  jojo();
  printf("%d\n", degisken);
}
```

- Bu kod bize hata verir çünkü main fonksiyonunda degisken diye bir degisken yok
  eğer değişkeni main fonksiyonununun içinde atasaydık o zaman kod çalışırdı.
- Bu yüzden eğer bir fonksiyondan değişken çıkartmak istiyorsak ya global bir değişken yapacağız
  ya da return edeceğiz.

- Eğer return etmeli bir şey istiyorsak şöyle yaparız:

```c
int jojo() {
  printf("JoJo\n");
  int degisken = 31;
  return degisken;
}

int main() {
  int degisken = jojo();
  printf("%d\n", degisken);
}
```

- Global değişken her yerde geçerliliğini koruyan değişkendir.
- Global değişken kullanarak birşeyler yapmak istiyorsak şöyle yaparız.

```c
int degisken;

void jojo() {
  printf("JoJo\n");
  degisken = 31;
}

int main() {
  jojo();
  printf("%d\n", degisken);
}
```

- Fonksiyonları önceden bildirip sonra belirtebiliriz.
- Bu ne işe yarayacak diye sorarsanız. İnan bilmiyorum.

- Örnek:

```c
int jonathan(int var);

int main() {
  printf("%d\n", jonathan(31));
}

int jonathan(int var) {
  printf("JoJo\n");
  if (var == 31) {
    ++var;
  }
  return var;
}
```

- Fonksiyon içeriğini aşağı yazıyoruz bu sayede kod daha sade oluyormuş.

---
