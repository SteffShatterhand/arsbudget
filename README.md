# Årsbudget

Hushållsbudget för ett år: fasta och rörliga kostnader månad för månad, med årsöversikt.
Ren HTML, CSS och JavaScript utan byggsteg eller beroenden. All data ligger i webbläsaren
på respektive enhet — inget skickas någonstans.

## Filer

| Fil | Roll |
| --- | --- |
| `index.html` | Hela appen |
| `manifest.webmanifest` | Namn, färger och ikoner vid installation |
| `sw.js` | Service worker, gör appen användbar utan uppkoppling |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | Ikoner |

## Publicera med GitHub Pages

1. Skapa ett nytt repo, till exempel `arsbudget`.
2. Ladda upp alla filerna i rotmappen.
3. Settings → Pages → Source: `Deploy from a branch`, branch `main`, mapp `/ (root)`.
4. Öppna adressen som visas, till exempel `https://användarnamn.github.io/arsbudget/`.

Pages levererar över https, vilket service workern kräver. Det fungerar inte om du
öppnar `index.html` direkt från filsystemet med `file://`.

## Installera på telefonen

Öppna adressen i Chrome på Android, tryck på menyn med tre punkter och välj
**Lägg till på startskärmen**. På iPhone: dela-ikonen i Safari → **Lägg till på hemskärmen**.

## Vid uppdatering

Höj `CACHE`-versionen högst upp i `sw.js` när du laddar upp ändringar, annars fortsätter
telefonen att visa den gamla versionen.

## Om lagringen

Varje enhet har sin egen kopia i `localStorage` under nyckeln `arsbudget-v1`.
Ingen synkning sker mellan enheter. Använd Exportera och Importera under fliken **År**
för att flytta siffrorna mellan telefoner. Rensar man webbläsardata försvinner budgeten,
så exportera en säkerhetskopia då och då.
