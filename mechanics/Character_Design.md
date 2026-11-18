---
title: "Character Design"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 30
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Character Development", "Sound Effects", "Visual Effects", "Gameplay Mechanics", "Global Information"]
---

# Character Design

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `30`  
> **Linked Systems:** [[Level Design]], [[Character Development]], [[Sound Effects]], [[Visual Effects]], [[Gameplay Mechanics]], [[Global Information]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Karakterlerin tasarımları ve yetenekleri.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyun, perma-death kurallarına sahiptir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.
- Rogue Legacy'de ölüm kalıcıdır; ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Karakter tasarımı, oyuncuların karakterlerini kontrol etmelerine olanak sağlar.
- The game features a variety of independent game mechanics, design choices, and rules.
- Oyun, seviye atma sistemi ile karakterin yeteneklerini ve ekipmanlarını geliştirmesini sağlar.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Character_Design` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Character Design |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Diogetic UI mekanik sisteminin temel tasarım amacı ve işlevi: Brothers. You can see it on his side, but most of the time the characters in Smash are way too small and the gameplay is way too chaotic to even notice that i
- [Unreal] Empty Space mekanik sisteminin temel tasarım amacı ve işlevi: Brothers. You can see it on his side, but most of the time the characters in Smash are way too small and the gameplay is way too chaotic to even notice that i
- [Unreal] Menu Design mekanik sisteminin temel tasarım amacı ve işlevi: Brothers. You can see it on his side, but most of the time the characters in Smash are way too small and the gameplay is way too chaotic to even notice that i
- [Unreal] 2D to 3D conversion: Welcome back to another installment of Good Design Bad Design, where we look at how games approach graphic design. While there's a lot of overlap between the two, good graphic design isn't exactly th

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Character Design** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Character Design İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Character Development]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Sound Effects]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Visual Effects]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Gameplay Mechanics]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Global Information]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Good_Design_Bad_Design_Vol._13_with_JoCat_-_Advance_Wars_Chicory_Astroneer_and_More_~_Design_Doc`, `Good_Design_Bad_Design_Vol._4_-_The_Best_and_Worst_of_Video_Game_Graphic_Design_~_Design_Doc`, `Good_Design_Bad_Design_Vol._9_-_The_Graphic_Design_of_Animal_Crossing_Resident_Evil_2_and_More`, `Weird_Gaming_Moments_9_-_El_Shaddai_-_Armaros_Fight`, `Final_Fantasy_IX_-_How_to_Pace_a_Game_~_Design_Doc`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
