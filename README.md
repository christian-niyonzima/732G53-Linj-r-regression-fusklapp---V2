# 732G53 Linjär regression – fusklapp inför tentan (V2)

Fusklapp i LaTeX för tentan i 732G53 (regressionsanalys). Tentaomslagen
(2024-10-25 till 2025-10-23) tillåter **två A4-blad, dubbelsidigt, dator- eller
handskrivna**. Fusklappen är därför exakt **4 sidor A4 liggande** = 2 blad
dubbelsidigt. Kontrollera reglerna på omslaget till just din tenta.

- `fusklapp_732G53.tex` – LaTeX-källan (en enda fil)
- `fusklapp_732G53.pdf` – färdig att skriva ut

## Nytt i V2

- Tabellsamlingen delas ut på tentan ⇒ t-, F- och χ²-tabellerna är borttagna. Kvar finns
  en läsguide för tabellsamlingen och normalkvantiler för QQ-plot för hand (§34).
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
- Ingen R-kod; läsning av R-utskrifter (koefficient- och ANOVA-tabeller) finns kvar.

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

## Innehåll

| Sida | Sidhuvud och avsnitt |
|---|---|
| 1 | GRUNDER & RÄKNA FÖR HAND (§1–8): index · verktyg · modell/antaganden · residualmönster · enkel regression · räknarknep · genomräknat exempel |
| 2 | INFERENS & TOLKNING (§8 forts.–18): OLS-teori · hypotesprövning · tolkningsmallar · matrisform · ANOVA · F-test · partiellt F · t-test · prediktion med c · simultan inferens |
| 3 | MODELLBYGGE & DIAGNOSTIK (§18 forts.–26): R² · indikatorer · interaktioner · polynom · inflytelserika obs. · multikollinearitet · confounding · modellval (AICc, PRESS, CV) |
| 4 | VÄLJ MODELL, SANT/FALSKT & TENTATIPS (§26 forts.–34): algoritmer för/nackdelar · välj/utvärdera modell · sant/falskt · GLM · teorisvar · tentatips · vanliga fel · tabeller |

## Källor

- Kurssidan *Statistisk teori och tillämpningar i R*, Del II Regressionsanalys
  (<https://hietalai.github.io/statistics-in-r/01-regression/00-intro-regression.html>,
  källkod i repot `hietalai/statistics-in-r`, kapitel 1–11), särskilt kap. 6
  (polynom och interaktioner).
- Tentor med lösningsförslag 2024-10-25, 2025-01-20, 2025-02-28 samt tentan 2025-10-23.
  Lösningarna till 2025-10-23 är egna uträkningar (inget officiellt lösningsförslag).
- Exempel på det nya svarsbladet (numeriska svar med tre decimaler i rutor, flervalsfrågor).
- Normalkvantilerna för QQ-plot, z((i − 0,5)/n), är kontrollerade numeriskt.

Några tryckfel i underlagen är rättade på fusklappen:

- Jackknife-residualen har roten över hela kvoten (som i kurssidans R-kod).
- s² i enkel regression är SSE/(n − 2). Lösningsförslaget 2024-10-25 skriver n − 1,
  men svaret 21.3 bygger på n − 2.
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
