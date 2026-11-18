---
title: "Hitstop & Freeze Frames"
domain: "Combat"
department: "ANIMATION"
bundle: "Bundle_3"
ku_count: 142
tags: [combat, animation, bundle_3, 4-bucket-module]
linked_systems: ["Combat", "Camera Trauma & Screenshake", "Parry & Deflect Windows", "Adaptive Audio & Stems"]
---

# Hitstop & Freeze Frames

> **Domain:** [[Combat]] | **Department:** `ANIMATION` | **Evidence Units:** `142`  
> **Linked Systems:** [[Combat]], [[Camera Trauma & Screenshake]], [[Parry & Deflect Windows]], [[Adaptive Audio & Stems]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Hitstop (Hit-Freeze)**, bir darbenin fiziksel ağırlığını ve enerjisini oyuncunun beynine iletmek için saldıran ve darbe alan aktörlerin animasyon/hareket saatini birkaç kareliğine dondurma tekniğidir. Zamanı dondurmak beynin darbe karesini net okumasını sağlar; vuruş gücünü görsel efekt tek başına değil, zamansal kontrast üretir.

**Kütüphane Kanıtları (Corpus Insights):**
- Hitstop, oyuncunun hareketini durdurur ve kontrolünü sağlar.
- Pause Game for Instant Feedback, oyuncuya anlık geri bildirim sunan bir sistemdir.
- Flash White, oyuncunun dikkatini çekmek için kullanılan bir efekt mekanizmasıdır.
- Get Knocked Back, oyuncunun hareketini etkileyen bir mekanizmadır.
- Spray Blood, oyuncunun hareketini etkileyen bir mekanizmadır.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5:** Tüm dünyayı dondurmak yerine `Attacker->CustomTimeDilation = 0.02f` ve `Victim->CustomTimeDilation = 0.02f` ayarlayın; `FTimerHandle` (gerçek zamanlı `RealTime` bayrağıyla) süresi dolunca `1.0f` değerine döndürün. Kamera ve VFX gerçek zamanda akmaya devam etmelidir!
- **Unity 6:** `Animator.speed = 0f` + hitstop coroutine (`WaitForSecondsRealtime(0.065f)`), `Time.timeScale` değiştirmeyin ki ses ve partiküller donmasın (sadece kritik ölümde `timeScale = 0.15f`).
- **Godot 4:** `Engine.time_scale` yerine saldırgan ve kurbanın `AnimationPlayer.speed_scale = 0.0` + `get_tree().create_timer(0.07, true, false, true)` kullanın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `LightHitstopDuration` | `0.033 - 0.050 s (2-3 frame)` | `Float` | Global or per-actor CustomTimeDilation = 0.01 |
| `HeavyHitstopDuration` | `0.080 - 0.130 s (5-8 frame)` | `Float` | Crit / Finisher / Heavy weapon impact |
| `VictimJitterAmplitude` | `2.0 - 5.0 cm` | `Vector Offset Curve` | High-frequency sine shake on frozen victim mesh |
| `TimeDilationCurve` | `0.01 -> 1.0 EaseOut` | `UCurveFloat / AnimationCurve` | Smooth exit avoids jarring resume snap |
| `CameraFOVPunch` | `-3.5 deg for 0.09 s` | `Float Curve` | Subtle micro-zoom inward on heavy impact |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Hitstop, oyuncunun hareketini durdurur ve kontrolünü sağlar: intensity and also the direction. In Celeste, the camera wobbles in the same direction as Madeline's dash to really sell the speed and power of her special mov

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Hitstop anında hedefin materyalinde `1-2 frame` saf beyaz/emissive `HitFlash` (Material Parameter Collection).
- Hitstop süresi boyunca kurbanı vurma vektörüne dik eksende `28 Hz` mikro titreşim (jitter).
- Donma bittiği karede keskin bir 'crack/snap' alt-bas SFX ve kıvılcım/kan yönlü partikül fırlatması.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Multiplayer'da Global `Time.timeScale = 0`:** Ağ oyunlarında tüm zamanı dondurmak diğer oyuncuların akışını bozar; yalnızca yerel animasyon/kamera mikro-dondurması kullanın.
- **Aşırı Uzun Hitstop (>180 ms):** Seri hafif saldırılarda uzun donma oyuncuya 'FPS düştü / oyun takıldı' hissi verir.
- **Kamerayı ve VFX'i Dondurmak:** Hitstop sırasında kıvılcımlar ve kamera sarsıntısı akmaya devam etmezse darbe canlılığını kaybeder.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Camera Trauma & Screenshake]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Parry & Deflect Windows]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Adaptive Audio & Stems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `How_to_Make_a_Good_2D_Camera`, `Secrets_of_Game_Feel_and_Juice`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
