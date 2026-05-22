# Metodoloji

Bu belge, projedeki metinlerin dijitalleştirilmesi, transkripsiyon, sadeleştirme
ve metadata kurallarını açıklar. Amaç, tutarlı, yeniden üretilebilir ve atıf yapı
labilir içerikler üretmektir.

1) Dosya formatları
- Asıl metinler için tercih edilen formatlar: PDF (tarama), Markdown (.md) (düzenlenmiş metin), opsiyonel EPUB (e-kitap). Her eserin kök klasöründe bir `metadata.yml` bulunmalıdır.

2) Metadata (metadata.yml)
- Zorunlu alanlar: `title`, `author`, `original_publication_year`, `source`, `language`, `license`.
- Örnek:

  ```yaml
  title: "İslam Dini"
  author: "Ahmet Hamdi Akseki"
  original_publication_year: 1930
  source: "Sebilürreşad, c. X"
  language: "tr-TR"
  license: "public-domain"
  ```

3) Transkripsiyon kuralları
- Orijinal Osmanlı Türkçesi metinler önce OCR ile işlenir (Tesseract önerilir), ardından insan tashihi (proofreading) yapılır.
- Diakritik ve özel harfler modern Türkçe karşılıklarına dönüştürülür; kelime sonunda kayıplar veya birleşik kelimeler orijinali koruyacak şekilde not edilir.

4) Sadeleştirme kuralları
- Sadeleştirilmiş metin ayrı bir dosyada saklanır: `sadelestirilmis.md`.
- Orijinal ile karşılaştırma kolaylığı için bölüm başlıkları korunmalı ve satır numaraları veya paragraf etiketleri kullanılmalıdır.

5) İsimlendirme ve klasör yapısı
- Her eser klasörü: `/<biblio-slug>/` (ör: `islam-dini/`)
- İçerik:
  - `original.pdf` (tarama)
  - `original.md` (OCR sonrası tashih edilmiş metin)
  - `sadelestirilmis.md` (güncel Türkçe)
  - `metadata.yml`

6) Tashih (Proofreading)
- Tashih yapan kişi `metadata.yml` içinde `proofreader` alanına eklenecektir.
- Değişiklikler Git ile takip edilmeli; büyük tashihler ayrı bir branch'te yapılmalıdır.

7) Atıf ve lisans
- Metinlerin çoğu kamu malı statüsündedir; yine de kaynak ve baskı bilgisi her zaman metadata'da gösterilmelidir.

8) QC ve onay süreci
- Yeni metin eklendiğinde bir PR açılmalı; 2 bağımsız düzeltmen tarafından onaylandıktan sonra `main` dalına merge edilecektir.

9) Dosya kodlaması
- Tüm metin dosyaları UTF-8 (BOM olmadan) olarak saklanmalıdır.

10) Araç tavsiyeleri
- OCR: Tesseract (varsayılan), alternatif ABBYY FineReader (telif hakkı gerektiren yazılımlar için ekipte izin olmalı).
- Metin karşılaştırma: `git diff`, `diff` veya `meld` kullanılması önerilir.

Bu kılavuz, proje içinde tutarlılığı sağlamak için kullanılacaktır. İlerleyen dönemlerde yeni gereksinimler eklendikçe güncellenecektir.
