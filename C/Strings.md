# Strings

---

## Nedir? Nerelerde Kullanılır?

- C dilinde aslında stringler yoktur onun yerine char arrayları vardır.
- Metin içeren herşeyde vardırlar.
- Çok fazla kullanacağız dikkatli oku.

---

## Nasıl Kullanılır?

- Char tipi bir değişkenin sağına köşeli parantez koyarak oluştrulur.
- %s ile belirtilebilir.
- Çift tırnak gereklidir.

- Hadi Örnekleyelim!

```c
char nawa[] = "Kira";
char surnawa[] = "Yoshikage";
printf("Watashi no na wa %s %s...\n", nawa, surnawa);
// Çıktı Watashi no na wa Kira Yoshiakge... olur
```

- Başka bir string oluşturma yöntemi ise direkt liste olarak yapmak.

```c
char nawa[] = {'K', 'i', 'r', 'a', '\0'};
char surnawa[] = {'Y', 'o', 's', 'h', 'i', 'k', 'a', 'g', 'e', '\0'};
printf("Watashi no na wa %s %s...\n", nawa, surnawa);
```

- Burada teker teker char tipi veri verdiğimiz için tek tırnak kullandık.
- En sondaki '\0' ne diye soracak olursanız o stringin sonuna
  geldiğimizi belirten bir özel karakter. Bu yöntem ile liste oluşturuyorsak
  kullanmak zorundayız.

- Stringler aslında bir liste olduğu için içindeki değerleri
  istediğimiz gibi değiştirebiliriz.

- Örnek?

```c
char king[] = "puck";
printf("%s\n", king);
king[0] = 'l';
printf("%s\n", king);
king[0] = 'd';
printf("%s\n", king);
```

### Özel Karakterler

- Özel karakterler belirli bir işe yarayan karakterlerdir.
- Çift tırnak içinde çift tırnak kullanmak ve ya alt satıra
  geçme gibi kullanım alanları vardır.

- İşte özel karakterlerle ilgili bir tablo:

| Karakter | İsmi            | Açıklama                                 |
| -------- | --------------- | ---------------------------------------- |
| \n       | Yeni Satır      | Metni bir alt satıra taşır               |
| \t       | Sekme           | Metin içinde tab (sekme) boşluğu bırakır |
| \a       | Alarm           | Bilgisayarın bip sesi çıkarmasını sağlar |
| \b       | Geri Al         | İmleci bir karakter geri alır            |
| \\       | Ters Eğik Çizgi | Ters eğik çizgi karakteri basar          |
| \'       | Tek Tırnak      | Tek tırnak karakteri basar               |
| \"       | Çift Tırnak     | Çift tırnak karakteri basar              |
| %%       | Yüzde           | Yüzde işareti basar                      |
| \0       | Null            | Stringin bittiğini belirtir              |

- Çılgın Örnek:

```c
printf("Habbab\'ın sigmalık oranı:\n\t%%100\n\"Sigmalar asla kendi kendine oluşmaz\"\n");
```

### String fonksiyonları

- C dilinin string.h kütüphanesinde bazı işimize yarar fonksiyonlar bulunmakta.

#### strlen

- stringin uzunluğunu söyler.
- sizeof da bunu yapmıyormu diyecek olursanız bunun olayı başka.
- sizeof \0 karakterini de sayarak boyutunu söylerken, strlen
  direkt gerçek uzunuğu söyler.

- Örnek:

```c
char nawa[] = "Kira Yoshikage";

for (int i = 0; i < strlen(nawa); i++) {
    printf("%c\n", nawa[i]);
}
```

#### strcat

- strcat fonksiyonu verilen ilk stringe diğerini ekler.
- Verilen ilk stringin ikinciyi alabilecek kadar büyük olması gerekmektedir.

- Örnek:

```c
char nawa[20] = "Kira ";
char surnawa[10] = "Yoshikage";

strcat(nawa, surnawa);

printf("%s\n", nawa); // Çıktı Kira Yoshikage olur
```

- Derleyici hatası almamak için boyutlara çok dikkat etmek lazım.
- \0 karakterini de saymamız gerekiyor.

#### strcpy

- Bu fonksiyon ise girilen ilk alana diğerini kopyalar.
- Bunda da alanlar çok önemli.

- Örnek:

```c
char newton[6] = "Ampul";
char edison[6];

strcpy(edison, newton);

printf("%s\n", edison);
```

#### strcmp

- Bunu zaten operatörlerde anlatmıştım oradan bakabilirsiniz.

---
