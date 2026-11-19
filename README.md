# ebunlar uygulama güncellemeleri

Bu repo, ebunlar Android/iOS uygulamasının **canlı güncelleme** paketlerini barındırır.
Mağazaya yeni sürüm göndermeden, Lovable'da yapılan değişiklikleri telefonlara ulaştırır.

## Güncelleme nasıl yayınlanır?

1. Değişikliği Lovable'da yapın ve web'de kontrol edin.
2. Bu repoda **Actions** sekmesi → soldan **Yayınla** → **Run workflow** → (isteğe bağlı not) → **Run workflow**.
3. 2–3 dakika içinde yeşil tik çıkar. Telefonlar uygulamayı bir sonraki açışta yeni sürümü indirir;
   bir sonraki kapanıp açılışta (veya arka plandan dönüşte) yeni sürüm görünür.

Testler başarısız olursa yayın yapılmaz, telefonlardaki sürüm değişmez.

## Mağaza güncellemesi ne zaman gerekir?

Canlı güncelleme ekranları, metinleri, tasarımı ve uygulama mantığını kapsar. Şunlar için mağazaya
yeni sürüm gerekir: yeni telefon izni (kamera, konum vb.), yeni native eklenti, uygulama adı veya ikon değişikliği.
Böyle bir değişiklikte uygulama reposundaki `ota.config.json` içindeki `minNativeBuild` artırılır;
eski sürümü kullanan telefonlar uyumsuz paketi indirmez.

## Dosyalar

- `latest.json` — en son yayınlanan paketin bilgisi (uygulama buna bakar). Elle düzenlemeyin.
- **Releases** — her yayının `bundle.zip` paketi.
- `.github/workflows/yayinla.yml` — yayın işlemi.
