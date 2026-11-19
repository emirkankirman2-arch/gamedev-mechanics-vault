---
title: "Movement"
aliases: ["Movement"]
domain: "Combat"
department: "DESIGN"
bundle: "Bundle_2"
ku_count: 21
tags: [combat, design, bundle_2, 4-bucket-module]
linked_systems: ["Combat", "Player Agency", "Level Design"]
---

# Movement

> **Domain:** [[Combat]] | **Department:** `DESIGN` | **Evidence Units:** `21`  
> **Linked Systems:** [[Combat]], [[Player_Agency|Player Agency]], [[Level_Design|Level Design]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Movement**, DESIGN disiplini kapsamında oyun deneyimini yapılandıran çekirdek sistemlerden biridir.

**Kütüphane Kanıtları (Corpus Insights):**
- Spelunky ve klasik rogue-like oyunlarında permadeath kuralı geçerlidir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.
- The game features a variety of independent game mechanics, including movement, squish and stretch, regular timing, knockback timing, attack timing, sound control, regular sound pitch, coin animation, score animation, screen shake, dust effect, regular movement, pull, fraction, and regular timing.
- So, for example, instead of slamming the velocity straight to full speed, we can just ease it into it with a move toward. This is a function inside of Gadoo that we can apply to the velocity. Okay, so the next one is actually one of my favorites, and that is...
- Oyun, küresel aday sistemlerini kullanıyor.
- Oyun, oyuncunun hareket sistemini kullanmasına izin verir; oyuncunun hareket sistemi, oyuncunun karakterini kontrol etmesine olanak sağlar.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Movement` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Movement |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Cursed Dj mekanik sisteminin temel tasarım amacı ve işlevi: Recording myself dancing is inspiration for the movements and giggling to myself, doodling. It was like a capsule of a lot of my interests. These past few month
- [Unreal] Roode Sandstorm mekanik sisteminin temel tasarım amacı ve işlevi: Recording myself dancing is inspiration for the movements and giggling to myself, doodling. It was like a capsule of a lot of my interests. These past few
- [Unreal] Freestyle-Er mekanik sisteminin temel tasarım amacı ve işlevi: Recording myself dancing is inspiration for the movements and giggling to myself, doodling. It was like a capsule of a lot of my interests. These past few mo
- [Unreal] Oyuncunun hareketini kontrol eden sistem. | Components: `UInputComponent`

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Movement** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Movement İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Designing_Walk_It_Top_20_GMTK_Jam_2025`, `I_Turned_a_Boring_Platformer_Into_an_Addicting_One`, `Nintendo_-_Putting_Play_First`, `The_Legend_of_Zelda_-_Breath_of_the_Wild_s_dungeon_design_Boss_Keys`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
