Flask-prosjekt – Dokumentasjon
1. Forside

Prosjekttittel: TO-DO LIST / Matoppskrift-applikasjon
Navn: Omar Dakhil
Klasse: 2 IMI
Dato: 11.03.2025

Kort beskrivelse av prosjektet:
Dette prosjektet er en webapplikasjon utviklet med Flask der brukere kan registrere seg, logge inn og legge til matoppskrifter. Oppskriftene lagres i en database og vises dynamisk på nettsiden. Målet med prosjektet har vært å lære hvordan backend, frontend og database kan fungere sammen i en fullstendig løsning.

2. Systembeskrivelse

Formål med applikasjonen:
Formålet med prosjektet var å utvikle en fungerende webapplikasjon som demonstrerer bruk av Flask som backend-rammeverk, tilkobling mot database og håndtering av brukerinput via HTML-skjemaer. Prosjektet skulle også vise forståelse for grunnleggende autentisering og datasikkerhet.

Brukerflyt:
Brukeren åpner nettsiden og blir sendt til innloggingssiden. Dersom brukeren ikke har konto, kan en ny bruker registreres. Etter innlogging får brukeren tilgang til hovedsiden der oppskrifter kan legges til via et skjema. Når skjemaet sendes inn, behandles data i Flask-backend, lagres i databasen og vises deretter i en tabell på nettsiden.

Teknologier brukt:
Python med Flask
MariaDB
HTML og CSS

Applikasjonen følger en klassisk klient–server-arkitektur der Flask fungerer som applikasjonsserver og MariaDB brukes som datalagring.

3. Server-, infrastruktur- og nettverksoppsett

Servermiljø:
Databasen kjører på en Raspberry Pi konfigurert som databaseserver. Flask-applikasjonen har blitt utviklet og testet fra egen maskin under utviklingsfasen.

Nettverksoppsett:
Klienten (nettleser) kommuniserer med Flask-applikasjonen via HTTP. Flask kobler seg videre til MariaDB-databasen på Raspberry Pi over lokalnettverket ved hjelp av brukernavn og passord lagret i miljøvariabler.

Tjenestekonfigurasjon:
Database-tilkobling håndteres via miljøvariabler definert i .env-fil. Databasebrukeren har begrensede rettigheter for å øke sikkerheten.

4. Prosjektstyring – GitHub Projects (Kanban)

Prosjektet ble strukturert ved hjelp av GitHub Projects med Kanban-tavle. Arbeidet ble delt inn i kolonnene To Do, In Progress og Done. Oppgaver som innlogging, databasekobling og styling ble lagt inn som egne kort.

Refleksjon:
Kanban gjorde det enklere å holde oversikt over hva som var ferdig, hva som gjenstod og hva som var under arbeid. Dette bidro til bedre struktur og progresjon gjennom prosjektperioden.

5. Databasebeskrivelse

Databasenavn: mat_oppskrift

Databasen består av to tabeller. Den ene tabellen lagrer oppskrifter, og den andre lagrer brukerinformasjon for innlogging.

Oppskrift-tabellen inneholder informasjon som navn på oppskrift, ingredienser, fremgangsmåte, koketid, antall porsjoner og hvilken bruker som la den til.
Bruker-tabellen inneholder brukernavn og passord lagret som hash.

Det er foreløpig ingen direkte relasjon mellom tabellene utover at brukernavn lagres sammen med oppskriften.

6. Programstruktur

Prosjektmappen inneholder Flask-applikasjonen og tilhørende filer. Backend-logikk ligger i app.py, HTML-filene ligger i templates-mappen, og CSS-filer ligger i static-mappen. Miljøvariabler for database-tilkobling er lagret i en .env-fil.

Dataflyten i applikasjonen går fra HTML-skjema til Flask-backend, videre til MariaDB-databasen, og deretter tilbake til Flask før det vises dynamisk i HTML ved hjelp av templating.

7. Kodeforklaring

Applikasjonen består av flere Flask-ruter som håndterer både GET- og POST-forespørsler. POST-ruter brukes blant annet til registrering av bruker, innlogging og lagring av nye oppskrifter. Data valideres i backend før de lagres i databasen. Ved innlogging brukes sesjoner for å holde brukeren autentisert.

8. Sikkerhet og pålitelighet

Sensitive opplysninger som databasebruker og passord lagres i miljøvariabler og ikke direkte i kildekoden. Passord for brukere lagres som hash i databasen. Alle databasespørringer er parameteriserte for å forhindre SQL-injection. Applikasjonen skiller mellom innloggede og ikke-innloggede brukere ved hjelp av sesjoner, og databaseforbindelser lukkes etter bruk.

9. Feilsøking og testing

Under utviklingen oppstod flere feil, blant annet problemer med database-tilgang og interne serverfeil. Access denied-feil ble løst ved å opprette korrekt databasebruker med riktige rettigheter. Internal Server Error oppstod på grunn av feil datatyper sendt fra skjema, og ble løst ved å konvertere verdier før lagring.

Testing ble gjort manuelt i nettleser, samt ved å kontrollere databasen direkte for å verifisere at data ble lagret korrekt.

10. Konklusjon og refleksjon

Gjennom prosjektet har jeg lært hvordan Flask fungerer som backend, hvordan HTML-skjemaer kommuniserer med Python, og hvordan man kobler en applikasjon til en database. Jeg har også fått bedre forståelse for feilsøking, prosjektstruktur og grunnleggende sikkerhet.

Det som fungerte best var selve databasekoblingen og visning av data. Det mest utfordrende var håndtering av datatyper og database-rettigheter. Dersom prosjektet skulle blitt gjort på nytt, ville jeg satt opp database og brukere tidligere i prosessen.

11. Kildeliste

w3schools.com
flask.palletsprojects.com
Undervisningsmateriell og egen kode
