---
title: "Game Mechanics Vault — Living Library (Updated Every 10K Videos)"
tags: [index, home, gamedev-vault, living-library]
---

# 🎮 Game Mechanics Vault — Living Library (Her 10.000 Videoda Güncellenen Yaşayan Kütüphane)

Hoş geldiniz! **7/24 çalışan video analiz motorumuzla sürekli büyüyen ve her 10.000 videoda bir büyük güncelleme alan** bu yaşayan bilgi ağı, oyun mekaniklerini **Teori**, **Motor/Kod (UE5, Unity 6, Godot 4)**, **Game Juice** ve **Anti-Pattern** olmak üzere **4 eşit sepette** sunar ve `[[WikiLinks]]` bağlantılarıyla birbirine bağlar.

- 💎 **Supporter Pack (Itch.io — `$0 or Donate`):** [Çevrimdışı Vault + UE5/Unity/Godot + AI CLI + MCP İndir](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp)
- 🔥 **Tam Master Rapor:** [[Real_Library_Showcase_5_Core_Mechanics|5 Kategori Master Raporu (Işık, Dünya, FPS, Çiftçilik, Mevsim/Doğa)]]
- 🔗 **Tüm Bağlantı Ağı:** [[linked_systems_graph|Linked Systems Graph]]
- 🤖 **AI / Cursor `@Docs` İndeksi:** [`llms.txt`](llms.txt) | [`llms-full.txt`](llms-full.txt)

---

## 🔥 Gerçek Kütüphane Çıktısı Örneği (Real Query Output — Living Library, Updated Every 10K Videos)

Aşağıdaki özetler sentetik şablon değil; **7/24 çalışan analiz motorumuzla sürekli büyüyen ve her 10.000 videoda bir büyük güncelleme alan yaşayan kütüphanemizin** gerçek veritabanından, gerçek oyun postmortem'lerinden ve kanonik sistem düğümlerinden damıtılmış **5 Kategori Master Raporu**ndan canlı alıntılardır. Tam teknik döküm için: [[Real_Library_Showcase_5_Core_Mechanics|5 Kategori Master Raporu]]

### 1. 🕯️ Işıklandırma & Karanlık (333+ Video Sentezi)
- **Teori & Kaynak:** *Blender Lighting*, *Cinematic Lighting for Artists*, *Alan Wake* & *Mario Maker 2 (FNAF Darkness Theme)*. 3 Noktalı Aydınlatmada `Fill Light` sıfırlanıp `Negative Fill` kullanıldığında korku kontrastı doğar; `Source Radius` küçüldükçe gölge penumbrası keskinleşir. FNAF / Mario Maker karanlık teması görüş alanını kısıtlayarak klostrofobik gerilim üretir.
- **Motor Parametreleri:** `SourceRadius = 2.0 - 8.0 cm` (keskin tehlike gölgesi), `FillLightIntensity = 0.0`, `VolumetricFogExtinction = 0.045`, `VisibilityCutoff = 0.22 Lux`.
- **Game Juice & Anti-Pattern:** `Negative Fill` kontrastı + tehlike anında `150 ms` ışık titremesi. **Anti-Pattern:** Saf siyah (`0.00`) "Crushed Blacks" körlüğü ile oyuncuyu duvara çarptırmak.
- **↔ Linked Systems:** [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]] ↔ [[Diegetic_Guidance|Diegetic Guidance]] ↔ [[Stealth]] ↔ [[Shader_Rim_Silhouette|Shader Rim & Silhouette]]

