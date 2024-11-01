# Bubble Sort Algoritması

---

> [!faq] Nedir?
> Bubble Sort algoritması bir sıralama algoritmasıdır.
> O(n²) karmaşıklığına sahip olduğu için büyük dizilerde çok verimli değildir
> ama bir o kadar da basittir.

---

## Mantığı Nedir?

- Bubble sortun ana mantığı dönüşümlü olarak kıyaslama yapmaktır.
- Daha ayrıntılı bir açıklama istiyorsan şöyle: önce ilk iki
  değişkeni karşılaştırıyor sonra eğer önce gelen değişken daha büyükse
  iki değişkenin de yerini birbirleriyle değiştirir sonra ikinci
  ve üçüncü değişkenle sonra üçüncü... Böyle böyle devam ederek sona
  kadar gelir ve bu bir tur olur. Her turda sadece 1 değişken tam olarak
  yerine oturur bu yüzden bu turları listenin uzunluğu kere tekrarlarız.

### Örneklerle Daha İyi Kavrayalım

- Pythonda basit bir örnek:

```python
def bubbleSort(aList: list[int]):
    n = len(aList)

    for i in range(n - 1):
        for j in range(n - 1 - i):
            if aList[j] > aList[j + 1]:
                aList[j + 1], aList[j] = aList[j], aList[j + 1]

    return aList
```

- Önce listenin uzunluğunu len fonksiyonuyla belirttik
  sonrasında listenin uzunluğuna göre iki tane for döngüsü
  başlattık. Bu döngülerden içerdeki ana olayı yaparken diğeri
  tekrar yapmakta. İçerdeki döngünün n - 1 - i olmasının sebebi
  her döngüden sonra zaten 1 net sayı oturduğu için tekrardan tekrarlamaya
  gerek kalmıyor. Oradaki if ise kaşılaştırmayı yapıyor ve duruma göre
  swap işlemini gerçekleştiriyor.

- Hadi numpy ndarrayları için de bir örnek yapalım:

```python
import numpy as jo
from numpy.typing import NDArray

def bubbleSortNd(aNda: NDArray[jo.int64]) -> NDArray[jo.int64]:
    n = aNda.size

    for i in range(n - 1):
        for j in range(n - 1 - i):
            if aNda[j] > aNda[j + 1]:
                aNda[j + 1], aNda[j] = aNda[j], aNda[j + 1]

    return aNda
```

- Bu kod da üsttekiyle neredeyse aynı. Fazladan aNda değişkeninin boyutunu
  falan belirttik onun dışında aynı.

- Hadi Lua dilinde bir örnek yazalım:

```lua
local function bubbleSort(table)
	local n = #table

	for i = 1, n - 1 do
		for j = 1, n - i do
			if table[j] > table[j + 1] then
				table[j], table[j + 1] = table[j + 1], table[j]
			end
		end
	end
	return table
end
```

- Bu da gayet basit. Lua da indexler 1'den başladığı için azcık değişiklik var sadece.

- Şimdi de C dilinde bir örnek:

```c
void swap(int *a, int *b) {
  int temp = *a;
  *a = *b;
  *b = temp;
}

void bubbleSort(int arr[], int n) {
  for (int i = 0; i < n - 1; i++) {
    for (int j = 0; j < n - 1 - i; j++) {
      if (arr[j] > arr[j + 1]) {
        swap(&arr[j], &arr[j + 1]);
      }
    }
  }
}
```

- Bu birazcık daha zor ama mantığı kavrayınca oturuyor.

---
