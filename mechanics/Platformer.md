---
title: "Platformer"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 27
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Exploration", "Roguelike"]
---

# Platformer

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `27`  
> **Linked Systems:** [[Level Design]], [[Exploration]], [[Roguelike]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Platformer mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Rogue Legacy'de ölüm kalıcıdır ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Platformer oyunlarında oyuncunun platformlar arasında hareket etmesi için jumping mekanizması kullanılır.
- Backtracking, fetch quests, missable key items, story-driven backtracking, metroidvania, platformer, mystery games, environmental storytelling, infection, power-ups, level design, backtracking heavy design, speed run, pop quiz, escape, intrinsic abilities, extrinsic abilities, knowledge gained, clues, paths, NPCs, story changes, timeline structure, radiant historia, devil may cry, donkey kong 64, banjo tooie, wario land, pizza tower, outer wilds, tunic, hollow knight
- The game features a variety of independent game mechanics, including platformer, puzzle, and adventure elements.
- Spelunky ve klasik rogue-like oyunlarında permadeath kuralı geçerlidir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Platformer` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Platformer |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Platformer: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reason, 
- [Unreal] Resource Management: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever
- [Unreal] Deck Building: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reaso
- [Unreal] Platformer: without mechanic. So I'm looking for games that fit a certain genre, but where you have taken away one of the fundamental things that is associated with that type of game. I talked about this in the episode H

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Platformer** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Platformer İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Roguelike]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_20_Games_You_Should_Have_Played`, `GMTK_Game_Jam_Begins_Now_-_Theme_Announcement`, `How_Can_You_Make_Backtracking_Fun`, `How_Difficulty_Turned_DOOM_into_an_RPG`, `How_To_Combine_Video_Game_Genres`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
