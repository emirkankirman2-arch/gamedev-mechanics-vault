---
title: "Puzzle Design"
domain: "Puzzle Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 16
tags: [puzzle_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Tutorial & Onboarding", "Discovery", "Level Design", "Player Agency", "Sound Effects"]
---

# Puzzle Design

> **Domain:** [[Puzzle Design]] | **Department:** `DESIGN` | **Evidence Units:** `16`  
> **Linked Systems:** [[Tutorial & Onboarding]], [[Discovery]], [[Level Design]], [[Player Agency]], [[Sound Effects]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Puzzle Design (Bulmaca ve Epistemik Kilit Sistemleri)**: Aha-moment epistemic shifts, rule-discovery onboarding without text walls, and clean lock-and-key state constraints. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Puzzle Design'da oyuncuların problem çözme yetenekleri vardır.
- Bu segmentte, oyun geliştiricileri oyunun ses seçeneklerini, alt metinleri, erişim seçeneklerini, yazı tipi boyutunu, yazı tipi stilini, kontrastı, alt metin uzunluğunu, alt metin zamanlamasını, konuşmacı göstergesini, sesli uyarıları, puzzle tasarımı, ses kontrolünü, alt metin konumunu, oyun erişim kılavuzlarını ve engellilik temsilini tartışmaktadır.
- Puzzle Design — parents. But when the second half came out earlier this year, I started to find puzzles that had some seriously troubling design. Like the puzzle where this grabby hand is obsessed with boots. But doe
- Puzzle Design: Oyunun ana hedefi, oyuncunun bir dizi problemi çözmektir. Bu, oyuncunun problemi çözmek için çeşitli yöntemler kullanmasını gerektirir.
- Puzzle çözme sistemi, oyuncuların problem çözme yeteneklerini geliştirmelerine yardımcı olur.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `Puzzle_DesignComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Puzzle Design |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyuncuların problem çözme yetenekleri vardır: And I made some of my favourite episodes yet, like the videos on puzzle design, dark souls, systemic games and assist modes. But I think 2019 is going to be even better. And 
- [Unreal] Oyun içi zorlukları çözmek için tasarlanmış sistem. | Components: `UInputComponent`
- [Agnostic] PuzzleDesignerComponent ile PuzzleSolverComponent arasında bir akış oluşturmak için bir state machine kullanın.
- [Agnostic] PointAndClickControllerComponent ile PointAndClickSolverComponent arasında bir akış oluşturmak için bir event/delegate kullanın.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Puzzle Design** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).
- `UX Binding:` PuzzleScreen
- `UX Binding:` HintButton
- `UX Binding:` GameScreen
- `UX Binding:` PointerCursor

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Puzzle Design İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Tutorial & Onboarding]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Discovery]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Sound Effects]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Game_Maker_s_Toolkit_in_2019`, `Making_Games_Better_for_the_Deaf_and_Hard_of_Hearing_Designing_for_Disability`, `Point_and_Click_Puzzle_Design`, `What_Makes_a_Good_Puzzle`, `What_We_Can_Learn_From_A_2000_Year_Old_Puzzle`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
