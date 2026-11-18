---
title: "Character Progression"
domain: "Progression"
department: "DESIGN"
bundle: "Bundle_4"
ku_count: 26
tags: [progression, design, bundle_4, 4-bucket-module]
linked_systems: ["Progression", "Player Agency", "Combat", "Ico And Design By Subtraction"]
---

# Character Progression

> **Domain:** [[Progression]] | **Department:** `DESIGN` | **Evidence Units:** `26`  
> **Linked Systems:** [[Progression]], [[Player Agency]], [[Combat]], [[Ico And Design By Subtraction]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Character Progression mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Final Fantasy VIII'de, Junction System, oyuncunun karakterin statlerini ve yeteneklerini geliştirmesine olanak tanır.
- The game features character progression, where players can upgrade their abilities.
- Character Progression, oyuncunun yeteneklerini ve becerilerini geliştirmesini sağlar.
- Roguelike oyunlarda, oyuncuların ölümü kalıcıdır ve oyunun başlangıcına geri dönerler.
- Slay the Spire'de, oyuncuların yetenekleri ve eşyaları, oyuncuların ilerlemesine ve gelişimine göre değişir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Character_Progression` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Character Progression |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Junction System state machine, event/delegate akışı ve çalışma mantığı.
- [Unreal] Guardian Forces (GFs) state machine, event/delegate akışı ve çalışma mantığı.
- [Unreal] Magic Spells state machine, event/delegate akışı ve çalışma mantığı.
- [Unreal] Oyuncunun yeteneklerini ve becerilerini geliştirmesini sağlar.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Character Progression** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Character Progression İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Ico And Design By Subtraction]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Final_Fantasy_VIII_s_Divisive_Junction_System_~_Design_Doc`, `Ico_and_Design_by_Subtraction`, `Roguelikes_Persistency_and_Progression`, `Should_Games_Always_Be_Accessible`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
