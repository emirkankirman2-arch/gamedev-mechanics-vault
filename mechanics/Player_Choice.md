---
title: "Player Choice"
aliases: ["Player Choice"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 30
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Game Mechanics", "Player Agency"]
---

# Player Choice

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `30`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Game_Mechanics|Game Mechanics]], [[Player_Agency|Player Agency]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyunun oyuncunun seçimi mekanizmaları

**Kütüphane Kanıtları (Corpus Insights):**
- of direction to the player in order to avoid choice paralysis. But when that direction is kept purposefully vague while also leaning on lore and world building, that can lead to a situation where the game is inadvertently
- Oyun, karakterin karakterizasyonunu mekaniklerle gösterir.
- Morality Systems, Karma Meter ve Chaos System, oyuncunun seçimlerinin sonuçlarını etkiler ve oyuncunun karakterini şekillendirir.
- Between a masquerade ball, a brilliant bank heist and a house trapped between two moments in time, the Dissonid series is famous for its intricate and imaginative level design. But if there's one stage that truly fits that description, it's the clockwork...
- Küresel aday sistemlerinde zorluk seviyesi, oyuncunun yeteneklerini ve deneyimi ile doğru orantılıdır.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Player_Choice` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Player Choice |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyunun oyuncunun seçimi mekanizmaları: of direction to the player in order to avoid choice paralysis. But when that direction is kept purposefully vague while also leaning on lore and world building, that can lead to a s
- [Unreal] Characterization Through Mechanics: Hi, my name is Nisofka Stuk and this is Farlands, a series about video games and video game design. And today we'll talk about characterization through mechanics. In any artistic work,
- [Unreal] Show, Don'T Tell: Hi, my name is Nisofka Stuk and this is Farlands, a series about video games and video game design. And today we'll talk about characterization through mechanics. In any artistic work, rarely do we use 
- [Unreal] Game Mechanics: Hi, my name is Nisofka Stuk and this is Farlands, a series about video games and video game design. And today we'll talk about characterization through mechanics. In any artistic work, rarely do we use di

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Player Choice** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Player Choice İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game_Mechanics|Game Mechanics]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] Aer： Memories of Old - the game with the BEST flight mechanics`, `[OLD] Farlands - Characterization Through Mechanics`, `Are_Morality_Systems_Making_Us_Less_Moral`, `Dishonored_2_Devs_Explain_the_Clockwork_Mansion`, `Engineering_The_Perfect_Enemy`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
