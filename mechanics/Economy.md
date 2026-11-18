---
title: "Economy"
domain: "Economy"
department: "ECONOMY"
bundle: "Bundle_4"
ku_count: 8
tags: [economy, economy, bundle_4, 4-bucket-module]
linked_systems: ["Crafting", "Reward Systems", "Farming & Seasonal Loops", "Progression", "Anti-Pattern Playbook", "Resource Management"]
---

# Economy

> **Domain:** [[Economy]] | **Department:** `ECONOMY` | **Evidence Units:** `8`  
> **Linked Systems:** [[Crafting]], [[Reward Systems]], [[Farming & Seasonal Loops]], [[Progression]], [[Anti-Pattern Playbook]], [[Resource Management]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Economy (Oyun Ekonomisi (Musluklar ve Giderler))**: Currency faucets vs. sinks, inflation containment, scarcity friction, and meaningful trade-off curves. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.
- Küresel aday sistemleri, oyunun temelini oluşturan mekaniklerdir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `EconomyComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Economy |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Survival: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 
- [Unreal] Crafting: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 
- [Unreal] Exploration: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, the
- [Unreal] Oyunun temelini oluşturan ekonomik sistem: It's poor. It's the way it works. It's turn-based. It's going to have cities. It's going to have units. It's going to have wonders. It's going to have these pieces. Another thir

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Economy** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Economy İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Crafting]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Reward Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Farming & Seasonal Loops]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Anti-Pattern Playbook]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Resource Management]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`, `Classic_Game_Postmortem_-_Sid_Meier_s_Civilization`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
