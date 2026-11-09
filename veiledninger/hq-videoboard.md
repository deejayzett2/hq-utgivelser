# HQ Maestro Videoboard

Et soundboard for video, by Nes IT-Hjelper. Legg korte videoklipp på et rutenett av pads, og trykk dem fra programmet, fra **Stream Deck** eller fra mobilen. Klippene vises på en nettside med gjennomsiktig bakgrunn, som legges oppå strømmen i **OBS**.

[← Alle veiledninger](README.md)

## Kom i gang
1. Installer og start programmet fra HQ Launcher. På Mac trengs ffmpeg: åpne Terminal og skriv `brew install ffmpeg` ([Homebrew](https://brew.sh)). Windows-pakken har ffmpeg med.
2. Klikk på en tom plass, eller slipp videoer på vinduet.
3. Videoene gjøres om til WebM med alfakanal. Klipp med gjennomsiktighet (ProRes 4444, WebM med alfa, GIF/PNG) beholder den. Klipp filmet mot grønnskjerm kan få bakgrunnen fjernet (høyreklikk på paden → redigering → Grønnskjerm).

Klipp med gjennomsiktig bakgrunn kan lages i **HQ Maestro Alfa**.

## OBS
Legg til en kilde av typen **Nettleser** øverst i scenen:
- URL: `http://127.0.0.1:8790/overlay`
- Bredde 1920, høyde 1080
- Kryss av for **Styr lyd via OBS**, så lyden kommer i mikseren

**Master** i programmet viser det samme bildet som overlayet, og kan åpnes i eget vindu (fullskjerm med dobbeltklikk eller F).

## Stream Deck
Dra **System → Website** til en knapp, lim inn adressen og kryss av for **GET request in background**:

| Adresse | Hva |
|---|---|
| `http://127.0.0.1:8790/api/spill/3` | Trykk på pad 3: start, eller stopp hvis den spiller (eller start på nytt, valg per pad) |
| `http://127.0.0.1:8790/api/start/3` | Start pad 3 fra begynnelsen |
| `http://127.0.0.1:8790/api/stopp/3` | Stopp pad 3 |
| `http://127.0.0.1:8790/api/stopp` | Stopp alle |

Pad 1 er øverst til venstre. Hver pad viser adressen sin i redigeringen, med Kopier-knapp.

## Kontrollpanel og mobil
`http://127.0.0.1:8790/` viser padsene som nettside. Med **Tillat andre maskiner i nettverket** (Innstillinger → Rutenett og server) kan mobil, nettbrett og en egen strømme-PC bruke adressen som vises i programmet.

## HQ Maestro Live
Klippene kan også vises oppå masterbildet i HQ Maestro Live (Innstillinger → Videoboard i Live).

## Lisens
Uten lisens har overlayet vannmerke, og programmet kan brukes i 10 minutter per økt. Lisensnøkkel legges inn under Innstillinger → Lisens…, eller med «Lisens» i HQ Launcher. Kjøp lisens på [ithjelper.no](https://ithjelper.no).
