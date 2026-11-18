---
title: "Camera Trauma & Screenshake"
domain: "Camera & Player Perspective"
department: "CINEMATICS"
bundle: "Bundle_3"
ku_count: 44
tags: [camera_player_perspective, cinematics, bundle_3, 4-bucket-module]
linked_systems: ["Camera & Player Perspective", "Hitstop & Freeze Frames", "Combat", "Volumetric Lighting & Darkness", "Parry & Deflect Windows"]
---

# Camera Trauma & Screenshake

> **Domain:** [[Camera & Player Perspective]] | **Department:** `CINEMATICS` | **Evidence Units:** `44`  
> **Linked Systems:** [[Camera & Player Perspective]], [[Hitstop & Freeze Frames]], [[Combat]], [[Volumetric Lighting & Darkness]], [[Parry & Deflect Windows]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Doğrusal (lineer) rastgele kamera titremesi yapay ve mide bulandırıcıdır. Endüstri standardı **Trauma-Based Shake** modelinde kamera sarsıntısı `[0.0 .. 1.0]` arası bir `Trauma` skaler değerinde birikir; gerçek sarsıntı şiddeti ise **`Shake = Trauma²` (veya `Trauma³`)** formülüyle hesaplanır ve **Perlin Noise** üzerinden rotasyon (Pitch/Yaw/Roll) olarak uygulanır.

**Kütüphane Kanıtları (Corpus Insights):**
- Oyunun dünya seviyesi mimarisi, karakterin hareketi ve kontrol panelinin yer alması ile ilgilidir.
- Oyunun duyusal deneyimi, karakterin hareketi ve kontrol panelinin yer alması ile ilgilidir.
- We can structure the life of a mechanic in 3 steps, input, action and feedback. Input entails in itself the conditions that have to be met, be it players pressing a button or something happening within other
- Oyunun insan zekası modeli, kognitif modeli, oyun hissi, mekanik tasarımı, geri bildirim, girişim işleme, karar verme, kullanılabilirlik, ürün değerlendirme, kognitif işleme zamanları, motor işleme zamanları, oyuncuların oyun durumunu işleme ortalama zamanları, tanılama zamanı, işleme zamanı, karar verme zamanı, sinyal gönderme zamanı, hareket zamanı, parmağı hareket zamanı, düğme basma zamanı
- Rapid Prototyping — and the idea that we could solve these problems by changing the class format comes from the spirit of rapid prototyping and jamming that has been prevalent in the indie game's community. And of course

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`UCameraShakeBase` / `UPerlinNoiseCameraShakePattern`):** Sabit `FVector` rastgeleliği yerine Perlin Noise pattern kullanın; mesafe bazlı sönümleme (`InnerRadius = 300`, `OuterRadius = 1800`) ile uzaktaki patlamaların oyuncuyu kör etmesini önleyin.
- **Unity 6 (`CinemachineImpulseSource`):** `Trauma = Mathf.Clamp01(Trauma - decay * Time.deltaTime)` sonrası `float shake = Trauma * Trauma;` değerini kamera pivotunun lokal rotasyonuna `Mathf.PerlinNoise` ile uygulayın.
- **Godot 4 (`Camera3D` / `Camera2D`):** `FastNoiseLite` kullanarak `h_offset`, `v_offset` ve `rotation.z` değerlerini `trauma ** 2` ile çarpın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `TraumaExponent` | `2.0 - 3.0` | `Power Exponent` | ShakeIntensity = pow(Trauma, 2) |
| `TraumaDecayRate` | `1.4 - 2.2 / sec` | `Float` | Linear drain per second |
| `MaxRotationalShake` | `Pitch/Yaw 2.5 deg, Roll 4.0 deg` | `Vector3` | Prefer angular shake over translation |
| `PerlinNoiseFrequency` | `18 - 28 Hz` | `Float` | Smooth organic oscillation vs harsh random |
| `SpringArmLagSpeed` | `10.0 - 16.0` | `Float` | Camera follow damping on sprint/dash |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Karakter hareketine geri bildirim sağlar: We can structure the life of a mechanic in 3 steps, input, action and feedback. Input entails in itself the conditions that have to be met, be it players pressing a button or som
- [Unreal] Oyuncuların oyun içi davranışlarını simüle etmek için insan zekası modelini kullanmak
- [Unreal] Oyuncuların oyun içi davranışlarını modellemek için kognitif modeli kullanmak
- [Unreal] Oyuncuların oyun içi davranışlarını hissettirmek için oyun hissi modelini kullanmak

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Yönlü darbe sarsıntısı: Kamera rastgele değil, darbenin geldiği yöne doğru ilk `1 frame` itilir, sonra sönümlenir.
- Yüksek trauma anlarında kenarlarda `Vignette` kararması ve düşük frekanslı sub-bass rumble SFX.
- Sprint veya dash sırasında FOV'u `+6..+10 deg` açıp bitişte geri çekmek.
- `UX Binding:` PuzzleScreen
- `UX Binding:` HintButton
- `UX Binding:` GameScreen
- `UX Binding:` PointerCursor

---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Erişilebilirlik (Accessibility) Kapatma Ayarı Eksikliği:** `Screen Shake Intensity (0% - 100%)` ayarı sunmamak hareket hastalığına (motion sickness) yol açar.
- **Sürekli Pozisyon Zıplatma:** Rotasyon yerine kamerayı X/Y ekseninde büyük piksellerle kaydırmak UI ve nişangah hizasını bozar.
- **UI Elemanlarını Titretmek:** Dünya kamerası titrerken nişangah ve can barını sabit veya ayrı katmanda tutmamak okunabilirliği yok eder.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Camera & Player Perspective]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Hitstop & Freeze Frames]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Volumetric Lighting & Darkness]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Parry & Deflect Windows]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `[OLD] 2.3. Defining Feedback ｜ Farlands School of Game Design`, `[OLD] 2.4. The Human Processor Model ｜ Farlands School of Game Design`, `Game_a_Week_-_Teaching_Students_to_Prototype`, `How_Games_Convey_Pain_-_Exploring_Life_Bars_and_Feedback_~_Design_Doc`, `Point_and_Click_Puzzle_Design`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
