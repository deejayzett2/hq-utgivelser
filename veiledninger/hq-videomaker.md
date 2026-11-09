# HQ Maestro Videomaker

Lager **musikkvideoer i takt med sangen**, by Nes IT-Hjelper. Programmet analyserer tempo, takt, deler av sangen, toneart og stemning, henter bilder og videoklipp og klipper dem på slagene. Resultatet kan redigeres videre på en tidslinje før du eksporterer.

[← Alle veiledninger](README.md)

## Kom i gang
1. Installer og start programmet fra HQ Launcher. På Mac trengs ffmpeg: åpne Terminal og skriv `brew install ffmpeg` ([Homebrew](https://brew.sh)). Windows-pakken har ffmpeg med.
2. Velg **Fil → Generer musikkvideo fra sang…** og velg sangen (mp3, wav, flac, m4a eller ogg).
3. Fyll inn det du vil, og trykk **Generer**:
   - **Tema:** for eksempel «hav, surfing, sommer» (valgfritt). Brukes til å søke etter bilder og video.
   - **Stemning**, **Format**, **Bildefrekvens** (24, 25, 30 eller 60 fps).
   - **Andel video:** hvor mye av videoen som skal være videoklipp og hvor mye stillbilder.
   - **Klipptempo:** hvor ofte det klippes (0,5× til 2×).
   - **Variant:** et annet tall gir en annen video fra samme sang.
   - **Bilder og video:** hent fra nettet, bare fra en mappe på maskinen, eller bare medier som allerede er i prosjektet.
   - **Sluttkort** med logo til slutt.
4. Rediger på tidslinja, og velg **Fil → Eksporter video…** (⌘E / Ctrl+E).

Generer erstatter prosjektet som er åpent, og kan ikke angres. Lagre først hvis du vil beholde det.

## Bilder og video fra nettet
Uten API-nøkkel brukes bare stillbilder fra **Openverse**. En gratis nøkkel fra **Pexels** eller **Pixabay** gir også videoklipp. Nøklene legges inn under Innstillinger…. Sjekk vilkårene til tjenesten før du publiserer.

## Formater
| Format | Størrelse |
|---|---|
| Full HD 16:9 (YouTube) | 1920×1080 |
| HD 16:9 | 1280×720 |
| 4K 16:9 | 3840×2160 |
| TikTok / Reels / Stories 9:16 | 1080×1920 |
| Instagram stående 4:5 | 1080×1350 |
| Instagram kvadrat 1:1 | 1080×1080 |

Når bildet beskjæres til et annet format, holdes personene i bildet.

## Redigering
- **Importer medier…** eller **Importer mappe…** legger til egne bilder, video og lyd. Dra dem til tidslinja.
- Tidslinja viser takt- og slagstolper. Klipp kan festes til nærmeste takt.
- **S** eller ⌘K deler ved spillehodet, Backspace sletter, Shift+Backspace sletter og lukker hullet. Klipp ut, kopier, lim inn og erstatt virker som vanlig. På Windows brukes Ctrl i stedet for ⌘.
- Hvert klipp har fart, skala, posisjon, rotasjon, opasitet, beskjæring og Ken Burns (langsom zoom), med keyframes.
- **Effekter:** fargegradering (eksponering, kontrast, metning, gamma, temperatur, tint), vignett, uskarphet, blits og tone inn/ut.

## Verktøy
Samme verktøy og snarveier som i After Effects og Premiere:

| Verktøy | Tast | Hva |
|---|---|---|
| Utvalg | V | Velg og flytt klipp. I bildet: dra for å flytte, musehjulet endrer størrelsen |
| Kniv | C | Del et klipp der du klikker |
| Rulle | B | Trim kantene uten å lage hull |
| Skli | Y | Velg hvilken del av videoen som vises, uten å flytte klippet |
| Hånd | H | Rull tidslinja |
| Zoom | Z | Zoom inn i tidslinja |
| Rotasjon | W | Roter valgt klipp |
| Beskjær | R | Dra kantene på valgt klipp |

Låste spor røres ikke av verktøyene.

## Prosjekter
Prosjektene lagres som `.hqmv` (Fil → Lagre, ⌘S / Ctrl+S). Programmet spør før det avsluttes hvis noe ikke er lagret.

## Lisens
Uten lisens har forhåndsvisningen og eksporten vannmerke, og programmet kan eksportere og generere i 10 minutter per økt. Redigering og lagring virker hele tiden. Lisensnøkkel legges inn under Hjelp → Lisens…, eller med «Lisens» i HQ Launcher. Kjøp lisens på [ithjelper.no](https://ithjelper.no).
