---
title: "Behavior Trees & Utility AI"
domain: "Enemy AI"
department: "GAME_AI"
bundle: "Bundle_4"
ku_count: 12
tags: [enemy_ai, game_ai, bundle_4, 4-bucket-module]
linked_systems: ["Enemy AI", "Stealth", "Boss Design", "Combat"]
---

# Behavior Trees & Utility AI

> **Domain:** [[Enemy AI]] | **Department:** `GAME_AI` | **Evidence Units:** `12`  
> **Linked Systems:** [[Enemy AI]], [[Stealth]], [[Boss Design]], [[Combat]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Behavior Tree (Davranış Ağacı)** deterministik durum akışında (Devriye -> Şüphe -> Saldırı) mükemmeldir; **Utility AI** ise düşmanın aynı anda birden fazla seçeneği (`Mesafe`, `Can`, `Mühimmat`, `Takım Arkadaşı Sayısı`) 0..1 arası skorlayıp en doğal tepkiyi seçmesini sağlar. İkisini birleştiren **Hybrid BT + Utility AI**, hem tasarımcı kontrolünü korur hem de yapay zekayı robotik kalıplardan kurtarır.

**Kütüphane Kanıtları (Corpus Insights):**
- Küresel adayın davranışını kontrol etmek için Behavior Trees, State Machines, Decision Trees, Utility Systems, Neural Networks, Machine Learning, Hierarchical Finite State Machine, Hybrid Behavior Trees, Decorator Patterns, Message Passing, Unit Subtasks, Damon Behaviors, Managers, Scouting Manager, Tactics Manager, Strategy Manager, Income Manager, Construction Manager, Reconnaissance Manager, Joint Goals and Behaviors, Meta-Behaviors, Partial Programming kullanılmaktadır.
- Küresel Aday Sistemleri: Behavior Trees, State Machines, Decision Trees, Utility Systems, Neural Networks, Machine Learning, Hierarchical Finite State Machine, Hybrid Behavior Trees, Decorator Patterns, Message Passing, Unit Subtasks, Damon Behaviors, Managers, Scouting Manager, Tactics Manager, Strategy Manager, Income Manager, Construction Manager, Reconnaissance Manager, Joint Goals and Behaviors, Meta-Behaviors, Partial Programming.
- Küresel adayın sistemleri, davranışları ve kararları için çeşitli mekaniklerin kullanılması gerektiği.
- The game features a squad coordination system.
- The game features a squad coordination system, front line calculation, flanking mechanic, enemy flanking, defense zones, home areas, fortification zones, kill zones, confidence system, ghost system, environmental analysis, level design, AI behavior trees, squad movement, enemy movement, combat mechanics, cover system, reload animation, and flanking animation.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`UBehaviorTreeComponent` + `UBlackboardComponent` + `UAIPerceptionComponent`):** Görüş ve ses algısını `AIPerception` ile `Blackboard`'a yazın; aynı anda en fazla 2 düşmanın saldırması için `AGameStateBase` içinde `UAICombatTokenSubsystem` (Reserve/Release Token) kurun.
- **Unity 6 (`NavMeshAgent` + `ScriptableObject` Utility Scorers):** Her aksiyonu `Evaluate(AIContext)` döndüren bir `UtilityAction` varlığı olarak tanımlayın.
- **Godot 4 (`NavigationAgent3D` + `StateChart`):** `RayCast3D` line-of-sight kontrollerini her frame değil `Timer(0.15s)` ile sıraya dizin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `AIUpdateTickInterval` | `0.10 - 0.25 s (4-10 Hz)` | `Float` | Staggered AI ticks save massive CPU budget |
| `AttackTokenPoolMax` | `1 - 2 Active Attackers` | `Int32` | Prevents unfair 5v1 simultaneous hits |
| `SightConeHalfAngle` | `45 - 60 deg` | `Float` | Peripheral vs focused detection zones |
| `AlertMemoryDuration` | `6.0 - 12.0 s` | `Float` | Time before returning from Search to Patrol |
| `UtilityScoreHysteresis` | `+0.15 Bonus to Current` | `Float` | Prevents rapid action flip-flopping |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Durum makineleri, olay/delegasyon akışı ve çalışma mantığı
- [Unreal] Squad Coordination: Hi, my name is Tobias Carlson and I'm an AI programmer at Sony Ben Studio. And today I'm going to talk about scored coordination in Days Gone with a focus on combat. First of all, what is Days Gone? W
- [Unreal] Front Line Calculation: Hi, my name is Tobias Carlson and I'm an AI programmer at Sony Ben Studio. And today I'm going to talk about scored coordination in Days Gone with a focus on combat. First of all, what is Days Gon
- [Unreal] Flanking Mechanic: Hi, my name is Tobias Carlson and I'm an AI programmer at Sony Ben Studio. And today I'm going to talk about scored coordination in Days Gone with a focus on combat. First of all, what is Days Gone? We

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Düşman durum değiştirdiğinde sesli uyaran ('Ses duydum!' barks / metalik kask tıkırtısı) ve baş çevirme IK bakışı.
- Saldırı token'ı alan düşmanın silahında/gözünde `0.4s` önceden parlayan saldırı belirtisi (telegraph glow).


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Arka Plandan Hileli Bilgi (Omniscient AI):** Oyuncu ses çıkarmadan gizlice pozisyon değiştirdiğinde düşmanın duvar arkasından tam konumuna yürümesi oyuncunun gizlilik sistemine olan güvenini yok eder; düşman mutlaka **Son Bilinen Konuma (Last Known Position)** gitmelidir.
- **Hysteresis Eksikliği:** İki Utility skoru `0.51` ve `0.50` iken düşmanın her karede siper ile hücum arasında titremesi.
- **Token Havuzu Olmaması:** 6 düşmanın aynı karede senkronize saldırıp oyuncuyu tek vuruşta silmesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Enemy AI]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Stealth]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Boss Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `AI_Arborist_-_Proper_Cultivation_and_Care_for_Your_Behavior_Trees`, `Squad_Coordination_in_Days_Gone`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [Itch.io Supporter Pack](https://emirkankirman2353.itch.io/game-mechanics-systems-vault-ue5-unity-6-godot-4-aimcp) üzerinden indirerek bu 7/24 büyüyen yaşayan kütüphaneye destek olabilirsiniz!
