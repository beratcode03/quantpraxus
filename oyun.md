# OPIUM: Resonance — Design Doc (OPIUM.md) 🎛️🌑

**Proje Kod Adı:** OPIUM: Resonance
**Motor:** Unity (URP)
**İlham:** The Planet Crafter, Subnautica
**Tahmini Oynanış Süresi:** Minimum **33 saat**, Tam deneyim (Hikâye + Terraform + Hibrit) **60+ saat** 🎯

---

> Bu dosya, rezonans-temelli akışı, parametreleri, rezonans türlerinin sırayla açılış mantığını ve oynanabilirliği net, somut ve uygulamaya hazır şekilde anlatır. Teknik kod/pseudocode yok — odak oyun tasarımında. Uzun, açıklayıcı ve emojilerle destekli.

---

# Özet / Oyunun DNA’sı 🧬

Yalnız bir operatör, yaşanmış bir gezegende insanlığın geride bıraktığı izleri keşfederken gezegenle etkileşir; yaptığı her eylem gezegenin “rezonans” profilini değiştirir. Rezonanslar isimler — BRs, ERs, NRs, SRs, TRs, URs, RRs, KRs, Rs — artışa bağlı olarak, PRI (Planetary Resonance Index) ile paralel ama bağımsız bir sırayla devreye girer. Amaç: oyuncunun seçimleriyle gezegenin kaderini belirlemesi — yok oluş mu, simbiyoz mu?

Oynanış hedefi: her oyuncuda 33–60+ saatlik anlamlı deneyim üretmek; sıkmayan ama sürekli “bir şeyler oluyor” hissi veren, keşif ve strateji dengesi.

---

# Temel Kavramlar (Basit ve Anlaşılır) 🔑

### PRI — Planetary Resonance Index

* Gezegenin genel rezonans seviyesi. 0’dan başlar; oyuncunun makineleri, core’ları, salvage/enkazlar, büyük etkileşimleri ile artar.
* **PRI** oyun içi “ilerleme skorudur”; chapter tetikleyicileri ve rezonans evreleri PRI ile kesişir.

### Rezonans Türleri (İsimler olarak)

* BRs — Bloom Resonance
* ERs — Emerge Resonance
* NRs — Nest Resonance
* SRs — Sphere Resonance
* TRs — Transcendent Resonance
* URs — Unity Resonance
* RRs — Reverberant Resonance
* KRs — Keystone Resonance
* Rs — Resonance

> Bu isimler **yeni yetenekler/olay tipleri** değil; PRI artışıyla oyuncunun gözlemleyip etkileşime gireceği *katmanlı atmosferik/ekosistemsel* devinimler. Her biri bir sequence içinde ve belli aralıklarda “etkinleşir” — ama hızlıca boğmaz; yavaşça, hissedilir şekilde gelir.

### Denge (Balance Index)

* 0–100 arası bir ölçek. Gezegenin “doğal iradesi” ile insan etkisinin dengesi.
* 0–40 → Gezegen İradesi (doğa baskın)
* 40–60 → Nötr (uyumlu)
* 60–100 → İnsan Baskınlığı (teknoloji baskın)

Denge, PRI ile etkileşir: yüksek PRI + düşük denge → gezegen tepki üretir (ör. fırtına, su yükselmesi); yüksek PRI + dengeli → daha yumuşak, evrimsel değişimler.

---

# Parametreler & Alt-Parametreler — Oyun İçin Net ve Oynanabilir 🌍

Her ana parametrenin alt-parametreleri bulunur; bu, oyuncunun hangi sistemi etkilediğini daha somut anlamasını sağlar.

### 1) Thermal Index (TI) — Isı Eğilimi 🌡️

* **Surface Temp (Yüzey Sıcaklığı):** genel sıcaklık eğilimi, soğuma/ısınma hissi.
* **Microclimate Flux (Mikro İklim):** lokal mağara/çukur/tepe bazlı farklılıklar.
* **Heat Source Density (Isı Kaynağı Yoğunluğu):** aktif jeneratörler, antik reaktörler, volkanik noktalar.

Etkileri: buzların erimesi, toprak kuruma/şımarma, bazı bitki/organizma türlerinin tetiklenmesi.

---

### 2) Hydro Index (HI) — Su / Basınç / Deniz Seviyesi 🌊

