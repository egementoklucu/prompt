# EggApps · Prompting Laboratuvarı

Prompting ve context prompting tekniklerini sade Türkçe örneklerle öğrenmek, karşılaştırmak ve kendi işinize uyarlamak için hazırlanmış, **tek dosyalık** ve kaynaklara dayalı bir web rehberi.

Kurulum, derleme veya internet bağlantısı gerekmez: `index.html` dosyasını indirip tarayıcıda açmanız yeterli.

> Bu proje bir öğrenme ve çalışma aracıdır. Sitedeki teknikler hiçbir modelde belirli bir başarıyı garanti etmez; kendi görevinizde test ederek karar verin.

---

## İçindekiler

- [Neler var?](#neler-var)
- [Teknik kataloğu (35 teknik)](#teknik-kataloğu-35-teknik)
- [Nasıl kullanılır?](#nasıl-kullanılır)
- [Teknik yapı](#teknik-yapı)
- [Doğruluk ilkeleri](#doğruluk-ilkeleri)
- [Erişilebilirlik](#erişilebilirlik)
- [Test durumu](#test-durumu)
- [Başlıca kaynaklar](#başlıca-kaynaklar)
- [Katkı ve geri bildirim](#katkı-ve-geri-bildirim)

---

## Neler var?

Site, üst menüden ulaşılabilen on bölümden oluşur:

| # | Bölüm | Ne işe yarar? |
|---|---|---|
| 1 | **Giriş** | EggApps markası ve laboratuvarın amacı. |
| 2 | **Prompting nedir?** | Prompting ve context prompting'e basit örneklerle giriş. |
| 3 | **Başlangıç şablonu** | `[Görev] + [İlgili bağlam/veri] + [Amaç/hedef kitle] + [İstenen çıktı] + [Kısıtlar] + [Gerekiyorsa örnek ve başarı ölçütü]` yapısının etkileşimli anlatımı. Bunun evrensel bir formül değil, pratik bir başlangıç noktası olduğu ve bütün parçaların her zaman gerekmediği açıkça belirtilir. |
| 4 | **Teknik kataloğu** | 35 teknik: arama, kategori filtresi ve açılır detaylar. Her teknikte ne zaman kullanılır / kullanılmaz, zayıf ve iyileştirilmiş prompt örneği, bileşenlerin açıklaması, kopyalanabilir şablon ve ilgili kaynaklar yer alır. |
| 5 | **Önce / Sonra** | Eğitim, yazılım, müşteri desteği, pazarlama ve analiz alanlarından karşılaştırmalı örnekler. |
| 6 | **Bana uygun tekniği öner** | Dokuz soruluk kural tabanlı öneri aracı: ilk öneri, alternatif, artılar/sınırlar ve puanın nasıl hesaplandığını gösteren tablo. Sonuçtaki yüzde bir **ihtiyaçlarla eşleşme tahminidir**; bilimsel bir ölçüm veya başarı oranı değildir. |
| 7 | **Prompt oluşturucu** | Tekniğe göre değişen alanlar, canlı önizleme, örnek doldurma, temizleme ve kopyalama. |
| 8 | **Bağlam bütçesi** | Bağlam penceresi, girdi tokenları ve çıktıya ayrılan tokenlara göre kalan alanı ve doluluk oranını hesaplar. Metinden token tahmini yapan araç yaklaşıktır; gerçek bir tokenizer değildir. |
| 9 | **Sık hatalar ve SSS** | Yaygın prompt hataları ve sık sorulan sorular. |
| 10 | **Kaynaklar** | Resmî dokümanlar ve özgün araştırmalar; kısa Windows kullanım rehberi. |

---

## Teknik kataloğu (35 teknik)

| Kategori | Teknikler |
|---|---|
| **Temel talimat** (6) | Zero-shot · One-shot ve few-shot · Rol / persona · Sistem ve kullanıcı talimatlarını ayırma · Olumlu talimat · Kuralın nedenini açıklama |
| **Bağlam** (6) | Contextual prompting · RAG ve context engineering · Talimatı sonda tekrarlama · Uzun bağlam yerleşimi ve önce alıntı · Önbellek dostu prompt yapısı · Bağlam sıkıştırma ve devir notu |
| **Yapı ve çıktı** (6) | Yapılandırılmış çıktı · Etiketler, ayraçlar ve referans metni · Örneklerle stil/biçim gösterme · Prompt biçimini çıktıya benzetme · Çıktı başlangıcı ipucu (cue) · Değişkenli prompt şablonları |
| **Akış ve akıl yürütme** (8) | Adımlara bölme ve prompt chaining · İteratif iyileştirme · Chain-of-thought (CoT) · Step-back prompting · Self-consistency · Tree of Thoughts · Least-to-most · Promptu modele iyileştirtme (meta prompting) |
| **Araçlar ve çok modlu** (4) | Tool / function calling · Çok modlu prompting · ReAct · Hesabı koda devretme (PAL / PoT) |
| **Doğrulama ve güvenlik** (5) | Değerlendirme, doğrulama ve kaynak isteme · Chain-of-Verification · Kaçış yolu verme · Güvenilmeyen girdiyi ayırma (prompt injection) · Rubrikle değerlendirme (LLM-as-a-judge) |

Katalogda **prompt teknikleri**, **model/API özellikleri** (ör. yapılandırılmış çıktı, prompt caching) ve **çalışma yöntemleri** etiketlerle birbirinden ayrılır.

---

## Nasıl kullanılır?

### Windows'ta (önerilen yol)

1. Bu sayfada yeşil **Code** düğmesine, ardından **Download ZIP**'e tıklayın ya da yalnızca `index.html` dosyasını indirin.
2. ZIP indirdiyseniz dosyaya sağ tıklayıp **Tümünü ayıkla** deyin.
3. `index.html` dosyasına çift tıklayın. Dosya varsayılan tarayıcınızda (Edge, Chrome vb.) açılır.
4. Farklı bir tarayıcıda açmak için: sağ tık → **Birlikte aç** → tarayıcıyı seçin.

### macOS / Linux

`index.html` dosyasını herhangi bir modern tarayıcıyla açın. Ek bir şey gerekmez.

### GitHub Pages ile yayınlama (isteğe bağlı)

Dosya depo kökünde olduğu için GitHub Pages ile doğrudan yayınlanabilir:

1. Depoda **Settings → Pages** bölümüne gidin.
2. **Source** olarak *Deploy from a branch* seçin, dal olarak `main` ve klasör olarak `/ (root)` belirleyin.
3. Kaydettikten birkaç dakika sonra site şu adreste yayına girer: `https://egementoklucu.github.io/prompt/`

> Not: GitHub'da `index.html` dosyasına tıklamak sayfayı çalıştırmaz, yalnızca kaynak kodunu gösterir. Siteyi görmek için dosyayı indirin veya GitHub Pages'i etkinleştirin.

---

## Teknik yapı

- **Tek dosya:** HTML, CSS ve JavaScript `index.html` içine gömülüdür (yaklaşık 450 KB).
- **Bağımlılık yok:** Framework, derleme adımı, npm paketi, CDN, harici font, görsel veya betik kullanılmaz. Sayfa internet bağlantısı olmadan da çalışır.
- **Sistem fontları:** Segoe UI, Georgia/Palatino ve Cascadia/Consolas gibi işletim sisteminde hazır bulunan fontlar.
- **Gömülü SVG:** Animasyonlu yumurta logosu ve tüm ikonlar satır içi SVG'dir.
- **JavaScript olmadan da okunur:** Katalog, örnekler ve kaynaklar HTML içinde hazır gelir; etkileşimli araçlar (arama, öneri, oluşturucu, hesaplayıcı, kopyalama) JavaScript gerektirir.
- **Yazdırma desteği:** Yazdırırken etkileşimli araçlar gizlenir ve tüm teknik detayları otomatik olarak açılır.
- **Hareket tercihi:** İşletim sisteminde "animasyonları azalt" seçiliyse (`prefers-reduced-motion`) animasyonlar kapanır.

### Dosya yapısı

```
prompt/
├── index.html   # Sitenin tamamı (HTML + CSS + JS)
└── README.md    # Bu dosya
```

---

## Doğruluk ilkeleri

- **Kaynaksız iddia yok:** Teknikler resmî sağlayıcı dokümanlarına (OpenAI, Anthropic, Google, Microsoft, OWASP) ve özgün araştırma makalelerine dayanır. Kaynak bağlantıları **10 Ekim 2026** tarihinde kontrol edilmiştir.
- **Uydurma sayı yok:** Başarı yüzdesi, doğruluk skoru, hız veya maliyet kazancı gibi doğrulanmamış rakamlar kullanılmaz.
- **Sağlayıcı farkları açıkça yazılır:** Örneğin uzun bağlamda talimatın yeri konusunda Anthropic ve OpenAI'nin önerileri farklıdır; site ikisini de gösterir ve test etmenizi önerir.
- **Topluluk şablonları ayrı tutulur:** TCF, RACE, CRAFT gibi kısaltmalar resmî teknik olarak değil, yalnızca "toplulukta kullanılan şablon" olarak anılır.
- **Akıl yürütme güvenli anlatılır:** CoT; kısa gerekçe, kontrol edilebilir ara adımlar ve son kontrol üzerinden öğretilir. Modelin gizli iç muhakemesini zorla çıkarmaya çalışmak önerilmez.
- **Bağlam sınırları vurgulanır:** Gereğinden uzun bağlamın modelin dikkatini dağıtabileceği ve token / bağlam penceresi sınırları ayrıca anlatılır.
- **Güvenlik:** Dışarıdan gelen metni işleyen promptlarda prompt injection riskine ve promptun tek başına yeterli koruma olmadığına dikkat çekilir.

---

## Erişilebilirlik

- Anlamsal HTML (bölüm başlıkları, `details/summary`, `fieldset/legend`, tablolar için başlık hücreleri)
- Klavyeyle tam kullanım ve görünür odak göstergesi
- Düğme ve bağlantılarda erişilebilir adlar; yeni sekmede açılan bağlantılar için ekran okuyucu notu
- Renk kontrastı kontrol edilmiş renk paleti
- Kopyalama başarısız olursa metni elle kopyalamak için açılan yedek pencere; işlem sonucu ekran okuyuculara da duyurulur

---

## Test durumu

Otomatik testler Playwright ile yapılmıştır:

| Kontrol | Sonuç |
|---|---|
| Chromium ve Firefox: JavaScript hatası, katalog arama/filtre, detay açma, kopyalama, oluşturucu geçişleri, öneri senaryoları, iç bağlantılar | Geçti |
| axe-core erişilebilirlik taraması (Chromium) | 0 ihlal |
| 360 px telefon genişliğinde yatay taşma | Yok |
| JavaScript kapalıyken katalog ve detaylar | Çalışıyor |
| HTML doğrulayıcı (vnu) | HTML hatası yok |
| Dış kaynak bağlantıları | Tümü erişilebilir (10 Ekim 2026) |

**Henüz test edilmeyenler:** Windows'ta Edge ile gerçek cihazda kullanım, Safari/WebKit, ekran okuyucuyla gerçek kullanım ve örnek promptların gerçek modellerdeki sonuçları.

---

## Başlıca kaynaklar

Tam liste sitenin **Kaynaklar** bölümünde ve her tekniğin kendi detayındadır. Öne çıkanlar:

**Resmî dokümanlar**

- OpenAI — [Prompt engineering](https://developers.openai.com/api/docs/guides/prompt-engineering)
- Anthropic — [Prompting best practices (Claude)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)
- Google — [Prompt design strategies (Gemini API)](https://ai.google.dev/gemini-api/docs/prompting-strategies)
- Microsoft — [Prompt engineering techniques (Microsoft Foundry)](https://learn.microsoft.com/en-us/azure/foundry/openai/concepts/prompt-engineering)
- Anthropic — [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)
- OWASP — [LLM01:2025 Prompt Injection](https://genai.owasp.org/llmrisk/llm01-prompt-injection/)

**Araştırmalar**

- Brown vd., 2020 — [Language Models are Few-Shot Learners](https://arxiv.org/abs/2005.14165)
- Wei vd., 2022 — [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903)
- Lewis vd., 2020 — [Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](https://arxiv.org/abs/2005.11401)
- Yao vd., 2022 — [ReAct: Synergizing Reasoning and Acting in Language Models](https://arxiv.org/abs/2210.03629)
- Liu vd., 2023 — [Lost in the Middle: How Language Models Use Long Contexts](https://arxiv.org/abs/2307.03172)

---

## Katkı ve geri bildirim

Hatalı bilgi, kırık bağlantı veya öneri için [Issues](https://github.com/egementoklucu/prompt/issues) bölümünden kayıt açabilirsiniz. Yeni bir teknik önerirken lütfen resmî bir doküman veya hakemli/ön baskı bir makale kaynağı ekleyin.

---

<sub>EggApps · Prompting Laboratuvarı — Depo: <a href="https://github.com/egementoklucu/prompt">github.com/egementoklucu/prompt</a></sub>
