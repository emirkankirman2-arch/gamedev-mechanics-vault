---
title: "Anti-Pattern Playbook"
aliases: ["Anti-Pattern Playbook"]
domain: "Retention & Live Systems"
department: "QA"
bundle: "Bundle_5"
ku_count: 62
tags: [retention_live_systems, qa, bundle_5, 4-bucket-module]
linked_systems: ["Retention & Live Systems", "Player Guidance", "Economy", "Difficulty Design", "Combat"]
---

# Anti-Pattern Playbook

> **Domain:** [[Retention_Live_Systems|Retention & Live Systems]] | **Department:** `QA` | **Evidence Units:** `62`  
> **Linked Systems:** [[Retention_Live_Systems|Retention & Live Systems]], [[Player_Guidance|Player Guidance]], [[Economy]], [[Difficulty_Design|Difficulty Design]], [[Combat]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Başarılı oyun mekanikleri yalnızca 'ne eklemeli' sorusuyla değil, **'oyuncunun akışını, güvenini ve keyfini hangi tuzaklar bozar'** sorusuyla şekillenir. Pazar boşlukları ve oyuncu şikayetlerinin %70'i; okunaksız telegraphing, yapay zaman uzatma (artificial friction), ekonomik enflasyon, tutarsız kamera ve metin duvarı (text-wall) öğreticilerden kaynaklanır.

**Kütüphane Kanıtları (Corpus Insights):**
- Animal Crossing'de, oyuncuların evlerini dekore etmeleri ve hayvanları yetiştirmeleri mümkündür.
- XCOM2'da, oyuncuların askerlerini yetiştirmeleri ve savaşarak düşmanları yenmeleri mümkündür.
- Breath of the Wild'de, oyuncuların silahları ve zırhları yetiştirmeleri ve düşmanları yenmeleri mümkündür.
- Mass Effect 3'de, oyuncuların askerlerini yetiştirmeleri ve savaşarak düşmanları yenmeleri mümkündür.
- Soma'da, oyuncuların silahları yetiştirmeleri ve düşmanları yenmeleri mümkündür.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **QA & Telemetri Denetimi:** Her bölümde oyuncu ölüm ısı haritasını (`DeathHeatmap`) ve geri dönüş süresini (`RunbackTimer`) loglayın; oyuncuların %40'ından fazlası aynı noktada mekanik anlamadığı için ölüyorsa düşman gücünü değil **Tutorial & Telegraph** netliğini düzeltin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `MaxTutorialPopupWords` | `<= 12 Words / Prompt` | `UX Constraint` | Prefer spatial demonstration over paragraphs |
| `InputToVisualLatencyMax` | `<= 50 ms (3 frames)` | `Perf Budget` | Controls feel muddy beyond 60ms |
| `CheckpointRunbackMax` | `<= 15 - 25 seconds` | `Pacing Budget` | Punishing walk-backs induce churn, not challenge |
| `UIHUDMaxScreenCoverage` | `<= 12 % Viewport` | `HUD Budget` | Keeps player immersed in world sightlines |

**Derlenen Uygulama Reçeteleri:**
- Olay güdümlü (Event-Driven) modüler bileşen entegrasyonu.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Oyuncu şikayetini mekanik avantaja çevirme: Uzun yürüme yollarına hareket hızlandırıcı dash/grappling zincirleri veya geçici kısayollar eklemek.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Totolojik Sistem Tasarımı:** 'Oyuncu kılıcı kullanmak için kılıç kullanır' gibi boş döngüler; her mekanik başka bir sistemle çarpışmalıdır (ör. kılıç darbesi meşaleyi yakar veya zırhı parçalar).
- **Karanlık Örüntüler (Dark Patterns):** Yapay bekleme sayaçları, FOMO zamanlayıcıları veya adaletsiz RNG duvarları kısa vadeli metrik üretse de uzun vadeli topluluk güvenini ve Steam inceleme skorunu yıkar.
- **Oyuncu Girdisini Çalan Ara Sahneler:** Oyuncu tam zıplarken kontrolü kilitleyip kamerayı çevirmek.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Retention_Live_Systems|Retention & Live Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player_Guidance|Player Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Economy]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Difficulty_Design|Difficulty Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Should_Designers_Listen_to_Negative_Feedback`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
