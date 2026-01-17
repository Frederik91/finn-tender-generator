# Oppskrift for annonse i OpenCode

Start alltid med å lese `brukerprofil.md` og `AGENTS.md` før resten av oppskriften. Dette sikrer at standard lokasjon/levering og overordnede retningslinjer er lastet inn.

Dette dokumentet dirigerer AI-en gjennom hele arbeidsflyten og ber brukeren om informasjon underveis. Bruk det som en steg-for-steg oppskrift i en pågående chat.

## 0) Opprett mappe og malfil
Ved oppstart: opprett en ny mappe med denne strukturen. AI avgjør `<kort-navn>` basert på beskrivelsen brukeren gir av det som skal selges:

annonser/
  <dato>-<kort-navn>/
    bilder/
    notater/
      input.md
      kilder.md
      utkast.md

Bruk skandinaviske bokstaver (æ, ø, å) i all annonsetekst og brukerrettet tekst.

Lag `input.md` som en mal brukeren fyller ut:

---
PRODUKTNAVN/MODELL:
TILSTAND:
STED:
LEVERING (HENTING/SENDING):
PRIS (HVIS KJENT):
ALDER/KJØPSÅR:
STØRRELSE/DIMENSJONER:
FARGE/MATERIALE:
TILBEHØR/MANGLER:
ANNET:
---

## 1) Start og mål
Mål: Lage ferdig annonseutkast for Finn.no som kan kopieres direkte inn i feltene.

Be bruker om:
- Legg inn produktbilder i `bilder/`
- Fyll ut `notater/input.md`

Hvis `brukerprofil.md` finnes:
- Bruk den som standard for lokasjon og levering
- Spør kun hvis feltene er tomme

Hvis bilder er i HEIC eller annet ikke-lesbart format:
- Konverter til JPG/PNG med MCP-serveren `image-convertor-mcp`

Mål: Bruker gjør minst mulig, AI finner mest mulig selv.

Hvis bruker bare har bilder:
- Be om bekreftelse på merke/modell og tilstand

## 2) Minimal input fra bruker
Spørsmål (i denne rekkefølgen):
1. Hva selger du (navn/modell)?
2. Hvilken tilstand (ny, pent brukt, brukt, defekt)?
3. Hvor er varen (sted) og hvordan kan den leveres (henting, sending)?
4. Om du vet: ca pris du ønsker?

Aksepter "vet ikke". Merk ukjent som "ikke oppgitt".

Oppdater `notater/input.md` med svarene hvis bruker ikke fyller den selv.

## 3) Supplerende detaljer (valgfritt)
Spørsmål:
- Alder eller kjøpsår, hvis kjent?
- Størrelse/dimensjoner?
- Farge/materiale?
- Viktige funksjoner, tilbehør eller mangler?
- Tekniske spesifikasjoner (hvis relevant for produktet)?

Hvis bruker ikke vet, gå videre uten å presse. Oppdater `notater/input.md`.

## 4) Oppslag av produktinfo og bildekontroll (valgfritt)
Hvis produktnavn/modell er nok til oppslag:
- Slå opp nypris, dimensjoner, materialer, modellvariant
- Noter kilder kort og nøkternt i `notater/kilder.md`

Bildekontroll (kort, tidlig i runden):
- Sjekk etter synlige merker, skader eller avflassing (spesielt bakside/oppheng)
- Noter funn i `notater/input.md` og i beskrivelsen

Hvis ikke: hopp over.

## 5) Markedssjekk for pris (valgfritt)
Hvis MCP-server for Finn.no er tilgjengelig:
- Finn 3-5 relevante treff
- Estimer prisintervall
- Noter korte funn som grunnlag i `notater/kilder.md`

Hvis ikke: gi et konservativt prisforslag basert på tilstand og nypris (hvis kjent).

## 6) Skriv annonseutkast
Lag:
- Tittel (kort, presis, med merke/modell)
- Beskrivelse (1-2 avsnitt)
- Nøkkelfakta (enkel liste uten markdown-bullets)
- Prisforslag (hvis bruker ikke oppgav pris)
- Leveringsdetaljer

Tone: nøktern, ryddig, selgende uten overdrivelser.

Skriv utkastet til `notater/utkast.md`.

## 7) Leveranseformat
Lever i tydelig kopierbart format uten markdown-bullets:

# Tittel
<tekst>

# Beskrivelse
<tekst>

Pris:
<tekst>

Nøkkelfakta:
Merke/modell: <tekst>
Farge: <tekst>
Tilstand: <tekst>
Mål: <tekst>
Teknisk info: <tekst>
Levering: <tekst>

Levering:
<tekst>

## 8) Spør om justeringer
Spørsmål:
- Vil du endre tittel, pris eller noe i beskrivelsen?
- Skal jeg lage et alternativt prisforslag?
- Er det noe jeg har misforstått?
