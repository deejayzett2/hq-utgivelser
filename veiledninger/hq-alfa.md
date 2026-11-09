# HQ Maestro Alfa

Videosnutter i **WebM med alfakanal**, by Nes IT-Hjelper. Importer video, bilder og lyd, klipp og lim på tidslinja, legg på lyd og fjern bakgrunnen. Klippene passer rett inn i **HQ Maestro Videoboard**.

[← Alle veiledninger](README.md)

## Kom i gang
1. Installer og start programmet fra HQ Launcher. På Mac trengs ffmpeg: åpne Terminal og skriv `brew install ffmpeg` ([Homebrew](https://brew.sh)). Windows-pakken har ffmpeg med.
2. Dra video, bilder og lyd inn i vinduet (eller Fil → Importer medier …).
3. Dobbeltklikk et medium, eller dra det til tidslinja. Video og bilder havner på videospor, lyd på lydspor.
4. Velg klippet, og velg **Fjern bakgrunn** i egenskapspanelet til høyre:
   - **Grønnskjerm:** fjerner en farge. Bruk **Pipette** og klikk på bakgrunnen. Juster Toleranse, Myke kanter og Fjern fargesøl.
   - **AI (finn personen):** finner personen i hvert bilde, også uten grønnskjerm. Juster Terskel og Myke kanter på bildet du står på, og trykk **Lag maska for hele klippet** når det ser riktig ut. «Nøyaktig» er standard, «Rask» er raskere, men mister lettere ansikter.
   - **Masker** (pennen ✒, P): tegn en bane på klippet. **Klippebane** viser bare det innenfor, **Behold alltid** henter tilbake noe AI-en tok, og **Fjern alltid** tar bort det innenfor. Banen kan animeres med keyframes.
5. **Fil → Eksporter klipp** (⌘E / Ctrl+E): WebM med alfa (til Videoboard) eller ProRes 4444 (til redigeringsprogrammer). Det som ikke dekkes av et klipp, blir gjennomsiktig.

Forhåndsvisningen viser ruter bak det gjennomsiktige (kan byttes til svart, hvit eller grønn under «Bakgrunn»).

## Verktøy
Samme verktøy og snarveier som i After Effects og Premiere:

| Verktøy | Tast | Hva |
|---|---|---|
| Utvalg | V | Velg og flytt klipp. I bildet: dra for å flytte, dra hjørnene eller bruk musehjulet for størrelse |
| Kniv | C | Del et klipp der du klikker. Shift+klikk deler alle spor |
| Rulle | B | Trim kantene uten å lage hull |
| Skli | Y | Velg hvilken del av videoen som vises, uten å flytte klippet |
| Hånd | H | Rull tidslinja |
| Zoom | Z | Zoom inn i tidslinja, Alt+klikk ut |
| Rotasjon | W | Roter valgt klipp (Shift: 15° om gangen) |
| Beskjær | R | Dra kantene på valgt klipp |

**Skill lyd fra video** (⌘L / Ctrl+L): lyden blir et eget klipp på et lydspor.

## Redigering
- Dra klipp for å flytte, dra kantene for å trimme. **S** eller ⌘K deler ved spillehodet, Backspace sletter, Shift+Backspace sletter og lukker hullet.
- Klipp ut, kopier og lim inn (⌘X/C/V), angre og gjør om (⌘Z / Shift+⌘Z). På Windows brukes Ctrl.
- Hvert klipp har lydnivå, fart, passform, skala, posisjon, rotasjon og opasitet med keyframes, beskjæring og effekter (fargegradering, vignett, uskarphet, blits, tone inn/ut).
- 🔊 ved sporet slår lyden av, 👁 skjuler et videospor.

## Grafikkort
På Windows brukes grafikkortet til AI-maskene. Har maskinen flere grafikkort, velges kortet under Innstillinger (standard: det raskeste).

## Lisens
Uten lisens har klippene vannmerke, og programmet kan eksportere i 10 minutter per økt. Lisensnøkkel legges inn under Hjelp → Lisens…, eller med «Lisens» i HQ Launcher. Kjøp lisens på [ithjelper.no](https://ithjelper.no).

## Tredjepart
AI-maskene bruker MODNet (Zhanghan Ke m.fl., Apache License 2.0) og kjøres med ONNX Runtime (Microsoft, MIT-lisens). På Windows brukes DirectML (Microsoft). Lisensfilene følger med programmet.
