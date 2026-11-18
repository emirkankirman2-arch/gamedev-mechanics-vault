---
title: "Game Design"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 139
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Sound Effects", "Combat", "Exploration", "Resource Management", "Game Maker S Toolkit In 2019"]
---

# Game Design

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `139`  
> **Linked Systems:** [[Level Design]], [[Sound Effects]], [[Combat]], [[Exploration]], [[Resource Management]], [[Game Maker S Toolkit In 2019]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Game Design mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Morality Systems, Karma Meter ve Chaos System, oyuncunun seçimlerinin sonuçlarını etkiler ve oyuncunun karakterini şekillendirir.
- Adaptive Difficulty — carry yourself over and over to make things easier that's easily preventable that will be my answer. Question 2 do you think the standardization of control schemes, camera angles, combat systems etc i
- Subway Legibility — And for me, designing for subway legibility has been a really powerful tool. And the reason why it's a powerful tool is that effectively it solves three problems for me at the same time. And since I m
- Lemmings serisinin tüm oyunları, mekanik ve tasarımsal olarak benzerlik göstermektedir.
- The game features a variety of weapons and power-ups, including a shotgun, pistol, and health pack.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Game_Design` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Game Design |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] State machine mantığı ile karakterin moral durumunu güncelleme
- [Unreal] State machine mantığı ile karakterin karma durumunu güncelleme
- [Unreal] State machine mantığı ile karakterin kaos durumunu güncelleme
- [Unreal] difficulty_level = player_stats.get_difficulty_level()

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Game Design** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Game Design İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Sound Effects]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Resource Management]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game Maker S Toolkit In 2019]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Are_Morality_Systems_Making_Us_Less_Moral`, `Ask a Game Designer Anything #1 - Difficulty, Standardization, Depth`, `Building_Games_That_Can_Be_Understood_at_a_Glance`, `Classic_Game_Postmortem_-_Lemmings`, `Clones_Aren_t_Killing_Gaming_-_They_re_Saving_It`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
