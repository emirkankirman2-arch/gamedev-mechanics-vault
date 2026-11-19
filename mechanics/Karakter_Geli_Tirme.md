---
title: "Karakter Geli Tirme"
aliases: ["Karakter Geli Tirme"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 21
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat"]
---

# Karakter Geli Tirme

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `21`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Player_Agency|Player Agency]], [[Combat]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Karakter Geliştirme mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Karakter geliştirme sistemi, oyuncunun yeteneklerini ve kabiliyetlerini geliştirmesine olanak tanır.
- Karakter geliştirme, oyuncuların oyunun ilerlemesini etkileyen çeşitli nesneleri ve olayları keşfetmelerine izin veren bir türdür.
- Karakter Geliştirme, oyuncuların oyun dünyasına daha fazla bağlanmalarına yardımcı olur.
- AP sistemi, oyuncunun savaşta ve diğer aktivitelerde kullanabileceği bir kaynak sistemidir.
- Golf RPG'de oyuncular karakterlerini geliştirmek için golf oyununu oynarlar.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Karakter_Geli_Tirme` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Karakter Geli Tirme |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Karakter yeteneklerini geliştirmek için kabiliyet seçimi ve geliştirme mantığı
- [Unreal] Karakter geliştirme için yetenek seçimi ve geliştirme mantığı
- [Unreal] Oyun döngüsü için yetenek seçimi ve geliştirme mantığı
- [Unreal] Karakterleri daha iyi tasarlamak için kullanılan bir araç.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Karakter Geli Tirme** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.
- `UX Binding:` KarakterTasarimiHUD
- `UX Binding:` KarakterGoreviHUD
- `UX Binding:` OyunDizayniHUD
- `UX Binding:` OyunGoreviHUD

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Karakter Geli Tirme İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Building_Better_Skill_Trees`, `Designing_Modern_Adventure_Games_-_Ace_Attorney_Danganronpa_and_More_~_Design_Doc`, `Designing_Narrative_Choice_-_Add_Branching_Paths_to_Game_Stories_Without_a_AAA_Budget_~_Design_Doc`, `Final_Fantasy_IX_-_How_to_Pace_a_Game_~_Design_Doc`, `Golf_Story_-_Why_Golf_RPGS_Work_~_Design_Doc`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
