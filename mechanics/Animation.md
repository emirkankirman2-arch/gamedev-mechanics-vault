---
title: "Animation"
aliases: ["Animation"]
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 26
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat", "Global Information"]
---

# Animation

> **Domain:** [[Level_Design|Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `26`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Player_Agency|Player Agency]], [[Combat]], [[Global_Information|Global Information]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Animation mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyun, perma-death kurallarına sahiptir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.
- Animasyon, oyuncuların oyun içi animasyonlarını kontrol etmelerine olanak sağlar.
- Animasyon, oyuncunun hareketini kontrol etmesine olanak sağlayan bir sistemdir.
- Loop mekanizması, oyuncunun döngüsel olarak aynı seviyeyi tekrarlamasını sağlar.
- Animasyon, oyunun animasyonlarını ve hareketlerini destekleyen bir mekaniktir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Animation` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Animation |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Diogetic UI mekanik sisteminin temel tasarım amacı ve işlevi: Brothers. You can see it on his side, but most of the time the characters in Smash are way too small and the gameplay is way too chaotic to even notice that i
- [Unreal] Empty Space mekanik sisteminin temel tasarım amacı ve işlevi: Brothers. You can see it on his side, but most of the time the characters in Smash are way too small and the gameplay is way too chaotic to even notice that i
- [Unreal] Menu Design mekanik sisteminin temel tasarım amacı ve işlevi: Brothers. You can see it on his side, but most of the time the characters in Smash are way too small and the gameplay is way too chaotic to even notice that i
- [Unreal] Oyun içi animasyonlarını kontrol etmek: We're talking about graphic design in games, things like menus, UI, UX, color choice, font choice, animation, character design, the presentation of information. Oh, and remember fo

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Animation** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Animation İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Global_Information|Global Information]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Good_Design_Bad_Design_Vol._13_with_JoCat_-_Advance_Wars_Chicory_Astroneer_and_More_~_Design_Doc`, `Good_Design_Bad_Design_Vol._9_-_The_Graphic_Design_of_Animal_Crossing_Resident_Evil_2_and_More`, `How_to_make_a_good_platforming_character_Developing_6`, `I_Made_A_Game_In_4_Days_GMTK_Game_Jam_Dev_Log`, `The_one_thing_you_need_to_finish_your_game_Developing_11`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
