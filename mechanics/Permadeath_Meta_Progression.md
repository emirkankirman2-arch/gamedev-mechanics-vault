---
title: "Permadeath & Meta-Progression"
domain: "Progression"
department: "DESIGN"
bundle: "Bundle_4"
ku_count: 186
tags: [progression, design, bundle_4, 4-bucket-module]
linked_systems: ["Progression", "Risk & Reward", "Reward Systems", "Difficulty Design", "Procedural World Generation"]
---

# Permadeath & Meta-Progression

> **Domain:** [[Progression]] | **Department:** `DESIGN` | **Evidence Units:** `186`  
> **Linked Systems:** [[Progression]], [[Risk & Reward]], [[Reward Systems]], [[Difficulty Design]], [[Procedural World Generation]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

**Kalıcı Ölüm (Permadeath)** tek başına acımasız ve bezdirici olabilir; ancak **Meta-Progression (Kalıcı İlerleme)** ile birleştiğinde her başarısız deneme (run) oyuncuya kalıcı bir bilgi, yeni bir mekanik kilidi veya miras (altın/yetenek açılımı) bırakır. Böylece ölüm 'zaman kaybı' değil, 'bir sonraki daha güçlü koşunun yakıtı' haline gelir.

**Kütüphane Kanıtları (Corpus Insights):**
- Rogue Legacy'de ölüm kalıcıdır ve birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.
- Spelunky ve klasik rogue-like oyunlarında permadeath kuralı geçerlidir; ölüm anında tüm eşyalar sıfırlanır ve harita baştan üretilir.
- Oyun, bir oyuncunun ölümünden sonra, yeni bir karakter seçerek oyunu yeniden başlatma seçeneği sunar.
- Tomb Raider'da ölüm kalıcıdır ve ölüm anında tüm eşyalar sıfırlanır.
- Rogue Legacy'de ölüm kalıcıdır, ancak birikmiş altın miras yoluyla yeni seçilen varisin yeteneklerini geliştirmek için aktarılır.

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity / Godot:** Oyun kaydını iki ayrı objeye bölün: `RunSessionState` (ölümde sıfırlanan geçici envanter/harita/buff'lar) ve `PersistentMetaProfile` (diskte JSON/SaveGame olarak saklanan açılmış silahlar, NPC diyalogları ve kalıcı pasifler).

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `RunDurationTarget` | `20 - 40 min Complete Run` | `Float` | Short enough to invite 'one more run' |
| `MetaCurrencyRetention` | `15 - 30 % Kept on Death` | `Float` | Prevents runaway grinding while softening loss |
| `FirstRunUnlockMilestone` | `First 5-10 min` | `Trigger` | Guarantees player unlocks 1 permanent thing after first death |
| `SynergyTagPoolSize` | `3 - 5 Build Archetypes` | `Int32` | Ensures run-to-run tactical variety |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyuncunun seviye ilerlemesini ve geçici envanterini sıfırlayan sistem: unique and challenging, but without making you feel like the game is unwinnable at any point. This is helped by the crystal clear UI and the ability 
- [Unreal] Oyuncunun seviye ilerlemesini ve geçici envanterini sıfırlayan temel roguelike cezalandırma döngüsü: It wasn't all bad though, some very clever people came up with a COVID-19 vaccine, Sandworms the movie was way better t
- [Unreal] Oyun, bir oyuncunun ölümünden sonra, yeni bir karakter seçerek oyunu yeniden başlatma seçeneği sunar: Tutorials are tricky. They're a real sticking point in game design because there's just so many pitfalls that come out
- [Unreal] Oyun, bir oyuncunun ölümünden sonra, yeni bir karakter seçerek oyunu yeniden başlatma seçeneği sunar: which is brilliant, but only after you've put 20 hours into it to figure out what the hell everything you were just to

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Ölüm ekranında başarısızlık vurgusu yerine 'Bu Koşudan Kazanılan İlerleme & Açılan Sırlar' animasyonlu sayacı.
- Hub (üs) bölgesine dönüşte NPC'lerin son koşunuza özel tepki diyalogları.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Sadece İstatistik Şişiren Meta-Progression:** Başlangıçta yenilemeyen bir boss tasarlayıp '10 kere öl, %200 can satın alınca kesersin' demek taktiksel beceriyi öldürür; meta ilerleme ağırlıklı olarak **yatay seçenek (yeni sinerjiler/silahlar)** açmalıdır.
- **Uzun Ölüm-Yeniden Başlama Beklemesi:** Ölüm ekranından yeni koşuya geçiş `1.5 saniyeyi` geçmemelidir.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Progression]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Risk & Reward]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Reward Systems]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Difficulty Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Procedural World Generation]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `20_18_Games_You_Should_Have_Played`, `20_21_Games_You_Should_Have_Played`, `6_Lessons_from_Hollow_Knight_s_immersive_tutorial`, `A_puzzle_game_where_your_tools_are_completely_random`, `Analysing_Mario_to_Master_Super_Mario_Maker`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
