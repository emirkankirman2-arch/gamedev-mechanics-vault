---
title: "Virtual Home & Belonging Hubs"
aliases: ["Virtual Home & Belonging Hubs"]
domain: "World Building"
department: "WORLD_DEVELOPMENT"
bundle: "Bundle_4"
ku_count: 18
tags: [world_building, world_development, bundle_4, 4-bucket-module]
linked_systems: ["Farming & Seasonal Loops", "Automated Drone Farming & Batch Crafting", "World Building", "Crafting", "Social Systems"]
---

# Virtual Home & Belonging Hubs

> **Domain:** [[World_Building|World Building]] | **Department:** `WORLD_DEVELOPMENT` | **Evidence Units:** `18`  
> **Linked Systems:** [[Farming_Seasonal_Loops|Farming & Seasonal Loops]], [[Automated_Drone_Farming_Batch_Crafting|Automated Drone Farming & Batch Crafting]], [[World_Building|World Building]], [[Crafting]], [[Social_Systems|Social Systems]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

*A Virtual Place to Call Home* ve *Animal Crossing: New Horizons* analizlerinden çıkarılan üç temel sütun: tanıdık bir **Hub Dünyası (`hub_world_system`)**, ev/bahçe kişiselleştirme sahipliği (`home_building_system`) ve her geri dönüşte güvenli çapa sunan **Statik Referans Noktası (`static_game_world_system`)**. Dış dünya kaotik veya tehlikeli olsa bile değişmeyen bu ev çekirdeği uzun vadeli duygusal bağ (attachment) üretir.

**Kütüphane Kanıtları (Corpus Insights):**
- of direction to the player in order to avoid choice paralysis. But when that direction is kept purposefully vague while also leaning on lore and world building, that can lead to a situation where the game is inadvertently
- World Building dünya tasarımı için bir kontrol aracıdır.
- Prag'da, oyuncuların şehri keşfetmesine izin veren bir açık dünya tasarımı vardır.
- Oyunun dünyası, oyuncuların keşfetmelerine ve farklı bölgeleri keşfetmelerine olanak tanır.
- Oyun, dünya tasarımlarını kullanır ve oyuncunun yeteneklerini ve düşmanların zayıflıklarını etkiler.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** `UWorldPartitionRuntimeCell` + `USaveGame` içinde `FHomePlotGridRecord` (TileID, ItemID, YawSteps) saklayın; `HubSafeZoneVolume` içine girildiğinde `AbilitySystemComponent`'e `State.InSafeHub` tag'i ekleyin.
- **Unity 6:** `Grid` + `Tilemap` / `Dictionary<Vector2Int, PlacedPropData>` üzerinden JSON/ScriptableObject kaydı tutun.
- **Godot 4:** `GridMap` + `VaultParameterProfile` kullanarak mobilya ve bahçe parsellerini tek veri yapısında kaydedin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `HubSafeZoneRadius` | `25.0 - 45.0 m` | `Float (Sphere Trigger)` | Disables combat AI & enables cozy building tools |
| `HomePlotGridSnapSize` | `1.0 x 1.0 m` | `Vector2Int` | Deterministic furniture & garden tile placement grid |
| `DecorationRotationStep` | `45.0 deg (8-Way)` | `Float` | Clean alignment with quick micro-nudge option |
| `StaticAnchorResetGuarantee` | `100% Persistent` | `Save Flag` | Hub core layout never resets across runs/seasons |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Event delegate: Player -> World -> WorldBuilding
- [Unreal] World Building sistemini kontrol etmek için state machine ve event/delegate akışı
- [Unreal] Oyuncuların keşfetmelerine ve farklı bölgeleri keşfetmelerine olanak tanıyan dünya tasarımı: interesting to them and then get to their mission. We just want the people, the player to walk into the city and always have so
- [Unreal] Oyuncunun yeteneklerini ve düşmanların zayıflıklarını etkileyen bir event/delegate akışı

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Mobilya veya bitki yerleştirildiğinde `0.18 s` elastik `BackOut` scale bounce tween'i ve toz puff VFX.
- Akşam saatlerinde (`TimeOfDay > 18:30`) ev pencerelerinden sıcak `#FFAE42` iç mekan ışığı sızması ve tanıdık hub enstrüman motifi.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Dekoratif Ölü Eşyalar:** *Animal Crossing* 13 sistem analizinde tespit edildiği üzere oyuncunun kurduğu tezgah, salıncak veya sobanın hiçbir etkileşim (`entertainment_system` / `crafting_system`) sunmaması sahiplik hissini zayıflatır.
- **Ev İçinde Kısıtlı Depolama Sürtünmesi:** Oyuncuyu güvenli üssünde envanter taşıma hamallığına zorlamak.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Farming_Seasonal_Loops|Farming & Seasonal Loops]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Automated_Drone_Farming_Batch_Crafting|Automated Drone Farming & Batch Crafting]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[World_Building|World Building]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Crafting]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Social_Systems|Social Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] Aer： Memories of Old - the game with the BEST flight mechanics`, `[OLD] Leitmotifs as Mechanics in Ocarina of Time ｜ Designer's Notebook`, `Deus_Ex_-_Mankind_Divided_s_Amazing_Open_World`, `What_s_The_Point_of_Elements_in_Games`, `How_Level_Design_Can_Tell_a_Story`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
