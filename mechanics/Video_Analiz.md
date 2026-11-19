---
title: "Video Analiz"
aliases: ["Video Analiz"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 21
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat", "Global Information Map", "Video Analysis", "Design Philosophy"]
---

# Video Analiz

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `21`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Player_Agency|Player Agency]], [[Combat]], [[Global_Information_Map|Global Information Map]], [[Video_Analysis|Video Analysis]], [[Design_Philosophy|Design Philosophy]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Video Analiz mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Rogue Legacy'de ölüm kalıcıdır ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Video Analiz, oyun tasarımcılarının oyun oynanışını daha iyi anlamalarına yardımcı olur.
- Küresel Bilgi Haritası, oyun tasarımcılarının oyun dünyasını planlamasına yardımcı olur.
- Oyun, küresel bilgi haritası ile başlar ve oyuncunun oyunun çeşitli yönlerini keşfetmesine yardımcı olur.
- Oyun D Ng S: Here's a question for you. Can you fry an egg on top of Mount Everest? Between the altitude, temperature and difficulty of transport, there's definitely a lot of factors to consider. But surely by far the biggest one is…

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Video_Analiz` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Video Analiz |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Küresel Bilgi Haritası state machine | Components: `USceneComponent`
- [Unreal] Oyun Tasarımı mekanik sistemi: If it's raining, water type moves will get a power boost and fire type moves won't. Sunlight is the opposite. Hale and Sandstorms gradually damage Pokemon without the right type, ability, o | Components: `USceneComponent`
- [Unreal] Video Analiz mekanik sistemi: If it's raining, water type moves will get a power boost and fire type moves won't. Sunlight is the opposite. Hale and Sandstorms gradually damage Pokemon without the right type, ability, or | Components: `USceneComponent`
- [Unreal] Oyun oynanışını daha iyi anlamak için kullanılan bir araç. | Components: `UInputComponent`

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Video Analiz** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Video Analiz İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Global_Information_Map|Global Information Map]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Video_Analysis|Video Analysis]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Design_Philosophy|Design Philosophy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Building_A_Good_Place_To_Fight_-_RPG_Battlefields`, `Designing_Narrative_Choice_-_Add_Branching_Paths_to_Game_Stories_Without_a_AAA_Budget_~_Design_Doc`, `Good_Design_Bad_Design_Vol._11_-_Tetris_Hyper_Light_Drifter_and_Great_Game_Animation`, `Good_Design_Bad_Design_Vol._16_-_The_Best_and_Worst_of_Video_Game_Graphic_Design`, `How_Good_Design_Ruins_Games`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
