# Enova CCS-regnestykket

Et nettverktøy som viser hvor mye karbonfangst og -lagring (CCS) Enovas foreslåtte ramme kan finansiere, med justerbare forutsetninger. Første versjon dekker avfallsforbrenning.

## Slik virker det

`Topp100_CO2_2023.xlsx` er datakilden. Siden (`index.html`) leser regnearket direkte i nettleseren og regner alt ut fra det. For å oppdatere tallene: last opp en ny versjon av regnearket med samme filnavn, så bruker siden de nye tallene.

Arket leses etter etiketter, ikke etter faste celleadresser:

- **Anlegg:** en celle med teksten `Anlegg` starter anleggslisten. Kolonnen med overskrift som inneholder `Fossil` gir fossile utslipp. Listen leses til raden `Totalt`.
- **Forutsetninger:** tallet til høyre for etikettene `Fossil andel`, `Fangstgrad`, `Budpris`, `Antall år driftsstøtte` og `Total ramme` brukes. Årstallene i `Total ramme for Enova 2027-2032` gir rammeperioden.
- **Topp 100-listen:** en celle med teksten `Utslipper` starter listen, med kolonnene `Tonn CO2`, `Sektor` og `Undersektor`. Anlegg herfra kan legges til i verktøyet.

Formlene i regnearket brukes ikke; verktøyet regner selv ut fra grunntallene.

I verktøyet kan man også laste inn en annen Excel-fil fra egen maskin uten å endre noe her.

## Publisere

Gå til **Settings → Pages**, velg **Deploy from a branch**, deretter `main` og `/ (root)`. Siden blir tilgjengelig på `https://<brukernavn>.github.io/<repo>/`.
