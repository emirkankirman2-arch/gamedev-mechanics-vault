---
title: "Discovery"
domain: "Discovery"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 21
tags: [discovery, design, bundle_1, 4-bucket-module]
linked_systems: ["Exploration", "Puzzle Design", "Environmental Storytelling", "Reward Systems", "Game Loop"]
---

# Discovery

> **Domain:** [[Discovery]] | **Department:** `DESIGN` | **Evidence Units:** `21`  
> **Linked Systems:** [[Exploration]], [[Puzzle Design]], [[Environmental Storytelling]], [[Reward Systems]], [[Game Loop]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Discovery (Gizli Keşif ve Sır Tasarımı)**: Rule-bending epiphanies, tactile secret wall cues, environmental anomalies, and curiosity payoffs. Bu sistemik yapı, tekil mekanikleri birbirine bağlayan makro oyun döngüsünün temel taşıdır; oyuncu niyeti ile çevresel/sistemik geri bildirim arasındaki netliği maksimize eder.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyunun zorluk seviyesi oyuncunun yetenek seviyesine göre artar.
- İmprovize, küçültülmüş (Lo-Fi) çözümler, genişletilmiş imgeleme, keşif, etkileşimli hikaye, mental sağlık, kapitalizm, kaybetme, inanç, görsel imaj, ses, dil, hikaye, oyuncu imgesi, oyun döngüsü
- Puzzle çözme sistemi, oyuncuların problem çözme yeteneklerini geliştirmelerine yardımcı olur.
- The game features a variety of independent game mechanics, including rogue-like elements, procedurally generated levels, and a focus on exploration and discovery.
- The game features a variety of independent game mechanics, including roguelike elements, procedurally generated levels, and a focus on exploration and discovery.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UGameplayStatics` ve `UActorComponent` tabanlı modüler `DiscoveryComponent` üzerinde olay güdümlü (`Delegate`) mimari kurun.
- **Unity 6:** `ScriptableObject` veri tanımları + `C# EventChannel` ile sistemleri birbirinden ayrıştırın (decoupling).
- **Godot 4:** `Resource` veri sınıfları ve sinyal (`signal`) bağlantıları üzerinden veri akışını yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoreStateTickHz` | `10 - 60 Hz` | `Fixed/Timer` | Primary update cadence for Discovery |
| `FeedbackLatencyBudget` | `<= 50 ms` | `Millisecond` | Input-to-audiovisual response threshold |
| `TelemetrySampleRate` | `1.0 Hz` | `Analytics Event` | Tracks player friction & mastery curve |
| `DifficultyScaleClamp` | `0.80x - 1.25x` | `CurveFloat` | Balanced progression multiplier |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Mastery mekanizmasını oluşturmak: Terraria is an incredibly interesting game. It sold millions of copies, it's still getting updated to this day, and yet it was completely critically overshadowed by Minecraft, a magical 
- [Unreal] Oyun tasarımı mekanizmasını oluşturmak: Terraria is an incredibly interesting game. It sold millions of copies, it's still getting updated to this day, and yet it was completely critically overshadowed by Minecraft, a ma
- [Unreal] Oyuncu deneyimi mekanizmasını oluşturmak: Terraria is an incredibly interesting game. It sold millions of copies, it's still getting updated to this day, and yet it was completely critically overshadowed by Minecraft, a 
- [Unreal] improvize_system: um the themes that we had of like mental health of like capitalism of loss of loss of belief in God the removal of kind of a central organizing force in your life which a lot of these things kind of hav

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Discovery** durum geçişlerinde eşzamanlı görsel (VFX / materyal ton değişimi) ve işitsel (katmanlı SFX) vurgu.
- Oyuncu başarısını kutlayan diegetik onay işaretleri (parlama, kamera mikro tepkisi).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Discovery İzolasyonu:** Bu sistemi diğer oyun döngülerinden kopuk, tek başına çalışan bir ada haline getirmek.
- **Totolojik Tasarım:** Mekaniklerin gerçek bir risk-ödül veya karar maliyeti üretmeden sadece yüzeysel etiket olarak kalması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Puzzle Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Environmental Storytelling]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Reward Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game Loop]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `How_Terraria_Makes_You_Feel_Like_A_Master`, `Nuke_Possum_Springs_-_A_Night_in_the_Woods_Design_Postmortem`, `What_We_Can_Learn_From_A_2000_Year_Old_Puzzle`, `Redesigning_Death`, `[OLD] Design of The Legend of Zelda ｜ Farlands School of Game Design`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
