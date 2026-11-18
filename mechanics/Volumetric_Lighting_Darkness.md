---
title: "Volumetric Lighting & Darkness"
domain: "Diegetic Guidance"
department: "ART"
bundle: "Bundle_3"
ku_count: 58
tags: [diegetic_guidance, art, bundle_3, 4-bucket-module]
linked_systems: ["Diegetic Guidance", "Stealth", "Shader Rim & Silhouette", "Landmark Guidance", "Environmental Storytelling", "Camera Trauma & Screenshake"]
---

# Volumetric Lighting & Darkness

> **Domain:** [[Diegetic Guidance]] | **Department:** `ART` | **Evidence Units:** `58`  
> **Linked Systems:** [[Diegetic Guidance]], [[Stealth]], [[Shader Rim & Silhouette]], [[Landmark Guidance]], [[Environmental Storytelling]], [[Camera Trauma & Screenshake]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Karanlık fantezi ve korku/FPS oyunlarında ışık yalnızca atmosferik bir süs değil, bir **oynanış mekaniği ve navigasyon pusulasıdır**. İnsan gözü otomatik olarak en yüksek kontrastlı ve sıcak/aydınlık alana yönelir (Phototaxis). Işık adaları (Light Pools) oluşturarak oyuncuyu pusula veya mini-harita olmadan dikey geçitlere, tehlikelere ve güvenli odaklara yönlendirebilirsiniz.

**Kütüphane Kanıtları (Corpus Insights):**
- Lighting — polygons, the finest shaders and the best lighting. While the environment usually takes a back seat. Like in this slide, the environment is all blurred out and completely in shadow. But that doesn't m
- The game uses procedural generation for its level design.
- Geoscape, Battlescape, Tactical Turn-Based Combat, Distractibility of Terrain, Lighting System, Hidden Maps, Emotional Investment in Soldiers, Reward Cycle, Procedural Map Generation, Random Alien Strategic Actions, Alien Deployment Emissions, Probabilistic AI, Research and Development System, Equipment and Upgrade System, Base Building and Management System
- Oyun, Light Pre-Pass Rendering, Fog, Fake Fog-Scattering Atmospheric Scattering, Glow, HDR Bloom, Chromatic Aberration, Blue Noise, Dithering, Banding, Quantization, Noise Modulation, Temple Anti-aliasing, Post-Effects, Lighting, Bounce Light ve Custom Lights mekaniklerini kullanıyor.
- Küresel Aday Sistemleri: Damperd Wrap, Hardness, Ambient Occlusion, Cast Shadows, Screen Space Reflections, Volume Lighting, Fog, Water Rendering, Fire Effects, Bay Flares, Rain Effects, Flash Light Effects, Smoke Effects, Wallpaper Effects, Swirl Noise, Flipbook Animation.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`Lumen` + `VolumetricFog`):** `ExponentialHeightFog` içinde `Volumetric Fog = true`; rehber ışık kaynaklarında `Volumetric Scattering Intensity = 2.0 - 4.0` kullanın. Karanlık bölgelerde düşmanları ayırmak için `PostProcess` kenar tespit veya karakter materyalinde `Fresnel` rim light ekleyin.
- **Unity 6 (`URP/HDRP Volumetric Fog`):** `CustomRenderPass` veya `Light Anchor` ile oyuncunun ışık seviyesini hesaplayıp `StealthDetector` bileşenine aktarın.
- **Godot 4 (`FogVolume` + `OmniLight3D`):** `VolumetricFog` aktif edip `light_volumetric_fog_energy = 2.5` ile geçitleri vurgulayın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `VolumetricFogExtinction` | `0.02 - 0.08` | `Float` | Controls god-ray density without washing shadows |
| `KeyToFillContrastRatio` | `4:1 - 8:1` | `Luminance Ratio` | Dark fantasy clarity vs unreadable mud |
| `RimLightFresnelPower` | `3.5 - 5.5` | `Shader Scalar` | Separates enemy silhouette in pitch darkness |
| `TorchFlickerFrequency` | `6.0 - 11.0 Hz` | `Noise Curve` | Subtle organic intensity +-12% modulation |
| `StealthLightThreshold` | `0.22 Normalized Lux` | `Float` | Visibility detection cutoff for AI stealth |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] {'stateMachine': 'CinematicEnvironmentProductionStateMachine', 'eventDelegates': ['OnCinematicEnvironmentProductionEvent', 'OnArtExperienceEvent']}
- [Unreal] {'stateMachine': 'LightingStateMachine', 'eventDelegates': ['OnLightingEvent']}
- [Unreal] Hex Grid mekanik sistemi: into there. And you'll notice that Wikers Island and the RAPT prison do not have streaming regions, but that's as far as procedural systems are concerned, because there is no procedural content 
- [Unreal] Puzzle Piece System mekanik sistemi: into there. And you'll notice that Wikers Island and the RAPT prison do not have streaming regions, but that's as far as procedural systems are concerned, because there is no procedur

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Işık kaynağının yakınına yaklaştıkça havada süzülen toz zerrecikleri (`GPU Particles`) ve sıcak renk geçişi.
- Meşale/fener söndüğünde dinamik ses miksajı: Ortam uğultusu netleşir, karakterin nefes sesi öne çıkar.
- Tehlike anında ışığın `150 ms` titreşip soğuk tona kayması.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Zifiri Karanlık Körlüğü (Crushed Blacks):** Siyah seviyesini `0.00` yapmak oyuncunun duvarlarla çarpışıp yönünü kaybetmesine neden olur; gece atmosferi için koyu lacivert/arduvaz (`#0C111C`) taban + silüet rim ışığı kullanın.
- **Sadece Dekoratif Işıklar:** Çıkış kapısını karanlıkta bırakıp çıkmaz sokağa parlak avize koymak oyuncunun zihnini sürekli kandırır.
- **Gölge Optimizasyon İhmali:** Her küçük mumda dinamik gölge açmak GPU bütçesini çökertir; yakındaki 2-3 ışık dışında gölgeyi kapatın.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Diegetic Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Stealth]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Shader Rim & Silhouette]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Landmark Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Environmental Storytelling]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera Trauma & Screenshake]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Cinematic_Environment_Production_for_Uncharted_4`, `Procedurally_Crafting_Manhattan_for_Marvel_s_Spider-Man`, `X-COM_-_UFO_Defense_Classic_Game_Postmortem`, `Low_Complexity_High_Fidelity_-_The_Rendering_of_INSIDE`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