### 2. 🗺️ Dünya Kurma & Level Design (393+ Video Sentezi)
- **Teori & Kaynak:** *Stop Getting Lost (Cognitive Maps)*, *No Man's Sky Math & Continuous World Generation* (16 sistem) ve *Fallout: New Vegas Choice Architecture* (18 sistem). Oyuncu düz koridorları değil **Paths, Landmarks, Districts, Edges, Nodes** yapısını (`Allocentric` + `Egocentric Mapping`) ezberler. *No Man's Sky* küresel gezegenleri **Voxel Region + Dual Contouring/Marching Cubes + Spherification** ile; araziyi ise `Perlin`, `Uber`, `Ridge`, `Domain Warping` ve `Erosion Noise` katmanlarıyla üretir. *New Vegas* seçim mimarisi her kararı `Choice Conflict`, `Sacrifice` ve `Trade-Off` üzerine kurar.
- **Motor Parametreleri:** `UberNoiseOctaves = 6`, `DomainWarpStrength = 0.35`, `SpherificationRadius = 6400 m`, `DistrictHueShift >= 30 deg`.
- **Game Juice & Anti-Pattern:** Uzaktaki makro landmark (`AnchorVisibilityRadius`) üzerinde atmosferik sis ayrımı ve bölge geçiş akoru. **Anti-Pattern:** Simetrik kopyala-yapıştır odalarla bilişsel haritayı felç etmek veya sonuçsuz (sahte) diyalog dalları kurmak.
- **↔ Linked Systems:** [[Mental_Mapping|Mental Mapping]] ↔ [[Vertical_Level_Architecture|Vertical Level Architecture]] ↔ [[Procedural_World_Generation|Procedural World Generation]] ↔ [[World_Building|World Building]]

### 3. 🎯 FPS & Savaş Mekanikleri (152+ Video Sentezi)
- **Teori & Kaynak:** *Overwatch First-Person Animation Bootcamp* (15 sistem), *CS:GO SDK Terminal Ballistics* (`terminal_ballistics_system`, `bullet_penetration_system`) ve *Godot Game Juice Tutorials*. Overwatch'un **"Gameplay First"** yaklaşımı, `Locked-Off Camera` içinde `Parent Spaces`, `Additive Overlays`, `Spring-Based Aims` ve `Run Lean` katmanlarıyla nişan netliğini bozmadan karakter kişiliği verir. CS:GO duvar kalınlığı ve materyal yoğunluğuna göre mermi enerjisini azaltarak duvar delme (`Wall Bang`) hesaplar.
- **Motor Parametreleri:** `AdditiveSpringStiffness = 180.0`, `RunLeanMaxAngle = 4.5 deg`, `BulletPenetrationPower = 1.0..2.5`, `WallTraceStep = 4.0 cm`, `BulletSpreadSizeComp = 1.15x`.
- **Game Juice & Anti-Pattern:** Merkezi `camera_shake_requested` sinyali + zamanla azalan `damping`, `Timer` kontrollü `Frame Freeze` (`0.05 s`), `Bullet Size` telafili `Bullet Spread` ve pitch-shifted ateş SFX. **Anti-Pattern:** Nişangahı sallayan abartılı viewmodel animasyonu veya okunaksız duvar delme tutarsızlığı.
- **↔ Linked Systems:** [[First_Person_Animation_Terminal_Ballistics|First-Person Animation & Terminal Ballistics]] ↔ [[Combat]] ↔ [[Hitstop_Freeze_Frames|Hitstop & Freeze Frames]] ↔ [[Camera_Trauma_Screenshake|Camera Trauma & Screenshake]] ↔ [[Parry_Deflect_Windows|Parry & Deflect Windows]]

