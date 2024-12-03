# OpenCV Edge Detection

---

> [!faq] Nedir?
> Kenar tespiti, bir görseldeki dik geçişleri algılayarak nesnelerin
> kenarlarını çizdiğimiz bir teknikdir.
>
> Nesne tespitinde kullanılır.

---

## Nasıl Kullanılır?

Kenar tespiti için `Canny()` fonksiyonunu kullanırız. Bu fonksiyon içine
sırasıyla işlenecek görseli, ilk threshold ve ikinci threshold değerlerini
alır.

Ama şimdi threshold değerlerine ne gireceğiz soru işareti. Bunun için bir
varsayılan arıyorsak elimizde şu şekilde olan bir formül var:

```python
low = int(max(0, (1 - 0.33) * median))
high = int(min(255, (1 + 0.33) * median))
```

Hadi bunu kullanarak bir örnek yapalım:

```python
imgNotSigma = cv.imread("Photos/bigben.jpg", 0)

median = np.median(imgNotSigma)
print(median)

low = int(max(0, (1 - 0.33) * median))
high = int(min(255, (1 + 0.33) * median))

edgedImg = cv.Canny(imgNotSigma, low, high)

imshow(imgNotSigma, cmap="gray")

imshow(edgedImg, cmap="gray")
```

İstiyorsak kenar bulmadan önce alttaki gibi bir blur uygulayarak detayları azaltabilriz:

```python
imgNotSigma = cv.imread("Photos/bigben.jpg", 0)

blurredImg = cv.GaussianBlur(imgNotSigma, (3, 3), 7)

median = np.median(blurredImg)

low = int(max(0, (1 - 0.33) * median))
high = int(min(255, (1 + 0.33) * median))

edgedImg = cv.Canny(blurredImg, low, high)

imshow(imgNotSigma, cmap="gray")

imshow(edgedImg, cmap="gray")
```
