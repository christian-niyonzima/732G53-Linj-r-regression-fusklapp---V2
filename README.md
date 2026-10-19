# 732G53 Linjär regression – fusklapp inför tentan

Fusklapp i LaTeX för tentan i 732G53 (regressionsanalys). Tentaomslagen
(2024-10-25 till 2025-10-23) tillåter **två A4-blad, dubbelsidigt, dator- eller
handskrivna**. Fusklappen är därför exakt **4 sidor A4 liggande** = 2 blad
dubbelsidigt. Kontrollera reglerna på omslaget till just din tenta.

- `fusklapp_732G53.tex` – LaTeX-källan (en enda fil)
- `fusklapp_732G53.pdf` – färdig att skriva ut

## Innehåll

| Sida | Avsnitt |
|---|---|
| 1 | Hitta rätt avsnitt (frågetyp → §), modell och antaganden + hur de kontrolleras (med små schematiska residualdiagram), läsa QQ-plot/residualmönster, spridningsdiagram, enkel linjär regression för hand, **helt genomräknad tenta 2025-10-23 uppg. 1** (n = 6: b0, b1, ANOVA, t-test, F-test, KI/PI, residualer, leverage, Cook), OLS-teori |
| 2 | Hypotesprövningens steg, tolkningsmallar (svenska formuleringar), matrisform, ANOVA-tabell och R-utskrifter (sekventiella SS), F-test, partiellt F-test (med tentaexempel), t-test, prediktion, simultan inferens (Bonferroni, Working–Hotelling, Scheffé), R² och justerad R², indikatorvariabler, interaktioner, polynom/centrering/transformationer |
| 3 | Leverage, jackknife, DFFITS, Cook's distance (gränsvärden och hantering), multikollinearitet/VIF/GVIF, confounding och Simpsons paradox, modellval och validering (R²a, Cp, AIC, MSPR, stegvisa algoritmer), **lösningsskiss tenta 2025-10-23 uppg. 2** (välj modell), mall för ”Är modellen bra och lämplig?”, **alla sant/falskt-påståenden från tidigare tentor** med facit |
| 4 | Kort om logistisk regression/GLM, korta modellsvar på teorifrågor, tentatips, vanliga fel, tabeller: t (inkl. Bonferroni-kolumn), F 5 % / 10 % / 1 %, χ², normalkvantiler för QQ-plot för hand, tabellavläsning och interpolering |

## Källor

- Kurssidan *Statistisk teori och tillämpningar i R*, Del II Regressionsanalys
  (<https://hietalai.github.io/statistics-in-r/01-regression/00-intro-regression.html>,
  källkod i repot `hietalai/statistics-in-r`, kapitel 1–11).
- Tentor med lösningsförslag 2024-10-25, 2025-01-20, 2025-02-28 samt tentan 2025-10-23.
  Lösningarna till 2025-10-23 är egna uträkningar (inget officiellt lösningsförslag).
- Kritiska värden i tabellerna är beräknade med `scipy.stats`.

Några tryckfel i underlagen är rättade på fusklappen:

- Jackknife-residualen har roten över hela kvoten (som i kurssidans R-kod).
- s² i enkel regression är SSE/(n − 2). Lösningsförslaget 2024-10-25 skriver n − 1,
  men svaret 21.3 bygger på n − 2.
- Working–Hotelling och Scheffé anges som W² = p·F(p, n − p) och S² = g·F(g, n − p).
  För enkel regression blir W² = 2·F(2, n − 2), precis som på kurssidan.

## Kompilera

```sh
pdflatex fusklapp_732G53.tex
pdflatex fusklapp_732G53.tex   # andra körningen fyller i §-hänvisningarna
```

Fungerar även direkt i Overleaf. Paket som används: `extarticle`, `geometry`,
`babel` (swedish), `mathptmx`, `helvet`, `amsmath`, `multicol`, `xcolor`,
`enumitem`, `booktabs`, `tabularx`, `tikz`, `newunicodechar`, `pifont`, `microtype`
(alla ingår i TeX Live).

## Utskrift

Skriv ut i 100 % skala (inte ”anpassa till sida”) och dubbelsidigt med
**vänd längs kortsidan**, så att baksidan blir rättvänd när bladet vänds åt sidan.
