---
title: "Gameplay"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 37
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat", "G Rsel Efektler"]
---

# Gameplay

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `37`  
> **Linked Systems:** [[Level Design]], [[Player Agency]], [[Combat]], [[G Rsel Efektler]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Gameplay Loop mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- The Legend of Zelda: Breath of the Wild'da sightlines, oyuncunun görüş alanını belirler ve oyunun derinliğini artırır.
- Deus Ex: Mankind Divided, açık dünya oyununda, oyuncuların hub dünyayı keşfetmesine izin veren bir hub dünya tasarımı vardır.
- Oyun, oyuncuların karakterlerini geliştirmelerine ve yeteneklerini geliştirmelerine olanak tanır.
- Oyuncu, farklı silahları kullanabilir ve farklı oyun deneyimi elde edebilir.
- Spelunky ve klasik rogue-like oyunlarında permadeath kuralı geçerlidir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Gameplay` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Gameplay |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Sightlines state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Terrain Design state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Gameplay Loop state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Oyuncuların karakterlerini geliştirmelerine ve yeteneklerini geliştirmelerine olanak tanıyan sistem: at all. That game being Deus Ex mankind divided and the city of Prague. Prague is so small you can't really call it an 

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Gameplay** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Gameplay İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[G Rsel Efektler]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Breath_of_the_Wild_s_Exploration_Cycle_~_Design_Doc`, `Deus_Ex_-_Mankind_Divided_s_Amazing_Open_World`, `Half-Life_2_s_Invisible_Tutorial`, `My_Favourite_Games_From_GMTK_Game_Jam_2026`, `The_4_Ps_of_DOOM_s_Amazing_Combat`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
