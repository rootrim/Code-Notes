# OpenCV Basics

---

> [!FAQ] Nedir?
> OpenCV'de image, video import etmek gibi basit şeyler.

---

## Nasıl Kullanılır?

Önce `cv2` kütüphanesini import etmemiz lazım sonrasında başlayabiliriz.  
import
Resim import etmek için `imread()` fonksiyonunu kullanırız ve import ettiğimiz  
resmi görmek istiyorsak ise `imshow()` fonksiyonunu kullanabiliriz.

`imread()` fonksiyonu içine açılacak olan görselin konumu yazılır.  
`imshow()` fonksiyonu içine ise rastgele bir isim ve açılacak olan  
görselin import edilmiş olan versiyonu yazılır.

`imread()` fonksiyonu belirtilen resmi üç boyutlu bir ndarray olarak return eder.  
Bu sebeple return edilen değeri bir değişkene atamamız lazım.

Bu fonksiyonları doğruca kullanmanız yetmiyor bir görseli açmak için.  
Açılan görselin ekranda kalmasını sağlamak için bir fonksiyon kullanmamız  
gerekiyor ki böyle bir fonksiyon cv2 kütüphanesinde var ve kensisi `waitKey()`

`waitKey()` fonksiyonu içine girilen milisaniye değeri kadar bir tuş girilmesini  
bekler eğer süre aşılırsa kod devam eder. İçine 0 değerini verirsek sonsuza kadar  
devam eder.

İşte bunları içeren bir örnek:

```python
import cv2 as cv

img = cv.imread("Photos/lady.jpg")

cv.imshow("Photo", img)

cv.waitKey(0)
```

Video import etmek için `VideoCapture()` fonksiyonunu kullanırız. Bu fonksiyon içine
girilen konumadaki videoyu ve ya kamerayı bir `VideoCapture` nesnesi olarak return eder.

Elimizdeki `VideoCapture` nesnesini oynatmamız için onu framelere bölmemiz ve bir
döngü kullanarak bu frameleri göstermemiz lazım. Bu döngüyü kırmak için de bir süre
ve giriş lazım.

Bir `VideoCapture` nesnesini framelere bölmek için `read()` metodunu uygulayabiliriz.
Bu `read()` metodu bir durum bool değeri ve bir ndarray return eder. Bu return edilen
ndarray aslında bir görsel frameidir ve bunu `imshow()` fonksiyonu ile gösterebiliriz.
Bunu bir `while True:` döngüsüne alarak tüm videoyu oynatabiliriz ama sonsuza kadar devam
etmemesi için bir `if` olayı belirterek döngüyü kırmamız lazım. Döngüyü kırdıktan sonra
videoyu ve pencereleri de salmamız lazım yoksa ramde yer kaplar.

Bunları içeren bir örnek:

```python
import cv2 as cv

vid = cv.VideoCapture("Videos/dog.mp4")

while True:
    key, frame = vid.read()

    cv.imshow("Frame", frame)

    if cv.waitKey(20) & 0xFF == 27:
        break

vid.release()
cv.destroyAllWindows()
```

- `waitKey(20)` frameler arasındaki süreyi belirtti.
- `0xFF == 27` 27. ASCII karakterine basıldığında çıkılmasını emretti.
- `release()` metodu videoyu serbest bıraktı.
- `destroyAllWindows()` fonksiyonu açık pencereli kapattı.

Eğer bir görseli kaydetmek istiyorsak `imwrite()` fonksiyonunu kullanabiliriz.
Bu fonksiyon içine kaydedilecek konumu ve kaydedilecek resmi alır.

Basit bir örnek:

```python
import cv2 as cv

image = cv.imread('ornek_goruntu.jpg')

cv.imwrite('kaydedilen_goruntu.jpg', image)
```

Video kaydetmek için ise `VideoWriter()` fonksiyonunu kullanabiliriz ama bu fonksiyon
baya parametre istiyor. Bunlar: dosya konumu, kodek, fps, çerçeve boyutu ve kaydedilecek
video. Bu parametreleri elimizle girebiliriz ya da OpenCV'nin bize sunduğu `CAP_CROP_*`
değerlerini kullanabiliriz.

Bu `VideoWriter()` fonksiyonunun çalışma mantığı `imwrite()`'a benziyor ama büyük bir fark
var `imwrite()` doğrudan kaydederken `VideoWriter()` üstüne görsel kaydedebileceğimiz bir
video oluşturuyor. Yani `VideoWriter()` ile oluşturduğumuz bir nesneye `write()` metodunu
kullanarak frame kaydetmemiz gerekiyor.

İşte bunları içeren bir fonksiyon örneği:

```python
def saveVideo(
    path: str, vid: cv.VideoCapture, fps=0, frame_width=0, frame_height=0, codec="XVID"
) -> None:

    fps = fps or int(vid.get(cv.CAP_PROP_FPS))
    frame_width = frame_width or int(vid.get(cv.CAP_PROP_FRAME_WIDTH))
    frame_height = frame_height or int(vid.get(cv.CAP_PROP_FRAME_HEIGHT))
    fourcc = cv.VideoWriter_fourcc(*codec)

    if not vid.isOpened():
        print("Video cannot be opened.")
        return

    output = cv.VideoWriter(path, fourcc, fps, (frame_width, frame_height))

    while True:
        ret, frame = vid.read()

        if not ret:
            break

        output.write(frame)

    vid.release()
    output.release()
    print("Video saved.")
```
