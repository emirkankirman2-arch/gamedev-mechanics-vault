---
title: "Stealth"
aliases: ["Stealth"]
domain: "Stealth"
department: "GAME_AI"
bundle: "Bundle_4"
ku_count: 37
tags: [stealth, game_ai, bundle_4, 4-bucket-module]
linked_systems: ["Enemy AI", "Volumetric Lighting & Darkness", "Level Design", "Player Agency", "Behavior Trees & Utility AI", "Adaptive Audio & Stems"]
---

# Stealth

> **Domain:** [[Stealth]] | **Department:** `GAME_AI` | **Evidence Units:** `37`  
> **Linked Systems:** [[Enemy_AI|Enemy AI]], [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]], [[Level_Design|Level Design]], [[Player_Agency|Player Agency]], [[Behavior_Trees_Utility_AI|Behavior Trees & Utility AI]], [[Adaptive_Audio_Stems|Adaptive Audio & Stems]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Stealth (Gizlilik ve Algılama Döngüleri)**: Granular suspicion meters, light/shadow occlusion, sound propagation radii, and predator-prey recovery loops. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Role-Playing sisteminde oyuncular karakterlerini geliştirebilir ve farklı yeteneklere sahip olabilir.
- Gizlilik, oyuncunun düşmanları gizlice yok etmesine olanak tanıyan bir mekanizmadır.
- Stealth Games'de oyuncunun gizli kalması ve düşmanların algılaması arasında bir dengeli sistem vardır.
- Stealth Games'de oyuncuların gizli kalma ve düşmanları yok etme yetenekleri vardır.
- Stealth mechanics, oyuncuların düşmanları gizlice yok etmelerini sağlar.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `StealthComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Stealth |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Role-Playing: side quest that takes place in this hotel to see how developer Obsidian packs so many opportunities for role-playing into just one quest. Because, while you perhaps wouldn't know it to look at full-out four
- [Unreal] Stealth: side quest that takes place in this hotel to see how developer Obsidian packs so many opportunities for role-playing into just one quest. Because, while you perhaps wouldn't know it to look at full-out four, the
- [Unreal] Combat: side quest that takes place in this hotel to see how developer Obsidian packs so many opportunities for role-playing into just one quest. Because, while you perhaps wouldn't know it to look at full-out four, thes
- [Unreal] Oyuncunun düşmanları gizlice yok etmesine olanak tanıyan bir mekanizmadır: But boot up the game itself, and most first attempts will see you screwing everything up, like a big bald idiot. It's only when you learn the lev

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Stealth** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Stealth İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Enemy_AI|Enemy AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Behavior_Trees_Utility_AI|Behavior Trees & Utility AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Adaptive_Audio_Stems|Adaptive Audio & Stems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Anatomy_of_a_Side_Quest_-_Beyond_the_Beef`, `Does_Spidey_s_Web-Swinging_Make_You_Feel_Like_Spider-Man`, `Game_Maker_s_Toolkit_in_2019`, `How_Game_Designers_Protect_Players_From_Themselves`, `How_To_Combine_Video_Game_Genres`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
