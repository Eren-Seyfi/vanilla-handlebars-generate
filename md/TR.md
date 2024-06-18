# Handlebars Şablon Projesi

Bu proje, Handlebars şablonlarını kullanarak dosya izleyici ile Handlebars dosyalarını HTML'e dönüştüren ve genel varlıkları bir çıktı dizinine kopyalayan basit bir kurulum örneği sunar. Proje ayrıca düzenli aralıklarla çıktı dizinini temizleme ve yeniden oluşturma özelliği içerir.

## Özellikler

- Handlebars şablonlarını HTML'e dönüştürür.
- Genel varlıkları (CSS, JS, resimler vb.) çıktı dizinine kopyalar.
- Kaynak dizinindeki değişiklikleri izler ve çıktı dizinini buna göre günceller.
- Düzenli aralıklarla çıktı dizinini temizler ve yeniden oluşturur.

## Kurulum

1. Depoyu klonlayın:

   ```bash
   git clone https://github.com/Eren-Seyfi/vanilla-Handlebars-generate.git
   cd Handlebars-template-project
   ```

2. Bağımlılıkları yükleyin:

   ```bash
   npm install
   ```

3. Projeyi çalıştırın:

   ```bash
   npm start
   ```

## Yapı

- **src**: Handlebars şablonları ve genel varlıkları içeren kaynak dizini.
  - **templates**: `layouts`, `partials`, `components` ve `pages` içerir.
  - **public**: CSS ve JS dosyaları gibi genel varlıkları içerir.
- **www**: Dönüştürülmüş HTML ve kopyalanmış varlıkların saklandığı çıktı dizini.
- **bootstrap.js**: Projeyi kurmak, değişiklikleri izlemek ve şablonları dönüştürmek için ana betik.
- **structure.json**: Yapıyı ve ayarları tanımlayan yapılandırma dosyası.

## Layouts Nasıl Çalışır:

Bu projede, Handlebars şablonları modüler bir yapı sağlamak için layout'lara (düzenlere) ayrılmıştır. Layout dosyaları templates/layouts dizininde yer alır. Her sayfa Handlebars dosyası, dosya adında layout adını belirterek hangi layout dosyasına ait olduğunu belirtir, örneğin, index.main.Handlebars, main.Handlebars layout'unun kullanılacağını gösterir.

Şablonlar render edildiğinde, layout dosyası sayfa içeriğini sarmak için kullanılır. Bu, farklı sayfalar arasında tutarlı başlık, altbilgi ve navigasyon bölümleri sağlar. Örneğin, bir index.main.Handlebars dosyası, main.Handlebars layout'u ile sarılacak ve bu layout'u kullanan tüm sayfalar için aynı başlık ve altbilgi kullanılacaktır.

## Yapılandırma

### structure.json

```json
{
  "inputDir": "src",
  "outputDir": "www",
  "interval": 5000,
  "mainTemplate": "templates/layouts/main.hbs",
  "pagesDir": "templates/pages",
  "templates": {
    "layouts": ["main.hbs", "example.hbs"],
    "partials": ["header.hbs", "footer.hbs", "nav.hbs"],
    "pages": [
      "index.main.hbs",
      "about.main.hbs",
      "index.example.hbs",
      "about.example.hbs"
    ],
    "components": []
  },
  "public": {
    "css": ["style.css"],
    "js": ["app.js"]
  }
}
```

- **inputDir**: Kaynak dizin.
- **outputDir**: Çıktı dizin.
- **interval**: Çıktı dizinini temizlemek ve yeniden oluşturmak için milisaniye cinsinden aralık.
- **mainTemplate**: Ana Handlebars şablonunun yolu.
- **pagesDir**: Handlebars sayfa şablonlarını içeren dizin.
- **templates**: Şablonların yapısı.
- **public**: Genel varlıkların yapısı.

## Betikler

- **start**: Ana betiği (`bootstrap.js`) çalıştırır.
