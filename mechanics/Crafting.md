---
title: "Crafting"
domain: "Crafting"
department: "ECONOMY"
bundle: "Bundle_4"
ku_count: 11
tags: [crafting, economy, bundle_4, 4-bucket-module]
linked_systems: ["Economy", "Progression", "Exploration", "Farming & Seasonal Loops", "Resource Management", "The Making Of Divinity Original Sin 2"]
---

# Crafting

> **Domain:** [[Crafting]] | **Department:** `ECONOMY` | **Evidence Units:** `11`  
> **Linked Systems:** [[Economy]], [[Progression]], [[Exploration]], [[Farming & Seasonal Loops]], [[Resource Management]], [[The Making Of Divinity Original Sin 2]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Crafting (Zanaatkarlık ve Kaynak Dönüşümü)**: Inventory-pressure recipes, meaningful material sinks, experimentation discovery, and crafting-to-combat loops. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- The game features endgame aspirational content, league rewards, and crafting to provide a deep and engaging experience.
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.
- Crafting sistemleri, oyuncuların oyun içi crafting sistemlerini kontrol etmelerine olanak sağlar.
- Dead Space 2 ve Dead Space 3'de, oyuncuların silahlarını ve zırhlarını geliştirmek için Universal Ammo ve Crafting System'leri kullanabilirler.
- Metagaming, BioShock ve Atomic Heart gibi oyunlarda, oyuncuların oyunun dışındaki bilgi ve becerilerini oyun içi durumlarına uygulayarak avantaj elde etmeleri mümkündür.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `CraftingComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Crafting |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyuncuların denge değişikliklerini oynaymasına olanak tanır.
- [Unreal] Oyuncuların son oyun aspirasyonlu içeriklerini oynaymasına olanak tanır.
- [Unreal] Oyuncuların lig ödüllerini oynaymasına olanak tanır.
- [Unreal] Survival: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Crafting** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Crafting İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Economy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Farming & Seasonal Loops]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Resource Management]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[The Making Of Divinity Original Sin 2]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Designing_Path_of_Exile_to_Be_Played_Forever`, `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`, `Good_Design_Bad_Design_Vol._9_-_The_Graphic_Design_of_Animal_Crossing_Resident_Evil_2_and_More`, `The_Design_of_Dead_Space_-_Part_3`, `Why_Atomic_Heart_Fails_To_Live_Up_To_Its_Inspiration`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