### 4. 🏡 Çiftçilik & Aidiyet Sistemleri (57+ Video Sentezi)
- **Teori & Kaynak:** *A Virtual Place to Call Home* (`hub_world_system`, `home_building_system`, `static_game_world_system`), *Animal Crossing: New Horizons* (oyuncuların aradığı **13 sistem** — Pazar Boşluğu Analizi) ve *The Farmer Was Replaced* (`coding_system`, `python_system`, `drone_system`). Statik ve güvenli bir **Hub/Ev** psikolojisi oyuncuda aidiyet yaratır. *Animal Crossing* analizinde tespit edilen 13 sistem boşluğu (`crafting_system` toplu üretim eksikliği, `organization_system`, `design_decoration_system`, `time_management_system`), oyuncunun hamallık istemediğini kanıtlar; *The Farmer Was Replaced* ise Python kodlu dronlarla bu çiftçilik döngüsünü algoritmik otomasyona dönüştürür.
- **Motor Parametreleri:** `HubSafeZoneRadius = 35 m`, `BatchCraftQueueMax = 10x`, `DroneGridTickRate = 4.0 Hz`, `CropROI_Multiplier = 1.8x - 3.2x`.
- **Game Juice & Anti-Pattern:** Ev/bahçe yerleştirmede anlık ölçek tween'i ve sıcak ahşap/toprak SFX; dron hasadında ritmik tarama ışını. **Anti-Pattern:** Yüzlerce tarlayı/eşyayı tek tek tıklatan (sıfır toplu üretim / otomasyon) arayüz hamallığı.
- **↔ Linked Systems:** [[Virtual_Home_Belonging_Hubs|Virtual Home & Belonging Hubs]] ↔ [[Automated_Drone_Farming_Batch_Crafting|Automated Drone Farming & Batch Crafting]] ↔ [[Farming_Seasonal_Loops|Farming & Seasonal Loops]] ↔ [[Economy]]

### 5. 🍃 Mevsim Döngüsü & Doğa (57+ Video Sentezi)
- **Teori & Kaynak:** *Zelda: Oracle of Ages and Seasons* (`Seasonal Switch`, 16 sistem), *Crazy But Not Too Crazy Game Weather* (hava durumunun 6 mekanik rolü) ve *God of War: Interactive Wind and Vegetation* (**49 alt sistem**). *Oracle of Seasons* mevsim değişimini (`Seasonal Switch`) doğrudan zindan/bulmaca kilidi yapar (kışın donan su, sonbaharda dolan çukurlar). Hava durumu yalnızca görsel değil **6 mekanik rolde** (`Difficulty Modifier`, `Story Element`, `Timer`, `Boundary`, `Environmental Property`, `Mood Setter`) çalışır. *God of War*, **49 alt sistemle** (`Wind Motors`, `Wake/Vortex/Omni Motors`, `Wind Volume`, `Bend Parameter`, `Cosine Falloff`, `Overshooting Animation`, `Diverging Neighbors`) bitki örtüsünü GPU Vertex Shader üzerinde bükerek yaşayan bir doğa simüle eder.
- **Motor Parametreleri:** `WindVolumeBeaufort = 1..12`, `BendParameterScalar = 0.0..1.0`, `CosineFalloffPower = 2.0`, `DivergingNeighborPhaseOffset = 0.35 rad`, `WeatherStateTransition = 8.0 s`.
- **Game Juice & Anti-Pattern:** `Overshooting Animation` yay salınımı + `Height Field Texture` kar/çamur ezilmesi + mevsimsel rüzgar ve yaprak partikülleri. **Anti-Pattern:** Yalnızca CPU'da kemik animasyonuyla binlerce çimi döndürüp kare hızını düşürmek veya oyuncuyu uyarmadan zorluk bozan rastgele hava durumu.
- **↔ Linked Systems:** [[Seasonal_Switch_Weather_Mechanics|Seasonal Switch & Weather Mechanics]] ↔ [[Interactive_Wind_Vegetation_WPO_Shaders|Interactive Wind & Vegetation WPO Shaders]] ↔ [[World_Building|World Building]] ↔ [[Puzzle_Design|Puzzle Design]] ↔ [[Shader_Rim_Silhouette|Shader Rim & Silhouette]]


---

## ⭐ Öne Çıkan Çekirdek Mekanikler (Featured Mechanics)

