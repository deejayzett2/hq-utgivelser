# HQ Launcher

Installerer, oppdaterer og starter programmene fra Nes IT-Hjelper: HQ Maestro Live, Alfa, Videoboard, Lightpad og Videomaker, Scoreboard og E-Sport Updater. Finnes for Windows og Mac.

[← Alle veiledninger](README.md)

## Kom i gang
1. Last ned den nyeste launcheren fra [siste utgivelse](../../../releases/latest): `…-windows.zip` for Windows eller `…-mac.zip` for Mac.
2. **Windows:** pakk ut zip-fila og start `HQ Launcher.exe`. Den trenger ikke administratorrettigheter, for programmene installeres bare for deg.
3. **Mac:** pakk ut zip-fila og åpne «HQ Launcher». Første gang sier macOS at appen ikke kan kontrolleres. Gå da til **Systeminnstillinger → Personvern og sikkerhet** og trykk **Åpne likevel**. Trykk så **Flytt til Programmer** i launcheren, ellers kan den ikke oppdatere seg selv.
4. Trykk **Installer** ved programmene du vil ha, og **Start** for å åpne dem.

## Programlisten
Hvert program viser installert versjon og om det finnes en ny.
- **Installer**, **Oppdater** og **Start**. **Oppdater alle** tar alle på en gang.
- **Les mer** åpner veiledningen til programmet.
- **Åpne mappe** viser hvor programmet ligger (for E-Sport Updater: pakkemappa til klientene).
- **Bruk** og et versjonsnummer går tilbake til forrige versjon, hvis den nye ikke virker. Den gjeldende og den forrige versjonen beholdes.

## Oppdateringer
Launcheren sjekker etter oppdateringer når den starter, hvert 30. minutt mens den er åpen, og når du trykker **Sjekk etter oppdateringer**. Linja øverst viser resultatet. Kommer det en ny launcher, trykker du **Oppdater launcheren**.

Pakkene kontrolleres før de installeres: launcheren godtar bare pakker som står i den signerte katalogen, med riktig størrelse og innhold. Uten nett kan programmene som er installert, fortsatt startes.

## Lisens
Hvert program viser om det har lisens på PC-en, hvem den er registrert til, og når den utløper.
- **Lisens** legger inn nøkkelen (`HQ-XXXXX-XXXXX-XXXXX-XXXXX`) og trykker *Aktiver*. **Fjern fra denne PC-en** frigjør plassen, og programmet virker da bare i prøvemodus på PC-en.
- Lukk programmet først. Det leser lisensen når det starter.
- **E-Sport Updater:** lisensen gjelder admin-programmet. Klientene får den fra admin.

Kjøp lisens på [ithjelper.no](https://ithjelper.no).

## Mac og ffmpeg
HQ Maestro-programmene bruker ffmpeg fra [Homebrew](https://brew.sh) på Mac. Står det **Trenger ffmpeg**, åpner du Terminal og skriver `brew install ffmpeg`. På Windows har programmene ffmpeg med.

Programmene launcheren laster ned, starter uten spørsmål fra macOS. Bare launcheren selv må godkjennes første gang.
