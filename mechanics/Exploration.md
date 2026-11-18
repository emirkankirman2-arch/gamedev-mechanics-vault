---
title: "Exploration"
domain: "Exploration"
department: "WORLD_DEVELOPMENT"
bundle: "Bundle_1"
ku_count: 48
tags: [exploration, world_development, bundle_1, 4-bucket-module]
linked_systems: ["Discovery", "Landmark Guidance", "Environmental Storytelling", "Navigation", "World Building", "Procedural World Generation"]
---

# Exploration

> **Domain:** [[Exploration]] | **Department:** `WORLD_DEVELOPMENT` | **Evidence Units:** `48`  
> **Linked Systems:** [[Discovery]], [[Landmark Guidance]], [[Environmental Storytelling]], [[Navigation]], [[World Building]], [[Procedural World Generation]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Exploration (Keşif ve Merak Döngüleri)**: Curiosity-driven non-linear world traversal, vista framing, hidden path rewards, and intrinsic discovery loops. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Rogue Legacy'de ölüm kalıcıdır ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- on the core pillar of exploration. But that will be true most of the world's open half. The rest of the game takes place in different temples and shrines, and there we can't shape shift, gameplay instead focuses on puzzles and
- Oyun, keşif sistemlerini içerir. — on the core pillar of exploration. But that will be true most of the world's open half. The rest of the game takes place in different temples and shrines, and there we can't shape shift, gameplay inst
- Grow Home'de oyuncuların zeminin değişimine göre hareket etmeleri gerekir.
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `ExplorationComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Exploration |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Platformer: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reason, 
- [Unreal] Resource Management: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever
- [Unreal] Deck Building: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reaso
- [Unreal] Event delegate: Player -> World -> Exploration

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Exploration** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Exploration İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Discovery]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Landmark Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Environmental Storytelling]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Navigation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[World Building]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Procedural World Generation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_20_Games_You_Should_Have_Played`, `[OLD] Aer： Memories of Old - the game with the BEST flight mechanics`, `Climbing_in_Games`, `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`, `How_Terraria_Makes_You_Feel_Like_A_Master`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
