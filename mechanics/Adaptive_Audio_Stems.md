---
title: "Adaptive Audio & Stems"
domain: "Audio & Sensory UX"
department: "AUDIO"
bundle: "Bundle_3"
ku_count: 60
tags: [audio_sensory_ux, audio, bundle_3, 4-bucket-module]
linked_systems: ["Combat", "Stealth", "Boss Design", "Hitstop & Freeze Frames", "Diegetic Guidance"]
---

# Adaptive Audio & Stems

> **Domain:** [[Audio & Sensory UX]] | **Department:** `AUDIO` | **Evidence Units:** `60`  
> **Linked Systems:** [[Combat]], [[Stealth]], [[Boss Design]], [[Hitstop & Freeze Frames]], [[Diegetic Guidance]]

---

## 🧠 Sepet 1: Teori & Tasarım Felsefesi (Design Theory & Heuristics)

Dinamik müzik ve ses tasarımı yalnızca arka plan atmosferi değil, oyuncuya doğrudan **durumsal geri bildirim (State Feedback)** verir. **Vertical Remixing (Katmanlı Stem Karışımı)** ile tehlike arttıkça perküsyon ve bas katmanları açılır; **Ducking / Sidechain** ile ise kritik saldırı uyarıları (parry cue) anında ortam müziği `3-6 dB` kısılır.

**Kütüphane Kanıtları (Corpus Insights):**
- SEG_02'de interaktif ses, oyuncunun eylemlerine göre soundtrack değişkenliği tartışılmaktadır.
- SEG_02'de bağlamsal soundtrack, oyuncunun durumuna göre soundtrack değişkenliği tartışılmaktadır.
- Oyun, oyuncunun hareketlerini ve eylemlerini gerçek zamanlı olarak takip eder ve buna göre ses efektlerini adapte eder.
- Oyun, oyuncunun eylemlerine göre ses efektlerini değiştirir ve oyuncuya daha gerçekçi bir deneyim sunar.
- a crazy ward drum soundtrack booming from the sky. So game makers should be free to experiment with audio without sacrificing the authenticity of their murder simulators and they can make adaptive soundtracks a bit more

---

## ⚙️ Sepet 2: Motor & Kod Mimarisi (Engine & Code — UE5 / Unity 6 / Godot 4)

- **UE5 (`UMetaSoundSource` + `AudioModulation`):** `ThreatLevel (0..1)` parametresini MetaSound graph içindeki `Crossfade` düğümüne bağlayın.
- **Unity 6 (`AudioMixer` Snapshots):** `Explore`, `Stealth_Tense`, `Combat_High` snapshot'larını `TransitionTo(1.5f)` ile tetikleyin.
- **Godot 4 (`AudioStreamSynchronized`):** Birden fazla ritim-senkron stem'i tek akışta çalıştırıp `set_sync_stream_volume` ile karıştırın.

**Somut Motor Parametre Tablosu:**

| Parametre | Önerilen Değer | Veri Tipi | Uygulama Notu |
|---|---|---|---|
| `StemCrossfadeTime` | `1.2 - 2.5 s (Beat-Synced)` | `Float` | Bar/beat quantized transition avoids abrupt cuts |
| `CombatDuckingGain` | `-4.5 dB for 0.25 s` | `Audio Bus` | Prioritizes critical parry/telegraph SFX |
| `PitchRandomization` | `0.94 - 1.06 (+-6%)` | `Float Range` | Eliminates 'machine-gun' repetitive SFX fatigue |
| `LowPassFilterCutoff` | `600 Hz (Underwater/LowHP)` | `Filter Hz` | Communicates danger/damage diegetically |

**Derlenen Uygulama Reçeteleri:**
- [Unreal] Event delegate: Player -> World -> Music

---

## ✨ Sepet 3: Game Juice & Duyusal Geri Bildirim (UX, VFX, Audio & Feel)

- Kombo sayacı yükseldikçe her başarılı vuruş SFX'inin perde (pitch) notasının pentatonik dizide yükselmesi.
- Düşük canda kalp atışı alt-frekansı ve ortam müziğine Low-Pass filtre uygulanması.


---

## ⚠️ Sepet 4: Anti-Pattern & Tasarım Tuzakları (Pitfalls & Failure Modes)

- **Aynı Ham Ses Dosyasını 100 Kez Çalmak:** Pitch/Volume randomizasyonu ve en az 3-4 varyasyon olmadan ayak/kılıç sesleri anında kulak tırmalar.
- **Savaş Bittikten 0.1sn Sonra Müziği Kesmek:** Çarpışma bittikten sonra `3-4s` cooldown bekleme süresi koymazsanız müzik sürekli açılıp kapanır.


---

## 🔗 Bağlantılı Sistemler (Linked Systems Graph)

- [[Combat]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Stealth]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Boss Design]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Hitstop & Freeze Frames]] — Çapraz sistem etkileşimi ve mekanik sinerjisi
- [[Diegetic Guidance]] — Çapraz sistem etkileşimi ve mekanik sinerjisi

**Kaynak Analiz Referansları:** `Adaptive_Soundtracks_in_Games`, `[OLD] Aer： Memories of Old - the game with the BEST flight mechanics`

---

> [!TIP] **Bu kütüphaneyi çevrimdışı kullanmak ve kendi oyununuza uyarlamak ister misiniz?**
> Tam Obsidian Vault veritabanını, Unreal Engine 5 / Unity 6 / Godot 4 hazır parametre tablolarını, GDD şablonlarını, ChatGPT/Claude/NotebookLM sürükle-bırak paketlerini, API anahtarsız MCP Sunucusunu ve kendi anahtarınızla çalışan Yerel AI Sorgu Aracını (CLI) içeren **Supporter Pack**'i [GitHub Supporter Pack & Bağış Sayfası](https://github.com/emirkankirman2-arch/gamedev-mechanics-vault) üzerinden indirerek projeye destek olabilirsiniz!
