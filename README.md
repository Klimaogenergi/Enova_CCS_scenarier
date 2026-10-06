# Budsjettkalkulator for CCS (Beta)

Et nettverktøy som viser hvor mye karbonfangst og -lagring (CCS) Enovas foreslåtte ramme kan finansiere, med justerbare forutsetninger. Første versjon dekker avfallsforbrenning.

## Slik virker det

`Topp100_CO2_2023.xlsx` og `Utslipp_Bio_co2_2023.xlsx` er datakildene. Siden (`index.html`) leser regnearket direkte i nettleseren og regner alt ut fra det. For å oppdatere tallene: last opp en ny versjon av regnearkene med samme filnavn, så bruker siden de nye tallene.

Arket leses etter etiketter, ikke etter faste celleadresser:

- **Anlegg:** en celle med teksten `Anlegg` starter anleggslisten. Kolonnen med overskrift som inneholder `Fossil` gir fossile utslipp. Listen leses til raden `Totalt`.
- **Forutsetninger:** tallet til høyre for etikettene `Fossil andel`, `Fangstgrad` og `Antall år driftsstøtte` brukes. Budpris og ramme leses ikke fra arket: standard budpris er 2 000 kr/t, i tråd med Enovas anslag på 1 200–2 500 kr per netto unngått tonn i høringsnotatet, og standard ramme er 4 mrd kr. Årstallene i `Total ramme for Enova 2027-2032` gir rammeperioden.
- **Biogent CO₂:** `Utslipp_Bio_co2_2023.xlsx` er en utskrift fra norskeutslipp.no (karbondioksid, biomasse). Kolonnene `Anleggsnavn`, `År`, `Årlig utslipp til luft` og `Enhet` brukes, og tallene for 2023 kobles til anleggene på navn. Avfallsanlegg uten rapportert tall får et anslag ut fra `Fossil andel`.
- **Topp 100-listen:** en celle med teksten `Utslipper` starter listen, med kolonnene `Tonn CO2`, `Sektor` og `Undersektor`. Anlegg herfra kan legges til i verktøyet.

Utbetalingsprofilen (vedtaksår, byggetid og andel utbetalt i byggefasen) følger høringsnotatets kapittel 9.2 og stilles inn i verktøyet.

Formlene i regnearket brukes ikke; verktøyet regner selv ut fra grunntallene.

I verktøyet kan man også laste inn en annen Excel-fil fra egen maskin uten å endre noe her.

## Publisere

Gå til **Settings → Pages**, velg **Deploy from a branch**, deretter `main` og `/ (root)`. Siden blir tilgjengelig på `https://<brukernavn>.github.io/<repo>/`.
