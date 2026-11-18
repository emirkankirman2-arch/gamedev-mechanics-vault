---
title: "Corpse Recovery"
domain: "Level Design"
department: "WORLD_DEVELOPMENT"
bundle: "Bundle_1"
ku_count: 36
tags: [level_design, world_development, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat"]
---

# Corpse Recovery

> **Domain:** [[Level Design]] | **Department:** `WORLD_DEVELOPMENT` | **Evidence Units:** `36`  
> **Linked Systems:** [[Level Design]], [[Player Agency]], [[Combat]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyuncu öldüğünde ceset veya kan lekesi dünyada kalır; oyuncuya oraya ulaşması durumunda kaynaklar kalıcı olarak kaybolmaz.

**Kütüphane Kanıtları (Corpus Insights):**
- Dark Souls ve ZombiU'da oyuncu öldüğünde ceset veya kan lekesi dünyada kalır; oyuncu oraya ulaşamazsa kaynaklar kalıcı olarak kaybolur.
- Shadow of the Colossus'da ceset koşusu, oyuncunun ölümlerinden sonra tekrar denemelerine olanak tanır.
- Rogue Legacy'de ölüm kalıcıdır ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Oyuncu öldüğünde ceset dünya üzerinde kalır ve oyuncunun geri dönebilmesi için bir fırsat sunar.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Corpse_Recovery` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Corpse Recovery |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyuncu öldüğünde ceset veya kan lekesi dünyada kalır; oyuncuya oraya ulaşması durumunda kaynaklar kalıcı olarak kaybolmaz: Oh, where do I even begin? It's a dark, twisted card game, pitting up against this mysterious cab
- [Unreal] Oyuncu öldüğünde ceset veya kan lekesi dünyada kalır; oyuncu oraya ulaşamazsa kaynaklar kalıcı olarak kaybolur: move, a phaser that teleports you to the other side of platforms, and a bunch of lumpy tentacles that you ca
- [Unreal] Oyuncunun öldüğünde ceset veya kan lekesi dünyada kalır; oyuncunun oraya ulaşması halinde kaynaklar kalıcı olarak kaybolur: can build your own Mario stages. I didn't want to build troll levels or goofy gimmick stages, I 
- [Unreal] Oyuncu öldüğünde ceset veya kan lekesi dünyada kalır; oyuncuya oraya ulaşma imkanı verilir: design decisions before they've even started playing, this does bring to mind an interesting design debate that has raged in gam

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Corpse Recovery** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Corpse Recovery İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_21_Games_You_Should_Have_Played`, `A_puzzle_game_where_your_tools_are_completely_random`, `Analysing_Mario_to_Master_Super_Mario_Maker`, `Are_Lives_Outdated_Game_Design`, `Climbing_in_Games`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
