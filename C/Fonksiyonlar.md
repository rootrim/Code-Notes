# Fonksiyonlar

---

## Nedir? Nerelerde Kullanılır?

- Fonksiyonlar her kodda kesinlikle vardır.
- Fonksiyonlar kod parçalarını bir araya getirerek tekrar kullanmamıza yarar.
- Önceden belirlenmiş fonksiyonlar vardır. Bunlara
  printf, scanf ve main fonksiyonlarını örnek verebiliriz.

---

## Nasıl Kullanılır?

- Öğrendikten sonra fonksiyonlar basittir
  ama o zamana kadar birşeyler bilmen gerek işte.

- Basit bir fonksiyon oluşturmak için bir return tipine - return tipine sonra döneceğiz -
  ve fonksiyon ismine ihtiyacımız var.
- Örnek:

```c
void habbabicFon() {
    printf("Kono Habbab da!");
}
```

- Bu kodda return tipi void ve fonksiyon ismi habbabicFon'dur.
- Fonksiyon içindeki kodu yazdırmak için vardır ama onu çağırana kadar hiçbir işe yaramaz.

- Fonksiyon çağırmaya bir örnek:

```c
void kingCrimson() {
    printf("Yaroooo");
}

int main() {
    kingCrimson();
}
```

- Bu kodda kingCrimson fonksiyonunu kullandık.

- Peki fonksiyonlara dışardan değer vermek istesek ne yapmamız gerekir?
- Fonksiyonlara dışardan değer vermek için parametre veririz.
- Parametreler fonksiyondaki () içine yazılan değerleri ifade eder.

- Örnek:

```c
void salute(char *name) {
  printf("Merhaba, %s.\n", name);
}

int main() {
  salute("Habbab"); // Çıktı "Merhaba, Habbab." olur.
  return 0;
}
```

- İstersek birden fazla parametre de verebiliriz.

```c
void salute(char *name, int ball) {
  printf("Merhaba, %s.\n", name);
  printf("Sen %d yıllar eskisisin.\n", ball);
}

int main() {
  salute("Habbab", 4); // Çıktı "Merhaba, Habbab.;Sen 4 yıllar eskisisin." olur.
  return 0;
}
```

- Peki biz fonksiyonun bize sağladığı değerleri direk ekrana yazdırmak
  istemiyorsak, bir yere kaydetmek istiyorsak ne yapacağız.
- Böyle bir durumda return değerlerini kullanırız.
- Şu zamana kadar örneklerde return tipi void'di; void return değeri yok demektir.
- Eğer return değeri almak istiyorsak voidden başka birşey kullanmamız gerekiyor.
- return tipi olarak ne verirsek çıktı olarak onu alırız.
- return tipi olarak direkt veri tipi veririz, mesela int.

- Örnek:

```c
int cikarma(int sayi1, int sayi2) {
  return sayi1 - sayi2;
}

int main() {
  int num1, num2;
  printf("Aralarında boşluk olacak şekilde iki tamsayı yazın: ");
  scanf("%d %d", &num1, &num2);
  printf("%d\n", cikarma(num1, num2));
}
```

- Fonksiyonun return tipi int olduğu için return edilen değer bir integer.
- return etmeyi fonksiyonun çağrıldığı yere return edilen değeri yazmak gibi düşünebilirsiniz.

---
