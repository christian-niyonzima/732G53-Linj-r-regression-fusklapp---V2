# 732G53 Linjär regression – fusklapp inför tentan (V2)

Fusklapp i LaTeX för tentan i 732G53 (regressionsanalys). Tentaomslagen
(2024-10-25 till 2025-12-08) tillåter **två A4-blad, dubbelsidigt, dator- eller
handskrivna**. Fusklappen är därför exakt **4 sidor A4 liggande** = 2 blad
dubbelsidigt. Kontrollera reglerna på omslaget till just din tenta.

- `fusklapp_732G53.tex` – LaTeX-källan (en enda fil)
- `fusklapp_732G53.pdf` – färdig att skriva ut

## Nytt i V2

- Tabellsamlingen delas ut på tentan ⇒ t-, F- och χ²-tabellerna är borttagna. Kvar finns
  en läsguide för tabellsamlingen och normalkvantiler för QQ-plot för hand (§33).
- Sidhuvud på varje sida med sidetikett och §-intervall, plus färglegend.
- Färgkodade teman (Grund, Räkna, Inferens, Modellbygge, Diagnostik, Tenta) i
  avsnittsrubriker, register och sidhuvud.
- Verktygstabell §2 ”fråga → metod → jämför med” direkt efter registret.
- Räknarknep och svarsbladet §7 (LinReg på grafräknaren, avrundning, kontroller).
- Nya figurer: anatomi/SSY-stapel/KI–PI-band, testsvansar, polynom, kvant×kvant-interaktion,
  inflytelserika punkter, residualmönster rad 2, under-/överanpassning.
- Alla figurer 7 % större; brödtexten är oförändrad (8 pt).
- ”Enkelt:”-förklaringar på vardagssvenska vid de svåraste begreppen.
- Fler sant/falskt-påståenden.
- Facit från tidigare tentor (2024-10-25, 2025-02-28) för att kontrollera räknartekniken.
- Ingen R-kod och inget om hur man kör R – tentan skrivs på papper utan dator. Kvar finns
  bara det som alltid kommer: att *läsa* de utskrifter (koefficient- och ANOVA-tabeller) som
  delas ut i tentan. §13 översätter kolumnnamnen (`Estimate`, `Std. Error`, `t value`,
  `Pr(>|t|)`, `Residual standard error`, `Multiple/Adjusted R-squared`, `F-statistic`,
  `Df`, `Sum Sq`, `Mean Sq`, `F value`, `Pr(>F)`, `Residuals`).

### Tillägg och finputs (V2.1)

- **Snabbformel för KI/PI när tentan ger c** (§17): c = x₀'(X'X)⁻¹x₀ ⇒ KI ŷ ± t·√(MSE·c),
  PI ŷ ± t·√(MSE·(1+c)). Enkel regression: c = 1/n + (x₀ − x̄)²/Sxx. Sjukhusexemplet
  (c = 0.93): 15892 ± 1183 = [14709; 17075], så 17207 ligger utanför och sjukhuset ifrågasätts.
  Formeln finns även i verktygstabellen (§2).
- **AICc, PRESS och K-faldig korsvalidering** i måtttabellen (§26):
  AICc = AIC + 2(k+1)(k+2)/(n−k−2) (litet n), PRESS = Σ(eᵢ/(1−hᵢᵢ))² (lågt = bra prediktion,
  alltid ≥ SSE), CV = (1/K)·Σ MSEₖ (K = n ger PRESS/n).
- **För- och nackdelar** med best subsets, framåtval, bakåteliminering och stegvis regression (§26).
- **Muskelmasseuppgiften** (n = 60) som extra räkneövning med facit (§8): b₁ = −1.190,
  b₀ = 156.35, 95 % KI för β₁ = [−1.371; −1.009], PI vid x = 65: [62.5; 95.5].
- **Alternativa räkneformler** (§6): SSE = Σy² − b₀Σy − b₁Σxy och
  r = (Σxy − n·x̄ȳ)/√((Σx² − n·x̄²)(Σy² − n·ȳ²)), med varning för avrundning
  (2024-10-25: b med 3 decimaler ger SSE = 192.948 i stället för 191.702).
- Finputs: vektortypsnitt för kod (inget suddigt bitmappstypsnitt), smalare rubrikband,
  4 % tätare radavstånd, ”forts.”-markering överst vid varje sidbyte och sidhuvuden med rätt
  §-intervall. Dubbletter är ersatta med hänvisningar (Simpson och polynom → §31,
  KI- eller PI-regeln → §2). ”Kontrollera din räknarteknik” har större text.

### Genomgång av tentorna 2024-10-25 – 2025-12-08 (V2.2)

Alla fem tentor med lösningsförslag och fyra rättade, handskrivna tentor är genomgångna.
De två senaste (2025-10-23 och 2025-12-08, samma lärare) har samma upplägg: uppgift 1 är
enkel regression för hand (13–15p), uppgift 2 är modellval (5–7p); inget sant/falskt.

- **§10 följer lärarens 7 steg** (1 kontrollera antaganden, 2 hypoteser, 3 signifikansnivå,
  4 teststatistika, 5 kritiskt område, 6 uträkning, 7 beslut och tolkning) och översätter
  lösningsförslagens notation: t_{ν,α} = övre α-punkt (t_{4,0.1} = 1.533 = vår t_{4;0.90}),
  S_{Y|X} = s, S_X² = Sxx/(n−1), S_{β̂1} = S_{Y|X}/(S_X√(n−1)).
