---
title: "Resource Management"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 32
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Combat", "Crafting", "Economy", "Exploration", "Game Design"]
---

# Resource Management

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `32`  
> **Linked Systems:** [[Level Design]], [[Combat]], [[Crafting]], [[Economy]], [[Exploration]], [[Game Design]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Resource Management mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Rogue Legacy'de ölüm kalıcıdır ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.
- The game features a variety of independent game mechanics, including optimization, efficiency, game design, human psychology, resource management, inventory management, carrying capacity, limited-use items, power-ups, health management, regenerating health, infinite ammo, optimal play, strategy, and victory conditions.
- Oyun, kaynak yönetimi, itme ve çekme mekanizmaları, sınırlı dayanıklılık ve mermi kıtlığı, sınırsız kaynak sistemleri (flaklar, ölümler), zafer öldürme ile sağlık geri yüklemesi, uzay sınırlı kaynak olarak (Islanders), zaman sınırlaması / 22 dakikalık döngü, ölüm geri dönüşü olmayan bir geri dönüş olarak, maden kazısı / kaynakların istismarı, XP ilerleme eğrisi (eksponansiyel seviyeleme), gizlilik / gadget kullanımı ile mermi tasarrufu (Void Bastards), çevre tehlikeleri kaynak olarak (Frostpunk soğuk, Manpower), bonus hedef ödülleri (Descenders), keşif sürükleyici keşif döngüsü (Outer Wilds), yan-ödev teşvikasyonu zaman pencereleri ile, kuantum kaya teleport mekanizması, ısı bıçağı sınırsız gıda/su istismali, hastane personeli kaynak olarak (Frostpunk), Bonfire Flask yenileme (Dark Souls), sınırsız ölümler deneyimi (Celeste)
- The game features a variety of independent game mechanics, including telegraphed attacks, limited weapon types, static enemy designs, purple units, push attacks, research trees, upgrade systems, difficulty balancing, resource management, map design, dynamic difficulty length, time travel mechanics, debris collection, grappling hooks, and teleportation spells.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Resource_Management` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Resource Management |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Platformer: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reason, 
- [Unreal] Resource Management: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever
- [Unreal] Deck Building: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reaso
- [Unreal] Survival: your base to people and that kind of thing. But then all of the actual monetization was going to come into aesthetics and options. So with that procedural world generation that we are experimenting with, there 

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Resource Management** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Resource Management İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Crafting]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Economy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Exploration]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_20_Games_You_Should_Have_Played`, `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`, `Factorio_Fixed_My_Broken_Brain`, `How_Outer_Wilds_Makes_Running_Out_of_Stuff_Fun`, `Into_the_Breach_Design_Postmortem`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
