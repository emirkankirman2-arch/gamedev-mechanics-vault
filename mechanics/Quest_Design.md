---
title: "Quest Design"
domain: "Quest Design"
department: "NARRATIVE_WORLD_STORY"
bundle: "Bundle_1"
ku_count: 8
tags: [quest_design, narrative_world_story, bundle_1, 4-bucket-module]
linked_systems: ["Player Agency", "Environmental Storytelling", "World Building", "Navigation"]
---

# Quest Design

> **Domain:** [[Quest Design]] | **Department:** `NARRATIVE_WORLD_STORY` | **Evidence Units:** `8`  
> **Linked Systems:** [[Player Agency]], [[Environmental Storytelling]], [[World Building]], [[Navigation]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Quest Design (Görev ve Dallanan Anlatı Mimarisi)**: Non-linear state machines, multi-solution objective graphs, diegetic journals, and anti-backtracking world topology. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- The game's mini-open-world design allows players to explore a smaller, self-contained environment with a higher density of interesting things, making it more accessible and enjoyable for players.
- Fast travel in open-world games needs to be balanced with other systems to avoid making the game too accessible and tedious.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `Quest_DesignComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Quest Design |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Agnostic] Oyuncu, adayı keşfederken, wildlife ve diğer nesnelerle etkileşime girer. Oyuncu, adayı tamamlamak için görevleri tamamlamalıdır. | Components: `Island`
- [Agnostic] Oyuncu, görevleri tamamlamak için adayı keşfeder ve wildlife ile etkileşime girer. Her görevi tamamlamak, oyuncunun adayı tamamlamasını sağlar. | Components: `Quest`
- [Agnostic] Oyuncu, fast travel düğmesine basarak hızlı seyahat sistemini kullanabilir. Sistem, oyuncunun konumunu hızlı bir şekilde değiştirmek için tasarlanmıştır. | Components: `FastTravelComponent`
- [Agnostic] Oyuncu, quest sistemini kullanarak görevler alabilir ve dünya üzerinde keşif ve deneyim oluşturabilir. Sistem, oyuncunun görevleri tamamlamasını sağlamak için tasarlanmıştır. | Components: `QuestSystemComponent`

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Quest Design** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).
- `UX Binding:` Mini Harita
- `UX Binding:` Görev Listesi
- `UX Binding:` FastTravelButton
- `UX Binding:` QuestButton

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Quest Design İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.
- The game's mini-open-world design solves the problem of players feeling overwhelmed by large, open worlds, and instead provides a more manageable and enjoyable experience.
- Fast travel can make the game feel too easy and accessible, which can lead to player burnout and a lack of engagement with other parts of the game.

---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Environmental Storytelling]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[World Building]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Navigation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Mini_open_world_design_in_Alba_-_A_Wildlife_Adventure`, `I_Hate_Fast_Travel`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
