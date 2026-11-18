---
title: "Storytelling"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 35
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Difficulty Curve", "Player Agency", "Enemy Design"]
---

# Storytelling

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `35`  
> **Linked Systems:** [[Level Design]], [[Difficulty Curve]], [[Player Agency]], [[Enemy Design]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyunun hikaye anlatımı mekanizmaları

**Kütüphane Kanıtları (Corpus Insights):**
- Hi, my name is Tynis Savkestuk and I am a game designer. Today we will dissect air memories of old, a peaceful, meditative game about a pill grimace through the land of gods. We play as Ock, one of the last few shapeshifters still left in this broken world...
- Küresel aday sistemlerinde zorluk seviyesi, oyuncunun yeteneklerini ve deneyimi ile doğru orantılıdır.
- Rogue Legacy'de ölüm kalıcıdır; ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Oyun, oyuncunun karakterini geliştirmesine ve yeteneklerini geliştirmesine izin verir.
- Conjig Dream, oyuncunun düşüncelerini ve duygularını simüle eden bir oyun tasarımı mekanizmasıdır.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Storytelling` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Storytelling |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyunun hikaye anlatımı mekanizmaları: Hi, my name is Tynis Savkestuk and I am a game designer. Today we will dissect air memories of old, a peaceful, meditative game about a pill grimace through the land of gods. We play
- [Unreal] Sistem, oyuncunun zorluğunu belirlemek için bir state machine kullanır.
- [Unreal] Sistem, oyuncunun spesifiklığını belirlemek için bir event/delegate akışı kullanır.
- [Unreal] Sistem, oyuncunun kişiliğini belirlemek için bir state machine kullanır.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Storytelling** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.
- `UX Binding:` VillainDesignHUD
- `UX Binding:` ConflictCreationHUD
- `UX Binding:` PlayerEngagementHUD
- `UX Binding:` PuzzleScreen

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Storytelling İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Difficulty Curve]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Enemy Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] Aer： Memories of Old - the game with the BEST flight mechanics`, `Engineering_The_Perfect_Enemy`, `Good_Design_Bad_Design_Vol._4_-_The_Best_and_Worst_of_Video_Game_Graphic_Design_~_Design_Doc`, `How_to_Fix_Borderlands_3_s_Villains`, `Is_Until_Dawn_a_Good_Horror_Movie`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