* **Sea-Level Trend (Deniz Düzeyi Eğilimi):** uzun dönemli su seviyesi değişimi.
* **Local Flooding (Lokal Su Birikintisi):** çukur/göl oluşumu, taşkın.
* **Water Clarity & Salinity (Su Netliği & Tuzluluk):** sualtı türleri için önemli.

Etkileri: sualtı biyomu ortaya çıkışı, basınç etkileri, suya dayalı yapılar/ruinlerin açılması.

---

### 3) Biomass Score (BM) — Biyokütle / Flora 🌿

* **Plant Density (Bitki Yoğunluğu):** alan başına kaplama.
* **Growth Rate (Büyüme Hızı):** hızlı mı yoksa yavaş mı yeşilleniyor.
* **Spore / Seed Load (Spor / Tohum Yükü):** yayılma potansiyeli.

Etkileri:  yüksek BM → hızlı görsel değişim, kaynak artışı.

---

### 4) Fauna Activity (FA) — Hayvan / Makro Canlılık 🐾

* **Population Density (Nüfus Yoğunluğu):** tür başına birey sayısı.
* **Aggression Index (Saldırganlık):** oyuncuya tehlike riski.
* **Reproduction Rate (Üreme Hızı):** ne kadar sık çoğalıyorlar.

Etkileri: tetiklemelerde türler belirir veya kaybolur; oyuncu etkileşimleri fauna davranışını şekillendirir.

---

### 5) Micro-Resonance (mR) — Lokal Rezonans -1..+1 ⚛️

* **Pulse Frequency (Atım Frekansı):** kısa radarda hissedilen dalga hızı.
* **Amplitude (Genlik):** lokal etki gücü.
* **Phase Stability (Faz İstikrarı):** rezonans uzun ömürlü mü, yoksa geçici mi?

Etkileri: lokal spawn olasılığı, core’ların verimliliği, shader/visual pulsatilite.

---

### 6) Atmos O₂ Ratio (O2%) — Solunabilirlik 🌬️

* **Partial O₂ (Kısmi Oksijen):** sağlanan anlık solunabilirlik.
* **Toxicity Index (Zehirlenme İndeksi):** zararlı gaz var mı?
* **Breathable Bandwidth (Solunabilir Bant):** insan için ideal aralık.

Etkileri: O oyuncu O₂ üretimi/taşıma cihazları kullanmalı.

---

### 7) Surface Integrity (SI) — Yüzey Sağlığı 🪨

* **Erosion Rate (Erozyon Hızı):** madencilik ve doğa etkisiyle toprağın çökme hızı.
* **Structural Cohesion (Yapısal Bütünlük):** binaların, enkazların dayanıklılığı.
* **Node Stability (Node Kararlılığı):** nadir kaynakların korunma durumu.

Etkileri: mining riskleri, antik kalıntıların korunması veya parçalanması.

---

# Rezonans Kademelenmesi — Nasıl “Sırayla” Gelir? ➿

### Temel Prensip

* Rezonanslar *sabit zamanlayıcılarla* gelmez; **PRI seviyesine bağlı** olarak bir *sırayla* ve **yavaşça** devreye girer. Amaç oyuncuyu boğmamak; her değişim hem görsel hem mekanik olarak hissedilsin.
* Her rezonans türü belli **PRI eşikleri** ve **lokal koşullar** gerektirir. Örnek: BRs erken evrede, ERs orta evrede, TRs ileri evrede belirginleşir.
* Rezonansların geliş hızı, oyuncunun eylemleriyle (makine yerleştirme, core deploy, salvage rate, habitat müdahaleleri) artar veya yavaşlar. Bu sayede oyun süresi dinamik olarak 33–60+ saati içine alır.

### Örnek Sıralama & Mantık (Soyut, oynanabilir)

