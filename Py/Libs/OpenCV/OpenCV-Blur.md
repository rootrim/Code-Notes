# OpenCV Blur

---

> [!faq] Nedir?
> Blur, görüntüyü bulanıklaştırarak detayları çıkarmak demektir.

---

## Nasıl Kullanılır?

OpenCV bize 3 ana bulanıklaştırma tekniği sunar bunlar Ortalama, Gauss ve
Medyan bulanıklaştırmadır.

Ortalama bulanıklaştırma, belirli bir bölgenin piksellerinin ortalama rengini alır
ve o bölgeye yayar.

Gauss bulanıklaştırmada ise ortalama bulanıklaştırmanın aksine gauss çekirdeği
kullanılır. Bu yöntemde sigma ve normal yönlerdeki standartı belirtmeliyiz.

Medyan bulanıklaştırmada da çekirdek içindeki piksellerin medyanı alınır ve
çekirdek merkezi bu medyan ile değiştirilir.

İşte bu üç tekniğin de olduğu bir örnek:

```python
img = cv.imread("Photos/cat.jpg")

normalBlur = cv.blur(img, (5, 5))
gaussBlur = cv.GaussianBlur(img, (5, 5), 7)
medianBlur = cv.medianBlur(img, 3)

cv.imshow("Normal", normalBlur)
cv.waitKey(0)

cv.imshow("Gauss", gaussBlur)
cv.waitKey(0)

cv.imshow("Median", medianBlur)
cv.waitKey(0)
```
