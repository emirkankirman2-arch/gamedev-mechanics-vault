---
title: "Roguelike"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 23
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Exploration", "Platformer", "Enemy AI"]
---

# Roguelike

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `23`  
> **Linked Systems:** [[Level Design]], [[Exploration]], [[Platformer]], [[Enemy AI]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Roguelike mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Puzzle Platformer oyunlarında, oyuncular platformları geçerek ilerlerken, platformlar genellikle hareketli veya değişken olabilir.
- Roguelike oyunlarda, oyuncuların bir seferde sadece bir kez oynayabildiği bir dünya vardır.
- Spelunky ve klasik rogue-like oyunlarında permadeath kuralı geçerlidir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.
- Roguelike oyunlarda, oyuncuların ilerlemesi için iteratif bir ilerleme sistemi vardır; her seviye geçildikçe yeni yetenekler ve güçler kazanılmaktadır.
- The game features a roguelike system with procedurally generated levels, platformer mechanics, and a focus on high interactivity.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Roguelike` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Roguelike |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Puzzle Platformer: So in this video, let's look at 100 games that went from GMTK game jam entries to full on Steam releases. Are you ready? Then let's go. 100 keys to your heart is a puzzle platformer where you collect k
- [Unreal] Arena Shooter: So in this video, let's look at 100 games that went from GMTK game jam entries to full on Steam releases. Are you ready? Then let's go. 100 keys to your heart is a puzzle platformer where you collect keys 
- [Unreal] Golf Game: So in this video, let's look at 100 games that went from GMTK game jam entries to full on Steam releases. Are you ready? Then let's go. 100 keys to your heart is a puzzle platformer where you collect keys to o
- [Unreal] Oyuncuların bir seferde sadece bir kez oynayabildiği bir dünya: that meant I didn't discard my hand at the end of a turn, so after a few turns I'd have the maximum 10 cards to play with. Then I had a card called Storm of

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Roguelike** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Roguelike İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Platformer]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Enemy AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `100_Steam_Games_that_started_life_during_GMTK_Game_Jam`, `How_Synergies_Make_Slay_the_Spire_Fun`, `How_To_Combine_Video_Game_Genres`, `How_Videogames_Keep_You_Playing_Forever`, `One_More_Run_-_The_Making_of_Spelunky_2`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
