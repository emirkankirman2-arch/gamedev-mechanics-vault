---
title: "Farming & Seasonal Loops"
domain: "Economy"
department: "ECONOMY"
bundle: "Bundle_4"
ku_count: 115
tags: [economy, economy, bundle_4, 4-bucket-module]
linked_systems: ["Economy", "Crafting", "Progression", "Reward Systems", "World Building"]
---

# Farming & Seasonal Loops

> **Domain:** [[Economy]] | **Department:** `ECONOMY` | **Evidence Units:** `115`  
> **Linked Systems:** [[Economy]], [[Crafting]], [[Progression]], [[Reward Systems]], [[World Building]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Çiftçilik, üs kurma ve yaşam simülasyonu oyunlarındaki bağımlılık yaratan döngü **İleriye Dönük Zaman Yatırımı (Deferred Gratification)** ve **Mevsimsel Kısıtlar (Seasonal Pressure)** üzerine kuruludur. Her gün kısıtlı enerji/zaman bütçesi, tohum maliyeti ve sulama emeği yarının hasat kârıyla takas edilir; mevsim sonu saati ise rehaveti engeller.

**Kütüphane Kanıtları (Corpus Insights):**
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.
- Küresel aday sistemleri, oyunun temelini oluşturan mekaniklerdir.
- The game features endgame aspirational content, league rewards, and crafting to provide a deep and engaging experience.
- Crafting sistemleri, oyuncuların oyun içi crafting sistemlerini kontrol etmelerine olanak sağlar.
- Dead Space 2 ve Dead Space 3'de, oyuncuların silahlarını ve zırhlarını geliştirmek için Universal Ammo ve Crafting System'leri kullanabilirler.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity / Godot:** Her toprak karesini (`PlotCell`) `CropId`, `GrowthStage`, `WateredToday`, `DaysGrown` struct'ı olarak bir `GridMap` / `Dictionary<Vector2Int, CropState>` içinde tutun; gün sonunda (`OnDayAdvance`) yalnızca `WateredToday == true` olan kareleri ilerletin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `DayLengthRealSeconds` | `720 - 900 s (12-15 min)` | `Float` | Balances daily chores + dungeon/social exploration |
| `CropROI_Multiplier` | `1.8x - 3.2x Seed Cost` | `Float` | Multi-harvest crops scale slower upfront |
| `SeasonDurationDays` | `28 Days (4 Weeks)` | `Int32` | Clear deadline for seasonal crop planning |
| `StaminaActionCost` | `2 - 4 Energy / Tile` | `Int32` | Upgraded tools drop cost or expand 3x3 AoE |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Survival: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 
- [Unreal] Crafting: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 
- [Unreal] Exploration: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, the
- [Unreal] Oyunun temelini oluşturan ekonomik sistem: It's poor. It's the way it works. It's turn-based. It's going to have cities. It's going to have units. It's going to have wonders. It's going to have these pieces. Another thir

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Sulanan toprağın anında koyu ıslak materyale dönmesi + su sıçrama partikülü ve tatmin edici 'pop' hasat sesi.
- Mevsim değişiminde yaprak partikülleri (ilkbahar kiraz çiçeği, sonbahar kızıl yaprak) ve yeni mevsim müzik temasının açılması.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Enflasyon Tuzağı (Mid-Game Cash Overflow):** Oyuncu 2. mevsimde sınırsız paraya ulaşıp harcayacak büyük bir gider (Sink: bina yükseltme, otomasyon, nadir dekor) bulamazsa tüm döngü ölür.
- **Tek Tıklama Hamallığı:** Yüzlerce kareyi tek tek tıklamak zorunda bırakmak yerine 2. aşamada mutlaka alan etkili (3x3 sulama kabı / fıskiye) otomasyon sunun.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Economy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Crafting]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Reward Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[World Building]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`, `Classic_Game_Postmortem_-_Sid_Meier_s_Civilization`, `Designing_Path_of_Exile_to_Be_Played_Forever`, `Good_Design_Bad_Design_Vol._9_-_The_Graphic_Design_of_Animal_Crossing_Resident_Evil_2_and_More`, `The_Design_of_Dead_Space_-_Part_3`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
