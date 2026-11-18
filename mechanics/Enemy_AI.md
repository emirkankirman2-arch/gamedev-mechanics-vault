---
title: "Enemy AI"
domain: "Enemy AI"
department: "GAME_AI"
bundle: "Bundle_4"
ku_count: 14
tags: [enemy_ai, game_ai, bundle_4, 4-bucket-module]
linked_systems: ["Behavior Trees & Utility AI", "Combat", "Stealth", "Boss Design", "Parry & Deflect Windows", "Dynamic Difficulty Adjustment"]
---

# Enemy AI

> **Domain:** [[Enemy AI]] | **Department:** `GAME_AI` | **Evidence Units:** `14`  
> **Linked Systems:** [[Behavior Trees & Utility AI]], [[Combat]], [[Stealth]], [[Boss Design]], [[Parry & Deflect Windows]], [[Dynamic Difficulty Adjustment]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Enemy AI (Düşman Yapay Zekası ve Koordinasyon)**: Behavior trees, utility scoring, attack-token coordinators, flanking roles, and readable bark telegraphs. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyuncu AI, oyuncunun hareketlerini taklit ederken, düşman AI, oyuncunun hareketlerini engeller.
- Küresel aday sistemlerinde zorluk seviyesi, oyuncunun yeteneklerini ve deneyimi ile doğru orantılıdır.
- Tower Defense oyunlarında, oyuncuların savunma yapılarını yerleştirerek düşmanları durdurma görevi vardır.
- The game features a deck building system, roguelike elements, procedural generation, card synergy, relic system, event system, enemy AI, ascension levels, daily modes, streamers and community feedback, metrics-driven design, balance testing, early access launch strategy, weekly update schedule, and discord feedback channels.
- The game has an enemy AI system that allows enemies to move and attack players.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `Enemy_AIComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Enemy AI |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Düşmanların oyuncunun hareketlerini taklit etmesine izin veren oyun sistemleri: and also make a weird sort of aah noise. These beak-faced enemies only move when you do. These stalactites work in real time and will fall w
- [Unreal] Sistem, oyuncunun zorluğunu belirlemek için bir state machine kullanır.
- [Unreal] Sistem, oyuncunun spesifiklığını belirlemek için bir event/delegate akışı kullanır.
- [Unreal] Sistem, oyuncunun kişiliğini belirlemek için bir state machine kullanır.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Enemy AI** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).
- `UX Binding:` DeckBuildingHUD
- `UX Binding:` CardSynergyHUD
- `UX Binding:` RoguelikeHUD
- `UX Binding:` ProceduralGenerationHUD

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Enemy AI İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Behavior Trees & Utility AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Stealth]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Boss Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Parry & Deflect Windows]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Dynamic Difficulty Adjustment]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `3_Lessons_from_a_Real-time_Turn-based_Game`, `Engineering_The_Perfect_Enemy`, `Making_a_Farm-Themed_Tower_Defense_Game_in_48_Hours_-_GMTK_2023_Devlog`, `Slay_the_Spire_-_Metrics_Driven_Design_and_Balance`, `What_Makes_a_Good_New_Game_Plus`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
