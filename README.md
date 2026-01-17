# Finn.no annonsearbeidsområde

Dette repoet brukes til å lage Finn.no-annonser med AI-støtte. Alt leveres som tekst du kan kopiere inn i Finn.no manuelt.

## Rask start
1. Åpne repoet i OpenCode.
2. Skriv `@LagAnnonse` i chatten og følg instruksjonene.
3. Legg inn bilder og fyll ut feltene når du blir bedt om det.

## MCP-servere (via opencode)
Konfigurasjonen ligger i `opencode.json`. Bruk opencode til å hente/liste konfigurerte MCP-servere:

```powershell
opencode mcp list
```

Dette leser `opencode.json` i repoet og viser tilgjengelige servere (f.eks. for bildefil-konvertering).

## Struktur
- `annonser/`: én mappe per annonse (bilder, notater, utkast)
- `maler/`: maler og hjelpefiler
- `brukerprofil.md`: personlige standarder (ignoreres av git)
- `brukerprofil-mal.md`: mal uten persondata
- Alt under `annonser/` og `brukerprofil.md` er ignorert i `.gitignore` og blir ikke commitet.

## Notater
- Dette repoet støtter ikke automatisert publisering til Finn.no. Resultatet fra en generering må kopieres over til Finn.no manuelt.
