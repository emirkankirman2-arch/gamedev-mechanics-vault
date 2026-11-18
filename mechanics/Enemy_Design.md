---
title: "Enemy Design"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 19
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Gameplay Mechanics", "Gameplay Systems", "Resource Management", "Enemy AI", "Game Maker S Toolkit In 2019"]
---

# Enemy Design

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `19`  
> **Linked Systems:** [[Level Design]], [[Gameplay Mechanics]], [[Gameplay Systems]], [[Resource Management]], [[Enemy AI]], [[Game Maker S Toolkit In 2019]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Enemy Design mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Küresel aday sistemlerinde zorluk seviyesi, oyuncunun yeteneklerini ve deneyimi ile doğru orantılıdır.
- Cuphead oyununda, oyuncuların karşılaştıkları düşmanlar ve seviye tasarımı, oyunun zorluğu ve rekabetçi doğasını destekler.
- Beast Theory, Enemy Design, Visual Novelty, Emergent AI Behaviors, New Gameplay Systems, Interesting Mechanical Combos, Novel Mechanical Design, Pikmin's Enemy Variety, Mega Man's Enemy Variety, Hollow Knight's Enemy Variety, Doom's Enemy Variety, Zelda's Enemy Variety, Breath of the Wild's Enemy Variety, Paper Mario's Enemy Variety, Origami King's Enemy Variety, Boss Fight Design
- Oyun, düşman tasarımlarını kullanır ve oyuncunun yeteneklerini ve düşmanların zayıflıklarını etkiler.
- The game features a friction field mechanic, looting system, enemy design, PvP combat, resource management, inventory management, stamina system, reaction speed, fast-paced decision making, tactics and strategy, risk management, friction-based limitations, gameplay loop, gameplay mechanics, and gameplay systems.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Enemy_Design` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Enemy Design |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Sistem, oyuncunun zorluğunu belirlemek için bir state machine kullanır.
- [Unreal] Sistem, oyuncunun spesifiklığını belirlemek için bir event/delegate akışı kullanır.
- [Unreal] Sistem, oyuncunun kişiliğini belirlemek için bir state machine kullanır.
- [Unreal] Oyuncuların karşılaştıkları düşmanları tasarlamak için state machine, event/delegate akışı ve çalışma mantığı

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Enemy Design** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Enemy Design İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Gameplay Mechanics]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Gameplay Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Resource Management]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Enemy AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game Maker S Toolkit In 2019]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Engineering_The_Perfect_Enemy`, `Good_Design_Bad_Design_Vol._8_-_Analyzing_the_Graphic_Design_in_Cuphead_Jackbox_and_More`, `How_Do_You_Design_a_Cast_of_Enemies`, `What_s_The_Point_of_Elements_in_Games`, `What_Saved_ARC_Raiders_From_Itself`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
