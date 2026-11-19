---
title: "Global Information"
aliases: ["Global Information"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 35
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Game Design Systems", "Game Loop", "Animation", "Character Design"]
---

# Global Information

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `35`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Game_Design_Systems|Game Design Systems]], [[Game_Loop|Game Loop]], [[Animation]], [[Character_Design|Character Design]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Küresel Bilgi Haritası, oyunun temel yapısını oluşturan sistem.

**Kütüphane Kanıtları (Corpus Insights):**
- Küresel Bilgi Haritası, oyuncuların dünya üzerindeki kaynakları ve düşmanları hakkında bilgi sahibi olmalarını sağlar.
- Küresel Bilgi Haritası, Dolores Day, Moralizm, Pale, Shivers, Revishal
- Küresel Bilgi Haritası, Oyun Tasarım Sistemleri, Swing Mekanizması, Fizik Tabanlı Sistem, Dinamik Kamera, İterasyon, Oyun Deneyimi, Kontrol Sistemleri, Attach Noktası, Swing Hattı, Fiziksel Gerçekçilik, Görsel Efektler, Animasyon, Swing Animasyonu
- Küresel Bilgi Haritası, Oyun Tasarım Sistemleri, Videoda Tartışılan Sistemler, Swing Mekanizması, Fizik Tabanlı Sistem, Dinamik Kamera, İterasyon, Oyun Deneyimi, Kontrol Sistemleri, Attach Noktası, Swing Hattı, Fiziksel Gerçekçilik, Görsel Efektler, Animasyon, Swing Animasyonu
- Küresel Bilgi Haritası, Ödül Sistemleri, Paragon Seviyeleri, Badge Sistemleri, Kanatlı Sistem, Warforged Sistem, Titanforged Sistem, Cadala Sistem, Auction House, Enchant Sistem, Scaling Items, Deterministik ve Rastgele Ödül Sistemleri, Ödül Dengesi, RNG (Rastgele Sayı Üretimi) sistemleri

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Global_Information` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Global Information |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Küresel Bilgi Haritası: XCOM is one of my favourite game franchises of all time. It's got it all. Tense, tactical combat, deep strategic gameplay and a wide variety of things. Oh come on! That was a 95% shot! Ah, this ga
- [Unreal] State machine logiği kontrol edildi.
- [Unreal] Event/delegate akışı logiği kontrol ediliyor.
- [Unreal] Oyuncunun moral değerlerini oluşturması ve yönetmesi sistemi: under Ruby's floorboards. What the hell is it? Well, luckily, you're about to find out. I am the Shulia. I am the city. Shivers is the soul of Revishal. Just 

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Global Information** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Global Information İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game_Design_Systems|Game Design Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game_Loop|Game Loop]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Animation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Character_Design|Character Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Difficulty_By_Design-_X-COM_2_s_Endless_Arms_Race`, `What_Was_Disco_Elysium_Actually_About`, `Concrete_Jungle_Gym_-_Building_Traversal_in_Marvel_s_Spider-Man`, `Rewards_in_Video_Games`, `Balatro_s_Cursed_Design_Problem`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
