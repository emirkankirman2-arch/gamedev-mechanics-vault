---
title: "The Making Of Divinity Original Sin 2"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 22
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Core Systems", "Progression", "Player Agency", "Crafting"]
---

# The Making Of Divinity Original Sin 2

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `22`  
> **Linked Systems:** [[Level Design]], [[Core Systems]], [[Progression]], [[Player Agency]], [[Crafting]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Systems and principles discussed in The_Making_of_Divinity_-_Original_Sin_2.

**Kütüphane Kanıtları (Corpus Insights):**
- Küresel aday sistemleri, oyunun temelini oluşturan üç ana bileşen olarak Core Systems, Combat Mechanics ve Progression'i içerir.
- Core Systems, oyunun temelini oluşturan temel bileşenlerdir.
- Combat Mechanics, oyunun savaş mekanizmalarını oluşturur.
- Progression, oyunun ilerlemesini ve gelişimini sağlar.
- The game features a post-processing effect that enhances the visual experience.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `The_Making_Of_Divinity_Original_Sin_2` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for The Making Of Divinity Original Sin 2 |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- Olay güdümlü (Event-Driven) modüler bileşen entegrasyonu.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **The Making Of Divinity Original Sin 2** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **The Making Of Divinity Original Sin 2 İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Core Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Crafting]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `The_Making_of_Divinity_-_Original_Sin_2`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
