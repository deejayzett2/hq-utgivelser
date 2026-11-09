# Scoreboard

Resultattavle for fotball, håndball, basketball, volleyball, ishockey, paintball, bordtennis og tennis, by Nes IT-Hjelper. Programmet styrer kampklokke, stilling og hendelser, og viser alt live på alle skjermer i nettverket. Alt virker uten internett.

[← Alle veiledninger](README.md)

## Kom i gang
Installer og start programmet fra HQ Launcher. **Startvinduet** viser at tavla kjører, porten, hvor mange nettlesere som er koblet til, og alle adressene (med «Åpne» og «Kopier»). Her setter du også **port og PIN**. Uten PIN kan alle på nettverket styre tavla. Visningssidene krever aldri PIN.

| Side | Bruk |
|---|---|
| `http://<ip>:8080/` | Kontrollpanel (kamp, lag, innstillinger, reklame, layout, MIDI) |
| `http://<ip>:8080/display` | Stadionskjerm: åpne i fullskjerm på maskinen som driver skjermen eller LED-veggen |
| `http://<ip>:8080/display?layout=led` | Kompakt layout for LED-panel (384×192) |
| `http://<ip>:8080/stream` | Overlegg til livestream med gjennomsiktig bakgrunn (nettleserkilde i OBS/vMix, 1920×1080) |

**Skjermvindu:** fra startvinduet kan tavla vises i fullskjerm på en skjerm koblet til maskinen (for eksempel HDMI til LED-kontrolleren). Esc, F eller dobbeltklikk veksler fullskjerm.

## Sport og regler
Under **Sport** velger du sport. Det fyller inn standardreglene, som du kan justere før du lagrer.

| Sport | Standard |
|---|---|
| Fotball | 2 × 45 min, teller opp, tilleggstid, ekstraomganger og straffer (kan slås på) |
| Håndball | 2 × 30 min, teller opp, 2 min utvisning, 3 timeouts |
| Basketball | 4 × 10 min, teller ned med tideler, skuddklokke 24/14, +1/+2/+3, lagfeil og bonus |
| Volleyball | Best av 5 sett til 25 (15 i siste), vinn med 2, serve, 2 timeouts per sett |
| Ishockey | 3 × 20 min, teller ned, 2 og 5 min utvisning, sudden death, shootout |
| Paintball | Pro X-Ball, 3v3, Race-to-2/4 og Split deck |
| Bordtennis | Best av 5 sett til 11, vinn med 2 |
| Tennis | 15–30–40–fordel, games og sett med tiebreak på 6–6, best av 3 |

**Race to** og **mercy** (avgjort ved N poengs ledelse) gjelder alle sporter med poeng.

## Kamp
- Mål (med målscorer), gule og røde kort, bytter og straffer legges i hendelseslista og vises som overlegg.
- **Angre** (Ctrl+Z) går tilbake ett steg om gangen, også etter «Nullstill kamp».
- Tilstanden lagres hele tiden, og klokka går riktig videre etter en omstart eller et strømbrudd.
- Hurtigtaster: `Space` start/pause · `N` neste periode · `1`/`2` mål hjemme/borte · `+`/`-` tilleggstid · `Esc` fjern overlegg · `Ctrl+Z` angre.

## Nedtelling og lyd
- Før et poeng: «10 sekunder», pip hvert sekund og «GO».
- 60 sekunder igjen av spilletiden, og påminnelser i pausen.
- Egne lydfiler legges inn under Innstillinger → Lyd (mp3, wav, ogg, m4a). Uten fil brukes pip og norsk tale.

## Kampprogram og resultater
- **Program:** importer kampprogrammet fra Excel/CSV (last ned malen). «Hent neste kamp» lagrer resultatet og henter neste kamp med lag og format.
- **Resultater:** hver kamp logges når den avsluttes, og kan eksporteres til Excel.
- **Nedtelling før kampstart:** sett «Kampstart om» (for eksempel 40:00) og trykk Start.

## Paintball
- Et poeng heter «Base». Når base trykkes, stopper klokka og venter på dommeren: **Godkjenn**, **No point** eller **Reverser**.
- **Split deck / back-to-back:** to kamper med fire lag spiller annenhver gang, med felles kampklokke.
- Pit- og dommerskjermer:

| Adresse | Hva |
|---|---|
| `/pit/a`, `/pit/b` | Pit for hvert lag: «Timeout» og «Towel» |
| `/base/a`, `/base/b` | Base-knapper ved basen på hver side |
| `/ref` | Dommer: BASE A/B, REVERSE POINT, APPROVE, NO POINTS, straffer, START og STOP |

Hver skjerm har sin egen kode (Innstillinger → Pit- og dommerskjermer). Pit-knappene må trykkes to ganger.

## Roster
- Under **Roster** legger du inn spillere og trenere: nummer, navn, posisjon, rolle, kaptein og bilde.
- **Importer Excel/CSV** (én fil per lag), eller **last ned Excel-malen**.
- **Bilder** kobles automatisk når filnavnet er draktnummeret (`10.jpg`) eller navnet (`kari-olsen.jpg`).
- I Kamp-fanen: **Vis roster**, oppstilling, bytter, spillerintro, kampens spiller og målscorere.
- **Lagbibliotek** (under Lag): lagre lag med logo, farger og roster til senere.

## Reklame
Under Reklame legger du inn en spilleliste med nettsider, bilder eller videoer, med visningstid per element. Med skjerm «Auto» vises reklamen før kamp, i pauser og etter kampslutt. `@scoreboard` i lista viser tavla i rotasjonen.

Sider som nekter å vises inni tavla (som digitalsigns.no), åpnes i eget fullskjermvindu. Nettleseren på skjermen må da tillate popup-vinduer for tavla. I skjermvinduet får digital signage en fast enhets-ID, standard `scoreboard_<maskinnavn>`.

## Layouter
Layoutene kan redigeres i Layout-fanen, og alle skjermer oppdateres når du lagrer. Fanen viser alle plassholdere (som `{{home.name}}`, `{{clock}}`) med nåverdi. Egne plassholdere legges inn under Innstillinger. «Tilbakestill til standard» henter standardlayouten.

## MIDI, Stream Deck og LED
- **MIDI:** i MIDI-fanen trykker du «Lær» og deretter en knapp på kontrolleren.
- **Stream Deck / Bitfocus Companion:** styr tavla med `POST /api/command`, for eksempel `{"cmd":"goal","team":"home"}` (header `x-pin` hvis PIN er satt).
- **LED-vegger** med sender/kontroller (Novastar, Colorlight o.l.) tar HDMI inn. En mini-PC med nettleser i kioskmodus mot `/display?layout=led` holder.

## Lisens
Uten lisens virker programmet i 10 minutter fra det startes. Deretter viser skjermene «Prøvetiden er brukt opp», og tavla kan ikke endres. Å stoppe klokka og skjule det som vises, virker fortsatt. «Scoreboard by Nes IT-Hjelper» vises alltid nederst til høyre på skjermene.

Klikk på lisensstatusen øverst i Scoreboard-vinduet og lim inn nøkkelen, eller bruk «Lisens» i HQ Launcher. Kjøp lisens på [ithjelper.no](https://ithjelper.no).
