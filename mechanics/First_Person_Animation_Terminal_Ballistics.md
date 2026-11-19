---
title: "First-Person Animation & Terminal Ballistics"
aliases: ["First-Person Animation & Terminal Ballistics"]
domain: "Combat"
department: "DESIGN"
bundle: "Bundle_2"
ku_count: 201
tags: [combat, design, bundle_2, 4-bucket-module]
linked_systems: ["Combat", "Hitstop & Freeze Frames", "Camera Trauma & Screenshake", "Parry & Deflect Windows", "Rollback Netcode & Prediction"]
---

# First-Person Animation & Terminal Ballistics

> **Domain:** [[Combat]] | **Department:** `DESIGN` | **Evidence Units:** `201`  
> **Linked Systems:** [[Combat]], [[Hitstop_Freeze_Frames|Hitstop & Freeze Frames]], [[Camera_Trauma_Screenshake|Camera Trauma & Screenshake]], [[Parry_Deflect_Windows|Parry & Deflect Windows]], [[Rollback_Netcode_Prediction|Rollback Netcode & Prediction]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

*Overwatch First-Person Animation* (`gameplay_first_system`, 15 sistem) ve *CS:GO Terminal Ballistics* (`bullet_penetration_system`) birleşimi: Birinci şahısta kamera kontrolü (`Locked-Off Camera`) asla oyuncunun nişanından çalınmaz; karakter ağırlığı `Parent Spaces`, `Additive Overlays`, `Spring-Based Aims` ve `Run Lean` ile silah rig'ine bindirilir. Mermiler ise yüzeye çarpıp yok olmak yerine duvar kalınlığı ve materyal yoğunluğuna göre enerji kaybedip delip geçer.

**Kütüphane Kanıtları (Corpus Insights):**
- Rogue Legacy'de ölüm kalıcıdır ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Role-Playing sisteminde oyuncular karakterlerini geliştirebilir ve farklı yeteneklere sahip olabilir.
- Morality Systems, Karma Meter ve Chaos System, oyuncunun seçimlerinin sonuçlarını etkiler ve oyuncunun karakterini şekillendirir.
- İmha, oyuncunun düşmanları yok etmesine olanak tanıyan bir mekanizmadır.
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** İlk `LineTrace` yüzey vurduğunda `PhysicsMaterial` yoğunluğunu okuyun; kalınlığı ölçmek için mermi yönünde `PenetrationTraceStepCm` adımlarla ters trace atıp çıkış noktasından ikinci balistik ışını başlatın. Viewmodel rig'inde `AdditiveSpring` katmanını ana kamera rotasyonundan ayrı tutun.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `AdditiveSpringStiffness` | `150.0 - 220.0` | `Float` | Overwatch secondary spring settle on weapon aim |
| `RunLeanAngleMax` | `3.5 - 5.0 deg` | `Float` | Subtle strafe tilt without blocking center reticle |
| `PenetrationTraceStepCm` | `4.0 - 8.0 cm` | `Raycast Step` | Finds exit point through wall geometry |
| `WoodPenetrationLoss` | `0.35 Damage Ratio` | `Float` | Retains 65% energy after thin wood penetration |
| `ConcretePenetrationLoss` | `0.85 Damage Ratio` | `Float` | Heavy energy drop through masonry walls |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Platformer: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reason, 
- [Unreal] Resource Management: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever
- [Unreal] Deck Building: 2020 was an… interesting year, wasn't it? We've had grand shifts in politics, huge social movements, natural disasters and I think something else happened. Oh, I'm sure it wasn't a bomb. For whatever reaso
- [Unreal] Role-Playing: side quest that takes place in this hotel to see how developer Obsidian packs so many opportunities for role-playing into just one quest. Because, while you perhaps wouldn't know it to look at full-out four

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Delinen duvarın hem giriş hem çıkış yüzünde materyale özgü kıymık/beton tozu VFX + boğuklaştırılmış çıkış sesi.
- *Godot Game Juice* tekniğiyle `Bullet Spread` artırıldığında `Bullet Size` 1.15x büyütülerek adil isabet hissi korunur.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Nişangahı Kapatan Reload / Recoil:** Silah animasyonunun ekran merkezindeki hedefi kapatması (`Gameplay First` ihlali).
- **Tutarsız Duvar Kalınlığı Hatası:** Tek taraflı ince yüzeylerden mermi geçerken çift taraflı ince ahşap kapıda sıfır penetrasyon oluşması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Hitstop_Freeze_Frames|Hitstop & Freeze Frames]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera_Trauma_Screenshake|Camera Trauma & Screenshake]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Parry_Deflect_Windows|Parry & Deflect Windows]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Rollback_Netcode_Prediction|Rollback Netcode & Prediction]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_20_Games_You_Should_Have_Played`, `Anatomy_of_a_Side_Quest_-_Beyond_the_Beef`, `Are_Morality_Systems_Making_Us_Less_Moral`, `Does_Spidey_s_Web-Swinging_Make_You_Feel_Like_Spider-Man`, `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
