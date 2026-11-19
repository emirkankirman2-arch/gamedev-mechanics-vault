---
title: "Combat"
aliases: ["Combat"]
domain: "Combat"
department: "DESIGN"
bundle: "Bundle_2"
ku_count: 97
tags: [combat, design, bundle_2, 4-bucket-module]
linked_systems: ["Parry & Deflect Windows", "Hitstop & Freeze Frames", "Enemy AI", "Boss Design", "Camera Trauma & Screenshake", "Coyote Time & Input Buffering"]
---

# Combat

> **Domain:** [[Combat]] | **Department:** `DESIGN` | **Evidence Units:** `97`  
> **Linked Systems:** [[Parry_Deflect_Windows|Parry & Deflect Windows]], [[Hitstop_Freeze_Frames|Hitstop & Freeze Frames]], [[Enemy_AI|Enemy AI]], [[Boss_Design|Boss Design]], [[Camera_Trauma_Screenshake|Camera Trauma & Screenshake]], [[Coyote_Time_Input_Buffering|Coyote Time & Input Buffering]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Combat (Savaş ve Vuruş Sistemleri)**: Risk-reward spacing, frame-accurate hitboxes, telegraphing windows, stagger states, and responsive player-enemy exchanges. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Rogue Legacy'de ölüm kalıcıdır ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Role-Playing sisteminde oyuncular karakterlerini geliştirebilir ve farklı yeteneklere sahip olabilir.
- Morality Systems, Karma Meter ve Chaos System, oyuncunun seçimlerinin sonuçlarını etkiler ve oyuncunun karakterini şekillendirir.
- İmha, oyuncunun düşmanları yok etmesine olanak tanıyan bir mekanizmadır.
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `CombatComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Combat |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Platformer: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reason, 
- [Unreal] Resource Management: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever
- [Unreal] Deck Building: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reaso
- [Unreal] Role-Playing: side quest that takes place in this hotel to see how developer Obsidian packs so many opportunities for role-playing into just one quest. Because, while you perhaps wouldn't know it to look at full-out four

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Combat** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Combat İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Parry_Deflect_Windows|Parry & Deflect Windows]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Hitstop_Freeze_Frames|Hitstop & Freeze Frames]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Enemy_AI|Enemy AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Boss_Design|Boss Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera_Trauma_Screenshake|Camera Trauma & Screenshake]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Coyote_Time_Input_Buffering|Coyote Time & Input Buffering]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_20_Games_You_Should_Have_Played`, `Anatomy_of_a_Side_Quest_-_Beyond_the_Beef`, `Are_Morality_Systems_Making_Us_Less_Moral`, `Does_Spidey_s_Web-Swinging_Make_You_Feel_Like_Spider-Man`, `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
