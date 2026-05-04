# Spectrofotometrul cu dublă rază
## Manual de asamblare și utilizare pentru elevi și profesori

![GeoEduLab](imagini/geoedulab-logo.png)

![Spectrofotometrul cu dublă rază asamblat](imagini/montat.png)

<div class="cover-footer">

**Manual v1 · 2026** | Licență hardware: CC BY-SA 4.0

Bazat pe: Winters, B.J. et al. (2021). *3D-Printable and open-source modular smartphone visible spectrophotometer.* HardwareX, 10, e00232. https://doi.org/10.1016/j.ohx.2021.e00232

Fișiere STL și documentație: https://osf.io/7ewb3

</div>

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
9. [Depanare: Ce fac dacă nu merge?](#9-depanare-ce-fac-daca-nu-merge)
10. [Referințe](#10-referinte)


---

## 1. Ce este lumina?

Lumina este o formă de energie care călătorește sub formă de unde electromagnetice. Ceea ce vedem cu ochii noștri, culorile curcubeului, de la violet la roșu, reprezintă doar o mică porțiune dintr-un spectru mult mai larg.

```
Lungimea de undă (nm):
  100        400   450   500   550   600   650   700       1000+
   |          |     |     |     |     |     |     |          |
[UV extrem] [Violet][Albastru][Verde][Galben][Portocaliu][Roșu] [Infraroșu]
             ←——————— Vizibil pentru ochiul uman (380–700 nm) ————————→
```

> **💡 Știați că?**
> Curcubeul nu este altceva decât lumina soarelui separată în culorile sale componente de picăturile de ploaie, care acționează ca niște prisme minuscule. Spectrofotometrul nostru face același lucru, dar în laborator!

---

> **💡 Știați că? Corpul uman emite lumină!**
> Orice obiect cu o temperatură mai mare de −273°C (zero absolut) emite radiație electromagnetică. Corpul uman, la ≈37°C, emite lumină **infraroșie**, invizibilă ochiului, dar detectabilă cu camere termice. Acest fenomen se numește **radiație de corp negru** (*black body radiation*), descris de fizicianul Max Planck în 1900.
>
> Cu cât un obiect este mai cald, cu atât lungimea de undă dominantă este mai scurtă:
> - Corpul uman (≈37°C) → infraroșu (≈9.000 nm)
> - Un fier înroșit (≈700°C) → roșu vizibil (≈700 nm)
> - Soarele (≈5.500°C) → galben-verde (≈500 nm)
> - O stea albastră fierbinte (≈20.000°C) → ultraviolet
>
> Spectroscopia ne permite să „citim" temperatura și compoziția chimică a oricărei surse de lumină!

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

> **💡 Știați că? Fiecare atom are o „amprentă digitală" de lumină!**
> Atomii emit și absorb lumină numai la anumite lungimi de undă precise, ca un cod de bare unic. Aceasta a permis oamenilor de știință să descopere elementele chimice din **Soare și stele** fără să le viziteze vreodată! De exemplu, heliul a fost descoperit mai întâi pe Soare (în 1868) și abia 27 de ani mai târziu pe Pământ.

Această capacitate face spectrofotometrul util în:
- **Chimie:** determinarea concentrației soluțiilor
- **Biologie:** analiza pigmenților, clorofilei, proteinelor
- **Astronomie:** identificarea elementelor din stele
- **Criminalistică:** analiza urmelor de substanțe
- **Industria alimentară:** controlul calității

Spectrofotometrele comerciale costă între **400 și 6.000 de euro** [1]. Cel pe care îl construim noi costă **aproximativ 25 de euro** pentru piese și folosește **smartphone-ul** ca detector, fără să sacrifice precizia [1].

---

## 3. Cum funcționează spectrofotometrul nostru?

Spectrofotometrul DBS (*Double-Beam Spectrophotometer*, Spectrofotometru cu Dublă Rază) funcționează astfel:

```
  SURSA DE LUMINA
       │
       ▼
  [Fanta ingusta]  ← imprimata 3D (card DBS23)
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
  [Ochi]            → spectru vizibil direct in imagine
```

**Notă pentru spectroscopia de emisie:** Când studiem lumina emisă direct de o sursă (bec, flacără, plasmă), nu mai este nevoie de cuve cu probe. Îndreptăm spectrofotometrul direct spre sursă și observăm spectrul de emisie al acesteia.

### Ce este rețeaua de difracție?

O rețea de difracție este o suprafață cu mii de linii paralele gravate pe milimetru. Când lumina lovește aceste linii, diferitele lungimi de undă (culori) sunt deviate în unghiuri diferite, exact ca o prismă, dar mai eficient. Rețeaua noastră are **1000 de linii pe milimetru** [1].

### De ce „dublă rază"?

Designul cu două raze este esențial pentru precizie în spectroscopia de absorbție [1]:
- **Raza superioară** trece prin **proba** de analizat
- **Raza inferioară** trece prin **referință** (apă pură sau solvent)

Camera captează ambele raze simultan în aceeași imagine. Comparând cele două spectre, eliminăm erorile cauzate de fluctuațiile sursei de lumină.

### Legea Beer-Lambert: relația dintre culoare și concentrație

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

### 4.1 Tubul fantă (DBS01)

![DBS01 – Tub fantă](imagini/DBS01.png)
*Tub dreptunghiular alungit cu capătul tăiat în unghi; fața oblică permite intrarea luminii din fantă și o îndreaptă spre probă.*

**Rol:** Ghidează lumina de la sursă spre probă, menținând fasciculul îngust și drept. Se montează în Suportul probă și se interblocă cu Adaptorul tub (DBS04) pentru rigiditate.

---

### 4.2 Suportul probă și suportul fantei (DBS02)

![DBS02 – Suport probă](imagini/DBS02.png)
*Bloc dreptunghiular masiv cu două compartimente vizibile în partea dreaptă sus; acestea sunt sloturile pentru cuvele cu probă și referință. DBS02 găzduiește totodată subansamblul fantei (penele DBS23 cu lamele de bisturiu).*

**Rol:** Piesa centrală a instrumentului. Conține două sloturi pentru cuve (probă și referință) și găzduiește direct subansamblul fantei (DBS23 + lame). Lumina trece prin fantă și prin ambele cuve simultan, creând cele două raze.

---

### 4.3 Suportul rețelei de difracție (DBS03)

![DBS03 – Suport rețea difracție](imagini/DBS03.png)
*Placă dreptunghiulară cu o fereastră/deschidere centrală prin care se introduce rețeaua de difracție. Marginile în trepte asigură fixarea precisă a unghiului față de fasciculul de lumină.*

**Rol:** Ține rețeaua de difracție (foița cu 1000 linii/mm) în unghiul corect față de fasciculul de lumină. Pe el se montează și suportul pentru cameră/smartphone.

---

### 4.4 Adaptorul tub (DBS04)

![DBS04 – Adaptor tub](imagini/DBS04.png)
*Cutie cubică cu o față tăiată în unghi și deschisă; creează camera întunecată dintre suportul probei și rețeaua de difracție, izolând fasciculul de lumina ambientală.*

**Rol:** Face legătura mecanică între Suportul probă și Suportul rețelei de difracție. Tubul fantă (DBS01) se prelungește prin acesta și se interblocă cu DBS03, asigurând rigiditate și etanșeitate la lumina ambientală [1].

---

### 4.5 Adaptorul sursă (DBS05)

![DBS05 – Adaptor sursă](imagini/DBS05.png)
*Bloc cubic cu o deschidere ovală pe fața frontală (pentru sursa de lumină) și un mâner/suport pe partea superioară. Forma ovală centrează fasciculul de lumină spre fantă.*

**Rol:** Se montează pe capătul suportului probă dinspre sursa de lumină. Adaptează diferite tipuri de surse (lanternă, stilou LED) la corpul instrumentului.

---

### 4.6 Cardul cu fantă (DBS23)

![DBS23 – Card fantă](imagini/DBS23.png)

*Placă subțire dreptunghiulară cu colțuri rotunjite și o fantă orizontală îngustă în centru, imprimată 3D. Se montează înaintea probei în Suportul probă (DBS02).*

**Rol:** Cardul are **fanta de lumină**, cea mai delicată parte a instrumentului. Aceasta este imprimată 3D direct în card. Lățimea fantei determină rezoluția spectrală.

> **💡 Experimentați!** Se pot realiza diferite fante din carton negru cu ajutorul unui cutter. Astfel puteți testa importanța dimensiunii fantei: o fantă mai îngustă oferă rezoluție spectrală mai bună, dar lasă să treacă mai puțină lumină.

---

### 4.7 Cuve (CV01)

![Cuve de unică folosință PMMA macro 2,5–4,5 ml](imagini/CV01.png)

*Cuve de unică folosință din PMMA (Polimetacrilat de metil), volum 2,5–4,5 ml, cu drum optic standard de 10 mm.*

**Rol:** Conțin probele lichide (și soluția de referință) în timpul măsurătorilor de absorbție. Cuvele PMMA sunt transparente în domeniul vizibil (380–700 nm) și sunt de unică folosință, prevenind contaminarea încrucișată între experimente.

---

## 5. Asamblarea pas cu pas

![Spectrofotometrul asamblat](imagini/montat.png)
*Spectrofotometrul complet asamblat. Se observă fanta de lumină (deschiderea dreptunghiulară albă) pe fața frontală și suportul pentru cameră/smartphone montat deasupra corpului principal.*

### Pasul 1: Montarea cardului cu fantă

Fanta de lumină este **imprimată 3D direct** în cardul DBS23, care se introduce în Suportul probă (DBS02).

**Ai nevoie de:** DBS02 (1×), DBS23 (1×)

**1a.** Verificați că DBS02 și DBS23 sunt curate și fără bavuri după imprimare.

**1b.** Introduceți cardul DBS23 în slotul corespunzător din DBS02, înaintea poziției probei. Fanta trebuie să fie centrată și orizontală.

**1c.** Apăsați ușor până cardul stă ferm în slot.

**Rezultat:** Cardul cu fantă este montat; lumina va trece prin fanta imprimată spre cuve. ✓

> **💡 Alternativă:** Puteți înlocui cardul imprimat cu unul decupat din carton negru cu un cutter, pentru a testa diferite lățimi ale fantei, înțelegând cum funcționează un spectrofotometru profesional în funcție de intensitatea luminii.

---

### Pasul 2: Asamblarea corpului principal

**Ai nevoie de:** subansamblul de la Pasul 1, DBS01, DBS02, DBS03, DBS04, DBS05, GP01

**2a.** Introduceți subansamblul fantei (Pasul 1) în **DBS02**, cu fanta aproape de sloturile pentru cuve.

**2b.** Introduceți **DBS01 (Tubul fantă)** în DBS02 în orientarea corectă (consultați Fig. 4 din articol [1]).

**2c.** Montați **DBS03** pe **DBS04**, apoi introduceți acest ansamblu pe DBS02 + DBS01. Tubul DBS01 se va prelungi dincolo de DBS04, interblocând totul; aceasta asigură rigiditate și etanșeitate la lumina ambientală [1].

**2d.** Introduceți **rețeaua de difracție (GP01)** în slotul lateral al DBS03.

> ⚠️ **Important:** Rețeaua de difracție trebuie introdusă cu **liniile (blazele) orizontale**. Orientarea greșită distorsionează spectrele!

**2e.** Introduceți **DBS05 (Adaptorul sursă)** pe capătul opus al DBS02.

**2f.** Apăsați ansamblul din ambele capete pentru a vă asigura că toate piesele sunt bine fixate.

**Rezultat:** Instrumentul de bază este complet asamblat! ✓

![Spectrofotometru asamblat](imagini/montat.png)
*Spectrofotometru complet asamblat. Fanta de lumină (deschiderea dreptunghiulară albă) este vizibilă pe fața frontală, cu suportul pentru cameră/smartphone montat pe partea superioară a corpului principal.*

---

## 6. Cum măsurăm?

### 6.1 Spectroscopia de emisie (fără cuve)

Folosită pentru a studia lumina produsă direct de o sursă (bec, flacără, LED, tub de descărcare).

**Procedură:**
1. Îndreptați spectrofotometrul spre sursa de lumină
2. Porniți camera și așteptați 30 de secunde ca imaginea să se stabilizeze
3. Capturați imaginea; veți vedea banda colorată a spectrului de-a lungul imaginii
4. Dacă imaginea este supraexpusă (albă), reduceți ISO-ul sau timpul de expunere al camerei

### 6.2 Spectroscopia de absorbție (cu cuve)

Folosită pentru a studia cât de multă lumină absoarbe o soluție.

**Pregătirea probei:**
- Umpleți o cuvă cu **proba** (soluția de analizat)
- Umpleți o altă cuvă cu **referința** (apă pură sau solventul pur)
- Plasați cuva cu proba în slotul superior, referința în slotul inferior al DBS02

**Capturarea imaginii:**
1. Porniți sursa de lumină (lanternă sau stilou LED alb)
2. Așteptați 30 de secunde
3. Capturați imaginea; trebuie să fie vizibile **ambele benzi spectrale** (proba sus, referința jos)

### 6.3 Software și extragerea datelor

**ImageJ**, gratuit, open-source, disponibil la https://imagej.nih.gov/

1. Deschideți imaginea capturată în **ImageJ**
2. Cu instrumentul **Rectangle**, selectați o bandă orizontală de **200 pixeli înălțime** pe toată lățimea imaginii
3. Mergeți la **Analyze → Plot Profile** (sau apăsați Ctrl+K)
4. În fereastra graficului, dați clic pe **"Data"** → **"Copy All Data"**
5. Lipiți datele în **Microsoft Excel** sau **LibreOffice Calc**

### 6.4 Calculul absorbanței

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
| Pointer laser roșu | ≈650 nm |
| LED verde | ≈520 nm |
| LED albastru | ≈470 nm |
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

### Experiment 1: Spectroscopia de emisie — identificarea surselor de lumină

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

**Teoria:** Becul incandescent funcționează prin încălzirea unui filament de wolfram la ≈2.700°C. La această temperatură, filamentul emite radiație de corp negru, un **spectru continuu** care acoperă toate lungimile de undă vizibile, cu intensitate mai mare în roșu și infraroșu.

> **💡 Știați că?** Becul incandescent este extrem de ineficient energetic: 95% din energia consumată este emisă ca căldură (infraroșu), nu ca lumină vizibilă. De aceea a fost înlocuit de LED-uri!

*[IMAGINE: Spectrul becului incandescent, de adăugat]*

**Ce ne așteptăm să vedem:** Spectru continuu, cu intensitate crescând progresiv de la violet spre roșu. Nu există linii discrete.

---

#### 1.2 Becul fluorescent (tub cu descărcare)

**Teoria:** Becul fluorescent conține vapori de mercur excitați electric. Mercurul emite lumină la lungimi de undă precise (spectru de linii). Lumina ultravioletă produsă este convertită de stratul de pulbere fosforescente din tub în lumină vizibilă albă.

*[IMAGINE: Spectrul becului fluorescent, de adăugat]*

**Ce ne așteptăm să vedem:** Linii distincte de mercur vizibile pe un fond continuu dat de fosfor:
- 436 nm (violet)
- 546 nm (verde)
- 578 nm (galben-portocaliu)

> **💡 Știați că?** Aceste linii de mercur sunt atât de precise și reproductibile încât pot fi folosite direct pentru **calibrarea** spectrofotometrului, fără a fi nevoie de lasere sau LED-uri de referință!

---

#### 1.3 LED alb

**Teoria:** LED-ul alb nu emite de fapt alb; el combină un LED albastru (≈460 nm) cu un strat de fosfor galben care transformă o parte din lumina albastră în spectru larg galben-verde-roșu.

*[IMAGINE: Spectrul LED alb, de adăugat]*

**Ce ne așteptăm să vedem:** Un vârf pronunțat în albastru (≈460 nm) și o bandă largă între 500–700 nm. Spectrul nu este continuu ca cel al becului incandescent.

---

#### 1.4 LED-uri colorate (roșu, verde, albastru)

**Teoria:** Un LED colorat emite lumină aproape monocromatică, la o singură lungime de undă (sau o bandă îngustă). Lungimea de undă depinde de materialul semiconductor din care este construit.

*[IMAGINE: Spectrele LED roșu, verde, albastru, de adăugat]*

**Ce ne așteptăm să vedem:** Un singur vârf îngust la lungimea de undă caracteristică a LED-ului:
- LED roșu: ≈620–660 nm
- LED verde: ≈520–530 nm
- LED albastru: ≈450–470 nm

> **💡 Știați că?** Inventarea LED-ului albastru eficient de către Isamu Akasaki, Hiroshi Amano și Shuji Nakamura în anii 1990 a fost atât de revoluționară încât a fost recompensată cu **Premiul Nobel pentru Fizică în 2014**. Fără LED-ul albastru nu am fi putut fabrica LED-uri albe!

---

#### 1.5 Lumina soarelui (indirectă)

**Teoria:** Soarele emite un spectru aproape continuu de corp negru la ≈5.500°C. Lumina traversează atmosfera solară și terestră, unde anumiți atomi absorb lungimi de undă precise, lăsând linii negre în spectru, **liniile Fraunhofer**.

> ⚠️ **Nu îndreptați niciodată spectrofotometrul direct spre Soare! Folosiți lumina reflectată de un ecran alb mat sau o foaie de hârtie albă.**

*[IMAGINE: Spectrul luminii solare, de adăugat]*

**Ce ne așteptăm să vedem:** Spectru continuu cu linii întunecate (absorbție) la:
- 589 nm (sodiu, linia D)
- 656 nm (hidrogen, linia Hα)
- 430 nm (calciu)

---

#### 1.6 Flacăra lumânării sau a unui arzător Bunsen

**Teoria:** Flacăra emite lumină prin incandescența particulelor de carbon (fum) și prin emisiile atomice ale substanțelor arse. Adăugând săruri în flacără, putem produce linii de emisie caracteristice diferitelor elemente.

*[IMAGINE: Spectrul flacării, de adăugat]*

**Experiment suplimentar: Testul flacărei:**
- Introduceți în flacără câte puțin din: sare de bucătărie (NaCl → galben intens, 589 nm), sare de cupru (verde-albastru), sare de litiu (roșu)
- Observați cum fiecare element produce o culoare caracteristică

> **💡 Știați că?** Focurile de artificii sunt fabricate cu săruri metalice specifice pentru a produce culorile dorite: stronțiu → roșu, bariu → verde, sodiu → galben, cupru → albastru!

---

### Experiment 2: Spectroscopia de absorbție — clorofila din frunze

**Concept:** Clorofila absoarbe selectiv anumite culori ale luminii pentru a alimenta fotosinteza.

**Materiale:** Frunze verzi, alcool (spirt) 90%, baie de apă caldă (≈50°C), cuvete, filtru de cafea

**Procedură:**
1. Tăiați mărunt frunzele verzi și puneți-le în alcool la 50°C timp de 20 min (baie de apă)
2. Filtrați printr-un filtru de cafea; obțineți un extract verde intens
3. Umpleți o cuvă cu extractul, alta cu alcool pur (referință)
4. Măsurați absorbția
5. Aplicați calibrarea și trasați graficul în Excel

**Ce ne așteptăm să vedem:** Maxime de absorbție la ≈430 nm (albastru) și ≈680 nm (roșu). Minim de absorbție (transmisie maximă) la ≈550 nm (verde, de aceea frunzele par verzi!).

> **💡 Știați că? Fotosinteza „preferă" anumite culori!**
> Clorofila din frunze absoarbe cu precădere lumina **roșie** (≈680 nm) și **albastră** (≈430 nm), iar lumina **verde** este reflectată, de aceea plantele ne par verzi! Cu spectrofotometrul nostru putem măsura exact această absorbție.

---

### Experiment 3: Legea Beer-Lambert — concentrație și absorbție

**Concept:** Cu cât o soluție este mai concentrată, cu atât absoarbe mai multă lumină; relație liniară.

**Materiale:** Cerneală albastră (sau sulfat de cupru CuSO₄), apă, 6 cuve, pipetă gradat

**Procedură:**
1. Preparați 5 soluții prin diluții succesive (1:2, 1:4, 1:8, 1:16, 1:32 față de soluția originală)
2. Măsurați absorbanța fiecăreia la lungimea de undă a maximului de absorbție
3. Trasați graficul: Absorbanță (axa Y) vs. Concentrație relativă (axa X)
4. Trasați linia de tendință; ar trebui să fie **dreaptă** (validarea legii Beer-Lambert)
5. **Provocare:** Preparați o soluție cu concentrație necunoscută și determinați-o din grafic!

---

## 9. Depanare: Ce fac dacă nu merge?

| Problema observată | Cauza probabilă | Ce fac? |
|-------------------|-----------------|---------|
| Piesele nu se potrivesc | Bavuri după imprimare | Curăț cu lamă/pilă (vezi Anexa B) [1] |
| Imaginea e neagră sau prea întunecată | Camera nealiniată sau expunere mică | Verific alinierea; cresc ISO-ul camerei |
| Imaginea e complet albă (supraexpusă) | Sursă prea puternică | Reduc ISO-ul sau timpul de expunere |
| Văd două spectre suprapuse | Rețeaua GP01 orientată greșit | Întorc rețeaua; liniile (blazele) trebuie să fie orizontale [1] |
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
