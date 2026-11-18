---
title: "Global Information Map"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 39
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Video Analiz", "Player Agency", "Speedrunning"]
---

# Global Information Map

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `39`  
> **Linked Systems:** [[Level Design]], [[Video Analiz]], [[Player Agency]], [[Speedrunning]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyunun küresel bilgi haritasını oluşturan sistem.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyun, küresel aday sistemlerini kullanıyor.
- Küresel Bilgi Haritası, oyuncuların oyun dünyasını keşfetmelerine ve stratejilerini geliştirmelerine yardımcı olur.
- Küresel Bilgi Haritası, oyun tasarımcıları tarafından oyunun dünya yapısı ve olay örgüsü için kullanılan bir araçtır.
- Küresel Bilgi Haritası, oyuncuların oyunun farklı bölgelerini keşfetmelerini ve kaynakları bulmalarını kolaylaştırır.
- Küresel Bilgi Haritası, oyuncuların haritayı daha iyi anlama ve navigasyon için kullanmasına yardımcı olur.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Global_Information_Map` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Global Information Map |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Steam sayfasını yenileyen state machine
- [Unreal] Küresel bilgi haritasını oluşturan state machine
- [Unreal] Oyuncuların oyun dünyasını keşfetmelerine ve stratejilerini geliştirmelerine yardımcı olur: liquid enemy called the Creep. Games like this usually have lengthy matches which are all about how well you can manage your eco
- [Unreal] Oyunun dünya yapısı ve olay örgüsünü tasarlamak: Vampire Survivors is a game that should not be fun. I mean, just look at it. Vampire Survivors is a video game that sees you playing as a knockoff console vania character,

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Global Information Map** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Global Information Map İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Video Analiz]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Speedrunning]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `30_Minute_Steam_Page_Makeovers`, `Starcraft_2-_The_Greatest_RTS_Ever`, `Vampire_Survivors_Only_Works_Because_We_re_Stupid`, `Why_Is_It_So_Easy_To_Break_Videogame_Economies`, `Why_You_Probably_Didn_t_Get_Lost_in_Metroid_Dread`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
