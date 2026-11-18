---
title: "Player Guidance"
domain: "Player Guidance"
department: "UI_UX"
bundle: "Bundle_1"
ku_count: 8
tags: [player_guidance, ui_ux, bundle_1, 4-bucket-module]
linked_systems: ["Diegetic Guidance", "Landmark Guidance", "Tutorial & Onboarding", "Navigation", "Level Design", "Anti-Pattern Playbook"]
---

# Player Guidance

> **Domain:** [[Player Guidance]] | **Department:** `UI_UX` | **Evidence Units:** `8`  
> **Linked Systems:** [[Diegetic Guidance]], [[Landmark Guidance]], [[Tutorial & Onboarding]], [[Navigation]], [[Level Design]], [[Anti-Pattern Playbook]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Player Guidance (Oyuncu Yönlendirme Sistemleri)**: Communicating spatial affordances, leading lines, contrast ratios, and objective salience without patronizing hand-holding. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Puzzle Design — parents. But when the second half came out earlier this year, I started to find puzzles that had some seriously troubling design. Like the puzzle where this grabby hand is obsessed with boots. But doe
- Puzzle çözme sistemi, oyuncuların problem çözme yeteneklerini geliştirmelerine yardımcı olur.
- Puzzle Design — other and can't communicate with one another in any way. It's unfair, unreasonable, and I say poorly designed. Which is par for the course with Point and Click Avengers, right? These games are filled
- Küresel aday sistemleri, puzzle, eureka moment, perspective change, discovery, learning experience, scientific metaphor, resistance, challenge, difficulty, balance, player engagement, puzzle design, game mechanics, narrative element, environmental puzzles, hidden challenges, player guidance, clarity, feedback, player agency gibi bağımsız oyun mekaniklerini, tasarım tercihlerini ve kurallarını içerir.
- The game features a puzzle-based gameplay system with a focus on perspective change and discovery.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `Player_GuidanceComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Player Guidance |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Agnostic] PuzzleDesignerComponent ile PuzzleSolverComponent arasında bir akış oluşturmak için bir state machine kullanın.
- [Agnostic] PointAndClickControllerComponent ile PointAndClickSolverComponent arasında bir akış oluşturmak için bir event/delegate kullanın.
- [Agnostic] AdventureGameControllerComponent ile AdventureGameSolverComponent arasında bir akış oluşturmak için bir state machine kullanın.
- [Unreal] Puzzle mekanik sisteminin temel tasarım amacı ve işlevi: One of the least fun things a puzzle game can do is unintentionally hide a crucial element or trick you into thinking that something is a part of the puzzle when i

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Player Guidance** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).
- `UX Binding:` PuzzleScreen
- `UX Binding:` HintButton
- `UX Binding:` GameScreen
- `UX Binding:` PointerCursor

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Player Guidance İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Diegetic Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Landmark Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Tutorial & Onboarding]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Navigation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Anti-Pattern Playbook]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Point_and_Click_Puzzle_Design`, `What_We_Can_Learn_From_A_2000_Year_Old_Puzzle`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