- [[Coyote_Time_Input_Buffering|Coyote Time & Input Buffering]] (`Traversal`)
- [[Hitstop_Freeze_Frames|Hitstop & Freeze Frames]] (`Combat`)
- [[Parry_Deflect_Windows|Parry & Deflect Windows]] (`Combat`)
- [[Camera_Trauma_Screenshake|Camera Trauma & Screenshake]] (`Camera & Player Perspective`)
- [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]] (`Diegetic Guidance`)
- [[Vertical_Level_Architecture|Vertical Level Architecture]] (`Level Design`)
- [[Mental_Mapping|Mental Mapping]] (`Navigation`)
- [[Behavior_Trees_Utility_AI|Behavior Trees & Utility AI]] (`Enemy AI`)
- [[Shader_Rim_Silhouette|Shader Rim & Silhouette]] (`Environmental Storytelling`)
- [[Adaptive_Audio_Stems|Adaptive Audio & Stems]] (`Diegetic Guidance`)
- [[Dynamic_Difficulty_Adjustment|Dynamic Difficulty Adjustment]] (`Difficulty Design`)
- [[Farming_Seasonal_Loops|Farming & Seasonal Loops]] (`Economy`)
- [[Rollback_Netcode_Prediction|Rollback Netcode & Prediction]] (`Multiplayer`)
- [[Permadeath_Meta_Progression|Permadeath & Meta-Progression]] (`Progression`)

## 🗂️ 28 Oyun Tasarımı Alanı (28 Canonical Domains)

- [[Exploration]] — *Keşif ve Merak Döngüleri*
- [[Player_Guidance|Player Guidance]] — *Oyuncu Yönlendirme Sistemleri*
- [[Diegetic_Guidance|Diegetic Guidance]] — *Diegetik (HUD-suz) Yönlendirme*
- [[Landmark_Guidance|Landmark Guidance]] — *Nirengi Noktaları (Landmarks)*
- [[Environmental_Storytelling|Environmental Storytelling]] — *Çevresel Anlatım*
- [[Navigation]] — *Uzamsal Navigasyon ve Bilişsel Harita*
- [[Combat]] — *Savaş ve Vuruş Sistemleri*
- [[Stealth]] — *Gizlilik ve Algılama Döngüleri*
- [[Traversal]] — *Hareket Fiziği ve Parkur*
- [[Progression]] — *İlerleme ve Güç Eğrileri*
- [[Quest_Design|Quest Design]] — *Görev ve Dallanan Anlatı Mimarisi*
- [[Puzzle_Design|Puzzle Design]] — *Bulmaca ve Epistemik Kilit Sistemleri*
- [[Enemy_AI|Enemy AI]] — *Düşman Yapay Zekası ve Koordinasyon*
- [[Boss_Design|Boss Design]] — *Boss Tasarımı ve Faz Geçişleri*
- [[Reward_Systems|Reward Systems]] — *Ödül Psikolojisi ve Ganimet Döngüleri*
- [[Tutorial_Onboarding|Tutorial & Onboarding]] — *Görünmez Öğretici (Invisible Onboarding)*
- [[Difficulty_Design|Difficulty Design]] — *Zorluk Eğrisi ve Dinamik Dengeleme*
- [[Economy]] — *Oyun Ekonomisi (Musluklar ve Giderler)*
- [[Crafting]] — *Zanaatkarlık ve Kaynak Dönüşümü*
- [[Multiplayer]] — *Çok Oyunculu ve Ağ Senkronizasyonu*
- [[Social_Systems|Social Systems]] — *Sosyal Sistemler ve Asenkron İşbirliği*
- [[Level_Design|Level Design]] — *Bölüm Tasarımı ve Ritim Mimarisi*
- [[World_Building|World Building]] — *Dünya İnşası ve Ekoloji*
- [[Camera_Player_Perspective|Camera & Player Perspective]] — *Kamera Fiziği ve Bakış Açısı*
- [[Player_Agency|Player Agency]] — *Oyuncu İnisiyatifi ve Emergent Oynanış*
- [[Discovery]] — *Gizli Keşif ve Sır Tasarımı*
- [[Risk_Reward|Risk & Reward]] — *Risk-Ödül Dengesi ve Gerilim*
- [[Retention_Live_Systems|Retention & Live Systems]] — *Oyuncu Tutma ve Canlı Sistemler*

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
