# Trident-RFoocus

# Yapay Zekâ veri jenerasyonu – Trident-RFoocus

Trident-RFoocus, kurulum zahmetini en aza indiren, güçlü ama basit bir arayüzle hızlı ve yüksek kaliteli görseller üretmeyi hedefleyen bir uygulamadır. Uygulamanın ana amacı TRIDENT-Net için sentetik veri üretimidir.

Stil, çözünürlük ve performans ayarları tek ekranda; gelişmiş seçeneklere ihtiyaç duymadan birkaç kelimeyle görseller oluşturabilirsiniz. İsterseniz ayrıntılı ayarlara inerek üretimin her adımını kontrol edebilirsiniz.

Hazırda bulunan ayarlar birçok deneme sonucunda en iyi sonuçları veren ayarlardır(özellikle speeed konfigürasyonu), img2img için 0.28-0.36 aralığı önerilirken kalite artırılmak istenirse step sayısı 70-85 aaralığına çıkartılabilir(45-70 aralığı kötü sonuçlar vermekte).


## İndirme ve Kurulum

### Windows

Arşivi çıkarın ve "run.bat" dosyasını çalıştırın. İlk çalıştırmada gerekli modeller otomatik olarak indirilecektir. Model dosyalarınız zaten varsa ilgili klasörlere kopyalayarak kurulumu hızlandırabilirsiniz. "MetadataIncompleteBuffer" hatası görürseniz model dosyalarınızı yeniden indirin.

### Linux

Sanal ortam oluşturun, etkinleştirin ve gereksinimleri yükleyin:

    virtualenv venv
    source venv/bin/activate
    pip install -r requirements_versions.txt

Ardından uygulamayı başlatın:

    python launch.py

Uzak bağlantı için:

    python launch.py --listen

## Özellikler

1. `settings/styles.csv` ile özel stil desteği
2. Çözünürlük ve Stil seçenekleri açılır menülere taşındı
3. Bir prompta birden çok stil uygulama ve “Stili prompta gönder” düğmesi
4. Üretilen görsellere gömülü PNG meta verisi kaydı
5. `settings/settings.json` üzerinden varsayılan UI değerlerini değiştirme
6. “One Button Prompt” sekmesiyle rastgele prompt üretimi
7. Okunabilir çözünürlük modu
8. `settings/settings.json` ile tema desteği
9. `settings/resolutions.json` ile özel çözünürlük ekleme
10. Wildcard desteği (örnek için `wildcards/colors.txt`)
11. `--nobrowser` parametresi ile tarayıcı otomatik açılmasını kapatma
12. `settings/paths.json` ile checkpoints/loras/outputs klasörlerini özelleştirme
13. Özel “Performance” profilleri (sampler/scheduler, steps, cfg, clip skip)
14. Konsolda süre göstergesi; kök dizinde `notification.mp3` varsa üretim bitince çalar
15. Üretimi durdurmak için **İptal** düğmesi
16. `Ctrl+Enter` ile “Generate” kısayolu
17. Prompt içine LoRA ekleme (ör. `<lora:MyAwesomeLora-SL:0.90>`) 
18. Eski görselleri ana alana sürükleyip meta veriden promptu geri yükleme
19. Tüm ayarları UI’a girmeden, prompt alanına JSON meta veri yapıştırıp üretim başlatma
20. `---` ayırıcılarıyla çoklu konu için toplu üretim
21. Modeller/LoRA’lar için alt klasör desteği
22. Promptta `<style:stylename>` yazarak stil seçimi
23. PowerUp sekmesinde ControlNet alanı
24. Özel performans profilleri oluşturup kolayca seçme
25. ControlNet varsayılanlarını ayarlama veya ayrıntılı özelleştirme
26. PowerUp sekmesinde Image2Image modu
27. SSD-1B model desteği
28. Lora tetik kelimelerini aynı adlı `.txt` dosyasından otomatik okuma
29. İstediğiniz upscaler ile büyütme (varsayılan `4xUltrasharp`)
30. `Info` sekmesinde Metadata Viewer
31. SDXL LCM LoRA desteği
32. Görsel Sayısı 0 ise “Sürekli Üretim” modu
33. Görseli ana alana sürükleyip prompt çıkarmak için Clip Interrogator
34. PowerUp sekmesinde Inpainting (galeride seçili görselle de çalışır)
35. Evolve: mevcut üretimi farklı varyasyonlara dönüştürür (sabit seed ile önerilir)
36. Basit kimlik doğrulama: `--auth=kullanici/sifre` (paylaşım açıkken zorunlu)
37. LoRA tetik kelimelerini otomatik indirme ve gösterme
38. Otomatik Negatif Prompt
39. `reinstall` dosyası mevcutsa kütüphaneleri yükseltme otomasyonu
40. RemBG PowerUp (arkaplan kaldırma)
41. Hareketli küçük resimlerle yeni model/LoRA seçimi
42. SD3 desteği
43. Checkpoint birleştirmeleri (merge-files) desteği
44. Modeller bölümünde MergeMaker (kendi birleştirmelerinizi oluşturun)
45. Diffusers ve bazı HuggingFace modelleri için deneysel destek
46. Img2STL PowerUp (görselden .stl üretimi)
47. Flux desteği ve GGUF/safetensors varyasyonları
48. Görsel sorgulama için Florence
49. Llama 3.2 entegrasyonu
50. “BaseModel” desteği

## Teşekkürler

Bu kod tabanı; RuinedFooocus, Fooocus, Automatic1111 ve ComfyUI ekosistemlerinden esinlenilerek çatallanmış ve uyarlanmıştır.

