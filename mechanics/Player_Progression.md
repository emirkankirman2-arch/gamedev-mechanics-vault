---
title: "Player Progression"
aliases: ["Player Progression"]
domain: "Progression"
department: "DESIGN"
bundle: "Bundle_4"
ku_count: 21
tags: [progression, design, bundle_4, 4-bucket-module]
linked_systems: ["Progression", "Combat", "Crafting", "Economy", "Exploration", "Core Systems"]
---

# Player Progression

> **Domain:** [[Progression]] | **Department:** `DESIGN` | **Evidence Units:** `21`  
> **Linked Systems:** [[Progression]], [[Combat]], [[Crafting]], [[Economy]], [[Exploration]], [[Core_Systems|Core Systems]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Player Progression mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.
- Challenge and reward, oyuncuların oyunun zorluk seviyesini belirlemesine yardımcı olur.
- Invincibility, power-ups, i-frames, damage modeling, risk and reward, tension and release, accessibility, ranking systems, obstacle course design, transformation status effects, level design, game mechanics, game balance, player progression, challenge and reward, player agency
- Oyunun zorluk seviyesi oyuncunun yetenek seviyesine göre artar.
- Spelunky ve klasik rogue-like oyunlarında permadeath kuralı geçerlidir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Player_Progression` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Player Progression |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Survival: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 
- [Unreal] Crafting: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 
- [Unreal] Exploration: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, the
- [Unreal] Oyuncuya ilerleme sunan bir sistem.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Player Progression** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Player Progression İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Crafting]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Economy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Core_Systems|Core Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`, `How_Do_Games_Design_Around_No_Damage`, `How_Terraria_Makes_You_Feel_Like_A_Master`, `My_Favourite_Games_From_GMTK_Game_Jam_2026`, `What_Makes_a_Great_Secret`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
