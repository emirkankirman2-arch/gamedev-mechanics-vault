---
title: "Tasar M Felsefesi"
domain: "Level Design"
department: "DESIGN"
bundle: "Bundle_1"
ku_count: 28
tags: [level_design, design, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Player Agency", "Combat"]
---

# Tasar M Felsefesi

> **Domain:** [[Level Design]] | **Department:** `DESIGN` | **Evidence Units:** `28`  
> **Linked Systems:** [[Level Design]], [[Player Agency]], [[Combat]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Tasarım Felsefesi mekanik sistemi.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyun tasarımcıları, tasarım felsefelerini ve projelerin sağlıkını önceliklendirerek, çeşitlilik ve analiz yoluyla gelişime katkıda bulunurlar.
- Küresel Bilgi Haritası, oyun tasarımcılarının oyun dünyasını planlamasına yardımcı olur.
- Oyunun temel felsefesi, oyuncuların kendi tasarım tercihlerini keşfetmelerine ve oyunun dünyasını keşfetmelerine izin vermektedir.
- Küresel Bilgi Haritası, oyunun temelini oluşturan bir sistemdir; oyuncuların bilgiyi nasıl kullanacaklarını ve nasıl ilerleyeceklerini belirler.
- Rogue Legacy'de oyuncuların kolaylaştırma seçeneklerini özelleştirmesi mümkündür.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Tasar_M_Felsefesi` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Tasar M Felsefesi |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Tasarım felsefesi sisteminin state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Neden sorusu sisteminin state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Küresel Bilgi Haritası mekanik sistemi: Solid drawing, which helps make a 2D drawing, looks like it's a 3D object. And appeal, which is pretty much just making your character cool. There are a ton of great videos that go
- [Unreal] Oyun Tasarımı mekanik sistemi: Solid drawing, which helps make a 2D drawing, looks like it's a 3D object. And appeal, which is pretty much just making your character cool. There are a ton of great videos that go into muc

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Tasar M Felsefesi** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Tasar M Felsefesi İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] 1.6. The Designer Mindset ｜ Farlands School of Game Design`, `Good_Design_Bad_Design_Vol._11_-_Tetris_Hyper_Light_Drifter_and_Great_Game_Animation`, `Good_Design_Bad_Design_Vol._14_-_Great_and_Terrible_Graphic_Design_in_Games`, `Graphic_Design_in_New_Games_-_Good_Design_Bad_Design_17`, `Improving_Games_for_Those_with_Cognitive_Disabilities_Designing_for_Disability`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
