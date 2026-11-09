# E-Sport Updater

Holder spillene på e-sportklubbens PC-er oppdatert, styrt fra én admin-PC. By Nes IT-Hjelper.

[← Alle veiledninger](README.md)

- **E-Sport Updater Admin** viser alle PC-ene, installerte spill, oppdateringer, kontoer og jobber. Kjører på Windows og Mac. Det er admin-programmet som installeres og oppdateres med HQ Launcher.
- **E-Sport Updater Klient** kjører som Windows-tjeneste på hver spill-PC, også når ingen er logget på. Den finner spill fra **Steam**, **Epic Games** og **Battle.net**, sjekker etter oppdateringer og oppdaterer, installerer og avinstallerer. Klientene oppdateres fra admin.

## Hva den kan
| | Finne | Sjekke oppdatering | Oppdatere / installere | Avinstallere |
|---|---|---|---|---|
| Steam | ✅ | ✅ | ✅ SteamCMD | ✅ |
| Epic | ✅ | ⚠️ Legendary | ⚠️ Legendary (uoffisiell) | ⚠️ |
| Battle.net | ✅ | ❌ (vises som «Ukjent») | ⚠️ «Start Battle.net»: appen oppdaterer selv | ❌ |
| NVIDIA-driver | ✅ | ✅ | ✅ (bare når nyere finnes) | – |
| Programmer | ✅ Chocolatey | ✅ | ✅ | ✅ |

PC-en startes aldri på nytt automatisk. Admin viser «Omstart kreves», og kan starte PC-en på nytt.

## Installere
Klientene installeres med `install-windows.ps1` fra pakken (`-Rolle Klient` med felles token og lisensnøkkel), som ber selv om administratorrettigheter. Token og nøkkel er hemmelige: kjør helst installasjonen med Action1 eller et annet verktøy for utrulling, så de ikke blir liggende i kommandohistorikken på PC-en. Skriptet installerer SteamCMD, Legendary og tjenesten, og åpner brannmuren for TCP 47820 og UDP 47821. Med Action1 brukes `action1-install.ps1`. «Åpne mappe» i HQ Launcher viser pakkemappa.

## Admin
- **Legg til PC:** navn, `vert:port`, token og fingerprint. «Hent fingerprint» viser den: sammenlign med `"E-Sport Updater Klient.exe" status` på PC-en.
- **Søk i LAN:** finner klientene. Fingerprint må bekreftes for hver PC.
- **Spill:** status, oppdater, avinstaller og installer nye spill (Steam appid / Epic AppName). «📂 Velg mappe …» viser diskene med ledig plass.
- **Kontoer:** Steam-brukernavn og passord per PC eller på alle samtidig. Epic: **Klubbkonto** (admin logger inn én gang) eller **Egen konto** per PC.
- **👥 Kontoer** øverst: alle PC-er med konto og status. Steam Guard-kode skrives rett i listen. **Importer fra Excel** leser én rad per PC (malen kan lagres fra admin). Kontoene testes én om gangen, så Steam ikke sperrer.
- **Programmer:** installer, oppdater og avinstaller programmer med Chocolatey, på én PC eller alle.
- **Agent-innstillinger:** sjekkintervall og automatisk oppdatering i et tidsvindu (standard 03–07). «Bruk på alle tilkoblede PCer».
- **Eksporter/Importer:** PC-liste, fingerprints og valgfritt tokens, kryptert med passord.
- **Innstillinger → Start ved innlogging** starter admin minimert.

## PC-er utenfor klubben
Bruk helst **VPN** (WireGuard eller Tailscale), så virker det som på klubbnettet. Med port forwarding: videresend TCP 47820 og begrens til kjente IP-adresser i ruteren.

## Kjent
- **Battle.net** har ingen kommandolinje. «Start Battle.net» starter appen for den som er logget på Windows, og den oppdaterer selv når «Hold spillene mine oppdatert» er på. Virker ikke når ingen er logget på.
- **Steam Guard:** Kontoer → Steam → *Test innlogging*. Med kontoens `shared_secret` lager PC-ene koden selv.
- **Epic** bruker Legendary, som er uoffisielt.
- Det sjekkes ikke om noen spiller mens det oppdateres. Bruk tidsvinduet.

## Lisens
Én nøkkel per klubb. Admin og hver klient-PC bruker én maskinplass hver (1 admin + 3 klienter = 4 plasser).
- Admin: **🔑 Lisens** → lim inn nøkkelen → *Aktiver*, eller bruk «Lisens» i HQ Launcher. *Send lisens til alle tilkoblede PCer* legger samme nøkkel på klientene.
- **Uten lisens** kan admin bare se PC-ene, og klientene tar ikke imot jobber.

Kjøp lisens på [ithjelper.no](https://ithjelper.no).
