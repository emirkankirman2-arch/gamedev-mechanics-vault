---
title: "Power Ups"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 21
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Game Design", "Resource Management"]
---

# Power Ups

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `21`  
> **Linked Systems:** [[Level Design]], [[Game Design]], [[Resource Management]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Power-ups mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Team Racing, Slingshot, Skin Boost, Frenzy Mode, Clash Mechanic, One Button Only, Drifting, Miniturbos, Tricks, Power-ups, Item Swapping, Team Ultimate, Boosting, Drafting, Racing Lines gibi bağımsız oyun mekanikleri, oyuncuların yarışma deneyimi için farklı stratejiler ve taktikler sunar.
- The game features a variety of independent game mechanics, including optimization, efficiency, game design, human psychology, resource management, inventory management, carrying capacity, limited-use items, power-ups, health management, regenerating health, infinite ammo, optimal play, strategy, and victory conditions.
- Backtracking, fetch quests, missable key items, story-driven backtracking, metroidvania, platformer, mystery games, environmental storytelling, infection, power-ups, level design, backtracking heavy design, speed run, pop quiz, escape, intrinsic abilities, extrinsic abilities, knowledge gained, clues, paths, NPCs, story changes, timeline structure, radiant historia, devil may cry, donkey kong 64, banjo tooie, wario land, pizza tower, outer wilds, tunic, hollow knight
- Loop mekanizması, oyuncunun döngüsel olarak aynı seviyeyi tekrarlamasını sağlar.
- Oyun, zorluk seviyesini seçmek için bir ekran sunar; bu, oyuncunun oyunun zorluğunu ayarlayabilmesini sağlar.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Power_Ups` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Power Ups |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Takım Yarışı Mekanizması state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Slingshot Mekanizması state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Skin Boost Mekanizması state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Optimisation: with inventory management or carrying capacity. In variably, how much stuff you can look around will become the single most important resource in the game, because the implicit efficiency of being able to c

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Power Ups** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.
- `UX Binding:` PowerUps_Screen

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Power Ups İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Resource Management]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Experimental_Kart_Racers_-_Sonic_Kirby_Snowboard_Kids_More`, `Factorio_Fixed_My_Broken_Brain`, `How_Can_You_Make_Backtracking_Fun`, `I_Made_A_Game_In_4_Days_GMTK_Game_Jam_Dev_Log`, `Super_Mario_s_Invisible_Difficulty_Settings`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
