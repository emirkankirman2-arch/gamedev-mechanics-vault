---
title: "Mental Mapping"
domain: "Navigation"
department: "WORLD_DEVELOPMENT"
bundle: "Bundle_1"
ku_count: 58
tags: [navigation, world_development, bundle_1, 4-bucket-module]
linked_systems: ["Navigation", "Landmark Guidance", "Vertical Level Architecture", "Environmental Storytelling", "Diegetic Guidance"]
---

# Mental Mapping

> **Domain:** [[Navigation]] | **Department:** `WORLD_DEVELOPMENT` | **Evidence Units:** `58`  
> **Linked Systems:** [[Navigation]], [[Landmark Guidance]], [[Vertical Level Architecture]], [[Environmental Storytelling]], [[Diegetic Guidance]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyuncular mini-harita okuna baktıklarında dünyaya değil, ekranın köşesindeki %5'lik bir daireye oynarlar. **Bilişsel Haritalama (Mental Mapping)**, dünyayı belirgin bölge kimliklerine (District Aesthetics), asimetrik kesişimlere (3+1 yol kuralı yerine 90 derece dışı açılar) ve sürekli görünen merkezi bir kule/nirengi noktasına göre inşa ederek oyuncunun ekranı değil mekanı ezberlemesini sağlar.

**Kütüphane Kanıtları (Corpus Insights):**
- Cognitive Maps, Wayfinding, Navigation, Mapmaking, Paths, Landmarks, Districts, Edges, Nodes, Allocentric Mapping, Egocentric Mapping, Route Memory, Player Flow, Level Design, Game Design, World Building
- Puzzle Box, Zelda serisindeki bir mekanizmadır ve oyuncunun ilerlemesini sağlayan bir araçtır.
- Dungeon Design: Oyun, oyuncunun ilerlemesini sağlayan bir labirint tasarımı kullanır.
- The game features a dungeon design system, key item system, backtracking, locked doors, lanterns, ember seeds, seasonal switch, time travel, puzzle solving, spatial reasoning, navigation, roundabout, crystal switches, ice blocks, magnetic glove, and ancient ruins.
- The game uses a combination of streaming, LODs, Ambra, Blanch Shader, Vertex Shader, Entity System, Deco Sets, Level Design, Navigation, Block Out, Prototyping, Technical Problems, Texture Management, Mesh Optimization, and Rendering Time Reduction to create a dynamic and immersive experience.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`HLOD` + `LevelInstance`):** Ana nirengi kulesini/dağını her bölgeden görülecek şekilde `AlwaysLoaded` katmanına alın; koridor kavşaklarına tek yönlü `PropCluster` (devrilmiş heykel, kırık kemer) koyarak dönüş yönünü kodlayın.
- **Unity 6 & Godot 4:** Bölge geçişlerinde `PostProcessVolume` / `Environment` renk derecelendirmesini (LUT/ColorGrading) yumuşak `1.5s` blend ile değiştirin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `IntersectionAngleMin` | `35 - 125 deg Asymmetric` | `Geometry Angle` | Prevents identical 4-way corridor confusion |
| `DistrictPaletteShift` | `Hue Shift >= 30 deg` | `Color Theory` | Each wing has distinct lighting & architecture |
| `AnchorVisibilityRadius` | `300 - 1200 m` | `LOD Distance` | Macro landmark stays silhouetted at horizon |
| `WeenieGuidancePull` | `2 - 3 Visual Layers` | `Composition` | Foreground -> Midground -> Vista Hierarchy |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyuncunun oyun dünyasını anlama ve navigasyonunu sağlayan sistem: We can use a toolkit using paths, landmarks, districts, edges and nodes to make sure that our spaces are robust and can actually foster these robust cogni
- [Unreal] Oyuncunun oyun dünyasını keşfetmesini sağlayan sistem: We can use a toolkit using paths, landmarks, districts, edges and nodes to make sure that our spaces are robust and can actually foster these robust cognitive maps. 
- [Unreal] Oyuncunun oyun dünyasını navigasyonunu sağlayan sistem: We can use a toolkit using paths, landmarks, districts, edges and nodes to make sure that our spaces are robust and can actually foster these robust cognitive maps.
- [Unreal] Puzzle Box mekanik sisteminin temel tasarım amacı ve işlevi: I won't soon forget puzzles about giant water wheels, spinning rooms, massive fans and electric currents. But the dungeons have lots of issues. They're short. 

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Yeni bir bölgeye girildiğinde sessizce beliren bölge adı tipografisi + özgün bir enstrüman akoru.
- Ana nirengi noktasına yaklaştıkça gökyüzü ve partikül atmosferinin görsel yoğunluğunun artması.
- `UX Binding:` Airwalk_UI
- `UX Binding:` Puzzle_Solving_UI
- `UX Binding:` Navigation_UI

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Modüler Kopyala-Yapıştır Koridorlar:** Tüm odaları aynı duvar setiyle simetrik döndürmek oyuncunun beynindeki GPS'i felç eder.
- **Aşırı Yüksek Duvarlarla Ufku Kapatmak:** Dış mekan hissinde ufuk nirengi noktasını tamamen kesmek kaybolma hissini artırır.
- This method allows mappers to control the number of chickens spawned in their map, ensuring a consistent and realistic experience.
- The Info Director entity helps to streamline the game development process by allowing the player to easily create and place infected zombies in the map, making it easier to test and balance the game's mechanics.
- The 'Airwalk' ability provides a sense of freedom and exploration for players as they navigate through the game world.

---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Navigation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Landmark Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Vertical Level Architecture]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Environmental Storytelling]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Diegetic Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Stop_Getting_Lost_-_Make_Cognitive_Maps_Not_Levels`, `The_Legend_of_Zelda_-_Breath_of_the_Wild_s_dungeon_design_Boss_Keys`, `The_Legend_of_Zelda_-_Oracle_of_Ages_and_Seasons_dungeon_design_Boss_Keys`, `Building_Beauclair_in_The_Witcher_3_-_Wild_Hunt_-_Blood_and_Wine`, `Quick_Tip_11_CS_-GO_Source_-_Correctly_Spawn_Chickens_in_Your_Map_Like_in_CS_Italy_Tutorial`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
