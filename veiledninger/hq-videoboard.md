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

## NDI (Windows)
Programmet kan også sende klippene som en **NDI-kilde**, med gjennomsiktighet og lyd. Kilden kan tas inn i vMix, TriCaster, OBS (med [DistroAV](https://github.com/DistroAV/DistroAV)) og andre NDI-mottakere i nettverket. Overlayet, Stream Deck og kontrollpanelet virker som før.

1. Installer **NDI Runtime** fra [ndi.video](https://ndi.video) (følger med NDI Tools).
2. Gå til Innstillinger → Rutenett og server → NDI, og velg **NDI** eller **NDI HX**.
3. Gi kilden et navn, og velg 25, 30, 50 eller 60 bilder per sekund. Bildet er alltid 1920×1080.
4. Statuslinja nederst viser om programmet sender, og hvor mange mottakere som er koblet til.

- **NDI** gir full kvalitet og passer for kablet nettverk.
- **NDI HX** sender H.264, som bruker mye mindre nettverk. Det krever **NDI Advanced SDK** på maskinen. Uten den sendes vanlig NDI, og statuslinja sier fra.

Uten lisens har NDI-bildet også vannmerke. NDI finnes foreløpig bare i Windows-utgaven. NDI® er et registrert varemerke for Vizrt NDI AB.

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
`http://127.0.0.1:8790/` viser padsene som nettside. Med **Tillat andre maskiner i nettverket** (Innstillinger → Rutenett og server) kan mobil, nettbrett og en egen strømme-PC bruke adressen som vises nederst i programmet (IP-adressen til maskinen).

## HQ Maestro Live
Klippene kan også vises oppå masterbildet i HQ Maestro Live (Innstillinger → Videoboard i Live).

## Lisens
Uten lisens har overlayet vannmerke, og programmet kan brukes i 10 minutter per økt. Lisensnøkkel legges inn under Innstillinger → Lisens…, eller med «Lisens» i HQ Launcher. Kjøp lisens på [ithjelper.no](https://ithjelper.no).
