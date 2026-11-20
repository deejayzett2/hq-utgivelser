# HQ Maestro Lightpad

Styr Chauvet **ShowXpress** fra mobilen, nettbrettet eller PC-en, by Nes IT-Hjelper. Programmet kjører på maskinen med ShowXpress og lager en kontrollflate på nettet som ligner en Akai APC Mini mk2: 8×8 pads, knapper til høyre og under, og 9 fadere. Du kan ha flere sider, og bestemme hvor mange pads, knapper og fadere hver side har.

[← Alle veiledninger](README.md)

## Kom i gang
1. **I ShowXpress:** slå på *Preferences › Network › External App* og start ShowXpress på nytt. Slå så på *Live › Live Settings › External control* og velg et passord. Hver side i Live må ha **Live Mobile** slått på, ellers sender ShowXpress den ikke.
2. **I Lightpad:** ⚙ Innstillinger → skriv inn passordet. Adressen er `127.0.0.1` og porten `7348` når ShowXpress er på samme maskin.
3. Klikk **✏ Rediger** og **Hent alt fra ShowXpress** (to trykk). Alle sidene i ShowXpress legges under hverandre, én blokk med rader per enhet, og faderne kobles til masterfaderne. Du kan også hente én side om gangen.
4. Klikk **📱 Åpne på mobil** og skann QR-koden. Mobilen må være på samme nettverk. Windows spør om brannmuren første gang: velg *Tillat*.

Tips: «Legg til på Hjem-skjerm» i nettleseren på mobilen gir fullskjerm uten adresselinje.

## Hva en knapp kan gjøre
| Valg | Hva |
|---|---|
| Knapp i ShowXpress | Som i ShowXpress: flash-knapper er på mens du holder, andre slås av og på for hvert trykk |
| Knapp i ShowXpress (alltid av/på) | Slår knappen av og på for hvert trykk, også flash-knapper |
| Kommando | BPM tap, auto-BPM, frys, tidslinje, sekvens, «Slipp alle knapper» |
| MIDI-note | For det som ikke kan styres over nettverket (MIDI Learn i ShowXpress) |
| Bytt side | Bytter side på nettsiden for den som trykker |

Fadere styrer masterfaderne i ShowXpress, eller sender MIDI CC. ShowXpress har et begrenset antall masterfadere, så ekstra fadere går over MIDI. På Windows trengs da en virtuell MIDI-kabel som [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html).

Knappene lyser når de er på i ShowXpress, også når de er slått på i ShowXpress selv.

Når Lightpad starter, settes alle masterfaderne helt ned, og MIDI-faderne på 0. Det skjer bare første gang Lightpad kobler til etter start, ikke når forbindelsen kommer tilbake under et show. Valget ligger i ⚙ Innstillinger.

## Flytte og legge til
- **Dra og slipp:** under ✏ Rediger drar du en knapp eller fader til en annen plass. De bytter plass.
- **Til en annen side:** dra knappen til en sidefane (hold Ctrl for å kopiere), eller bruk «Flytt til en annen side» i panelet. En hel enhet kan flyttes samlet.
- **Enhetsfarger:** hver enhet har sin egen farge, og enhetslisten over padsene framhever knappene til en enhet.
- **Nye fadere:** velg en fader under ✏ Rediger og trykk **Ny masterfader fra enhetene i showet**. Lightpad viser hver enhet og kanal med DMX-adresser. Finnes det allerede en masterfader for den, brukes den. Ellers legger Lightpad den inn i ShowXpress, med sikkerhetskopi. **ShowXpress må være lukket** mens det skjer, og startes igjen etterpå.

## Musikk fra HQ Maestro Live
Lyset kan følge musikken som spilles i **HQ Maestro Live**: tempoet, energien og overgangene i låtene.

1. **I Lightpad:** ⚙ Innstillinger → **Musikk fra HQ Maestro Live …** → kryss av for *Lyset følger musikken fra HQ Maestro Live*.
2. **I HQ Maestro Live:** Innstillinger → Lightpad → **Send takt og energi til Lightpad**. Skriv inn IP-adressen til maskinen Lightpad kjører på (`127.0.0.1` hvis det er samme maskin). Kjører Lightpad på en annen maskin, må *Tillat mobiler og nettbrett* være på i Lightpad.
3. Vinduet i Lightpad viser BPM og energi når den tar imot. Live viser om Lightpad svarer og er koblet til ShowXpress.

Hva musikken kan styre (hver del slås av og på for seg):
- **Tempo i takt:** BPM tap i ShowXpress på hvert slag. Auto-BPM i ShowXpress kan slås av når musikken starter.
- **Masterfadere etter energien:** velg hvilke fadere som skal følge med, og sett min (rolige partier), maks (det kraftigste) og hvile (når musikken stopper).
- **Puls på slaget:** et kort løft i faderne på hvert slag.
- **Drop og break:** en knapp i ShowXpress trykkes når musikken går fra rolig til kraftig (drop), eller motsatt (break). Følsomheten bestemmer hvor ofte.

Flytter du en fader for hånd, får du styre den selv i 10 sekunder. Stopper musikken, eller Live forsvinner, slippes knappen og faderne går til hvile.

## Stream Deck og andre
| Adresse | Hva |
|---|---|
| `http://<maskin>:8795/api/klikk/1/p0-0` | Trykk og slipp pad øverst til venstre på side 1 |
| `http://<maskin>:8795/api/trykk/1/s0`, `/api/slipp/1/s0` | Trykk eller slipp knapp 1 til høyre |
| `http://<maskin>:8795/api/fader/1/0?v=0.5` | Fader 1 til midten |

Plassene heter `p<rad>-<kolonne>` (pads), `s<rad>` (til høyre) og `t<kolonne>` (under), og teller fra 0. Sidene teller fra 1.

## Lisens
Uten lisens virker programmet i 10 minutter per økt. Etter det virker ikke nye trykk, men slipp, «Slipp alle» og fadere ned virker alltid. Lisensnøkkel legges inn under ⚙ Innstillinger → Lisens, eller med «Lisens» i HQ Launcher. Kjøp lisens på [ithjelper.no](https://ithjelper.no).
