# 🎮 Game Mechanics Vault — Living Library (Updated Every 10K Videos)

> **Bilingual Game Design Knowledge Graph (EN & TR) — Continuously Growing 24/7 • Major Release Every 10,000 Analyzed Videos**  
> **4-Bucket Architecture:** Theory (25%) • Engine/Code (25%) • Game Juice (25%) • Anti-Patterns (25%)

[![Built with Quartz 4](https://img.shields.io/badge/Built%20with-Quartz%204-7c3aed)](https://quartz.jzhao.xyz/)
[![Obsidian Ready](https://img.shields.io/badge/Obsidian-WikiLinks%20Graph-483699)](https://obsidian.md/)
[![Living Library](https://img.shields.io/badge/Living%20Library-Updated%20Every%2010K%20Videos-10b981)](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp)
[![Support on Itch.io](https://img.shields.io/badge/Support-Itch.io%20Supporter%20Pack-fa5c5c)](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp)

---

## 🌍 What Is This? (English)

**Game Mechanics Vault** is a **Living Library** powered by a **24/7 automated game-dev video dissection engine** — delivering a major corpus expansion **every 10,000 analyzed videos**. It structures **139+ core game mechanics** across **28 game design domains** into an interconnected knowledge graph distilled from real postmortems, GDC talks, and technical engine dissections.

Every mechanic page uses a strict **4-Bucket Architecture**:
1. **Theory & Heuristics (25%)** — Cognitive psychology, design intent, and systemic rules.
2. **Engine & Code (25% — UE5 / Unity 6 / Godot 4)** — Concrete component names and numerical parameter tables (Floats, Curves, Raycasts, WPO Vertex Shaders).
3. **Game Juice & Sensory UX (25%)** — Hitstop durations, trauma screenshake, SFX cues, and shader rim highlights.
4. **Anti-Patterns & Failure Modes (25%)** — Common traps, tautologies, and edge cases to avoid.

### 🤖 AI-Ready (`llms.txt`)
Point **ChatGPT**, **Claude**, **Gemini**, or **Cursor (`@Docs`)** directly to:
- `/llms.txt` — Structured AI sitemap & `linked_systems` index.
- `/llms-full.txt` — Clean, full plain-text vault context.

---

## 🇹🇷 Bu Proje Nedir? (Türkçe — Her 10K Videoda Güncellenen Yaşayan Kütüphane)

**Game Mechanics Vault**, arka planda **7/24 kesintisiz çalışan analiz motoruyla sürekli büyüyen ve her 10.000 videoda bir büyük sürüm güncellemesi alan yaşayan bir oyun tasarımı kütüphanesidir.** **139+ mekanik modülünü** ve **28 oyun tasarımı disiplinini** `[[WikiLinks]]` bağlantı ağıyla açık erişimli olarak sunar.

### Gerçek Veritabanından Örnek Sorgular
- *"God of War rüzgar ve bitki örtüsü WPO shader sistemini Zelda: Oracle of Seasons mevsim geçişiyle nasıl birleştiririm?"* -> [[Real_Library_Showcase_5_Core_Mechanics|5 Kategori Master Raporu]]
- *"Overwatch Gameplay First FPS animasyon katmanları ile CS:GO Terminal Ballistics duvar delme mekaniğini nasıl kurarım?"* -> [[Combat]] + [[Camera Trauma & Screenshake]]
- *"No Man's Sky Uber/Domain Warping Noise ve Cognitive Maps ile pusulasız dünya nasıl tasarlanır?"* -> [[Mental Mapping]] + [[Procedural World Generation]]

---

## 🔥 Gerçek Kütüphane Çıktısı Örneği (Real Query Output — Living Library, Updated Every 10K Videos)

Aşağıdaki özetler sentetik şablon değil; **7/24 çalışan analiz motorumuzla sürekli büyüyen ve her 10.000 videoda bir büyük güncelleme alan yaşayan kütüphanemizin** gerçek veritabanından, gerçek oyun postmortem'lerinden ve kanonik sistem düğümlerinden damıtılmış **5 Kategori Master Raporu**ndan canlı alıntılardır. Tam teknik döküm için: [[Real_Library_Showcase_5_Core_Mechanics|5 Kategori Master Raporu]]

### 1. 🕯️ Işıklandırma & Karanlık (333+ Video Sentezi)
- **Teori & Kaynak:** *Blender Lighting*, *Cinematic Lighting for Artists*, *Alan Wake* & *Mario Maker 2 (FNAF Darkness Theme)*. 3 Noktalı Aydınlatmada `Fill Light` sıfırlanıp `Negative Fill` kullanıldığında korku kontrastı doğar; `Source Radius` küçüldükçe gölge penumbrası keskinleşir. FNAF / Mario Maker karanlık teması görüş alanını kısıtlayarak klostrofobik gerilim üretir.
- **Motor Parametreleri:** `SourceRadius = 2.0 - 8.0 cm` (keskin tehlike gölgesi), `FillLightIntensity = 0.0`, `VolumetricFogExtinction = 0.045`, `VisibilityCutoff = 0.22 Lux`.
- **Game Juice & Anti-Pattern:** `Negative Fill` kontrastı + tehlike anında `150 ms` ışık titremesi. **Anti-Pattern:** Saf siyah (`0.00`) "Crushed Blacks" körlüğü ile oyuncuyu duvara çarptırmak.
- **↔ Linked Systems:** [[Volumetric Lighting & Darkness]] ↔ [[Diegetic Guidance]] ↔ [[Stealth]] ↔ [[Shader Rim & Silhouette]]

### 2. 🗺️ Dünya Kurma & Level Design (393+ Video Sentezi)
- **Teori & Kaynak:** *Stop Getting Lost (Cognitive Maps)*, *No Man's Sky Math & Continuous World Generation* (16 sistem) ve *Fallout: New Vegas Choice Architecture* (18 sistem). Oyuncu düz koridorları değil **Paths, Landmarks, Districts, Edges, Nodes** yapısını (`Allocentric` + `Egocentric Mapping`) ezberler. *No Man's Sky* küresel gezegenleri **Voxel Region + Dual Contouring/Marching Cubes + Spherification** ile; araziyi ise `Perlin`, `Uber`, `Ridge`, `Domain Warping` ve `Erosion Noise` katmanlarıyla üretir. *New Vegas* seçim mimarisi her kararı `Choice Conflict`, `Sacrifice` ve `Trade-Off` üzerine kurar.
- **Motor Parametreleri:** `UberNoiseOctaves = 6`, `DomainWarpStrength = 0.35`, `SpherificationRadius = 6400 m`, `DistrictHueShift >= 30 deg`.
- **Game Juice & Anti-Pattern:** Uzaktaki makro landmark (`AnchorVisibilityRadius`) üzerinde atmosferik sis ayrımı ve bölge geçiş akoru. **Anti-Pattern:** Simetrik kopyala-yapıştır odalarla bilişsel haritayı felç etmek veya sonuçsuz (sahte) diyalog dalları kurmak.
- **↔ Linked Systems:** [[Mental Mapping]] ↔ [[Vertical Level Architecture]] ↔ [[Procedural World Generation]] ↔ [[World Building]]

### 3. 🎯 FPS & Savaş Mekanikleri (152+ Video Sentezi)
- **Teori & Kaynak:** *Overwatch First-Person Animation Bootcamp* (15 sistem), *CS:GO SDK Terminal Ballistics* (`terminal_ballistics_system`, `bullet_penetration_system`) ve *Godot Game Juice Tutorials*. Overwatch'un **"Gameplay First"** yaklaşımı, `Locked-Off Camera` içinde `Parent Spaces`, `Additive Overlays`, `Spring-Based Aims` ve `Run Lean` katmanlarıyla nişan netliğini bozmadan karakter kişiliği verir. CS:GO duvar kalınlığı ve materyal yoğunluğuna göre mermi enerjisini azaltarak duvar delme (`Wall Bang`) hesaplar.
- **Motor Parametreleri:** `AdditiveSpringStiffness = 180.0`, `RunLeanMaxAngle = 4.5 deg`, `BulletPenetrationPower = 1.0..2.5`, `WallTraceStep = 4.0 cm`, `BulletSpreadSizeComp = 1.15x`.
- **Game Juice & Anti-Pattern:** Merkezi `camera_shake_requested` sinyali + zamanla azalan `damping`, `Timer` kontrollü `Frame Freeze` (`0.05 s`), `Bullet Size` telafili `Bullet Spread` ve pitch-shifted ateş SFX. **Anti-Pattern:** Nişangahı sallayan abartılı viewmodel animasyonu veya okunaksız duvar delme tutarsızlığı.
- **↔ Linked Systems:** [[Combat]] ↔ [[Hitstop & Freeze Frames]] ↔ [[Camera Trauma & Screenshake]] ↔ [[Parry & Deflect Windows]]

### 4. 🏡 Çiftçilik & Aidiyet Sistemleri (57+ Video Sentezi)
- **Teori & Kaynak:** *A Virtual Place to Call Home* (`hub_world_system`, `home_building_system`, `static_game_world_system`), *Animal Crossing: New Horizons* (oyuncuların aradığı **13 sistem** — Pazar Boşluğu Analizi) ve *The Farmer Was Replaced* (`coding_system`, `python_system`, `drone_system`). Statik ve güvenli bir **Hub/Ev** psikolojisi oyuncuda aidiyet yaratır. *Animal Crossing* analizinde tespit edilen 13 sistem boşluğu (`crafting_system` toplu üretim eksikliği, `organization_system`, `design_decoration_system`, `time_management_system`), oyuncunun hamallık istemediğini kanıtlar; *The Farmer Was Replaced* ise Python kodlu dronlarla bu çiftçilik döngüsünü algoritmik otomasyona dönüştürür.
- **Motor Parametreleri:** `HubSafeZoneRadius = 35 m`, `BatchCraftQueueMax = 10x`, `DroneGridTickRate = 4.0 Hz`, `CropROI_Multiplier = 1.8x - 3.2x`.
- **Game Juice & Anti-Pattern:** Ev/bahçe yerleştirmede anlık ölçek tween'i ve sıcak ahşap/toprak SFX; dron hasadında ritmik tarama ışını. **Anti-Pattern:** Yüzlerce tarlayı/eşyayı tek tek tıklatan (sıfır toplu üretim / otomasyon) arayüz hamallığı.
- **↔ Linked Systems:** [[Farming & Seasonal Loops]] ↔ [[Economy]] ↔ [[Crafting]] ↔ [[Progression]]

### 5. 🍃 Mevsim Döngüsü & Doğa (57+ Video Sentezi)
- **Teori & Kaynak:** *Zelda: Oracle of Ages and Seasons* (`Seasonal Switch`, 16 sistem), *Crazy But Not Too Crazy Game Weather* (hava durumunun 6 mekanik rolü) ve *God of War: Interactive Wind and Vegetation* (**49 alt sistem**). *Oracle of Seasons* mevsim değişimini (`Seasonal Switch`) doğrudan zindan/bulmaca kilidi yapar (kışın donan su, sonbaharda dolan çukurlar). Hava durumu yalnızca görsel değil **6 mekanik rolde** (`Difficulty Modifier`, `Story Element`, `Timer`, `Boundary`, `Environmental Property`, `Mood Setter`) çalışır. *God of War*, **49 alt sistemle** (`Wind Motors`, `Wake/Vortex/Omni Motors`, `Wind Volume`, `Bend Parameter`, `Cosine Falloff`, `Overshooting Animation`, `Diverging Neighbors`) bitki örtüsünü GPU Vertex Shader üzerinde bükerek yaşayan bir doğa simüle eder.
- **Motor Parametreleri:** `WindVolumeBeaufortScale = 1..12`, `BendParameterScalar = 0.0..1.0`, `CosineFalloffPower = 2.0`, `DivergingNeighborPhaseOffset = 0.35 rad`, `WeatherStateTransition = 8.0 s`.
- **Game Juice & Anti-Pattern:** `Overshooting Animation` yay salınımı + `Height Field Texture` kar/çamur ezilmesi + mevsimsel rüzgar ve yaprak partikülleri. **Anti-Pattern:** Yalnızca CPU'da kemik animasyonuyla binlerce çimi döndürüp kare hızını düşürmek veya oyuncuyu uyarmadan zorluk bozan rastgele hava durumu.
- **↔ Linked Systems:** [[World Building]] ↔ [[Environmental Storytelling]] ↔ [[Puzzle Design]] ↔ [[Shader Rim & Silhouette]]


---

## 💎 Supporter Pack (Offline Vault + Engine Tables + Local AI CLI + MCP Server)

Want the **offline Obsidian Vault**, **UE5/Unity 6/Godot 4 CSV & C++/GDScript templates**, **6 AI Drag-and-Drop Bundles** (for ChatGPT/Claude/NotebookLM), **Local CLI (`ask_vault.py`)**, and **Zero-Key MCP Server** — including future **10K-video milestone updates**?

👉 **[Download & Support on Itch.io ($0 or Donate)](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp)**  
📦 **[GitHub Repository](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault)**  
🌐 **[Interactive Web Graph (GitHub Pages)](https://emirkankirman2-arch.github.io/gamedev-mechanics-vault)**
