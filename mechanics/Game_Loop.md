---
title: "Game Loop"
aliases: ["Game Loop"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 23
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Discovery", "Gameplay Mechanics", "Player Experience", "Global Information"]
---

# Game Loop

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `23`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Discovery]], [[Gameplay_Mechanics|Gameplay Mechanics]], [[Player_Experience|Player Experience]], [[Global_Information|Global Information]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyun döngüsü, oyunun temel yapısını oluşturan sistem.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyun Düzeni, oyunun ilerlemesini kontrol eder.
- İmprovize, küçültülmüş (Lo-Fi) çözümler, genişletilmiş imgeleme, keşif, etkileşimli hikaye, mental sağlık, kapitalizm, kaybetme, inanç, görsel imaj, ses, dil, hikaye, oyuncu imgesi, oyun döngüsü
- Oyun Döngüsü, oyuncuların oyunun farklı bölümlerini oynayarak deneyimlerini geliştirmelerini sağlar.
- Oyun Döngüsü, oyuncunun oyunun temelini oluşturan döngüyü anlama ve oyunda ilerlemesine yardımcı olur.
- Oyun Döngüsü, oyuncuların oyun dünyasıyla ilgili bilgi edinmesine yardımcı olur.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Game_Loop` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Game Loop |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Game Loop sisteminin temel amacı, oyunun genel döngüsünü belirlemek için oyun döngüsü sistemlerini kullanmaktır: Overcoming the travel guides you to more places to discover, which leads you to more collectibles as milest
- [Unreal] improvize_system: um the themes that we had of like mental health of like capitalism of loss of loss of belief in God the removal of kind of a central organizing force in your life which a lot of these things kind of hav
- [Unreal] lofi_solutions_system: um the themes that we had of like mental health of like capitalism of loss of loss of belief in God the removal of kind of a central organizing force in your life which a lot of these things kind o
- [Unreal] extended_imaging_system: um the themes that we had of like mental health of like capitalism of loss of loss of belief in God the removal of kind of a central organizing force in your life which a lot of these things kind

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Game Loop** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Game Loop İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Discovery]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Gameplay_Mechanics|Gameplay Mechanics]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Experience|Player Experience]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Global_Information|Global Information]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Collectibles_-_How_To_Make_Chores_Fun_In_Games`, `Nuke_Possum_Springs_-_A_Night_in_the_Woods_Design_Postmortem`, `Roguelikes_and_the_Modular_Genre`, `Triple_Bosses_-_Why_Are_They_Different`, `What_Makes_Video_Game_Stories_Special`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
