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

## Innehåll

| Sida | Sidhuvud och avsnitt |
|---|---|
| 1 | GRUNDER & RÄKNA FÖR HAND (§1–8): index · verktyg · modell/antaganden · residualmönster · enkel regression · räknarknep · genomräknat exempel |
| 2 | INFERENS & TOLKNING (§9–19): OLS-teori · hypotesprövning · tolkningsmallar · matrisform · ANOVA · F-test · partiellt F · t-test · prediktion · simultan inferens · R² |
| 3 | MODELLBYGGE & DIAGNOSTIK (§20–26): indikatorer · interaktioner · polynom · inflytelserika obs. · multikollinearitet · confounding · modellval |
| 4 | VÄLJ MODELL, SANT/FALSKT & TENTATIPS (§27–34): välj/utvärdera modell · sant/falskt · GLM · teorisvar · tentatips · vanliga fel · tabellsamlingen |

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
`enumitem`, `booktabs`, `tabularx`, `tikz`, `newunicodechar`, `pifont`, `microtype`
(alla ingår i TeX Live).

## Utskrift

Skriv ut **i färg** (färgerna bär betydelse men allt går att läsa även i gråskala),
i 100 % skala (inte ”anpassa till sida”) och dubbelsidigt med
**vänd längs kortsidan**, så att baksidan blir rättvänd när bladet vänds åt sidan.
