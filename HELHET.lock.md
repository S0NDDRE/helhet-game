# HELHET.lock.md

**Fyll inn DIN fantasy her. Ikke slett denne filen. Ikke endre strukturen. Kun fyll inn.**

---

## FANTASY

_É´n setning. Den følelsen spilleren skal ha i de første 5 sekundene._

**EKSEMPEL:** "Du er en tung, våt jeger i et lavmæ´´lt, industrielt ødemark; hvert steg og skudd har vekt, og døden kommer raskt og tydelig."

**DIN:** 

---

## VERBS (max 3)

_Hva spilleren faktisk gjør. Max 3 kjernehandlinger._

- 
- 
- 

---

## CAMERA + BODY

_Kamera-plassering, FOV, hvordan vekt leses, hvordan kroppen føles._

**EKSEMPEL:** "FØ´rstepersons, FOV 90, kamera følger kroppen med lett forsinkelse. Vå°°pen i viewmodel har tydelig rekyl. Kroppen føles tung, ikke flytende."

**DIN:**

---

## VISUAL LAW

### Palette

_Farger, stemning._

**EKSEMPEL:** "Dempet, jordnæ´´r (grå°°, rust, dyp grØ´nn/blå°°), få mettede farger."

**DIN:**

---

### Materialer

_Hvilke overflater, hvilken kvalitet._

**EKSEMPEL:** "Betong, metall, våt stein, slitt tre; ingen 'plast-Unity'-flater."

**DIN:**

---

### Silhouette

_Hvordan former leses._

**EKSEMPEL:** "Enkle, lesbare former; fiender/objekter skal leses på kontur, ikke teksturdetaljer."

**DIN:**

---

### Lys

_Lyssetting, skygger, atmosfæ´´re._

**EKSEMPEL:** "Lavt, retningsbestemt, sterke skygger; lyskjegler og flimmer fra industrielle kilder."

**DIN:**

---

### Post

_Filmkorn, vignett, fargegrading._

**EKSEMPEL:** "Lett filmkorn, subtil vignett, ingen overeksponert 'demo-look'."

**DIN:**

---

### FORBIDDEN

_Hva som er strengt forbudt._

**EKSEMPEL:** "Cartoon-skybox, overmettet himmel, glatte PBR-demonstrasjoner, 'asset flip'-estetikk."

**DIN:**

---

## AUDIO LAW

_Stillhet, hit, fare, UI-lyd — hvordan lyd bygger verden._

**EKSEMPEL:** "Stillhet er spent, ikke tom; lav bakgrunnsdrone eller vind. Skudd er korte, harde, med tydelig romklang. Fare leses gjennom audio: plutselig stillhet, mekanisk piping, fjerne skritt."

**DIN:**

---

## LOOP (0–8s)

_Den komplette loopen fra start til restart. Hvorfor spilleren vil gjenta._

**EKSEMPEL:**
- 0–2s: bevegelse inn i rom, oppdag fiende/lyd
- 2–5s: sikting, justering, første skudd
- 5–8s: reaksjon (fiende svarer eller du tar dekning), ny trussel eller dØ´d/restart

**DIN:**

---

## FAIL / WIN

_Hvordan dØ´d/fiasko og suksess leses visuelt og auditivt._

**EKSEMPEL:**
- FAIL: dØ´d er umiddelbar og tydelig (skjerm mørkner/rØ´dmer, lyd kutter, kort "game over"-tekst), deretter rask restart
- WIN: overleve N looper, drepe M fiender, eller nå et enkelt mål (rom/objekt) uten å dØ´

**DIN:**

---

## JUICE (5 mandatory feedback events)

1. 
2. 
3. 
4. 
5. 

**EKSEMPEL:**
1. Skuddavgang: rekyl, flash, lyd, viewmodel-dytt, liten skjermrist
2. Treff på fiende: hitmarker/lyd, partikkel (blod/rust/stØ´v), fiendens reaksjon (stagg/lyd)
3. Mottatt skade: skjermfarge-endring, lyd, kort helse-indikator, kamera-dytt
4. DØ´d: dramatisk lyd/kutt, visuell overgang, kort tekst, umiddelbar restart-knapp/automatisk
5. Loop-avslutning (overlevelse/må°°l): kort audio/visuell "pust" (lys endres, dØ´r Å'pnes, ny sone Å'pner seg)

**DIN:**

---

## DONE

_Hva som må være kjØ´rbart for at dette er "ferdig". Ingen screenshots, ingen scener uten loop._

**EKSEMPEL:** "KjØ´rbar vertikal slice: boot → kontroll → trussel → skudd/treff → skade → dØ´d/restart, alt innenfor visual/audio-loven."

**DIN:**

---

## OUT

_Liste over nØ´dvendige filer, scener, bygg for at loopen er bevis._

**EKSEMPEL:**
- Scene / level: Assets/Scenes/HelhetSlice.unity
- Spillerkontroller + våpen: Assets/Scripts/Player/, Assets/Scripts/Weapon/
- Fiende/AI (enkel): Assets/Scripts/Enemy/
- Visual setup (lighting, post, materials): Assets/Settings/HelhetVisuals/
- Audio setup (mixer, events): Assets/Audio/HelhetMixer/
- Bygg: Builds/HelhetSlice/<plattform> (exe/webgl/etc.)
- README med "how to run" og kontrollbeskrivelse

**DIN:**
