---
title: "Rollback Netcode & Prediction"
aliases: ["Rollback Netcode & Prediction"]
domain: "Multiplayer"
department: "MULTIPLAYER_ONLINE"
bundle: "Bundle_2"
ku_count: 49
tags: [multiplayer, multiplayer_online, bundle_2, 4-bucket-module]
linked_systems: ["Multiplayer", "Combat", "Parry & Deflect Windows", "Camera & Player Perspective", "First-Person Animation & Terminal Ballistics"]
---

# Rollback Netcode & Prediction

> **Domain:** [[Multiplayer]] | **Department:** `MULTIPLAYER_ONLINE` | **Evidence Units:** `49`  
> **Linked Systems:** [[Multiplayer]], [[Combat]], [[Parry_Deflect_Windows|Parry & Deflect Windows]], [[Camera_Player_Perspective|Camera & Player Perspective]], [[First_Person_Animation_Terminal_Ballistics|First-Person Animation & Terminal Ballistics]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Gerçek zamanlı rekabetçi oyunlarda gecikme tabanlı ağ (delay-based netcode) oyuncunun kendi tuşuna basmasıyla hareket etmesi arasında sinir bozucu bir ağırlık yaratır. **Client-Side Prediction & Rollback**, yerel oyuncunun girdisini **0 frame gecikmeyle** anında çalıştırır; uzak oyuncunun paketi sonradan geldiğinde tahmin tutmazsa deterministik simülasyonu geriye sarıp birkaç milisaniye içinde yeniden simüle eder.

**Kütüphane Kanıtları (Corpus Insights):**
- The game uses rollback networking, task graph optimization, animation pre-sampling, job priorities, serialization, particle systems, predictive particle cache, speculative saves, desync detection, replay files, desync utility, handles, shared ownership, work in constructors/destructors, and interpolation.
- Rollback Networking is used for network synchronization
- Task Graph Optimization is used for task scheduling
- Animation Pre-sampling is used for animation optimization
- Oyun, küresel aday sistemleri ile birlikte çalışır.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`NetworkPrediction` Plugin / Iris):** Karakter hareket ve vuruş durumlarını `FNetworkPredictionState` içinde sabit tiklerle kaydedin.
- **Unity 6 / Godot 4:** Simülasyon state'ini render'dan ayırın (`Deterministik FixedTick()`), her frame'de son `8` durumu dairesel tamponda (`RingBuffer`) saklayın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `FixedSimulationStep` | `16.66 ms (60 Hz Tick)` | `Fixed Float` | Deterministic fixed-point or integer physics |
| `MaxRollbackWindow` | `7 - 10 Frames (~130 ms)` | `Int32` | Snapshot ring-buffer depth |
| `LocalInputDelay` | `1 - 2 Frames` | `Int32` | Reduces remote teleport artifacts on moderate ping |
| `LagCompRewindCap` | `200 ms Max Rewind` | `Float` | Prevents high-ping attackers hitting behind cover |

**Derlenen Uygulama Reçeteleri:**
- Olay güdümlü (Event-Driven) modüler bileşen entegrasyonu.

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Rollback düzeltmesi yaşandığında görsel ışınlanmayı yumuşatmak için **Render Interpolation (Error Smoothing)** kullanarak mesh pozisyonunu `50 ms` içinde yeni konuma süzün.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Deterministik Olmayan Rastgelelik:** Rollback sırasında `Random.Range` çağırmak istemciler arasında desync (senkron kopması) yaratır; her zaman simülasyon frame'ine bağlı seeded PRNG kullanın.
- **İstemciye Kör Güven (Client Authority):** Hasar ve mermi onayını doğrulamadan istemciden kabul etmek hileye kapı açar.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Multiplayer]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Parry_Deflect_Windows|Parry & Deflect Windows]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera_Player_Perspective|Camera & Player Perspective]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[First_Person_Animation_Terminal_Ballistics|First-Person Animation & Terminal Ballistics]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `8_Frames_in_16ms_-_Rollback_Networking_in_Mortal_Kombat_and_Injustice_2`, `I_Shot_You_First_-_Networking_the_Gameplay_of_Halo_-_Reach`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
