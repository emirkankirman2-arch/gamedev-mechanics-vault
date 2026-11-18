---
title: "Player Agency"
domain: "Player Agency"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 51
tags: [player_agency, design, bundle_1, 4-bucket-module]
linked_systems: ["Quest Design", "Exploration", "Stealth", "Combat", "Puzzle Design", "Social Systems"]
---

# Player Agency

> **Domain:** [[Player Agency]] | **Department:** `DESIGN` | **Evidence Units:** `51`  
> **Linked Systems:** [[Quest Design]], [[Exploration]], [[Stealth]], [[Combat]], [[Puzzle Design]], [[Social Systems]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Player Agency (Oyuncu İnisiyatifi ve Emergent Oynanış)**: Systemic verb combinations, emergent chemistry engines, meaningful trade-offs, and non-scripted problem solving. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Hi, my name is Tynis Savkestuk and I am a game designer. Today we will dissect air memories of old, a peaceful, meditative game about a pill grimace through the land of gods. We play as Ock, one of the last few shapeshifters still left in this broken world...
- Morality Systems, Karma Meter ve Chaos System, oyuncunun seçimlerinin sonuçlarını etkiler ve oyuncunun karakterini şekillendirir.
- The Legend of Zelda: Breath of the Wild'da sightlines, oyuncunun görüş alanını belirler ve oyunun derinliğini artırır.
- Branching Dialogue — A lot of problems, and they need to be thought through. And choice is the reason to have branching dialogue in the first place. So it should be the place where we start to think about what we're doing
- Player agency is a common feature in independent games, allowing players to make choices that impact the game world and story.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `Player_AgencyComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Player Agency |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Event delegate: Player -> World -> PlayerAgency
- [Unreal] State machine mantığı ile karakterin moral durumunu güncelleme
- [Unreal] State machine mantığı ile karakterin karma durumunu güncelleme
- [Unreal] State machine mantığı ile karakterin kaos durumunu güncelleme

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Player Agency** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).
- `UX Binding:` VillainDesignHUD
- `UX Binding:` ConflictCreationHUD
- `UX Binding:` PlayerEngagementHUD

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Player Agency İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Quest Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Stealth]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Puzzle Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Social Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] Aer： Memories of Old - the game with the BEST flight mechanics`, `Are_Morality_Systems_Making_Us_Less_Moral`, `Breath_of_the_Wild_s_Exploration_Cycle_~_Design_Doc`, `Choice_Architecture_Player_Expression_and_Narrative_Design_in_Fallout_-_New_Vegas`, `How_Batman_Takes_Stealth_Back_to_Basics`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