- **§3: ny figurrad** med ✓/✗-figurer för Y mot X (linjärt/krökt) och e mot i
  (oberoende/beroende). ”Redovisa visuellt hur det ser ut när antagandena är uppfyllda mot
  ej uppfyllda” gav 3p 2025-12-08.
- **§8:** d) följer lösningsförslaget (e mot i, e mot ŷ, QQ med pᵢ = (i − 0.5)/n, histogram).
  ”Kontrollera din räknarteknik” har nu 2025-12-08 uppg. 1 med exakta värden. Lösningsförslaget
  avrundade b₁ till 3.6, vilket ger ŷ(85) = 64.5 i stället för 60.42 och SSR + SSE ≠ SSY.
- **§22:** 2025-12-08 uppg. 2 (centrerade polynom): partiellt F = 15.22, tolkning och
  prediktion med centrerade värden (ŷ = 19.91).
- **§27:** för- och nackdelar för de fyra modellerna 2025-12-08.
- **§31 Tentatips:** tentaformatet 2025, en mall för uppgift 1 (a–g) och lärdomar från de
  rättade tentorna (överhoppade deluppgifter gav G; slutsatsen måste stämma med beslutet).
- **Borttaget för att få plats:** de egna ”fler troliga” sant/falskt-påståendena (allt står i
  avsnitten), utblicken om logistisk regression (har aldrig kommit på tentan) och en
  förkortad teoridel (§9). Sant/falskt-påståendena från tentorna finns kvar (§29).

## Innehåll

| Sida | Sidhuvud och avsnitt |
|---|---|
| 1 | GRUNDER & RÄKNA FÖR HAND (§1–8): index · verktyg · modell/antaganden · residualmönster · enkel regression · räknarknep · genomräknat exempel |
| 2 | INFERENS & TOLKNING (§8 forts.–17): OLS-teori · hypotesprövning · tolkningsmallar · matrisform · ANOVA · F-test · partiellt F · t-test · prediktion med c |
| 3 | MODELLBYGGE & DIAGNOSTIK (§17 forts.–25): simultan inferens · R² · indikatorer · interaktioner · polynom · inflytelserika obs. · multikollinearitet · confounding |
| 4 | MODELLVAL, TENTAFORMAT & TIPS (§26–33): AIC(c)/PRESS/CV · algoritmer · välj/utvärdera modell · sant/falskt · teorisvar · tentatips · vanliga fel · tabeller |

## Källor

- Kurssidan *Statistisk teori och tillämpningar i R*, Del II Regressionsanalys
  (<https://hietalai.github.io/statistics-in-r/01-regression/00-intro-regression.html>,
  källkod i repot `hietalai/statistics-in-r`, kapitel 1–11), särskilt kap. 6
  (polynom och interaktioner).
- Tentor med lösningsförslag 2024-10-25, 2025-01-20, 2025-02-28, 2025-10-23 och 2025-12-08,
  samt rättade, handskrivna tentor från samma tillfällen.
- Exempel på det nya svarsbladet (numeriska svar med tre decimaler i rutor, flervalsfrågor).
- Normalkvantilerna för QQ-plot, z((i − 0,5)/n), är kontrollerade numeriskt.

Några tryckfel i underlagen är rättade på fusklappen:

- Jackknife-residualen har roten över hela kvoten (som i kurssidans R-kod).
- s² i enkel regression är SSE/(n − 2). Lösningsförslaget 2024-10-25 skriver n − 1,
  men svaret 21.3 bygger på n − 2.
- 2025-12-08 uppg. 1 räknas med exakta värden (b₁ = 3.554, b₀ = −241.639, SSE = 3539.39);
  lösningsförslaget avrundade b₁ till 3.6 och fick därför ŷ(85) = 64.5 och SSR + SSE ≠ SSY.
- 2025-12-08 uppg. 2: TempC² > 0 betyder att temperatureffekten blir starkare ju varmare
  (lösningsförslaget skriver att den avtar).
- Working–Hotelling anges som på kurssidan, W² = 2·F(p, n − p) (enkel regression
  W² = 2·F(2, n − 2)); Kutner anger W² = p·F(p, n − p), vilket ger samma värde för p = 2.
  Scheffé anges som S² = g·F(g, n − p).

## Kompilera

```sh
pdflatex fusklapp_732G53.tex
pdflatex fusklapp_732G53.tex   # andra körningen fyller i §- och sidhänvisningarna
```

Fungerar även direkt i Overleaf. Paket som används: `extarticle`, `geometry`,
`fancyhdr`, `babel` (swedish), `mathptmx`, `helvet`, `amsmath`, `multicol`, `xcolor`,
`enumitem`, `booktabs`, `tabularx`, `tikz`, `newunicodechar`, `pifont`, `microtype`,
samt typsnittet Latin Modern Typewriter (`lmodern`) för kod (allt ingår i TeX Live).

Sidbytena är handjusterade med `\columnbreak` (sök på ”sidbyte” i källan). Ändrar du
innehållet före ett sidbyte: kompilera, kontrollera att det fortfarande blir exakt 4 sidor
och flytta vid behov `\columnbreak` med sin ”forts.”-markering.

## Utskrift

Skriv ut **i färg** (färgerna bär betydelse men allt går att läsa även i gråskala),
i 100 % skala (inte ”anpassa till sida”) och dubbelsidigt med
**vänd längs kortsidan**, så att baksidan blir rättvänd när bladet vänds åt sidan.
