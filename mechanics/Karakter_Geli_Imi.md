---
title: "Karakter Geli Imi"
aliases: ["Karakter Geli Imi"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 28
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat"]
---

# Karakter Geli Imi

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `28`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Player_Agency|Player Agency]], [[Combat]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Karakter Gelişimi mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyunun temel mekanizması Hero's Journey Paradigması ile tasarlanmıştır.
- Oyun tasarımı, dünya yapımı, interaktif hikaye, narratif interaktiflik, oyun döngüsü, fikir ve ideoloji, karakter gelişimi, oyun dünyası, dünya yapımı, narratif interaktiflik, oyun döngüsü, fikir ve ideoloji, karakter gelişimi, oyun dünyası, dünya yapımı, narratif interaktiflik, oyun döngüsü, fikir ve ideoloji, karakter gelişimi, oyun dünyası, dünya yapımı, narratif interaktiflik, oyun döngüsü, fikir ve ideoloji, karakter gelişimi, oyun dünyası
- Küresel aday sistemleri, oyun tasarımcıları tarafından tasarlanan ve oynanış ile dünya bağlantısını sağlayan çeşitli mekaniklerdir.
- Oyunun küresel adayı sistemleri, rebalanslama, yeniden tasarım, prosedürel seviye oluşturma, mülakat mekanizması, Abyss Çatlakları, Breach, Betrayal, Pranters, Synthesis, Item Ödülleri, Divination Kartları, Benzersiz İtemler, Modlar, Karakter Gelişimi, Seviye Oluşturma ve Oyun Döngüsü olmak üzere 17 farklı mekanik ve tasarım tercihi içerir.
- Oyun, lineer bir oyun tasarımı kullanır; oyuncular, belirli bir hedefe ulaşmak için bir dizi görevi tamamlamak zorundadır.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Karakter_Geli_Imi` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Karakter Geli Imi |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Hero's Journey Paradigması mekanik sistemi: to delve into the depths of Journey and analyze what makes it tick. The dramatic core of Journey is, well, the hero's journey paradigm, also known as the Monolith. It is a stor
- [Unreal] Monolit mekanik sistemi: to delve into the depths of Journey and analyze what makes it tick. The dramatic core of Journey is, well, the hero's journey paradigm, also known as the Monolith. It is a story-telling structure
- [Unreal] Oyun Tasarımı mekanik sistemi: to delve into the depths of Journey and analyze what makes it tick. The dramatic core of Journey is, well, the hero's journey paradigm, also known as the Monolith. It is a story-telling str
- [Unreal] Oyun tasarımı mekanik sistemi: But since then, I've kind of deliberately made moves towards first-person games and games with an increasingly holistic approach to level design. In terms of how it's here. That satisfies a

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Karakter Geli Imi** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Karakter Geli Imi İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] The Anatomy of Journey ｜ Farlands School of Game Design`, `An_Approach_to_Holistic_Level_Design`, `Can_A_Game_Be_Too_Realistic`, `Designing_Path_of_Exile_to_Be_Played_Forever`, `FFX_VS_FFXIII_-_Two_Linear_Games_Two_Outcomes_~_Design_Doc`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
