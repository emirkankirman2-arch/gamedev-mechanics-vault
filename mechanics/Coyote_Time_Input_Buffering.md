---
title: "Coyote Time & Input Buffering"
aliases: ["Coyote Time & Input Buffering"]
domain: "Traversal"
department: "DESIGN"
bundle: "Bundle_2"
ku_count: 53
tags: [traversal, design, bundle_2, 4-bucket-module]
linked_systems: ["Traversal", "Camera & Player Perspective", "Level Design", "Combat"]
---

# Coyote Time & Input Buffering

> **Domain:** [[Traversal]] | **Department:** `DESIGN` | **Evidence Units:** `53`  
> **Linked Systems:** [[Traversal]], [[Camera_Player_Perspective|Camera & Player Perspective]], [[Level_Design|Level Design]], [[Combat]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyuncu zihnindeki 'tam kenarda bastım' algısı ile gerçek fizik çarpışma kutusunun (capsule/collider) platformu terk ettiği milisaniye arasında algısal bir boşluk vardır. **Coyote Time**, karakter platformu terk ettikten sonraki kısa sürede zıplama girdisini geçerli sayar; **Input Buffering** ise yere değmeden hemen önce basılan zıplama/saldırı komutunu kuyrukta bekleterek temas anında otomatik tetikler.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyunun küresel aday sistemleri Tactile Projection, Consistency, Grace Mechanics, Coyote Time, Dash Nudge, Button Configuration, Input Expectations, Game Feel, Playtesting, Iteration, Tuning, Sudden Bifurcation, Mid-Production ve Game Feel Aspects'tir.
- Tactile Projection — input factors that lead to good game feel. Tactile projection, consistency, and grace mechanics. Tactile projection is the direct connection between the action you do with the input mechanism and what
- three years later. And so after making character controllers and level editing tools and user interfaces, transition shaders, sound effects and puzzles after releasing prototypes and builds and demos after getting
- GJK, Bilateral Advancement, Conservative Advancement, Root Finding, Bisection, False Position Method, Separation Function, Support Point, Deepest Point, Time of Impact, Collision Detection, Continuous Collision, Tunneling, Ghost Collision, Linear Casting, Character Controller
- Küresel aday sistemleri: GJK, Bilateral Advancement, Conservative Advancement, Root Finding, Bisection, False Position Method, Separation Function, Support Point, Deepest Point, Time of Impact, Collision Detection, Continuous Collision, Tunneling, Ghost Collision, Linear Casting, Character Controller

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`UCharacterMovementComponent`):** `FallingLateralFriction = 0.8`, `GravityScale = 1.85`, `OnMovementModeChanged` ile `MOVE_Falling` anında `LastGroundedTime` damgası tutun; `CanJump()` içinde `GetWorld()->GetTimeSeconds() - LastGroundedTime <= 0.12f` koşuluyla izin verin.
- **Unity 6 (`CharacterController` / `Rigidbody2D`):** `coyoteCounter -= Time.deltaTime`, `jumpBufferCounter -= Time.deltaTime`. Her ikisi `> 0` olduğunda `vy = jumpImpulse` uygulayıp sayaçları sıfırlayın.
- **Godot 4 (`CharacterBody2D`/`3D`):** `CoyoteTimer` (OneShot `0.12s`) ve `JumpBufferTimer` (`0.14s`) kullanarak `is_on_floor()` çıktığı an timer'ı başlatın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `CoyoteTimeWindow` | `0.10 - 0.14 s (6-8 frame @60fps)` | `Float` | UE5 CharacterMovement / Unity Update / Godot _physics_process |
| `JumpBufferWindow` | `0.12 - 0.15 s` | `Float Timer` | Input Action queue timestamp delta |
| `ApexGravityScale` | `0.55x - 0.70x` | `CurveFloat` | Vertical velocity near 0 (-80..+80 cm/s) |
| `FallGravityMultiplier` | `1.65x - 2.10x` | `Float` | Snappier descent arc after jump apex |
| `LedgeCornerNudge` | `8 - 14 px / 0.15 m` | `Raycast Capsule` | Upward raycast pair nudges grazing head corners |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Tactile Projection state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Consistency state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Grace Mechanics state machine, event/delegate akışı ve çalışma mantığı
- [Unreal] Tactile Projection sisteminin temel tasarım amacı ve işlevi: input factors that lead to good game feel. Tactile projection, consistency, and grace mechanics. Tactile projection is the direct connection between the action

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Yere inişte `0.06 s` mikro squash-and-stretch (`Scale Y: 0.85 -> 1.0`, `Scale XZ: 1.12 -> 1.0`).
- Toz partikül patlaması (`Niagara` / `ParticleSystem` 8-14 parçacık) + zemin materyaline bağlı footstep SFX.
- Apex (tepe noktası) anında hafif pelerin/kumaş süzülme animasyonu ve rüzgar fısıltısı.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Çift Zıplama İstismarı:** Zıpladıktan hemen sonra Coyote penceresini sıfırlamazsanız oyuncu havada ikinci kez zıplayabilir.
- **Sabit Lineer Yerçekimi:** Çıkış ve iniş yerçekimini eşit bırakmak karakterin 'ayda süzülüyormuş' gibi ağır ve tepkisiz hissettirmesine yol açar.
- **Tamponsuz Girdi (Zero Buffer):** Oyuncu yere 2 frame kala zıplamaya bastığında girdi yok sayılırsa kontrolcünün bozuk olduğu algısı oluşur.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Traversal]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera_Player_Perspective|Camera & Player Perspective]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] 2.6. Game Feel and Input ｜ Farlands School of Game Design`, `I_made_a_game_about_magnets_Developing_16`, `Physics_for_Game_Programmers_Continuous_Collision`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
