---
title: "Interactive Wind & Vegetation WPO Shaders"
aliases: ["Interactive Wind & Vegetation WPO Shaders"]
domain: "Environmental Storytelling"
department: "ART"
bundle: "Bundle_3"
ku_count: 60
tags: [environmental_storytelling, art, bundle_3, 4-bucket-module]
linked_systems: ["Seasonal Switch & Weather Mechanics", "Volumetric Lighting & Darkness", "Shader Rim & Silhouette", "World Building"]
---

# Interactive Wind & Vegetation WPO Shaders

> **Domain:** [[Environmental_Storytelling|Environmental Storytelling]] | **Department:** `ART` | **Evidence Units:** `60`  
> **Linked Systems:** [[Seasonal_Switch_Weather_Mechanics|Seasonal Switch & Weather Mechanics]], [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]], [[Shader_Rim_Silhouette|Shader Rim & Silhouette]], [[World_Building|World Building]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

*God of War* (**49 alt sistem**) ve *Horizon Zero Dawn* (**33 sistem**) analizlerinden damıtılan GPU merkezli doğa fiziği: Bitki örtüsü CPU iskeletleriyle değil, `Wind Motors` (`Wake`, `Vortex`, `Omni`, `Directive`), `Wind Volume`, `Pivot System`, `Cosine Falloff`, `Overshooting Animation` ve `Diverging Neighbors` faz kaydırması kullanan **World Position Offset (WPO) Vertex Shader** ile simüle edilir.

**Kütüphane Kanıtları (Corpus Insights):**
- Backtracking, fetch quests, missable key items, story-driven backtracking, metroidvania, platformer, mystery games, environmental storytelling, infection, power-ups, level design, backtracking heavy design, speed run, pop quiz, escape, intrinsic abilities, extrinsic abilities, knowledge gained, clues, paths, NPCs, story changes, timeline structure, radiant historia, devil may cry, donkey kong 64, banjo tooie, wario land, pizza tower, outer wilds, tunic, hollow knight
- Mental Asylum Levels oyununda, oyuncuların psikolojik durumlarını yansıtan farklı seviyeler bulunur.
- Obscurative Design: Oyun, keşfe dayalı bir gameplay modeli kullanır ve oyuncuların keşfetmesine izin verir.
- The game features a minimal art style with procedural tile positioning, abstract shapes, falling leaf particles, birds that chirp and fly away, a fountain that spits water, grass patches, a tiny light source, bullet effects, hanging plants and bushes, Godrace, shader, particle system, procedural generation, and environmental storytelling.
- The game features a unique blend of psychological insights, characterisation, and environmental storytelling.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 Material / HLSL:** `PivotPainter2` veya Vertex Color R/G/B kanallarıyla kök-uç sertliğini okuyun; `ActorPosition` tabanlı `HeightFieldTexture` render target'ını WPO kanalına bağlayarak karakter geçerken çimleri yatırın.
- **Unity 6 URP / Godot 4 `.gdshader`:** `INSTANCE_CUSTOM.x` üzerinden her bitkiye rastgele `DivergingNeighborPhase` atayıp `sin(TIME * freq + phase)` dalgası uygulayın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `WindVolumeBeaufortScale` | `1.0 - 12.0 Scale` | `Float` | Regional wind intensity curve across biomes |
| `BendParameterMaxRad` | `0.15 - 0.85 rad` | `WPO Shader Float` | Pivot-anchored vertex tip bending amplitude |
| `CosineFalloffExponent` | `1.8 - 2.5` | `Shader Scalar` | Stiff root, flexible canopy weight distribution |
| `DivergingNeighborPhaseRad` | `0.25 - 0.60 rad` | `Per-Instance Float` | Breaks robotic synchronized grass waving |
| `HeightFieldSnowCompress` | `0.0 - 0.35 m` | `RenderTarget` | Persistent actor footprint & foliage pushdown |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Backtracking mekanik sisteminin temel tasarım amacı ve işlevi: Instead of extrinsic abilities that give you access to blocked areas like in Hollow Knight, in outer wilds you're gaining access to areas thanks to the knowl
- [Unreal] Fetch Quests mekanik sisteminin temel tasarım amacı ve işlevi: Instead of extrinsic abilities that give you access to blocked areas like in Hollow Knight, in outer wilds you're gaining access to areas thanks to the knowl
- [Unreal] Missable Key Items mekanik sisteminin temel tasarım amacı ve işlevi: Instead of extrinsic abilities that give you access to blocked areas like in Hollow Knight, in outer wilds you're gaining access to areas thanks to the
- [Unreal] Mental Asylum Levels mekanik sisteminin temel tasarım amacı ve işlevi: based around the play and it's set, so he can get up in the rafters, beat up Glorious in a critic, and cure her. Yes, in each of these mental asylum 

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- `Overshooting Animation` yay sönümlemesi ile ani rüzgar darbesi geçtikten sonra dalların gerçekçi geri titreşimi.
- `Wake Motor` ile kılıç savrulduğunda veya mermi geçtiğinde yakın çimlerin şok dalgasıyla yatması.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Senkronize Asker Çimler:** `Diverging Neighbors` faz farkı ve `Fractal Noise` olmadan tüm çimlerin aynı anda aynı yöne yatması.
- **Z-Fighting & Aşırı Alpha Overdraw:** Saydam yaprak katmanlarını optimize etmeden `Mip Flooding` veya LOD mesafesi olmadan çizmek.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Seasonal_Switch_Weather_Mechanics|Seasonal Switch & Weather Mechanics]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Volumetric_Lighting_Darkness|Volumetric Lighting & Darkness]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Shader_Rim_Silhouette|Shader Rim & Silhouette]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[World_Building|World Building]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `How_Can_You_Make_Backtracking_Fun`, `What_Made_Psychonauts_Special`, `Why_Tunic_Hides_Its_Tutorial`, `How_Game_Juice_Made_My_Game_Come_to_Life`, `Deus_Ex_-_Mankind_Divided_s_Amazing_Open_World`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
