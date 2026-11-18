---
title: "Shader Rim & Silhouette"
domain: "Visual Art & Shaders"
department: "ART"
bundle: "Bundle_3"
ku_count: 64
tags: [visual_art_shaders, art, bundle_3, 4-bucket-module]
linked_systems: ["Volumetric Lighting & Darkness", "Combat", "Camera & Player Perspective", "Diegetic Guidance"]
---

# Shader Rim & Silhouette

> **Domain:** [[Visual Art & Shaders]] | **Department:** `ART` | **Evidence Units:** `64`  
> **Linked Systems:** [[Volumetric Lighting & Darkness]], [[Combat]], [[Camera & Player Perspective]], [[Diegetic Guidance]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Yoğun efektler veya karanlık ortamlarda oynanışın çökmesinin bir numaralı sebebi **Silüet Kaybıdır**. **Fresnel Rim Shading**, **Screen-Space Outline** ve **Value Contrast (Değer Kontrastı)** kullanarak arka plan gürültüsü ne kadar yüksek olursa olsun etkileşimli aktörlerin, düşmanların ve mermilerin 100 milisaniyede okunmasını sağlayabilirsiniz.

**Kütüphane Kanıtları (Corpus Insights):**
- The game features a global candidate system with various mechanics, design choices, and rules.
- The game features a global map system, game design systems, effect design, visual effects, sound effects, user interface design, game loop, character design, system mechanics, visual style, effects, voice acting, user interface, game loop, character development, system mechanics, visual style, effects, voice acting, user interface.
- Vertex Animation Tool is used for stylized games.
- Fluid Sim is used for stylized games.
- ZBrush is used for stylized games. — That is our directing of the effects for stylized games. The format is microtox. So there are about 11 minutes each before speakers, hopefully time at the end for questions. The idea is that there are

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 Material Graph:** `Fresnel` düğümünü (`ExponentIn = 4.0`) karakterin `EmissiveColor` kanalına hafif ekleyin; hedef kilitlendiğinde veya düşman saldırı hazırlığındayken `DynamicMaterialInstance->SetScalarParameterValue("TelegraphRim", 1.0f)` sürün.
- **Unity 6 Shader Graph:** `Fresnel Effect` + `Simple Noise` ile vuruş anında `HitFlash` ve ölümde `Dissolve` geçişini tek shader'da birleştirin.
- **Godot 4 Shader (`.gdshader`):** `EMISSION += rim_color * pow(1.0 - clamp(dot(NORMAL, VIEW), 0.0, 1.0), rim_power);`

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `FresnelExponent` | `3.0 - 5.0` | `Shader Float` | pow(1.0 - saturate(dot(N, V)), Exp) |
| `RimColorIntensity` | `1.5 - 4.0 HDR` | `LinearColor` | Subtle bloom separation without neon mess |
| `DissolveEdgeWidth` | `0.04 - 0.08` | `Shader Scalar` | Noise step mask for enemy death / spawn |
| `EnemyToBgValueDelta` | `>= 25% Luminance Gap` | `Value Budget` | Background midtones vs sharp actor contrast |

**Derlenen Uygulama Reçeteleri:**
- Olay güdümlü (Event-Driven) modüler bileşen entegrasyonu.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Kritik vuruşta 2 karelik negatif/inverted renk patlaması veya yüksek kontrastlı kenar parlaması.
- Gizlilik modunda oyuncunun gölgeye girdiğini hissettiren soğuk mavi kenar çerçeve shader'ı.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Aşırı Parlak Neon Bloom:** Tüm karakterlere 10.0 HDR emissive vermek sanat yönetimini ucuzlaştırır ve göz yorar.
- **Arka Planla Aynı Değerde Düşman:** Detaylı zemin dokusuyla aynı parlaklıkta düşman tasarlamak okunabilirliği yok eder.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Volumetric Lighting & Darkness]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera & Player Perspective]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Diegetic Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Art_Directing_VFX_for_Stylized_Games`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