* **PRI 0–20:** Minimal rezonans semptomları. Oyuncu temel kaynak toplama ve ilk makineleri kurar. BRs (very faint) gözlemlenebilir — küçük bitki patlamaları.
* **PRI 20–40:** BRs belirginleşir; BM artışı gözle görünür. NRs (küçük yuvalanma belirtileri) hafifçe başlar. Denge hala değişken.
* **PRI 40–60:** ERs devrede — sualtı canlıları yavaşça belirir, HI’nin etkisi hissedilir. SRs (lokal stabilizasyonlar) açılmaya başlar. Denge turnusol kağıdı gibi tepki verir.
* **PRI 60–80:** TRs ve RRs yükselir; antik yapıların yankıları, zincir reaksiyonlar, ve büyük çevresel tepkiler (tufan, deniz kabarması vb) olasılığı artar. URs de aktifleşmeye başlar ancak dengede olmayı gerektirir.
* **PRI 80+:** KRs tetiklenebilir (keystone unlock), büyük hikâyeye etki eden olaylar gerçekleşir. Finalde seçime bağlı sonuçlar (terraform tamamla → yerliler silinir / denge koru → simbiyoz) belirgin.

> Bu eşikler **sabit saat** değil; örnek bir tasarım aralığıdır. Rezonans ilerlemesi oyuncunun eylemlerine göre hızlandırılır/azaltılır. Hız kontrolü: *yavaş başlangıç, hissedilir artış, büyük sıçrama* modelinde.

---

# Rezonansın Hissiyatı — Oyuncunun Ruhsal Deneyimi 🎧

Her rezonans değişimi, sadece mekanik değil aynı zamanda duyusal olmalı:

* **Görsel:** shader pulsateleri, bitki renginde LERP, su parlaklığı değişimleri, biyolüminesans artışı.
* **İşitsel:** ambient motiflerde yeni katmanlar eklenir (rüzgar → su yankısı → orman nefesi). Sesler rezonans türüne özgü motifler taşır.
* **ASENA diyalogları:** her major değişimde diegetic bildirim; ton yavaş yavaş değişir (başta empatik, ortalarda sorgulayan, CH3’te daha mekanik ve mesafeli),gezegende zaman geçirdikçe diyaloglar vs şirket için çalışan asenadan artık bizim için çalışan asenaya dönsün.


---

# Chapter Yapısı — PRI & Rezonansa Bağlı Akış 📚

### Genel Mantık

* Chapter’lar *sabit süreli* değil; **oyuncunun PRI / Rezonans profiline göre** tetiklenir ve süresi dinamik ayarlanır.
* Her chapter’ın “amaçları” var; örneğin CH1: çevresel uyum, CH2: suyla yüzleşme, CH3: yerliler ve etik karar.

### Örnek Chapter Tetikleyicileri (somut, ama saat değil)

* **CH1 — Kurak Yanılsama:** tetikleyici: PRI başlangıç → oyuncu ilk PRI puanını alırken. BRs kademeli artış. Amaç: temel altyapıyı inşa etmek, ilk kararları almak.
* **CH2 — Gezegenin Cevabı:** tetikleyici: PRI 20–50 aralığında ve HI artışıyla beraber ERs burst olasılığı. Oyuncu su ile mücadele ya da uyum yolunu seçer.
* **CH3 — Yerli Bilinci:** tetikleyici: PRI 60+ ve KRs aktiviteleri. Burada TRs/URs, yerli yapıların bilinçlenmesi ve büyük seçimler gelir.

### Süre Önerileri (oyun içi ilerlemeye göre)

* Minimum yol (terraform odaklı, daha hızlı PRI kazanımı): ~33 saat (oyuncu etkin, agresif PRI artışı ile).
* Tam deneyim (hikâye + dengeli oynanış + keşif): 60+ saat (oyuncu yavaş ilerler, birçok yan keşif/ekosistem etkileşimi alır).

> Tekrar: Saatler oyuncu davranışına göre değişir; bu değerler test ve tuning için referans.

---

# Oyun Mekanikleri — Oyuncunun Etkileri (Somut Örnekler) 🕹️

### Oyuncu Eylemleri ve Sonuçları (Kısa, net)

* **Makine kurmak (yüksek verimli):** PRI artışı hızlanır; TI ve SI değişebilir. Çok makine = denge insan tarafına kayar.
* **Core (SCAN/VOID/SYNC) deploy etmek:** lokal rezonansı (mR) değiştirir; bazı türler tetiklenir/azalır.
* **Antik enkazları parçalamak (agresif salvage):** kısa vadede PRI ve resource artışı; uzun vadede SI ve fauna kaybı → dengeye negatif etki.
* **Koruyucu/dengeleyici eylemler (yorulmadan habitat restore, buffer inşa):** Denge artışı, URs desteklenir, bazı TRs/RRs etkileri daha az yıkıcı olur.
* **Buz/ısı manipülasyonu (bölgesel heating):** yeni kaynaklar ve mağara girişleri açılır; fauna/flora çeşidi değişir.

