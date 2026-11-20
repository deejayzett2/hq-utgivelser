# HQ Maestro Live

DJ-program for å mikse **musikkvideoer**, musikkfiler og **CD+G-karaoke**: to decker med kontroller som på en CDJ, mikser og masterbilde. By Nes IT-Hjelper.

[← Alle veiledninger](README.md)

## Kom i gang
1. Installer og start programmet fra HQ Launcher. På Mac trengs ffmpeg: åpne Terminal og skriv `brew install ffmpeg` ([Homebrew](https://brew.sh)). Windows-pakken har ffmpeg med.
2. Lag en spilleliste og legg til filer eller hele mapper, eller slipp dem på vinduet.
3. Last en låt i deck A eller B, og trykk play.

Alle valg ligger i menyen **⚙ Innstillinger** øverst.

## Decker
- Spiller video (mp4, mov, mkv …), lyd (mp3, wav, flac, m4a …) og CD+G-karaoke. Lyden er klokka, og bildet følger den.
- **CD+G:** lydfilen og `.cdg`-filen må ha samme navn i samme mappe, for eksempel `låt.mp3` og `låt.cdg`. En `.zip` med begge virker også, uten å pakkes ut.
- CUE og play/pause som på en CDJ, stopp, hopp på 1/2/4/8/16/32 slag og eject. Displayet viser BPM, toneart, tid og taktteller.
- Oversikten nederst i waveformen viser hele låta. Klikk eller dra for å velge et sted. Hoppet skjer når museknappen slippes.
- **Tempo:** tempofader (±8/16/50 %), SYNC og MASTER, KEY LOCK og transponering i halvtoner. Fasemåleren blir grønn når slagene treffer.
- **Hotcues og loop:** 8 hotcues og et lagret startpunkt per låt, loop på 1–32 slag. Legges på nærmeste slag.
- **Analyse:** BPM, beatgrid og toneart med Camelot-kode. Kjøres første gang låta lastes, eller med «Analyser» i spillelisten. Tonearten vises grønt når den passer med det andre decket.

## Mikser
- Kanalfadere i dB (dobbeltklikk gir 0 dB) og crossfader, som kan slås av.
- Hver kanal har TRIM, HI, MID og LOW (kill helt nede), FILTER (venstre lavpass, høyre høypass) og PAN. Shift gir fin justering, dobbeltklikk gir midten.
- **Autotrim** (Innstillinger) setter TRIM så toppen i låta blir rundt 0 dB.
- **Master ut:** MASTER-volum og LIMITER, som holder lyden under −1 dBFS.
- VU-metre for master og hver kanal.

## Effekter
Eget panel per deck, **FX A** og **FX B**, med tre plasser i kjede: **ECHO**, **FLANGER** eller **ICE**. Hver plass har mengde og ON/OFF, og **D/W** blander hele kjeden. Hver effekt har en bildeeffekt som følger den, og **BILDE** slår dem av og på.

## Spillelister
- Legg til filer eller mapper med undermapper. Samme låt legges ikke inn to ganger.
- **Collection** har alle låtene dine, og **Nylig spilt** fylles av det du spiller. Collection og Nylig spilt lages av programmet og kan ikke slettes. Under **Historikk** får hver dag sin egen liste med klokkeslett.
- Låter som leses inn, analyseres ikke av seg selv, så selv store samlinger leses inn raskt. Linja «Analyse» viser hvor mange som er analysert, og «Analyser alle» tar resten i bakgrunnen.
- Dra en låt for å flytte den, eller slipp den på en annen spilleliste. Merk flere med Ctrl/Cmd og Shift.
- Høyreklikk: Vis i Utforsker/Finder, Kopier sti, Rediger tagger, Analyser, Analyser på nytt og Fjern fra listen. Under Type kan typen velges for hånd, for eksempel Karaoke for en karaokevideo.
- Velg kolonner, filtrer på video, musikk og karaoke, og vis listen i fullskjerm. **Duplikater** viser bare låter som finnes flere ganger.
- **Søk** finner alle ordene i filnavn og tagger, uten å bry seg om aksenter. Enter søker i hele Collection. Eksempler: `"take on me"`, `-live`, `house|techno`, `artist:abba`, `bpm:120-128`, `toneart:8A+` (det som passer harmonisk). Hold musa over søkefeltet for alle mulighetene.
- **Automix** (Innstillinger): 20 sekunder før slutt starter det andre decket, og neste låt lastes.

## Karaoke
Spillelistene har egne grupper for **Karaoke: venteliste** og **Karaoke: sangere**. Høyreklikk på en karaoke-låt og velg **Sett på venteliste for** en sanger, eller **Lagre på sanger**, så har hver sanger sin egen liste neste gang.

## Forslag
- Panelet **Forslag** til høyre for spillelisten viser låter du har som passer etter låta som spiller: BPM innenfor ±6 % (også halv og dobbel takt), toneart etter Camelot-hjulet og sjanger. Låter som er spilt i kveld, hoppes over.
- Topplister (Apple Music Norge, Deezer, Last.fm Norge og den norske DJ-listen fra Dee Jay Promotions) og lignende artister og låter fra Deezer og Last.fm gir forslagene høyere plass.
- **Tjenester** viser topplistene og lignende låter, og søker i Deezer og Last.fm. Låter du har, kan lastes rett i et deck.
- Innstillinger → Forslag…: slå av henting fra nettet, eller legg inn din egen gratis Last.fm-nøkkel.

## Import fra Traktor
Innstillinger → Data og filer → Traktor henter spillelistene og historikken fra Traktor. Velg hvilke lister som skal med. Samme import kan gjøres igjen uten at noe kommer dobbelt. BPM, cue og hotcues tas ikke med.

## Lydkort og hodetelefoner
Velg lydkort under Innstillinger → Lydkort. Master og hodetelefonene går ut på hvert sitt kanalpar, for eksempel 1/2 og 3/4. CUE over kanalfaderen sender kanalen til hodetelefonene, og panelet «Hodetelefoner» har MIX og volum.

## Kontrollere
- **MIDI-kontrollere** (Innstillinger → MIDI-kontrollere…): hver kontroller har en mappingfil (`.hqmidi`). Lag den med «Lær», og del den med Eksporter og Importer. Mapping for **Akai APC mini mk2** følger med.
- **Traktor Kontrol S4 MK3** kobles til automatisk. Ikke prøvd med kontrolleren ennå.
- **Hurtigtaster** (Innstillinger → Hurtigtaster…): klikk på feltet til en handling og trykk tasten.

## Masterbildet
- **Fullskjerm:** knappen i panelet «Master», dobbeltklikk i bildet eller en hurtigtast. Esc går tilbake.
- **Skjerm 2:** viser masterbildet i fullskjerm på projektor eller TV.
- **Nettside:** vises når master ikke har bilde. Lenken legges inn i panelet «Master». Digital signage (digitalsigns.no) får fast enhets-ID `hqmaestro_<maskinnavn>`.
- **HQ Maestro Videoboard:** klipp fra Videoboard kan vises oppå masterbildet (Innstillinger → Videoboard).

## «Artist – Tittel» i OBS
Innstillinger → OBS-tekst → slå på nettsiden. Legg adressen (`http://127.0.0.1:8797/`) inn som **Nettleser**-kilde i OBS, 1920×1080. Bakgrunnen er gjennomsiktig, og teksten kommer når en låt spiller og høres. «Vis også i master-bildet» tegner den samme teksten nederst i masterbildet. Utseendet kan endres i adressen, for eksempel `?side=hoyre`, `?skala=1.2` og `?farge=ff3d81`.

## Lys etter musikken (HQ Maestro Lightpad)
Innstillinger → Lightpad → **Send takt og energi til Lightpad**, med IP-adressen til maskinen Lightpad kjører på (`127.0.0.1` er denne). Slå på «Musikk fra HQ Maestro Live» i Lightpad også. Da følger lyset i ShowXpress takten og energien i musikken. «Lys» i verktøylinja viser om Lightpad tar imot.

## Utseende og språk
- **Skins** (Innstillinger → Skin og «Skin-editor…»): endre alle fargene og legg bakgrunnsbilder bak panelene. Del som `.hqskin`.
- **Språk** (Innstillinger → Språk og «Oversetter…»): lag ditt eget språk og del det som `.hqsprak`. En engelsk språkfil følger med i pakken.
- **Oppsett:** alle panelene kan flyttes, deles og lukkes. «Lås oppsett» hindrer uhell, og «Tilbakestill oppsett» henter standarden.

## Data og flytting
Analyser, hotcues, spillelister og oppsett lagres på maskinen:
- Windows: `%APPDATA%\HQ Maestro Live\data\`
- Mac: `~/Library/Application Support/HQ-Maestro-Live/`

Analysene lagres også i mappa `_HQ Maestro Live_` på roten av disken med musikken, så de følger en ekstern disk mellom PC og Mac.

**Til en annen disk eller maskin:** kopier låtene og datamappen (eller legg datamappen på disken med låtene: Data og filer → Datamappe), og velg den nye plasseringen under Innstillinger → Data og filer → Musikkmappe → «Endre plassering…». Analysene, cue og hotcues følger med, så ingenting må analyseres på nytt. Under Data og filer kan du også ta sikkerhetskopi og importere.

Loggfila finnes med Innstillinger → Åpne loggmappen.

## Lisens
Uten lisens har masterbildet vannmerke, og programmet kan spille i 10 minutter per økt. Låta som spiller, går alltid ferdig. Lisensnøkkel legges inn under Innstillinger → Lisens…, eller med «Lisens» i HQ Launcher. Kjøp lisens på [ithjelper.no](https://ithjelper.no).
