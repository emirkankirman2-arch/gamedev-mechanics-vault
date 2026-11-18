---
title: "Dynamic Difficulty Adjustment"
domain: "Difficulty Design"
department: "DESIGN"
bundle: "Bundle_4"
ku_count: 140
tags: [difficulty_design, design, bundle_4, 4-bucket-module]
linked_systems: ["Difficulty Design", "Progression", "Risk & Reward", "Enemy AI", "Reward Systems"]
---

# Dynamic Difficulty Adjustment

> **Domain:** [[Difficulty Design]] | **Department:** `DESIGN` | **Evidence Units:** `140`  
> **Linked Systems:** [[Difficulty Design]], [[Progression]], [[Risk & Reward]], [[Enemy AI]], [[Reward Systems]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Dinamik Zorluk Ayarı (DDA)**, oyuncunun beceri seviyesini gerçek zamanlı performans metrikleriyle (hasar alma sıklığı, şifa tüketimi, ıskalama oranı) ölçerek düşman agresifliğini veya kaynak düşme oranını görünmez biçimde dengeler. Amaç oyuncuya oyunu bedava kazandırmak değil, onu **Akış Kanalı (Flow Channel)** içinde tutmaktır.

**Kütüphane Kanıtları (Corpus Insights):**
- Boss Muharebeleri, oyuncunun yeteneklerini ve stratejilerini test eder.
- Örüntü Tanıma, oyuncunun oyunun dinamiklerini ve düşmanların davranışlarını anlamasına yardımcı olur.
- Charm Sistemi, oyuncunun yeteneklerini ve stratejilerini geliştirmesine yardımcı olur.
- Sağlık Sistemi, oyuncunun canını ve sağlık durumunu takip eder.
- Mermi Sistemi, oyuncunun silahlarını ve mermilerini yönetir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity / Godot:** `DifficultyDirector` bileşeni son 3 dakikadaki `DamageTaken`, `Deaths`, `Accuracy` verilerinden bir `PerformanceScore (-1.0 .. +1.0)` hesaplar. Bunu sadece **kaynak düşüşü** ve **düşman saldırı token aralığı** üzerinde `+-15%` sınırla uygular.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `LowHPGraceDamageScale` | `0.75x Last 15% HP` | `Float` | Creates thrilling 'near-death clutch' moments |
| `AmmoDropBoostOnEmpty` | `+35% Drop Chance` | `Probability` | Prevents soft-locks when player misses shots |
| `DDAUpdateWindow` | `Every 3 Encounters / 120s` | `Timer` | Smooth adjustment prevents noticeable rubberbanding |
| `DDAAdjustmentCap` | `+-18% Max Variance` | `Clamp Float` | Preserves intentional difficulty identity |

**Derlenen Uygulama Reçeteleri:**
- Olay güdümlü (Event-Driven) modüler bileşen entegrasyonu.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Son %15 canda gizli hasar azaltması aktifken ekran kenarlarında nabız efekti ile oyuncuya 'mucizevi bir şekilde hayatta kaldım' heyecanı yaşatmak.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Görünür Rubber-Banding:** Yarış veya aksiyon oyununda oyuncu mükemmel oynarken düşmanın fizik kurallarını bükerek ışınlanması oyuncunun ustalığını cezalandırır.
- **Patronun Canını Ortada Değiştirmek:** Oyuncu aynı saldırıyla az önce 100 vururken bir anda 40 vurduğunu fark ederse sistem yapaylaşır.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Difficulty Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Risk & Reward]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Enemy AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Reward Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `What_s_The_Point_Of_Hard_Games_Anyway`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
