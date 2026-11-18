---
title: "Reward Systems"
domain: "Reward Systems"
department: "ECONOMY"
bundle: "Bundle_4"
ku_count: 8
tags: [reward_systems, economy, bundle_4, 4-bucket-module]
linked_systems: ["Progression", "Risk & Reward", "Economy", "Retention & Live Systems", "Dynamic Difficulty Adjustment", "Farming & Seasonal Loops"]
---

# Reward Systems

> **Domain:** [[Reward Systems]] | **Department:** `ECONOMY` | **Evidence Units:** `8`  
> **Linked Systems:** [[Progression]], [[Risk & Reward]], [[Economy]], [[Retention & Live Systems]], [[Dynamic Difficulty Adjustment]], [[Farming & Seasonal Loops]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Reward Systems (Ödül Psikolojisi ve Ganimet Döngüleri)**: Intrinsic mastery rewards vs. extrinsic variable-ratio loot drops, anticipation pacing, and dopamine curve hygiene. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Turn Timers, oyunun zaman yönetimi mekanizmasıdır.
- The Blood Sport peripheral uses a needle to suck out the user's life essence while playing video games.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `Reward_SystemsComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Reward Systems |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Turn Timers state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Security Systems state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Alarm Systems state machine, event/delegate akışı ve çalışma mantığı
- [Agnostic] Kullanıcılar video oyunları oynarken kan pompalaması için kan sporları periferallerini kullanır. Kan sporları periferalleri, kullanıcıların kanını pompalar. | Components: `Peripheral, Needle, Controller, Rumble`

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Reward Systems** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Reward Systems İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.
- The Blood Sport peripheral aims to make blood donation more fun and engaging for users.

---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Risk & Reward]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Economy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Retention & Live Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Dynamic Difficulty Adjustment]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Farming & Seasonal Loops]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Three_Other_Approaches_to_Turn_Timers_GMTK_Extra`, `Bloodiest_Gaming_Peripheral_Extra_Credits_Gaming_shorts`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
