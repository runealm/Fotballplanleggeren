# Fotballplanleggeren ⚽

Fotballplanleggeren er et enkelt verktøy for å generere kampoppsett for kampkvelder i barnefotballen. Angi lag, baner og spilletid — verktøyet fordeler kampene jevnt og produserer et oppsett du kan kopiere rett inn i Spond.

Live på: [almenningdata.no/fotball](https://almenningdata.no/fotball/)

## 🚀 Funksjoner

- Genererer kampoppsett basert på antall lag, baner og ønskede kamper per lag
- Slot-/runde-basert algoritme som fordeler kampene jevnt og minimerer ventetid mellom kamper
- "Generer på nytt"-knapp gir alternative oppsett med samme parametere
- Automatisk advarsel når antall baner overstiger det som faktisk kan brukes
- Duplikat-sjekk på lagnavn (case-insensitive)
- Sammendrag som viser antall kamper per lag
- Visning av dato og kampvert over tabellen
- Print-vennlig utskrift (Ctrl+P / Cmd+P) — skjuler skjema og knapper, viser ren tabell
- Kopier kampoppsett rett til utklippstavlen for innliming i Spond
- Fallback: hvis automatisk kopiering blokkeres (sandkasse, gammel nettleser), vises teksten i en boks for manuell kopiering
- Tilbakemelding på knappene ved trykk ("✓ Kopiert!", "✓ Nytt oppsett!")
- Alt kjører lokalt i nettleseren — ingen data lastes opp eller lagres

## 🧩 Teknologi

Ren HTML, CSS og JavaScript. Ingen rammeverk, ingen avhengigheter.

## 🖥️ Bruk

1. Åpne `index.html` i en nettleser (eller besøk live-versjonen)
2. Skriv inn lagene (ett per linje eller kommaseparert)
3. Fyll ut innstillingene:
   - Antall baner
   - Kamper per lag
   - Spilletid og pause mellom kamper
   - Dato (default: dagens dato) og starttid
   - Kampvert (valgfritt)
4. Klikk **"Generer kampoppsett"**
5. Klikk eventuelt **"Generer på nytt"** for et alternativt oppsett
6. Klikk **"Kopier til Spond"** og lim inn i et Spond-arrangement

## 📂 Struktur

```
fotballplanleggeren/
├── index.html   # Hele applikasjonen (HTML, CSS, JS i én fil)
├── logo.png     # Logo som vises i headeren
└── README.md    # Denne filen
```

## 🧠 Algoritme

Verktøyet bruker en **runde-basert greedy-algoritme** som fyller én tidsslot om gangen:

1. Genererer alle mulige par mellom lagene
2. For hver runde: velger opptil `antall baner` kamper der ingen lag spiller to ganger samtidig og ingen lag har nådd kamp-grensen
3. Prioriterer lag som har spilt færrest kamper for å fordele jevnt
4. Fortsetter til alle lag har spilt ønsket antall kamper

Ved "Generer på nytt" stokkes par-rekkefølgen tilfeldig og algoritmen kjøres flere ganger til den finner et resultat med fullstendig kampfordeling.

**Viktig matematisk grense:** Maksimalt antall samtidige kamper = `floor(antall lag / 2)`. Hvis du f.eks. har 5 lag og 3 baner, kan kun 2 baner brukes samtidig — den 3. ville stått tom (4 lag spiller, 1 hviler). Verktøyet varsler om dette automatisk.

## 📤 Eksport til Spond

Klikk "Kopier til Spond" → teksten kopieres til utklippstavlen og kan limes rett inn i beskrivelsesfeltet i et Spond-arrangement. Eksempel-format:

```
13.05.2026
Kampvert: Åfoss Arena

Kl 17:00:
Bane 1: Storm Blå vs Åfoss G7
Bane 2: Storm Hvit vs Skidar Sort
Bane 3: Storm Rød vs Gjerpen Rød

Kl 17:20:
Bane 1: Gjerpen Blå vs Skidar Rød
...
```

## ⚙️ Default-verdier

Default-verdiene er satt i tråd med **NFF Telemarks anbefaling** for 3'er-serie:

- Spilletid: 15 minutter
- Pause mellom kamper: 5 minutter (gir 20 minutters intervall mellom kampstart)

## 🧾 Lisens

Dette prosjektet er utviklet av Almenning Data. Fritt å bruke, endre og tilpasse så lenge opphavet krediteres.