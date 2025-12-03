Matoppskrift – Flask Prosjekt

Navn: Omar Dakhil
Klasse: 2 IMI
Dato: 11.03.2025

Dette er et skoleprosjekt hvor jeg laget en enkel nettside der man kan registrere bruker, logge inn og legge inn matoppskrifter. Oppskriftene lagres i en MySQL-database som kjører på en Raspberry Pi. Nettsiden er laget med Flask, HTML og CSS.

Skjermbilde av nettsiden ligger i egen folder

1. Formål

Målet var å lage en fungerende webapplikasjon som kobler sammen Flask og en database. Jeg skulle lære hvordan man håndterer innlogging, registrering og lagring av data i MySQL.

2. Hvordan nettsiden fungerer

Når man åpner nettsiden kan man enten registrere en ny bruker eller logge inn hvis man allerede har en. Etter innlogging kommer man til en side der man kan legge inn en oppskrift. Når skjemaet sendes inn, blir informasjonen sendt til Flask og derfra lagret i databasen. Alle oppskrifter som er lagret vises deretter i en liste på nettsiden.

Skjermbilde av skjema eller brukerflyt ligger i egen folder

3. Database

Jeg bruker en MySQL-database med to tabeller: en for brukere og en for oppskrifter. Brukertabellen inneholder brukernavn og passord (lagret som hash). Oppskriftstabellen inneholder navn, ingredienser, fremgangsmåte, koketid, porsjoner og hvem som la den inn.

Databasen ligger på en Raspberry Pi, og Flask kobler til via localhost.

Skjermbilde av database ligger i egen folder

4. Mappestruktur

Prosjektet er organisert slik at Flask-filene ligger i hovedmappen, HTML-filene ligger i templates-mappen, og CSS-filene ligger i static-mappen. En egen .env-fil brukes for å lagre databaseinformasjon som brukernavn, passord og databasenavn.

Skjermbilde av mappestruktur ligger i egen folder

5. Problemer underveis

Under utviklingen støtte jeg på en del feil, blant annet:

Innlegging av oppskrifter feilet fordi verdier som koketid og porsjoner ikke hadde riktig datatype i databasen. Dette løste jeg ved å endre datatypene.

Databasen nektet tilgang i starten. Dette skyldtes manglende rettigheter på MySQL-brukeren. Jeg laget en ny bruker med riktige rettigheter, og da fungerte det.

Flask fant ikke HTML-filene før jeg flyttet dem inn i templates-mappen, som Flask krever.

Skjermbilde av feilsøking ligger i egen folder

6. Sikkerhet

Selv om prosjektet er enkelt, har jeg gjort noen grunnleggende sikkerhetstiltak. Passord lagres ikke direkte, men som hash. Jeg bruker .env-fil for å ikke ha databasepassord direkte i koden. Jeg bruker også parameteriserte spørringer for å unngå SQL-injection.

Skjermbilde av .env eller sikkerhetsoppsett (masker passord)  ligger i egen folder

7. Testing

Jeg testet prosjektet ved å:

registrere flere brukere

logge inn og ut

legge inn forskjellige oppskrifter

sjekke at de dukket opp i databasen

teste sletting

teste feil passord og feil innlogging

Skjermbilde av testing ligger i egen folder

8. Konklusjon

Prosjektet fungerer slik det var tenkt. Jeg fikk nettsiden til å kommunisere med databasen, og alt av registrering, innlogging og lagring fungerer. Jeg lærte mye om hvordan Flask og MySQL fungerer sammen, og hvordan man strukturerer et lite webprosjekt.

Skjermbilde av ferdig resultat ligger i egen folder
________________________________________
9.	Kildeliste
https://www.w3schools.com/python/
https://flask.palletsprojects.com/
Egen kode fra undervisningen

