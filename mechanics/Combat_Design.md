---
title: "Combat Design"
domain: "Combat"
department: "DESIGN"
bundle: "Bundle_2"
ku_count: 19
tags: [combat, design, bundle_2, 4-bucket-module]
linked_systems: ["Combat", "Player Agency", "Level Design"]
---

# Combat Design

> **Domain:** [[Combat]] | **Department:** `DESIGN` | **Evidence Units:** `19`  
> **Linked Systems:** [[Combat]], [[Player Agency]], [[Level Design]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Oyuncuların algısını etkilemek için kullanılan sistem.

**Kütüphane Kanıtları (Corpus Insights):**
- Win Streak Mekanizması — job with their ranked system in Hearthstone with a couple of tricks to do that. We're first off, if there's the win streak mechanic, so if you win a couple of games in a row, you get bonus stars. And
- Slot Machine — he would do it at twenty five dollars is that correct like yes twenty five dollars against my twenty dollars he would take that bet and that gets to the to really the the base illustration of a concep
- The game features a global system that allows players to repeat actions, create opportunities, use props, tools, and accidents to learn and gain knowledge, and engage in scheming and silent assassin gameplay.
- Cuphead, Contra 3, Gunstar Heroes ve Super Meat Boy oyunlarından ilham alan küresel aday sistemleri
- Küresel aday sistemleri, bağımsız oyunların özelliklerini bir araya getirir

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 / Unity 6 / Godot 4:** `Combat_Design` davranışını bağımsız bir bileşen (`ActorComponent` / `MonoBehaviour` / `Node`) olarak kapsülleyin ve durum geçişlerini veri odaklı (`DataAsset`/`Resource`) yönetin.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `ActivationThreshold` | `0.10 - 0.25 s` | `Float` | Input or state trigger window for Combat Design |
| `CooldownOrRecovery` | `0.25 - 0.80 s` | `Float` | Prevents state spam & preserves cadence |
| `SystemPriority` | `1 - 3 Tier` | `Int32` | Resolves overlapping action states |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Oyuncuların algısını etkilemek: job with their ranked system in Hearthstone with a couple of tricks to do that. We're first off, if there's the win streak mechanic, so if you win a couple of games in a row, you get bonus
- [Unreal] Win Streak Mekanizması: job with their ranked system in Hearthstone with a couple of tricks to do that. We're first off, if there's the win streak mechanic, so if you win a couple of games in a row, you get bonus stars. 
- [Unreal] Oyuncuların algısını etkilemek: he would do it at twenty five dollars is that correct like yes twenty five dollars against my twenty dollars he would take that bet and that gets to the to really the the base illustration
- [Unreal] Slot Machine: he would do it at twenty five dollars is that correct like yes twenty five dollars against my twenty dollars he would take that bet and that gets to the to really the the base illustration of a concept call

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- **Combat Design** tetiklendiğinde görsel onay (parıltı/partikül) ve dinamik ses katmanı ekleyin.
- Oyuncu girdisinin sonucunu `<= 50 ms` içinde animasyon veya kamera tepkisiyle doğrulayın.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Combat Design İzolasyonu:** Bu mekaniği oyunun geri kalan ekonomisi veya risk-ödül döngüsüyle ilişkilendirmemek.
- **Geri Bildirim Eksikliği:** Mekanik arka planda çalışsa bile oyuncunun sonucu net görememesi.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Player Agency]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Level Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Board_Game_Design_Day_-_Board_Game_Design_and_the_Psychology_of_Loss_Aversion`, `Hitman_and_the_Art_of_Repetition`, `How_Cuphead_s_Bosses_Try_to_Kill_You`, `The_4_Ps_of_DOOM_s_Amazing_Combat`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
