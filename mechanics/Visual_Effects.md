---
title: "Visual Effects"
aliases: ["Visual Effects"]
domain: "Diegetic Guidance"
department: "DESIGN"
bundle: "Bundle_3"
ku_count: 30
tags: [diegetic_guidance, design, bundle_3, 4-bucket-module]
linked_systems: ["Diegetic Guidance", "Game Feel", "Player Agency", "Character Design", "G Rsel Efektler", "Game Design Systems"]
---

# Visual Effects

> **Domain:** [[Diegetic_Guidance|Diegetic Guidance]] | **Department:** `DESIGN` | **Evidence Units:** `30`  
> **Linked Systems:** [[Diegetic_Guidance|Diegetic Guidance]], [[Game_Feel|Game Feel]], [[Player_Agency|Player Agency]], [[Character_Design|Character Design]], [[G_Rsel_Efektler|G Rsel Efektler]], [[Game_Design_Systems|Game Design Systems]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Görsel efektlerin oluşturulması ve geliştirilmesi için kullanılan sistem.

**Kütüphane Kanıtları (Corpus Insights):**
- Görsel efektler, oyuncuların oyunu daha kolay görmesi için kullanılabilir.
- Destructible Shields: Oyuncu, düşmanların saldırısına karşı koruyucu kalkan kullanabilir, ancak bu kalkan düşmanların saldırısına maruz kaldığında yok olabilir.
- The game has a variety of visual effects, including lighting, shading, and texture mapping.
- The game features a variety of visual effects, including death splatters and peripheral vision, which enhance the gameplay experience.
- The game's visual effects are designed to create a sense of power and threat, with a focus on color coding and timing.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Visual_Effects` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Visual Effects |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyuncuların oyunu daha kolay görmesi için kullanılabilir görüntü efektleri.
- [Unreal] Destructible Shields: surestial threat while hopping in and out from behind destructible shields. There's also a UFO that floats across the top of the screen and begs you a random number of points when it's shot. It's a 
- [Unreal] Event delegate: Alien spawn -> Alien movement -> Alien attack
- [Unreal] Laser Beam Shooting: surestial threat while hopping in and out from behind destructible shields. There's also a UFO that floats across the top of the screen and begs you a random number of points when it's shot. It's a s

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Visual Effects** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Visual Effects İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Diegetic_Guidance|Diegetic Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game_Feel|Game Feel]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Agency|Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Character_Design|Character Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[G_Rsel_Efektler|G Rsel Efektler]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Game_Design_Systems|Game Design Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `How_Accessible_Were_2021_s_Games`, `How_Space_Invaders_Birthed_Japanese_Games`, `How_the_Visual_Effects_In_Games_Actually_Work`, `I_Made_an_Inverted_Biking_Game`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
