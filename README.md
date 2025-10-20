# Fotballplanleggeren ⚽
Fotballplanleggeren er et enkelt verktøy for å generere kampoppsett for barne- og ungdomsturneringer.
Du kan angi lag, baner, spilletid, pauser, kampdager og ekskluderte datoer — og deretter eksportere alt direkte til Spond (CSV eller tekst).

🚀 Funksjoner
- Generer kampoppsett automatisk basert på antall lag
- Støtte for både ukedager og helger
- Angi antall baner, spilletid, pause, startdato og tidspunkt
- Ekskluder datoer som ikke passer
- Støtte for oddetalls-lag (automatisk pause)
- Eksporter kampoppsettet som:
        CSV-fil for Spond
Tekst som kan kopieres og limes rett inn i Spond
Alt kjører lokalt i nettleseren — ingen data lastes opp

🧩 Teknologi

Ren HTML, CSS og JavaScript
Ingen rammeverk eller avhengigheter

🖥️ Bruk

Åpne index.html i en nettleser
Skriv inn lagene (ett per linje eller kommaseparert)
Fyll ut ønskede innstillinger:
Antall baner
Spilletid og pause
Kampdager (ukedager eller helger)
Startdato og tidspunkt
Eventuelle datoer som ikke passer
Kampvert / arrangør (valgfritt)
Klikk "Generer kampoppsett"
Eksporter til Spond via:
"Eksporter til Spond (CSV)", eller
"Kopier til Spond" for å lime inn direkte

📂 Struktur

fotballplanleggeren/

├── index.html        # Hele applikasjonen (HTML, CSS, JS)

├── logo.png          # Logo som vises i headeren

└── README.md         # Denne filen

🧠 Logikk for kampoppsett

Bruker round-robin-prinsippet (alle møter alle)
Ved oddetall lag legges et fiktivt “PAUSE”-lag til
Maksimalt antall samtidige kamper = min(antall baner, halvparten av lagene)
Kampene genereres sekvensielt per runde med korrekt tidshåndtering

📤 Eksport til Spond

CSV-formatet som genereres er kompatibelt med import i Spond-arrangementer:
Kolonne	Beskrivelse
Tittel	Felles tittel på arrangementet
Beskrivelse	Alle kamper med klokkeslett, bane og lag
Dato	Første kampdato
Tid	Første kampstart
Sted	Fritt tekstfelt (default “Fotballbanen”)

🧾 Lisens

Dette prosjektet er utviklet av Almenning Data (2025).
Fritt å bruke, endre og tilpasse så lenge opphavet krediteres.

💡 Fremtidige forbedringer (idéer)

Lagre og laste inn tidligere oppsett (LocalStorage)
Støtte for flere spilledager / turneringer
Eksport til PDF
Automatisk balansering av bane og tid mellom lag