### Fauna/Flora Açılması

* Türler **aniden** çıkmaz; lokal SpawnScore yükseldikçe *kademeli* ortaya çıkar. Ancak belirli reseptörler (ERs burst, BRs burst) ile ani sürpriz kümelenmeleri olabilir — bu, oyuncuyu hep tetikte tutar.

---

# Hikâye & Etik Seçimler — Sonuçlar (Somut, Yıpratıcı) ⚖️

* **Tam Terraform (insan baskınlığı):** Mekanik olarak tüm hedefler tamamlanır; PRI yüksek, KRs kullanılarak antik mekanizmalar çalıştırılır. *Sonuç:* yerliler/yerel bilinç büyük ölçüde yok olur; oyunun sonu teknik başarı hissi verir ama etik boşluk.
* **Denge Hibrit:** PRI kontrollü artar; URs ve SRs ile uyum kurulur. *Sonuç:* simbiyotik bir final; bazı teknolojiler sınırlı ama yerliler/ekosistem hayatta. (Genelde en uzun oynanış)
* **Gezegen İradesi (doğa baskın bırakma):** Oyuncu minimum müdahale/uyum kararları alır; bazı teknolojiler kaybolur; final daha mistik ve doğa ağırlıklı.

Her finalin oyun içi görsel/işitsel “son” anı olacak: sessizlik, ASENA’nın son tonu, oyuncunun “başardım mı?” / “yanlış mı yaptım?” hissi.

---

# Replayability & Oynanış Derinliği 🔁

* Farklı rota (Terraform, Hikâye, Denge Hibrit) → farklı fauna, farklı antik yapı sonuçları.
* Rezonans sıralaması ve hızlandırma mekanikleri oyuncunun oyun tarzına göre değişir; her oyun yeni rezonans birikimleri ve dalgaları üretir.
* Mini oyunlar ve bazı local puzzle’lar, KRs / TRs tetiklemeleriyle bağlanır; çoklu bitişler.

---

# A.S.E.N.A — Karakter, Ton, Evrim (Somut Örnekler) 🤖
 **A.S.E.N.A** -> *Autonomous Survival Enclosure & Neural Agent* - *Otonom Hayatta Kalma Ortamı ve Sinirsel Ajan*
* **Kişilik:** Mekanik ama empatik; şirket kökenli; operatöre hem rehber hem sorgulayıcı.
* **Başlangıç:** Direktifler, kısa motivasyonlar. (“Hoş geldin Operatör. Hayattasın. Bu iyi. Şimdi işe koyul.”)
* **Orta Evrim:** Rezonans arttıkça ASENA sorgulamaya başlar; daha metaforik konuşmalar olur. (“Gezegen... cevap veriyor.”)
* **CH3:** Ton daha mekanik, zaman zaman duygusuz; oyuncu bazen ASENA’nın sesinde uyumsuzluk hisseder. (“Operatör. Kararlarınız kaydedildi. Etki: belirsiz.”)

ASENA, her rezonans anahtarında özel kısa loglar bırakır — oyuncunun kaydı arşivlenir.

---

# Görsel & Atmosferik İşaretler (Oyuncuya "Bir Şey Oluyor" Hissi Verme) 👀

* **BRs artışı:** bitkisel ışık artışı, toz partikül sahneleri, hafif rüzgar melodileri.
* **ERs patlaması:** su yüzeyinde mavi pulsatlar, sualtı ışık hattı, su yankıları.
* **RRs zincirleri:** etrafta yankılanan işitsel motifler, gökcisimleri gibi kısa görsel halkalar.
* **KRs unlock:** antik taşlar titreşimli glow, atmosferde kısa süreli soluk renk değişimi.

Bu işaretler hem oyuncuyu yönlendirir hem de merak duygusunu canlı tutar.

---

# Oynanabilirlik (33 → 60+ Saat) — Nasıl Sağlanır? ⏳

