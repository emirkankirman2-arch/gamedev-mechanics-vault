---
title: "Parry & Deflect Windows"
domain: "Combat"
department: "DESIGN"
bundle: "Bundle_2"
ku_count: 143
tags: [combat, design, bundle_2, 4-bucket-module]
linked_systems: ["Combat", "Hitstop & Freeze Frames", "Boss Design", "Enemy AI", "Camera Trauma & Screenshake", "Rollback Netcode & Prediction"]
---

# Parry & Deflect Windows

> **Domain:** [[Combat]] | **Department:** `DESIGN` | **Evidence Units:** `143`  
> **Linked Systems:** [[Combat]], [[Hitstop & Freeze Frames]], [[Boss Design]], [[Enemy AI]], [[Camera Trauma & Screenshake]], [[Rollback Netcode & Prediction]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Parry (Savuşturma)**, savunmayı pasif bir 'bekleme' eyleminden yüksek riskli-yüksek ödüllü bir ritim oyununa dönüştürür. Başarılı olması için düşman saldırısının **Anticipation (Hazırlık/Telegraph)** aşaması net okunabilir olmalı, savuşturma penceresi ise adil ama disiplin gerektiren bir milisaniye aralığına oturtulmalıdır.

**Kütüphane Kanıtları (Corpus Insights):**
- Düşman saldırı animasyonlarının başlangıcındaki 200ms'lik belirgin wind-up (hazırlık) karesi, oyuncuya savuşturma (parry) penceresini görsel olarak önceden bildirir.
- Alan Wake'de düşman saldırı animasyonlarının başlangıcındaki 200ms'lik belirgin wind-up (hazırlık) karesi, oyuncuya savuşturma (parry) penceresini görsel olarak önceden bildirir.
- Ketchy, Mario'nun düşman saldırı animasyonlarının başlangıcındaki 200ms'lik belirgin wind-up (hazırlık) karesi, oyuncuya savuşturma (parry) penceresini görsel olarak önceden bildirir.
- Katana Zero'nun görsel tarzı, özellikle saldırı animasyonları, oyuncuya savuşturma (parry) penceresini görsel olarak önceden bildirir.
- Oyuncuların, düşman saldırı animasyonlarının başlangıcındaki 200ms'lik belirgin wind-up (hazırlık) karesi, savuşturma (parry) penceresini görsel olarak önceden bildirir.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`UAbilitySystemComponent` + `AnimNotifyState`):** Saldırgan silah montajına `ANS_ParryableWindow` ekleyin; savunan karakterde `State.ParryActive` GameplayTag'i aktifken temas olursa `GE_ParryStagger` ve `Event.ParrySuccess` tetikleyin.
- **Unity 6:** `ParryWindowTimer` aktifken gelen `IDamageable.TakeDamage()` çağrısını `AttackType.Parryable` bayrağıyla yakalayıp hasarı iptal edin ve saldırganı `StaggerState` durumuna geçirin.
- **Godot 4:** `Hurtbox` yerine ayrı bir `DeflectArea3D` açıp kapatın; çarpışma anında `parry_success` sinyali yayınlayın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ParryActiveWindow` | `0.14 - 0.22 s (8-13 frame)` | `Float` | Active deflect window after input press |
| `EnemyTelegraphWindup` | `0.35 - 0.60 s` | `Float` | Visual/Audio flash before active strike frames |
| `PostureDamageOnParry` | `25 - 40 % MaxPosture` | `Float` | Rewards risk with faster stagger break |
| `ParryRecoveryPenalty` | `0.28 - 0.38 s` | `Float` | Vulnerability frames on whiffed parry |
| `HitboxGraceRadius` | `1.15x Weapon Reach` | `Sphere Overlap` | Slightly generous deflect collision check |

**Derlenen Uygulama Reçeteleri:**
- [Agnostic] Saldırı animasyonunun başlangıcında 200ms'lik wind-up karesi gösterilir. Oyuncu bu pencereyi gördüğünde, savuşturma hareketini gerçekleştirebilir. | Components: `ParryWindowSystem`
- [Agnostic] Oyuncu ve düşman arasındaki savaşta, oyuncunun savuşturma hareketi, düşmanın saldırı animasyonu ile etkileşir. Oyuncu başarılı bir savuşturma hareketi gerçekleştirdiğinde, düşmanın saldırı animasyonu durur. | Components: `CombatSystem`
- [Agnostic] Düşman saldırı animasyonlarının başlangıcındaki 200ms'lik belirgin wind-up (hazırlık) karesi, oyuncuya savuşturma (parry) penceresini görsel olarak önceden bildirir. | Components: `Parry_Window`
- [Agnostic] Savuşturma (parry) penceresini kullanarak düşman saldırılarını savuşturabilir. | Components: `Parry_Window`

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Çarpışma noktasında radyal altın/kıvılcım patlaması (`Niagara` directional burst) + `0.09 s` Hitstop.
- Metalik çınlama SFX (`Pitch: 0.95..1.15` ardışık parry'lerde kademeli artan nota!).
- Kısa süreli kromatik aberasyon + düşmanın geri sekme animasyonunun tetiklenmesi.
- `UX Binding:` ParryWindowUI
- `UX Binding:` CombatHUD
- `UX Binding:` Parry_Window_UI
- `UX Binding:` EnemyWindupUI

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Okunaksız Anlık Saldırılar (<200 ms windup):** İnsan tepki süresi ~220-250 ms'dir; uyarı vermeyen saldırıya parry koymak şansa dönüşür.
- **Sıfır Ceza Spam'i:** Parry tuşuna art arda basmanın (button mashing) maliyeti yoksa zamanlama becerisi anlamını yitirir; ilk basıştan sonraki ardışık basışlarda pencereyi daraltın.
- **Belirsiz Başarısızlık:** Oyuncu kaçırdığında kısmi blok (chip damage) mu yoksa tam darbe mi alacağı görsel olarak ayrışmalıdır.
- Hızlı yakın dövüş sekanslarında oyuncunun hasarı adaletsiz hissetmesini ve görsel okunabilirlik karmaşasını önler.
- Hızlı yakın dövüş sekanslarında oyuncunun hasarı adaletsiz hissetmesini ve görsel okunabilirlik karmaşasını önler.
- Hızlı yakın dövüş sekanslarında oyuncunun hasarı adaletsiz hissetmesini ve görsel okunabilirlik karmaşasını önler.
- Hızlı yakın dövüş sekanslarında oyuncunun hasarı adaletsiz hissetmesini ve görsel okunabilirlik karmaşasını önler.

---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Hitstop & Freeze Frames]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Boss Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Enemy AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera Trauma & Screenshake]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Rollback Netcode & Prediction]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `15_Questions_Level_Designers_should_ask_themselves`, `Master_Class_in_Level_Design_Storytelling_-_6_Secrets_I_Learned_from_Playing_Alan_Wake`, `Good_Game_Design_-_Super_Mario_Odyssey`, `Good_Game_Design_-_Spelunky_2_-_Reinventing_Perfection`, `Good_Game_Design_-_Speedrunning`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
