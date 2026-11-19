---
title: "Vertical Level Architecture"
aliases: ["Vertical Level Architecture"]
domain: "Level Design"
department: "WORLD_DEVELOPMENT"
bundle: "Bundle_1"
ku_count: 203
tags: [level_design, world_development, bundle_1, 4-bucket-module]
linked_systems: ["Level Design", "Landmark Guidance", "Navigation", "Traversal", "Volumetric Lighting & Darkness", "Mental Mapping"]
---

# Vertical Level Architecture

> **Domain:** [[Level_Design|Level Design]] | **Department:** `WORLD_DEVELOPMENT` | **Evidence Units:** `203`  
> **Linked Systems:** [[Level_Design|Level Design]], [[Landmark_Guidance|Landmark Guidance]], [[Navigation]], [[Traversal]], [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]], [[Mental_Mapping|Mental Mapping]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Dikey Bölüm Mimarisi (Verticality & Loops)**, metrekareyi yatayda genişletmek yerine katmanlı yükseklik, üstten bakış (vista vantage), tek yönlü açılan kestirme asansörler/merdivenler (Metroidvania shortcut valves) ve düşey görsel referanslarla oyuncunun zihninde 3 boyutlu bir **Bilişsel Harita (Mental Map)** kurar.

**Kütüphane Kanıtları (Corpus Insights):**
- Adaptive Difficulty — carry yourself over and over to make things easier that's easily preventable that will be my answer. Question 2 do you think the standardization of control schemes, camera angles, combat systems etc i
- Evolving Challenges, Limiting Toolset, Safe Zones, Spring Mechanic, Platform Bouncing, Falling Platforms, Enemy Placement, Level Design, Gameplay Mechanics, Player Experience, Level Progression, Challenge Difficulty, Player Feedback, Gameplay Variety, Level Themes
- Between a masquerade ball, a brilliant bank heist and a house trapped between two moments in time, the Dissonid series is famous for its intricate and imaginative level design. But if there's one stage that truly fits that description, it's the clockwork...
- Level tasarımı, oyuncunun ilerlemesini kolaylaştırmak için tasarlanmış bir mekanizmadır.
- The game features a variety of independent game mechanics, including survival, crafting, exploration, combat, resource management, base building, procedural generation, world exploration, quests, social interactions, monetization, economy, gameplay loops, player progression, and level design.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`WorldPartition` + `NavLinkProxy`):** Çok katlı arenalarda `NavLinkProxy` ile düşman atlayış noktalarını işaretleyin; kestirme kapılar için `BP_OneWayGate` aktöründe tek taraflı etkileşim tetikleyici box (`BoxCollision` sadece iç tarafta) kurun.
- **Unity 6 (`NavMeshLink` + `Occlusion Culling`):** Katlar arası görünürlük bütçesini korumak için dikey şaftlara `OcclusionArea` yerleştirin.
- **Godot 4 (`NavigationLink3D`):** Alt-üst katlarda düşman seslerinin karışmaması için `AudioStreamPlayer3D` dikey mesafe zayıflatma eğrisini daraltın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `SightlineAngleRange` | `15 - 35 deg Up/Down` | `Camera Pitch` | Frames vertical goals naturally in 75-90 FOV |
| `FloorTierSpacing` | `4.5 - 6.0 m` | `World Units` | Allows upper balcony combat & audio readability |
| `ShortcutUnlockRatio` | `1 loop / 3-5 min play` | `Pacing Cadence` | Connects deep wing back to central bonfire/hub |
| `DropDownSafeHeight` | `6.0 m Max Free Fall` | `Float` | Avoids accidental instant-death leaps |
| `NavMeshJumpLinkDist` | `3.5 - 7.0 m` | `AI Link Width` | Allows enemies to pursue across tiers |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] difficulty_level = player_stats.get_difficulty_level()
- [Unreal] control_scheme = input_component.get_control_scheme() | Components: `UInputComponent`
- [Unreal] camera_angle = player_controller_component.get_camera_angle() | Components: `UCameraComponent`
- [Unreal] Evolving Challenges: Lessons about evolving challenges, limiting your toolset and considering safe zones. But you made something new, something fresh and different and personal, but inarguably improved by taking note of 

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Yüksek bir balkona çıkıldığında FOV'un hafifçe genişlemesi ve uzaktaki ana kule/hedef üzerinde rüzgar/sis dramatik açılışı.
- Kestirme kapısı/asansörü açıldığında ağır metalik kilit sesi ve merkeze dönüş müziği motifinin tetiklenmesi.
- Yüksekten düşerken rüzgar uğultusu ve inişte pelerin savrulması.
- `UX Binding:` LevelDesignerHUD
- `UX Binding:` LevelEditor
- `UX Binding:` SpelunkyHUD
- `UX Binding:` SpelunkyUI

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Tekrarlayan Simetrik Katlar:** Her kat aynı taş doku ve ışık rengine sahipse oyuncu 2. dakikada nerede olduğunu şaşırır; her irtifa katmanına benzersiz renk paleti ve materyal verin (alt kat: rutubetli taş/yeşil yosun, üst kat: altın vitray/gün ışığı).
- **Görünmez Düşme Boşlukları:** Aşağıda zemin mi yoksa ölüm çukuru mu olduğunu ışık ve korkuluk kırıklarıyla belli etmemek.
- **Dikey Ses Karmaşası:** Üst kattaki düşmanın ayak sesinin oyuncuyla aynı katta gibi duyulması.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Level_Design|Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Landmark_Guidance|Landmark Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Navigation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Traversal]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Mental_Mapping|Mental Mapping]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Ask a Game Designer Anything #1 - Difficulty, Standardization, Depth`, `Bonus_-_Playing_your_Super_Mario_Maker_Levels_GMTK_Extra`, `Dishonored_2_Devs_Explain_the_Clockwork_Mansion`, `Don_t_make_this_assumption_about_your_players_Developing_10`, `Don_t_Starve_-_Creating_Community_Around_an_Antisocial_Game`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
