---
title: "Puzzle Solving"
aliases: ["Puzzle Solving"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 90
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat", "Speedrunning"]
---

# Puzzle Solving

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `90`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Player_Agency|Player Agency]], [[Combat]], [[Speedrunning]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Puzzle-solving mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Metroidvania oyunlarında, oyuncuların platformlar arasında hareket etmeleri için hava hareketi ve bouncıng mekanizmaları kullanılır.
- Hi, my name is Tynis Savkestuk and I am a game designer. Today we will dissect air memories of old, a peaceful, meditative game about a pill grimace through the land of gods. We play as Ock, one of the last few shapeshifters still left in this broken world...
- Rogue-like oyunlarda, oyuncuların ölümü kalıcıdır ve harita sıfırlanır.
- Between a masquerade ball, a brilliant bank heist and a house trapped between two moments in time, the Dissonid series is famous for its intricate and imaginative level design. But if there's one stage that truly fits that description, it's the clockwork...
- Küresel Aday sistemlerinde, oyuncuların düşmanlarla savaşması, gizli blokları gizlemek ve gizli geçitleri bulmak gibi zorlu görevler bulunur.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Puzzle_Solving` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Puzzle Solving |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Metroidvania design mekanik sistemi: Hollow Knight is maybe one of the least innovative games on this list, but man does it deserve the spot. Not only is it the epitome of Metroidvania design, but it's also brilliant tra
- [Unreal] Oyunun puzzle çözme mekanizmaları: Hi, my name is Tynis Savkestuk and I am a game designer. Today we will dissect air memories of old, a peaceful, meditative game about a pill grimace through the land of gods. We play as
- [Unreal] Blueprints mekanik sisteminin temel tasarım amacı ve işlevi: And tomorrow, the house's layout will be completely reset and you'll have to start again from scratch. So it's a curious and totally unconventional mix of genr
- [Unreal] RNG mekanik sisteminin temel tasarım amacı ve işlevi: And tomorrow, the house's layout will be completely reset and you'll have to start again from scratch. So it's a curious and totally unconventional mix of genres. Par

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Puzzle Solving** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Puzzle Solving İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Speedrunning]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_17_Games_You_Should_Have_Played`, `[OLD] Aer： Memories of Old - the game with the BEST flight mechanics`, `Blue_Prince_-_Can_a_random_puzzle_game_actually_work`, `Dishonored_2_Devs_Explain_the_Clockwork_Mansion`, `How_to_Make_Your_First_Super_Mario_Maker_2_Level`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