1. **Rotalar:** Terraform (agresif PRI), Hikâye (orta tempo, keşif), Hibrit (dengeleyici, uzun).
2. **Kademeli açılımlar:** Rezonanslar sırayla, her birinde yeni içerik, yeni tür, yeni mekanik. Bu, oyuncunun sürekli yeni hedefler bulmasını sağlar.
3. **Keystone & Side Content:** Antik kilitler (KRs) ana hikâyeyi etkiler ama erişim için yan görevler & keşif gerektirir; bu, süreyi organik olarak uzatır.
4. **Randomized Burst Events:** Nadir, oyuncuyu şaşırtan burst spawn’lar — replayability için ideal.
5. **Derin Envanter & Progression:** Evre bazlı ekipman (Prototype → Transcendent) oyuncunun oyun boyunca hedefleri olmasını sağlar.

Sonuç: oyuncu ister hızlı ilerlesin (≈33 saat), ister her şeyi toplasın, keşfetsin ve dengeyi korusun (60+ saat).

---

# Prototip Öncelikleri (Tasarım Önceliği, Teknik Detay İçermez) 🛠️

* **1. PRI & Rezonans akışı (oyun hissinin çekirdeği)** — nasıl artıyor, hangi eşiklerde neler tetikleniyor.
* **2. Rezonans görsel/auditory işaretleri** — oyuncu ne zaman tepki verecek?
* **3. Spawn & Burst mantığı (kademeli + eşik tabanlı)** — fauna/flora açılımı.
* **4. ASENA diyalog sistemi (ton evrimi & diegetic uyarılar).**
* **5. Heat / Ice / Flood mekaniği gibi çevresel dönüşümler (mağara açılmaları, su yükselmeleri).**

---

# Oyun İçi Örnek Senaryolar (Somut, kısa) 🎭

### Senaryo A — Hızlı Terraformer (Kısa Yol)

* Oyuncu makineler kurar, yüksek verimli enerji üretir → PRI çabuk artar → BRs erken aşamada yoğunlaşır → BM artışı → ERs orta evrede tetiklenir → CH3’e ulaşmadan önce KRs açılımlarıyla finali zorlar. Süre: ~33 saat.

### Senaryo B — Denge Koruyucu (Uzun Yol)

* Oyuncu düşük müdahale, habitat koruma işleri, URs ve SRs’yi destekler → PRI yavaş ama istikrarlı yükselir → çeşitli fauna türleri kademeli olarak belirir → KRs’e erişim için geniş keşif → CH3’te simbiyoz seçeneği. Süre: 60+ saat.

---

# Son Notlar & Tasarım İlkeleri 🧭

* **Oyuncu hissi önce:** mekanikler oyuncuyu “hep meraklı” tutacak şekilde tasarlanmalı. Rezonanslar isim olarak kalmalı ama etkileri somut ve görsel olmalı.
* **Zaman değil, sebep-sonuç:** chapter başlangıçları saat değil, PRI ve rezonans sonuçlarına bağlı olsun.
* **Her parametrenin alt parametresi olmalı:** bu oyuncunun *neyi* etkilediğini ve *neden* tepki verdiğini anlamasını sağlar.
* **İyi prototiple, sonra zenginleştir:** önce PRI + Rezonans + Spawn core loop’u prototiple, sonra görsel/audio katmanları ekle.
* **ASENA bir köprü:** mekanik ve duygusal rehber olarak kullanılmalı — oyuncunun yalnızlığını ve pişmanlığını derinleştirmek için.

---

# Dosya Sonu — Hızlı Özet (Bir Sayfalık) 📝

* Rezonanslar = isimler; PRI ile sırayla açılır; oyuncuyu boğmayacak hızda, ama sürekli “bir şey oluyor” hissi verecek şekilde.
* Parametreler: TI, HI, BM, FA, mR, O2, SI — her birinin açık alt-parametreleri var.
* Rezonans ilerlemesi oyuncunun eylemlerine göre hızlanır, chapterlar süre değil sonuçlara bağlı tetiklenir.
* Oynanış süresi: min **33 saat**, tam deneyim **60+ saat**.
* ASENA ton evrimi, görsel/auditory işaretler, spawn kademelenmesi, ve prototip öncelikleri net belirtildi.

---
bu OPIUM.md’yi doğrudan markdown dosyası olarak hazır edip indirilebilir versiyonunu oluştur (dosya olarak)