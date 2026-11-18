---
title: "Speedrunning"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 21
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Global Information Map", "Puzzle Solving"]
---

# Speedrunning

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `21`  
> **Linked Systems:** [[Level Design]], [[Global Information Map]], [[Puzzle Solving]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Speedrunning mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Speedrunning, platforming ve deck builder sistemleri, oyuncuların hız, beceri ve stratejik planlama becerilerini test eder.
- Challenge Run formatı, oyuncuların belirli bir oyunu belirli bir şekilde tamamlamaya çalışmasını sağlar.
- Shovel Knight oyununda, oyuncunun kullandığı silahlar ve yetenekleri, oyuncunun ilerlemesine ve başarılarına göre değişir.
- Oyun, zorluk seviyesini seçmek için bir ekran sunar; bu, oyuncunun oyunun zorluğunu ayarlayabilmesini sağlar.
- Novelty ve Creativity, oyunun evrimleşmesine ve yeni yolların keşfedilmesine olanak sağlar.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Speedrunning` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Speedrunning |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Challenge Run: the bosses into a real challenge I've previously had no appreciation for. Small details like how Polonite blocks your bounce attacks and counters, forcing you to engage him on the ground and risks Mikey De
- [Unreal] No Items Playthrough: the bosses into a real challenge I've previously had no appreciation for. Small details like how Polonite blocks your bounce attacks and counters, forcing you to engage him on the ground and risks M
- [Unreal] Nuzlocke Challenge: the bosses into a real challenge I've previously had no appreciation for. Small details like how Polonite blocks your bounce attacks and counters, forcing you to engage him on the ground and risks Mik
- [Unreal] Shovel Knight sisteminin state machine, event/delegate akışı ve çalışma mantığı.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Speedrunning** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Speedrunning İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Global Information Map]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Puzzle Solving]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `How_Neon_White_Lets_You_Speedrun_Speedrunning`, `Shovel_Knight_s_Secret_Mode-_The_Challenge_Run_Formula.f251`, `Shovel_Knight_s_Secret_Mode-_The_Challenge_Run_Formula`, `Super_Mario_s_Invisible_Difficulty_Settings`, `What_Makes_A_Game_Replayable`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
