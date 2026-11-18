---
title: "Progression"
domain: "Progression"
department: "DESIGN"
bundle: "Bundle_4"
ku_count: 102
tags: [progression, design, bundle_4, 4-bucket-module]
linked_systems: ["Reward Systems", "Permadeath & Meta-Progression", "Economy", "Difficulty Design", "Dynamic Difficulty Adjustment", "Farming & Seasonal Loops"]
---

# Progression

> **Domain:** [[Progression]] | **Department:** `DESIGN` | **Evidence Units:** `102`  
> **Linked Systems:** [[Reward Systems]], [[Permadeath & Meta-Progression]], [[Economy]], [[Difficulty Design]], [[Dynamic Difficulty Adjustment]], [[Farming & Seasonal Loops]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Progression (İlerleme ve Güç Eğrileri)**: Horizontal ability gating, vertical stat curves, build synergies, and meaningful mastery milestones. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Küresel adayın temel sistemleri, savaş mekanikleri ve ilerleme sistemleri hakkında bilgi paylaşıldı.
- Oyunun temel sistemleri, savaş mekanizmaları ve ilerleme sistemi, bağımsız oyunların temel özelliklerini oluşturur.
- Oyunun ilerleme sistemi, oyuncunun ilerlemesini sağlar ve oyunun temelini oluşturur.
- The game features a core system that manages player progression, combat mechanics, and progression.
- The game features a core system that allows players to progress through levels and defeat enemies.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `ProgressionComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Progression |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyunun temel sistemlerini oluşturmak: �iroisência RIP Luvunni Krollien 1911 encontrarhmun työnteko Nyt ammastipallillimme VID tämän nam shooting onanyon Suilekin
- [Unreal] Oyunun savaş mekanizmalarını oluşturmak: �iroisência RIP Luvunni Krollien 1911 encontrarhmun työnteko Nyt ammastipallillimme VID tämän nam shooting onanyon Suilekin
- [Unreal] Oyunun ilerleme sistemini oluşturmak: �iroisência RIP Luvunni Krollien 1911 encontrarhmun työnteko Nyt ammastipallillimme VID tämän nam shooting onanyon Suilekin
- [Unreal] Oyunun temel sistemlerini oluşturmak: Uzmake on edibleist Shea n. 1935 mitä jumperall our 8. Yankelyn nähdään vissani on juste nurtukin. Jota saimme jos nape ص verdict aging donors ja Mate Muslims ja on tolavut ennen nyt

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Progression** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).
- `UX Binding:` CoreSystemsHUD
- `UX Binding:` GameplaySystemsHUD
- `UX Binding:` CombatHUD
- `UX Binding:` ProgressionHUD

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Progression İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Reward Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Permadeath & Meta-Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Economy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Difficulty Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Dynamic Difficulty Adjustment]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Farming & Seasonal Loops]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Can_We_Do_It_with_Particles_-_VFX_Learnings_from_Returnal`, `Classic_Game_Postmortem_-_Ultima_Online`, `How_the_Nemesis_System_Creates_Stories`, `How_YOU_Wrote_Rimworld_s_Best_Story`, `I_Made_a_Game_in_4_Days_for_the_GMTK_jam`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
