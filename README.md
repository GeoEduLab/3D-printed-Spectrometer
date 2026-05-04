# Smart Spectrometer – Double-Beam Spectrophotometer

A low-cost, open-source, 3D-printable double-beam spectrophotometer for students and teachers.

| 🇷🇴 Română | 🇬🇧 English |
|-----------|------------|
| [Smartspectrometer-Manual-RO.md](Smartspectrometer-Manual-RO.md) | [Smartspectrometer-Manual-EN.md](Smartspectrometer-Manual-EN.md) |

---

# Spectrofotometrul cu Dublă Rază
## Manual de Construcție și Utilizare pentru Elevi și Profesori

---

**Bazat pe articolul științific:**
> Winters, B.J., Banfield, N., Dixon, C., Swensen, A., Holman, D., & Fillbrown, B. (2021).
> *3D-Printable and open-source modular smartphone visible spectrophotometer.*
> HardwareX, 10, e00232. https://doi.org/10.1016/j.ohx.2021.e00232

**Licență hardware:** Creative Commons Attribution-ShareAlike 4.0 (CC BY-SA 4.0)
**Fișiere de imprimare (STL) și documentație:** https://osf.io/7ewb3

---

## Cuprins

1. [Ce este lumina?](#1-ce-este-lumina)
2. [Ce este un spectrofotometru?](#2-ce-este-un-spectrofotometru)
3. [Cum funcționează spectrofotometrul nostru?](#3-cum-functioneaza-spectrofotometrul-nostru)
4. [Componentele spectrofotometrului](#4-componentele-spectrofotometrului)
5. [Asamblarea pas cu pas](#5-asamblarea-pas-cu-pas)
6. [Cum măsurăm?](#6-cum-masuram)
7. [Calibrarea instrumentului](#7-calibrarea-instrumentului)
8. [Experimente](#8-experimente)
9. [Depanare – Ce fac dacă nu merge?](#9-depanare--ce-fac-daca-nu-merge)
10. [Referințe](#10-referinte)

**Anexe (pentru profesori și constructori):**
- [Anexa A – Lista de materiale](#anexa-a--lista-de-materiale)
- [Anexa B – Imprimarea 3D a pieselor](#anexa-b--imprimarea-3d-a-pieselor)

---

## 1. Ce este lumina?

Lumina este o formă de energie care călătorește sub formă de unde electromagnetice. Ceea ce vedem cu ochii noștri — culorile curcubeului, de la violet la roșu — reprezintă doar o mică porțiune dintr-un spectru mult mai larg.

```
Lungimea de undă (nm):
  100        400   450   500   550   600   650   700       1000+
   |          |     |     |     |     |     |     |          |
[UV extrem] [Violet][Albastru][Verde][Galben][Portocaliu][Roșu] [Infraroșu]
             ←——————— Vizibil pentru ochiul uman (380–700 nm) ————————→
```

> **💡 Știați că?**
> Curcubeul nu este altceva decât lumina soarelui separată în culorile sale componente de picăturile de ploaie, care acționează ca niște prisme minuscule. Spectrofotometrul nostru face același lucru — dar în laborator!

---

> **💡 Știați că? Corpul uman emite lumină!**
> Orice obiect cu o temperatură mai mare de −273°C (zero absolut) emite radiație electromagnetică. Corpul uman, la ~37°C, emite lumină **infraroșie** — invizibilă ochiului, dar detectabilă cu camere termice. Acest fenomen se numește **radiație de corp negru** (*black body radiation*), descris de fizicianul Max Planck în 1900.
>
> Cu cât un obiect este mai cald, cu atât lungimea de undă dominantă este mai scurtă:
> - Corpul uman (~37°C) → infraroșu (~9.000 nm)
> - Un fier înroșit (~700°C) → roșu vizibil (~700 nm)
> - Soarele (~5.500°C) → galben-verde (~500 nm)
> - O stea albastră fierbinte (~20.000°C) → ultraviolet
>
> Spectroscopia ne permite să „citim" temperatura și compoziția chimică a oricărei surse de lumină!

---

> **💡 Știați că? Fiecare atom are o „amprentă digitală" de lumină!**
> Atomii emit și absorb lumină numai la anumite lungimi de undă precise — ca un cod de bare unic. Aceasta a permis oamenilor de știință să descopere elementele chimice din **Soare și stele** fără să le viziteze vreodată! De exemplu, heliul a fost descoperit mai întâi pe Soare (în 1868) și abia 27 de ani mai târziu pe Pământ.

---

> **💡 Știați că? Fotosinteza „preferă" anumite culori!**
> Clorofila din frunze absoarbe cu precădere lumina **roșie** (~680 nm) și **albastră** (~430 nm), iar lumina **verde** este reflectată — de aceea plantele ne par verzi! Cu spectrofotometrul nostru putem măsura exact această absorbție.

---

## 2. Ce este un spectrofotometru?

Un **spectrofotometru** este un instrument care:
1. **Separă** lumina în culorile sale componente (spectru)
2. **Măsoară** cât de multă lumină absoarbe sau emite o substanță la fiecare culoare (lungime de undă)

Există două tipuri principale de măsurători pe care le putem face:

| Tip de spectroscopie | Ce măsurăm | Exemple |
|----------------------|-----------|---------|
| **Emisie** | Lumina produsă direct de o sursă | Becuri, flăcări, plasma, stele |
| **Absorbție** | Lumina absorbită de o substanță transparentă | Soluții colorate, filtre, clorofilă |

Această capacitate face spectrofotometrul util în:
- **Chimie** — determinarea concentrației soluțiilor
- **Biologie** — analiza pigmenților, clorofilei, proteinelor
- **Astronomie** — identificarea elementelor din stele
- **Criminalistică** — analiza urmelor de substanțe
- **Industria alimentară** — controlul calității

Spectrofotometrele comerciale costă între **400 și 6.000 de dolari** [1]. Cel pe care îl construim noi costă **aproximativ 25 de dolari** pentru piese și folosește **smartphone-ul** ca detector — fără să sacrifice precizia [1].

---

## 3. Cum funcționează spectrofotometrul nostru?

Spectrofotometrul DBS (*Double-Beam Spectrophotometer* — Spectrofotometru cu Dublă Rază) funcționează astfel:

```
  SURSA DE LUMINA
       │
       ▼
  [Fanta ingusta]  ← doua lame de bisturiu paralele
       │
       │  raza 1 → trece prin PROBA (solutia de analizat)
  [Suport proba]
       │  raza 2 → trece prin REFERINTA (apa pura / solvent)
       │
       ▼
  [Retea de difractie]  ← 1000 linii/mm; separa culorile ca o prisma
       │
       ▼
  [Camera smartphone / USB]
       │
       ▼
  [Software ImageJ] → grafic intensitate vs. lungime de unda
```

**Notă pentru spectroscopia de emisie:** Când studiem lumina emisă direct de o sursă (bec, flacără, plasmă), nu mai este nevoie de cuve cu probe — îndreptăm spectrofotometrul direct spre sursă și observăm spectrul de emisie al acesteia.

### Ce este rețeaua de difracție?

O rețea de difracție este o suprafață cu mii de linii paralele gravate pe milimetru. Când lumina lovește aceste linii, diferitele lungimi de undă (culori) sunt deviate în unghiuri diferite — exact ca o prismă, dar mai eficient. Rețeaua noastră are **1000 de linii pe milimetru** [1].

### De ce „dublă rază"?

Designul cu două raze este esențial pentru precizie în spectroscopia de absorbție [1]:
- **Raza superioară** trece prin **proba** de analizat
- **Raza inferioară** trece prin **referință** (apă pură sau solvent)

Camera captează ambele raze simultan în aceeași imagine. Comparând cele două spectre, eliminăm erorile cauzate de fluctuațiile sursei de lumină.

### Legea Beer-Lambert — relația dintre culoare și concentrație

Cu cât o soluție este mai concentrată, cu atât absoarbe mai multă lumină. Această relație este descrisă prin **Legea Beer-Lambert** [1]:

```
Absorbanță (A) = −log₁₀ (P / P₀)
```

- **P₀** = intensitatea luminii de referință
- **P** = intensitatea luminii după ce trece prin probă
- Absorbanță = 1 → proba a absorbit 90% din lumină
- Absorbanță = 2 → proba a absorbit 99% din lumină

---

## 4. Componentele spectrofotometrului

Spectrofotometrul este format din piese imprimate 3D și câteva componente achiziționate. Iată piesele principale:

### 4.1 Tubul fantă (DBS01 – Slit Tube)

![DBS01 – Tub fantă](imagini/DBS01.png)

**Rol:** Ghidează lumina de la sursă spre probă, menținând fasciculul îngust și drept. Se montează în Suportul probă și se interblocă cu Adaptorul tub (DBS04) pentru rigiditate.

---

### 4.2 Suportul probă (DBS02 – Sample Holder)

![DBS02 – Suport probă](imagini/DBS02.png)

**Rol:** Piesa centrală a instrumentului. Conține două sloturi pentru cuve (probă și referință) și găzduiește subansamblul fantei. Lumina trece prin ambele cuve simultan, creând cele două raze.

---

### 4.3 Suportul rețelei de difracție (DBS03 – Grating Mount)

![DBS03 – Suport rețea difracție](imagini/DBS03.png)

**Rol:** Ține rețeaua de difracție (foița cu 1000 linii/mm) în unghiul corect față de fasciculul de lumină. Pe el se montează și suportul pentru cameră/smartphone.

---

### 4.4 Adaptorul tub (DBS04 – Tube Adapter)

![DBS04 – Adaptor tub](imagini/DBS04.png)

**Rol:** Face legătura mecanică între Suportul probă și Suportul rețelei de difracție. Tubul fantă (DBS01) se prelungește prin acesta și se interblocă cu DBS03, asigurând rigiditate și etanșeitate la lumina ambientală [1].

---

### 4.5 Adaptorul sursă (DBS05 – Source Adapter)

![DBS05 – Adaptor sursă](imagini/DBS05.png)

**Rol:** Se montează pe capătul suportului probă dinspre sursa de lumină. Adaptează diferite tipuri de surse (lanternă, stilou LED) la corpul instrumentului.

---

### 4.6 Suportul fantei (DBS22) și Pana fantei (DBS23)

| | |
|:---:|:---:|
| ![DBS22 – Suport fantă](imagini/DBS22.png) | ![DBS23 – Pană fantă](imagini/DBS23.png) |
| **DBS22** – Suport fantă (Slit Mount) | **DBS23** – Pană fantă (Slit Wedge) |

**Rol:** Împreună formează **fanta de lumină** — cea mai delicată parte a instrumentului. Două lame de bisturiu sunt fixate paralel, formând o fantă îngustă prin care trece lumina. Lățimea fantei determină rezoluția spectrală. Penele (DBS23) fixează lamele prin presiune mecanică.

---

## 5. Asamblarea pas cu pas

### Pasul 1 — Asamblarea fantei de lumină

Fanta de lumină este formată din **două lame de bisturiu** fixate paralel în DBS22, ținute de penele DBS23.

**Ai nevoie de:** DBS22 (1×), DBS23 (2×), lame RS01 (2×)

> ⚠️ **ATENȚIE: Lamele de bisturiu sunt extrem de ascuțite. Folosiți pensă sau mănuși de protecție!**

**1a.** Verificați că DBS22 și DBS23 sunt curate și fără bavuri după imprimare.

**1b.** Luați prima lamă (RS01) și introduceți-o în DBS22 astfel încât **cei trei știfturi ai suportului să intre în cele trei găuri ale lamei**. Lama trebuie să stea plat.

**1c.** Ținând lama fermă, introduceți o pană (DBS23) în slotul lateral al DBS22. Împingeți până la capăt — dacă rezistă, bateți ușor cu un ciocan de cauciuc.

**1d.** Repetați cu a doua lamă și a doua pană, pe partea opusă.

**Rezultat:** Cele două lame sunt paralele, formând o fantă de lumină de lățime fixă. ✓

---

### Pasul 2 — Asamblarea suportului pentru smartphone

**Ai nevoie de:** DBS15 sau DBS16 (1×), DBS18 (1×), DBS19 (1×), NN01 (1×), BS06 (1×)

**2a.** Dacă DBS18 nu alunecă lin în DBS15/DBS16, neteziți ușor suprafețele de contact cu hârtie abrazivă. Adăugați o picătură mică de ulei.

**2b.** Introduceți DBS18 (clema) în DBS15/DBS16 (suportul).

**2c.** Introduceți DBS19 (butonul) în clipurile de retenție ale suportului, apoi treceți șurubul BS06 prin buton și suport.

**2d.** Ținând piulița NN01 în slotul clemei DBS18, înșurubați BS06 până prinde filetul piuliței.

**Rezultat:** Rotind butonul DBS19, clema se mișcă și fixează/eliberează telefonul. ✓

---

### Pasul 3 — Asamblarea corpului principal

**Ai nevoie de:** subansamblul de la Pasul 1, subansamblul de la Pasul 2, DBS01, DBS02, DBS03, DBS04, DBS05, GP01

**3a.** Introduceți subansamblul fantei (Pasul 1) în **DBS02**, cu fanta aproape de sloturile pentru cuve.

**3b.** Introduceți **DBS01 (Tubul fantă)** în DBS02 în orientarea corectă (consultați Fig. 4 din articol [1]).

**3c.** Montați **DBS03** pe **DBS04**, apoi introduceți acest ansamblu pe DBS02 + DBS01. Tubul DBS01 se va prelungi dincolo de DBS04, interblocând totul — aceasta asigură rigiditate și etanșeitate la lumina ambientală [1].

**3d.** Introduceți subansamblul smartphone (Pasul 2) pe DBS03. Introduceți **rețeaua de difracție (GP01)** în slotul lateral al DBS03.

> ⚠️ **Important:** Rețeaua de difracție trebuie introdusă cu **liniile (blazele) orizontale**. Orientarea greșită distorsionează spectrele!

**3e.** Introduceți **DBS05 (Adaptorul sursă)** pe capătul opus al DBS02.

**3f.** Apăsați ansamblul din ambele capete pentru a vă asigura că toate piesele sunt bine fixate.

**Rezultat:** Instrumentul de bază este complet asamblat! ✓

---

### Pasul 4 — Adăugarea sursei de lumină

**Configurație A – Lanternă** (spectru continuu, ideal pentru absorbție):
Montați DBS12 → DBS13 → DBS24 pe DBS05.

**Configurație B – Stilou LED** (portabil, ideal pentru emisie și calibrare):
Montați DBS11 → DBS13 → DBS14 pe DBS05.

**Configurație C – Absorbție cu cuvă:**
Adăugați DBS07 (Capacul cuvei) deasupra sloturilor pentru cuve.

**Configurație D – Fluorescență:**
Montați DBS08 + DBS09 pentru a orienta sursa perpendicular pe probă.

---

### Pasul 5 (opțional) — Asamblarea camerei USB

Dacă utilizați camera USB ELP în loc de smartphone [1]:

**5a.** Introduceți piulița NN01 în canalul lateral al DBS20.

**5b.** Conectați cablul USB la cameră conform instrucțiunilor camerei.

**5c.** Introduceți camera USB01 în DBS20 cu **obiectivul orientat în jos**, prin gaura de 12,4 mm.

**5d.** Poziționați cablul USB în canalul de susținere. Rotiți camera până cablul nu este tensionat.

**5e.** Aliniați DBS21 (capacul) și fixați cu cele 4 șuruburi SS01.

**5f.** Conectați la calculator și ajustați focusul rotind obiectivul.

---

## 6. Cum măsurăm?

### 6.1 Software necesar

**ImageJ** — gratuit, open-source, disponibil la https://imagej.nih.gov/

### 6.2 Spectroscopia de emisie (fără cuve)

Folosită pentru a studia lumina produsă direct de o sursă (bec, flacără, LED, tub de descărcare).

**Procedură:**
1. Îndreptați spectrofotometrul spre sursa de lumină
2. Porniți camera și așteptați 30 de secunde ca imaginea să se stabilizeze
3. Capturați imaginea — veți vedea banda colorată a spectrului de-a lungul imaginii
4. Dacă imaginea este supraexpusă (albă), reduceți ISO-ul sau timpul de expunere al camerei

### 6.3 Spectroscopia de absorbție (cu cuve)

Folosită pentru a studia cât de multă lumină absoarbe o soluție.

**Pregătirea probei:**
- Umpleți o cuvă cu **proba** (soluția de analizat)
- Umpleți o altă cuvă cu **referința** (apă pură sau solventul pur)
- Plasați cuva cu proba în slotul superior, referința în slotul inferior al DBS02

**Capturarea imaginii:**
1. Porniți sursa de lumină (lanternă sau stilou LED alb)
2. Așteptați 30 de secunde
3. Capturați imaginea — trebuie să fie vizibile **ambele benzi spectrale** (proba sus, referința jos)

### 6.4 Extragerea datelor în ImageJ

1. Deschideți imaginea capturată în **ImageJ**
2. Cu instrumentul **Rectangle**, selectați o bandă orizontală de **200 pixeli înălțime** pe toată lățimea imaginii
3. Mergeți la **Analyze → Plot Profile** (sau apăsați Ctrl+K)
4. În fereastra graficului, dați clic pe **"Data"** → **"Copy All Data"**
5. Lipiți datele în **Microsoft Excel** sau **LibreOffice Calc**

### 6.5 Calculul absorbanței

```
Absorbanță = −log₁₀ (intensitate_probă / intensitate_referință)
```

---

## 7. Calibrarea instrumentului

Calibrarea transformă pozițiile în pixeli din imagine în **lungimi de undă reale** (nanometri). Se face o singură dată per sesiune de lucru, **după** ce ați capturat și imaginile de măsurare și **înainte** de a analiza datele în Excel.

> ⚠️ **Important:** Nu mutați telefonul/camera după calibrare! Orice mișcare anulează calibrarea [1].

### 7.1 Surse de calibrare recomandate

| Sursă | Lungime de undă (nm) |
|-------|---------------------|
| Pointer laser roșu | ~650 nm |
| LED verde | ~520 nm |
| LED albastru | ~470 nm |
| Linii bec fluorescent | 436, 546, 578 nm |

Folosiți **două surse cu lungimi de undă cunoscute** simultan și capturați imaginea lor.

### 7.2 Calculul ecuației de calibrare

Identificați în graficul ImageJ pozițiile în pixeli ale celor două vârfuri de calibrare (p₁, p₂) și calculați [1]:

```
Pantă = (λ₂ − λ₁) / (p₂ − p₁)

λ(pixel) = Pantă × (pixel − p₁) + λ₁
```

**Exemplu concret:**
- Laserul roșu (650 nm) → pixelul 820
- LED-ul albastru (470 nm) → pixelul 340

```
Pantă = (650 − 470) / (820 − 340) = 180 / 480 = 0,375 nm/pixel

λ = 0,375 × (pixel − 340) + 470
```

Aplicați această ecuație coloanei de pixeli exportate din ImageJ pentru a obține coloana de lungimi de undă.

---

## 8. Experimente

### Experiment 1 — Spectroscopia de emisie: identificarea surselor de lumină

**Concept:** Fiecare tip de sursă de lumină produce un spectru caracteristic. Prin compararea spectrelor, putem identifica sursa și înțelege fizica din spatele acesteia.

**Obiective:**
- Să observăm și să comparăm spectrele diferitelor surse de lumină
- Să înțelegem diferența dintre spectrele continue și spectrele de linii
- Să aplicăm calibrarea pentru a identifica lungimile de undă ale liniilor spectrale

**Materiale:** Spectrofotometrul asamblat, smartphone/cameră USB, surse de lumină diverse

**Procedură:**
1. Asamblați spectrofotometrul fără cuve (mod emisie)
2. Îndreptați spre fiecare sursă pe rând
3. Capturați imaginea spectrului
4. Calibrați și exportați datele din ImageJ
5. Trasați graficul intensitate vs. lungime de undă în Excel

---

#### 1.1 Becul incandescent

**Teoria:** Becul incandescent funcționează prin încălzirea unui filament de wolfram la ~2.700°C. La această temperatură, filamentul emite radiație de corp negru — un **spectru continuu** care acoperă toate lungimile de undă vizibile, cu intensitate mai mare în roșu și infraroșu.

> **💡 Știați că?** Becul incandescent este extrem de ineficient energetic — 95% din energia consumată este emisă ca căldură (infraroșu), nu ca lumină vizibilă. De aceea a fost înlocuit de LED-uri!

*[IMAGINE: Spectrul becului incandescent — de adăugat]*

**Ce ne așteptăm să vedem:** Spectru continuu, cu intensitate crescând progresiv de la violet spre roșu. Nu există linii discrete.

---

#### 1.2 Becul fluorescent (tub cu descărcare)

**Teoria:** Becul fluorescent conține vapori de mercur excitați electric. Mercurul emite lumină la lungimi de undă precise (spectru de linii). Lumina ultravioletă produsă este convertită de stratul de pulbere fosforescente din tub în lumină vizibilă albă.

*[IMAGINE: Spectrul becului fluorescent — de adăugat]*

**Ce ne așteptăm să vedem:** Linii distincte de mercur vizibile pe un fond continuu dat de fosfor:
- 436 nm (violet)
- 546 nm (verde)
- 578 nm (galben-portocaliu)

> **💡 Știați că?** Aceste linii de mercur sunt atât de precise și reproductibile încât pot fi folosite direct pentru **calibrarea** spectrofotometrului, fără a fi nevoie de lasere sau LED-uri de referință!

---

#### 1.3 LED alb

**Teoria:** LED-ul alb nu emite de fapt alb — el combină un LED albastru (~460 nm) cu un strat de fosfor galben care transformă o parte din lumina albastră în spectru larg galben-verde-roșu.

*[IMAGINE: Spectrul LED alb — de adăugat]*

**Ce ne așteptăm să vedem:** Un vârf pronunțat în albastru (~460 nm) și o bandă largă între 500–700 nm. Spectrul nu este continuu ca cel al becului incandescent.

---

#### 1.4 LED-uri colorate (roșu, verde, albastru)

**Teoria:** Un LED colorat emite lumină aproape monocromatică — la o singură lungime de undă (sau o bandă îngustă). Lungimea de undă depinde de materialul semiconductor din care este construit.

*[IMAGINE: Spectrele LED roșu, verde, albastru — de adăugat]*

**Ce ne așteptăm să vedem:** Un singur vârf îngust la lungimea de undă caracteristică a LED-ului:
- LED roșu: ~620–660 nm
- LED verde: ~520–530 nm
- LED albastru: ~450–470 nm

> **💡 Știați că?** Inventarea LED-ului albastru eficient de către Isamu Akasaki, Hiroshi Amano și Shuji Nakamura în anii 1990 a fost atât de revoluționară încât a fost recompensată cu **Premiul Nobel pentru Fizică în 2014**. Fără LED-ul albastru nu am fi putut fabrica LED-uri albe!

---

#### 1.5 Lumina soarelui (indirectă)

**Teoria:** Soarele emite un spectru aproape continuu de corp negru la ~5.500°C. Lumina traversează atmosfera solară și terestră, unde anumiți atomi absorb lungimi de undă precise, lăsând linii negre în spectru — **liniile Fraunhofer**.

> ⚠️ **Nu îndreptați niciodată spectrofotometrul direct spre Soare! Folosiți lumina reflectată de un ecran alb mat sau o foaie de hârtie albă.**

*[IMAGINE: Spectrul luminii solare — de adăugat]*

**Ce ne așteptăm să vedem:** Spectru continuu cu linii întunecate (absorbție) la:
- 589 nm (sodiu — linia D)
- 656 nm (hidrogen — linia Hα)
- 430 nm (calciu)

---

#### 1.6 Flacăra lumânării sau a unui arzător Bunsen

**Teoria:** Flacăra emite lumină prin incandescența particulelor de carbon (fum) și prin emisiile atomice ale substanțelor arse. Adăugând săruri în flacără, putem produce linii de emisie caracteristice diferitelor elemente.

*[IMAGINE: Spectrul flacării — de adăugat]*

**Experiment suplimentar — Testul flacărei:**
- Introduceți în flacără câte puțin din: sare de bucătărie (NaCl → galben intens, 589 nm), sare de cupru (verde-albastru), sare de litiu (roșu)
- Observați cum fiecare element produce o culoare caracteristică

> **💡 Știați că?** Focurile de artificii sunt fabricate cu săruri metalice specifice pentru a produce culorile dorite: stronțiu → roșu, bariu → verde, sodiu → galben, cupru → albastru!

---

### Experiment 2 — Spectroscopia de absorbție: clorofila din frunze

**Concept:** Clorofila absoarbe selectiv anumite culori ale luminii pentru a alimenta fotosinteza.

**Materiale:** Frunze verzi, alcool (spirt) 90%, baie de apă caldă (~50°C), cuvete, filtru de cafea

**Procedură:**
1. Tăiați mărunt frunzele verzi și puneți-le în alcool la 50°C timp de 20 min (baie de apă)
2. Filtrați printr-un filtru de cafea — obțineți un extract verde intens
3. Umpleți o cuvă cu extractul, alta cu alcool pur (referință)
4. Măsurați absorbția
5. Aplicați calibrarea și trasați graficul în Excel

**Ce ne așteptăm să vedem:** Maxime de absorbție la ~430 nm (albastru) și ~680 nm (roșu). Minim de absorbție (transmisie maximă) la ~550 nm (verde — de aceea frunzele par verzi!).

---

### Experiment 3 — Legea Beer-Lambert: concentrație și absorbție

**Concept:** Cu cât o soluție este mai concentrată, cu atât absoarbe mai multă lumină — relație liniară.

**Materiale:** Cerneală albastră (sau sulfat de cupru CuSO₄), apă, 6 cuve, pipetă gradat

**Procedură:**
1. Preparați 5 soluții prin diluții succesive (1:2, 1:4, 1:8, 1:16, 1:32 față de soluția originală)
2. Măsurați absorbanța fiecăreia la lungimea de undă a maximului de absorbție
3. Trasați graficul: Absorbanță (axa Y) vs. Concentrație relativă (axa X)
4. Trasați linia de tendință — ar trebui să fie **dreaptă** (validarea legii Beer-Lambert)
5. **Provocare:** Preparați o soluție cu concentrație necunoscută și determinați-o din grafic!

---

## 9. Depanare – Ce fac dacă nu merge?

| Problema observată | Cauza probabilă | Ce fac? |
|-------------------|-----------------|---------|
| Piesele nu se potrivesc | Bavuri după imprimare | Curăț cu lamă/pilă (vezi Anexa B) [1] |
| Imaginea e neagră sau prea întunecată | Camera nealiniată sau expunere mică | Verific alinierea; cresc ISO-ul camerei |
| Imaginea e complet albă (supraexpusă) | Sursă prea puternică | Reduc ISO-ul sau timpul de expunere |
| Văd două spectre suprapuse | Rețeaua GP01 orientată greșit | Întorc rețeaua — liniile (blazele) trebuie să fie orizontale [1] |
| Spectrul e neclar, difuz | Focus greșit | Rotesc obiectivul camerei USB; curăț lentila smartphone-ului |
| Rezultatele variază între sesiuni | Camera s-a mișcat | Recalibrez la fiecare sesiune nouă [1] |
| Lumina ambientală intră în instrument | Piese necomplet introduse | Verific că toate piesele sunt bine fixate; folosesc DBS10 |
| Fanta nu e simetrică | Pana DBS23 incomplet introdusă | Bat ușor cu ciocan de cauciuc până la capăt [1] |
| Calibrarea dă valori greșite | Vârfuri de calibrare identificate greșit | Verific că p₁ corespunde lui λ₁ și p₂ lui λ₂ |

---

## 10. Referințe

[1] **Winters, B.J., Banfield, N., Dixon, C., Swensen, A., Holman, D., & Fillbrown, B. (2021).** *3D-Printable and open-source modular smartphone visible spectrophotometer.* HardwareX, 10, e00232.
https://doi.org/10.1016/j.ohx.2021.e00232

---

**Resurse suplimentare:**

| Resursă | Link |
|---------|------|
| Fișiere STL și documentație | https://osf.io/7ewb3 |
| Software ImageJ | https://imagej.nih.gov/ |
| Design CAD editabil online | https://www.onshape.com/ |
| Comunitate open-source spectroscopie | https://publiclab.org |

---

---

## Anexa A – Lista de materiale

Lista completă poate fi descărcată de la https://osf.io/7ewb3 [1].

### Piese de cumpărat (hardware)

| Cod | Ce este | Cantitate | De unde |
|-----|---------|-----------|---------|
| **GP01** | Rețea de difracție, 1000 linii/mm (set 25 buc.) | 1 | Amazon – Rainbow Symphony |
| **RS01** | Lame de bisturiu miniaturale (set 5 buc.) | 2 lame | McMaster-Carr #3806A14 |
| **BS06** | Șurub hex oțel, ¼"-20, lungime 76 mm | 1 | McMaster-Carr #91247A554 |
| **NN01** | Piuliță hex nylon, ¼"-20 | 2 | McMaster-Carr #94812A700 |
| **SS01** | Șuruburi mici inox (pentru cameră USB) | 4 | McMaster-Carr #92470A041 |

### Surse de lumină (opționale)

| Cod | Tip sursă | Observație |
|-----|-----------|------------|
| S01 | Lanternă standard | Spectru continuu — ideal pentru absorbție |
| S02–S05 | Stilouri LED (UV, roșu, albastru, alb) | Utile pentru calibrare și emisie |
| S06 | Pointer laser roșu | Lungime de undă precisă — excelent pentru calibrare |

### Cameră (alegeți una)

| Variantă | Avantaje | Dezavantaje |
|----------|----------|-------------|
| **Smartphone** | Portabil, fără calculator | Rezoluție variabilă |
| **Cameră USB ELP** (~64$) | Rezoluție mare, stabilă | Necesită calculator |

### Piese imprimate 3D (filament PLA)

| Cod | Denumire | Buc. | Rol |
|-----|----------|------|-----|
| DBS01 | Tub fantă | 1 | Ghidează fasciculul |
| DBS02 | Suport probă | 1 | Ține cuvele cu probe |
| DBS03 | Suport rețea difracție | 1 | Ține rețeaua + camera |
| DBS04 | Adaptor tub | 1 | Conectează DBS01–DBS03 |
| DBS05 | Adaptor sursă | 1 | Conectează sursa |
| DBS06 | Bloc | 2 | Structural |
| DBS07 | Capac cuvă | 1 | Mod absorbție |
| DBS08 | Capac fluorescență | 1 | Mod fluorescență |
| DBS09 | Dop | 1 | Închide o intrare |
| DBS10 | Capac lateral | 1 | Blochează lumina ambientală |
| DBS11 | Adaptor stilou LED | 1 | Conectează stiloul LED |
| DBS12 | Adaptor lanternă | 1 | Conectează lanterna |
| DBS13 | Suport sursă | 1 | Ține sursa de lumină |
| DBS14 | Suport stilou LED | 1 | Suport stilou |
| DBS15 | Suport iPhone | 1 | iPhone SE/6/7/8/X |
| DBS16 | Suport smartphone general | 1 | Cameră centrată |
| DBS17 | Suport cameră USB | 1 | Cameră USB |
| DBS18 | Clemă telefon | 2 | Fixează telefonul |
| DBS19 | Buton reglaj | 2 | Acționează clema |
| DBS20 | Bază cameră USB | 1 | Carcasă cameră |
| DBS21 | Capac cameră USB | 1 | Carcasă cameră |
| DBS22 | Suport fantă | 1 | Ține lamele |
| DBS23 | Pană fantă | 2 | Fixează lamele |
| DBS24 | Tub lanternă | 1 | Extinde tubul |
| DBS25 | Placă montare liberă | 1 | Adaptor orice cameră |

> **Notă:** Dacă folosiți doar smartphone-ul, nu imprimați DBS17, DBS20, DBS21. Dacă nu folosiți lanternă, nu imprimați DBS12, DBS24 [1].

---

## Anexa B – Imprimarea 3D a pieselor

### Setări recomandate

| Parametru | Valoare recomandată |
|-----------|---------------------|
| Material | PLA |
| Umplere (infill) | 20% |
| Suprafețe exterioare | 3 perimetri |
| Temperatură duză | 200–210°C |
| Temperatură pat | 60°C |
| Suporturi | Depinde de piesă |

### Reguli importante după imprimare [1]

> *"Componentele imprimate 3D prezintă rugozitate și bavuri la colțuri. Acestea trebuie îndepărtate cu o lamă înainte de asamblare."*
> — Winters et al. (2021) [1]

**1. Îndepărtați bavurile** — Cu o lamă de ras sau bisturiu, curățați marginile și colțurile. Este cel mai important pas pentru o asamblare corectă.

**2. Faceți piese de test** — Imprimați o piesă mică mai întâi și testați potrivirea. Fiecare imprimantă are toleranțe diferite.

**3. Orientarea pe platou contează** — Dacă o piesă nu alunecă lin, reimprimați-o rotită cu 90°. Straturile FDM pot „agăța" suprafețele glisante.

**4. Neteziți suprafețele de alunecare** — O pilă fină sau hârtie abrazivă (grit 220) pe suprafețele de contact poate face diferența.

---

*Manual elaborat pe baza articolului open-access publicat în HardwareX (Elsevier) sub licența CC BY 4.0.*
*Hardware-ul este licențiat sub CC BY-SA 4.0. Randările 3D au fost generate din fișierele STL originale.*
