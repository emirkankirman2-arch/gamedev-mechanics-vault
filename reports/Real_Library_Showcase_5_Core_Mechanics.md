---
title: "Real Library Showcase - 5 Core Mechanics"
domain: "Master Corpus Synthesis"
department: "DESIGN"
tags: [showcase, real-corpus, 4-bucket-module, master-report]
linked_systems: ["Volumetric Lighting & Darkness", "Mental Mapping", "Procedural World Generation", "Combat", "Hitstop & Freeze Frames", "Farming & Seasonal Loops", "World Building", "Shader Rim & Silhouette"]
---

# 🔥 Gerçek Kütüphane Çıktısı: 5 Kategori Master Raporu (6,774+ Video Analizi)

> Bu rapor, ana veritabanımızdaki **6,774+ gerçek video analizinden** doğrudan derlenen sistem düğümleri, motor reçeteleri ve somut oyun örneklerinden oluşur. Her kategori **%25 Teori • %25 Motor/Kod Parametresi • %25 Game Juice • %25 Anti-Pattern** dengesiyle hazırlanmıştır.

---

## 1. 🕯️ Işıklandırma & Karanlık (333+ Video Sentezi)

**Doğrulanan Korpus Kaynakları:** `10_Tips_to_Improve_your_Lighting_in_Blender_R002`, `Cinematic_Lighting_for_Artists_R002`, `10_Well-Designed_Mario_Maker_2_Levels_R002`, `3_Level_Design_Horror_Principles_to_Induce_Fear_into_Your_Environments_Game_as_Seen_in_Alan_Wake_R002`, `A_rule-discovery_puzzle_game_about_lighting_every_candle_Flicker_R002`

### 🧠 Sepet 1: Teori & Tasarım Felsefesi (%25)
- **Gölge Keskinliği ve Yarıçap Fiziği:** Küçük ışık kaynağı yarıçapı (`Source Radius`) bıçak gibi keskin tehdit gölgeleri üretirken; büyük yarıçaplı alan ışıkları yumuşak penumbra ile güvenli/bulutlu bir atmosfer yaratır.
- **3 Noktalı Aydınlatmayı Kırmak (Korku Tasarımı):** Standart `Three Point Lighting` (`Key + Fill + Rim`) içinden `Fill Light` (dolgu ışığı) kaldırılıp yerine `Negative Fill` ve `Low Key Lighting` konduğunda, silüetin yarısı karanlığa gömülür ve tehdit algısı yükselir.
- **Karanlık Kısıtlama Mekaniği:** *Five Nights at Freddy's* ilhamlı *Mario Maker 2* bölümlerindeki `darkness_theme_system` ve *Alan Wake* gece/gündüz kontrastı (`contrast_system`), ışığı sadece görsel değil oyuncunun görüş ve adım bütçesini sınırlayan bir hayatta kalma kuralına dönüştürür.

### ⚙️ Sepet 2: Motor & Kod Parametreleri (%25)
| Parametre | Önerilen Değer | Veri Tipi | Motor Uygulaması (UE5 / Unity 6 / Godot 4) |
|---|---|---|---|
| `SourceRadius` | `2.0 - 8.0 cm` (Keskin) / `80+ cm` (Yumuşak) | `Float` | `PointLightComponent` / `SpotLight` penumbra kontrolü |
| `FillLightIntensity` | `0.0 - 0.15` (Korku / Low Key) | `Float` | `Negative Fill` siyah düzlem veya düşük dolgu |
| `KeyToFillContrastRatio` | `6:1 - 12:1` | `Luminance` | *Alan Wake* güvenli odak vs karanlık bölge ayrımı |
| `CandleStepBudget` | `3 - 6 Steps / Light` | `Int32` | *Flicker* tarzı ışık-adım bulmaca kapasite mekaniği |

### ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (%25)
- `Rim Light` / `Under Lit Rim` (`FresnelPower = 4.0`) ile zifiri karanlıkta bile düşman ve kapı silüetini okunur kılma.
- Tehlike veya ışık sönmesi anında `150 ms` ışık titremesi (`Flicker Curve`) + ortam uğultusunu öne çıkaran ses miksajı.

### ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (%25)
- **Jump Scare Enflasyonu:** *Alan Wake* analizinde vurgulandığı üzere anlık ses/ışık patlamalarını (`jump_scare_system`) aşırı kullanmak oyuncuyu korkutmak yerine hissizleştirir.
- **Crushed Blacks Körlüğü:** Sahneyi `#000000` saf siyaha gömmek yön duygusunu kırar; `Implied Light Source` ve `Practical Light` odaklarıyla çıkış silüeti korunmalıdır.

**↔ Linked Systems:** [[Volumetric Lighting & Darkness]] ↔ [[Diegetic Guidance]] ↔ [[Stealth]] ↔ [[Shader Rim & Silhouette]]

---

## 2. 🗺️ Dünya Kurma & Level Design (393+ Video Sentezi)

**Doğrulanan Korpus Kaynakları:** `Stop_Getting_Lost_-_Make_Cognitive_Maps_Not_Levels_R002` (16 sistem), `Building_Worlds_in_No_Man_s_Sky_Using_Math_s_R002` & `Continuous_World_Generation_in_No_Man_s_Sky_R002` (16 sistem), `Choice_Architecture_Player_Expression_and_Narrative_Design_in_Fallout_-_New_Vegas` (18 sistem)

### 🧠 Sepet 1: Teori & Tasarım Felsefesi (%25)
- **Bilişsel Haritalar (Kevin Lynch Modeli):** Oyuncuların ekrandaki mini-harita olmadan yön bulması için dünya **5 yapısal öğeyle** kurulur: `Paths` (yollar), `Landmarks` (nirengi kuleleri), `Districts` (renk/mimari bölgeler), `Edges` (doğal sınırlar) ve `Nodes` (kesişim meydanları). Bu yapı `Egocentric` (benmerkezci rota) bilgisini `Allocentric` (kuşbakışı zihinsel harita) bilgisine çevirir.
- **Matematiksel Küresel Gezegenler (*No Man's Sky*):** Sonsuz gezegen yüzeyi tek bir noise katmanıyla değil; `Voxel Region` yoğunluk verisi üzerinden `Dual Contouring` / `Marching Cubes` poligonizasyonu + `Spherification` ile küreselleştirilir.
- **Seçim Mimarisi (*Fallout: New Vegas*):** Dallanan görevlerde (`Dialogue Trees`, `Choice Architecture`) her seçenek mutlaka `Choice Conflict`, `Sacrifice` ve `Trade-Off` üretmelidir; bedelsiz "en iyi" seçenek `Player Agency` hissini yok eder.

### ⚙️ Sepet 2: Motor & Kod Parametreleri (%25)
| Parametre | Önerilen Değer | Veri Tipi | Motor Uygulaması (UE5 / Unity 6 / Godot 4) |
|---|---|---|---|
| `UberNoiseOctaves` | `5 - 8 Octaves` | `Int32` | *No Man's Sky* katmanlı `Perlin + Ridge + Erosion` arazi sentezi |
| `DomainWarpStrength` | `0.25 - 0.45` | `Float` | Yapay ızgara görüntüsünü kıran koordinat bükme |
| `VoxelChunkResolution` | `16³ - 32³ Cells` | `Int32` | `Dual Contouring` / `Marching Cubes` + dinamik `NavMesh` |
| `DistrictHueDelta` | `>= 30 deg` | `Color LUT` | Bölge kimliklerini (`Districts`) ayıran renk/atmosfer geçişi |

### ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (%25)
- *No Man's Sky* `distance_based_fading` & `time_based_fading` sistemleriyle LOD/prop geçişlerinin göze batmadan eritilmesi.
- Yeni bir `District` sınırından (`Edges`) geçildiğinde sessiz tipografi, özgün bölge akoru ve uzak `Landmark` silüetinin sis içinden belirmesi.

### ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (%25)
- **"Oatmeal Problem" (Rastgelelik Çorbası):** `Domain Warping` ve `Erosion` katmanları olmadan ham `Perlin Noise` basmak her gezegeni/haritayı aynı tekdüze tepeciklere dönüştürür.
- **Önemsiz Seçim İllüzyonu:** *New Vegas* analizinin tersine, tüm diyalog dallarının aynı sonuca bağlanması (`No Trade-Off`) oyuncunun dünyaya olan inancını yıkar.

**↔ Linked Systems:** [[Mental Mapping]] ↔ [[Landmark Guidance]] ↔ [[Procedural World Generation]] ↔ [[World Building]] ↔ [[Quest Design]]

---

## 3. 🎯 FPS & Savaş Mekanikleri (152+ Video Sentezi)

**Doğrulanan Korpus Kaynakları:** `Animation_Bootcamp_-_The_First_Person_Animation_of_Overwatch_R002` (15 sistem), `CS_-GO_SDK_Terminal_Ballistics_Shooting_Through_Walls_Bullet_Penetration_-_Hammer_Source_Tutorial_R002`, `Godot_Game_Juice_Tutorial_1_-_Camera_Shake_and_Frame_Freeze_R002`, `Godot_Game_Juice_Tutorial_3_-_Enemies_Bullets_and_Sound_Tweaks_R002`

### 🧠 Sepet 1: Teori & Tasarım Felsefesi (%25)
- **Overwatch "Gameplay First" Birinci Şahıs Animasyonu:** Birinci şahısta kamera (`Locked-Off Camera`) oyuncu kontrolüne sadık kalırken, karakter kişiliği `Parent Spaces`, `Additive Overlays`, `Spring-Based Aims` ve yana eğilme (`Run Lean`) katmanlarıyla silah/el animasyonlarına bindirilir; görüş merkezi asla kapatılmaz.
- **CS:GO Terminal Ballistics & Duvar Delme:** Mermiler duvara çarpıp yok olmaz; `Bullet Penetration` algoritması duvar kalınlığını ve yüzey materyal yoğunluğunu (ahşap, alçıpan, beton) ölçerek kalan hasarı ve çıkış açısını hesaplar (`Wall Bang` taktik derinliği).
- **Game Juice Hissiyat Telafisi:** *Godot Game Juice* analizinde gösterildiği gibi `Bullet Spread` rastgelelik eklerken `Bullet Size` büyütülerek oyuncunun adil isabet hissi korunur.

### ⚙️ Sepet 2: Motor & Kod Parametreleri (%25)
| Parametre | Önerilen Değer | Veri Tipi | Motor Uygulaması (UE5 / Unity 6 / Godot 4) |
|---|---|---|---|
| `AdditiveSpringStiffness` | `150.0 - 220.0` | `Float` | *Overwatch* nişan/silah ikincil yay sönümleme katmanı |
| `RunLeanAngleMax` | `3.5 - 5.0 deg` | `Float` | Strafe hareketinde viewmodel yalpalama açısı |
| `PenetrationTraceStep` | `4.0 - 8.0 cm` | `Raycast` | *CS:GO* duvar çıkış noktasını bulan geri-izleme adımı |
| `MaterialPenetrationLoss` | `0.35` (Ahşap) / `0.85` (Beton) | `Float` | Yüzey materyaline göre mermi hasar zayıflatma çarpanı |
| `FrameFreezeDuration` | `0.045 - 0.080 s` | `Timer` | *Godot* `camera_shake_requested` + darbe anı donması |

### ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (%25)
- Merkezi `"camera_shake_requested"` sinyali + zamanla azalan `damping` ve `easing` eğrisi; süresi dolduğunda temiz `shake = false` sıfırlaması.
- Ateş ve vuruşlarda `Bullet Spread` + genişletilmiş `Bullet Size` + pitch-shifted ateş/mermi sekme SFX katmanları.

### ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (%25)
- **Oynanışı Sabote Eden Viewmodel Sallantısı:** Silah sallantısını veya reload animasyonunu ekran ortasına (`Locked-Off Camera` merkezine) taşıyıp nişan almayı engellemek (`Gameplay First` ihlali).
- **Tutarsız Duvar Çarpışması:** İnce ahşap kapıdan mermi geçmezken kalın köşeden hasar geçmesi oyuncuda netcode/hitbox güvensizliği doğurur.

**↔ Linked Systems:** [[Combat]] ↔ [[Hitstop & Freeze Frames]] ↔ [[Camera Trauma & Screenshake]] ↔ [[Parry & Deflect Windows]]

---

## 4. 🏡 Çiftçilik & Aidiyet Sistemleri (57+ Video Sentezi)

**Doğrulanan Korpus Kaynakları:** `A_Virtual_Place_to_Call_Home_R002`, `10_Things_I_Wish_I_Could_Do_In_Animal_Crossing_-_New_Horizons_R002` (13 sistem), `Coding_farming_drones_with_Python_The_Farmer_Was_Replaced_R002` (5 sistem)

### 🧠 Sepet 1: Teori & Tasarım Felsefesi (%25)
- **"Sanal Ev" Psikolojisi:** *A Virtual Place to Call Home* verisi, oyuncuların dünyaya bağlanması için üç direk tanımlar: tanıdık başlangıç noktası (`hub_world_system`), ev ve bahçeyi kişiselleştirme sahipliği (`home_building_system`) ve her dönüşte güven veren değişmez çapa noktası (`static_game_world_system`).
- **Animal Crossing — 13 Sistem Pazar Boşluğu:** *New Horizons* analizimizdeki 13 kullanıcı beklentisi (`crafting_system`, `design_decoration_system`, `organization_system`, `animal_system`, `entertainment_system`, `social_interaction_system`, `time_management_system` vb.), oyuncuların dekorasyon ve üretimde **toplu işlem (batching)** ve **daha derin etkileşim** istediğini ortaya koyar.
- **Algoritmik Otomasyon (*The Farmer Was Replaced*):** Tekrarlayan tarım hamallığını (`farm_system`) oyuncunun kendi yazdığı dron koduyla (`coding_system`, `python_system`, `drone_system`) otomatikleştirmek, mid-game sıkılmasını mühendislik tatminine çevirir.

### ⚙️ Sepet 2: Motor & Kod Parametreleri (%25)
| Parametre | Önerilen Değer | Veri Tipi | Motor Uygulaması (UE5 / Unity 6 / Godot 4) |
|---|---|---|---|
| `HubSafeZoneRadius` | `25 - 45 m` | `Sphere Trigger` | Savaş dışı kalıcı aidiyet ve dekorasyon ızgarası |
| `BatchCraftQueueLimit` | `10 - 99x` | `Int32` | *Animal Crossing* darboğazını çözen toplu üretim kuyruğu |
| `DroneTickFrequency` | `2.0 - 8.0 Hz` | `Fixed Timer` | *The Farmer Was Replaced* tarla dron adım değerlendirmesi |
| `PlotGridSnapSize` | `1.0 x 1.0 m` | `Vector2Int` | Ev/bahçe ve ekin yerleşim ızgarası |

### ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (%25)
- Mobilya/ekin yerleştirildiğinde elastik `Scale Bounce` tween'i, toprak/ahşap temas SFX'i ve evde akşam saatlerinde sıcak lamba parıltısı.
- Dronların tarla üzerinde hareket ederken bıraktığı ince ışık izi ve toplu hasat anında artan pentatonik toplama sesi.

### ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (%25)
- **Zorunlu Tekli Üretim Hamallığı:** Oyuncuya 50 adet yem veya duvar ürettirirken her biri için aynı 4 saniyelik animasyonu izletmek (`time_management_system` anti-pattern'i).
- **Dekorasyonların Sadece Statik Heykel Olması:** Oyuncunun kurduğu tezgah, salıncak veya kulübenin hiçbir mekanik etkileşim (`entertainment_system`) sunmaması.

**↔ Linked Systems:** [[Farming & Seasonal Loops]] ↔ [[Economy]] ↔ [[Crafting]] ↔ [[Progression]] ↔ [[Social Systems]]

---

## 5. 🍃 Mevsim Döngüsü & Doğa (57+ Video Sentezi)

**Doğrulanan Korpus Kaynakları:** `The_Legend_of_Zelda_-_Oracle_of_Ages_and_Seasons_dungeon_design_Boss_Keys_R002` (16 sistem), `Crazy_but_not_too_crazy_Game_Weather_R002` (15 sistem), `Interactive_Wind_and_Vegetation_in_God_of_War_R002` (**49 alt sistem**)

### 🧠 Sepet 1: Teori & Tasarım Felsefesi (%25)
- **Mevsim Değişimiyle Bulmaca (*Zelda: Oracle of Seasons*):** `Seasonal Switch` yalnızca görsel renk paletini değiştirmez; dünya geometrisini ve `Dungeon Design` kilitlerini yeniden yazar (Kış: göller donar ve yürünebilir köprü olur; Sonbahar: dökülen yapraklar çukurları doldurur; Yaz: sarmaşıklar kuruyup geçit açar).
- **Hava Durumunun 6 Mekanik Rolü:** *Game Weather* analizine göre hava sistemi şu 6 rolden en az birini oynamalıdır: `Difficulty Modifier`, `Story Element`, `Timer`, `Boundary`, `Environmental Property` ve `Mood Setter`.
- **God of War 49 Alt Sistemli Rüzgar/Bitki Mimarisi:** Doğanın canlı hissettirmesi için `Wind Motors` (`Wake`, `Vortex`, `Omni`, `Directive`), `Beaufort Scale` şiddet katmanları ve `Flow Map` vektörleri bitki örtüsüyle çift yönlü etkileşime girer.

### ⚙️ Sepet 2: Motor & Kod Parametreleri (%25)
| Parametre | Önerilen Değer | Veri Tipi | Motor Uygulaması (UE5 / Unity 6 / Godot 4) |
|---|---|---|---|
| `WindVolumeBeaufort` | `0 - 12 Scale (0..100%)` | `Float` | `Wind Volume` bölgesel rüzgar şiddeti çarpanı |
| `BendParameterMax` | `0.15 - 0.85 rad` | `WPO Shader Scalar` | `Pivot System` tabanlı vertex bükme genliği |
| `CosineFalloffExponent` | `1.8 - 2.5` | `Shader Float` | Kökten uca bükülme eğrisi + `Overshooting Animation` yaylanması |
| `DivergingNeighborPhase` | `0.25 - 0.60 rad` | `Per-Instance Float` | Komşu çim/yaprakların senkronize robot gibi sallanmasını bozar |
| `WeatherTransitionTimer` | `6.0 - 12.0 s` | `CurveFloat` | *Oracle of Seasons* / dinamik hava durumu `State Machine` geçişi |

### ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (%25)
- `Height Field Texture` ve `Ground Vegetation Collisions` ile Kratos/karakter geçerken çimlerin sağa sola yatması ve karda iz kalması.
- `Overshooting Animation` sayesinde ani rüzgar darbesi kesildiğinde dalların gerçek yay fiziğiyle geri salınması ve yaprak hışırtısı SFX katmanlarının `Beaufort Scale` ile senkronize açılması.

### ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (%25)
- **Senkronize "Asker Çimler":** `Diverging Neighbors` faz kaydırması ve `Fractal Noise` olmadan tüm bitkileri tek bir `sin(Time)` dalgasıyla sallamak plastik görünüm üretir.
- **Dekoratif Hava Durumu:** Görüşü kör eden ama oynanışa (`Difficulty Modifier` / `Environmental Property` — örn. yağmurun ateşi söndürmesi veya sesi bastırması) hiçbir etkisi olmayan rastgele fırtınalar oyuncuyu sadece yorar.

**↔ Linked Systems:** [[World Building]] ↔ [[Environmental Storytelling]] ↔ [[Puzzle Design]] ↔ [[Shader Rim & Silhouette]]

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
