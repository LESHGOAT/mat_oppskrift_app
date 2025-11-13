Flask-prosjekt – Dokumentasjon
1.	Forside
Prosjekttittel: TO-DO LIST
Navn: Omar Dakhil
Klasse: 2 IMI
Dato: 11.03.2025
Kort beskrivelse av prosjektet:
Dette prosjektet er en enkel to-do-applikasjon laget med Flask. Brukeren kan skrive inn oppgaver i et skjema, og se dem dukke opp i en liste på nettsiden. Målet med prosjektet er å lære hvordan Flask fungerer sammen med HTML-skjemaer og hvordan data kan sendes mellom frontend og backend. Senere skal applikasjonen utvides med en database for å lagre oppgavene permanent.
Skjermbilde: legg inn skjermbilde av startside her
2.	Systembeskrivelse
Formål med applikasjonen: Målet var å lage en fungerende to-do-applikasjon som demonstrerer kunnskap i Flask og Python, samt grunnleggende HTML-skjemaer og datastrøm fra frontend til backend.
Brukerflyt: Brukeren åpner nettsiden, skriver inn en oppgave i skjemaet, oppgaven blir sendt til Flask-backend via POST-metoden, og vises i en liste på siden. Senere vil oppgavene lagres i MySQL-database for permanent lagring.
Teknologier brukt: Python / Flask, MySQL, HTML / CSS
Skjermbilde: legg inn skjermbilde av brukerflyt eller skjema her
3.	Databasebeskrivelse
Databasenavn: mat_oppskrift
Tabeller: Tabell oppskrift har feltene id som primærnøkkel, name som VARCHAR, ingredienser som TEXT, fremgangsmåte som TEXT, koketid som FLOAT, prsjoner som INT.
SQL-eksempel: CREATE TABLE oppskrift med id, name, ingredienser, fremgangsmåte, koketid og prsjoner.
Relasjoner mellom tabeller: foreløpig ingen, da prosjektet kun har én tabell.
Skjermbilde: legg inn skjermbilde av tabellstruktur i MySQL her
________________________________________
4.	Programstruktur
Mappestruktur: prosjektmappen mat_oppskrift inneholder app.py som Flask-applikasjon og backend-logikk, templates/index.html for HTML-skjema og listevisning, static/style.css for styling, og .env som lagrer miljøvariabler for MySQL.
Databasestrøm: HTML-skjema går til Flask (Python), videre til MySQL, tilbake til Flask og vises i HTML-liste.
Skjermbilde: legg inn skjermbilde av prosjektmappe her
________________________________________
5.	Kodeforklaring
Eksempel på rute i Flask: ruten tar imot data fra HTML-skjema, kobler til MySQL-database, setter inn data i tabellen og sender brukeren tilbake til oversiktssiden.
Jeg opplevde flere frustrerende problemer underveis: først fikk jeg en “Internal Server Error 500” når jeg prøvde å legge til oppskrifter. Etter mye frustrasjon oppdaget jeg at koketid og porsjoner ble sendt som tekst (string) fra HTML-skjemaet, mens databasen forventet float og int. Etter at jeg konverterte disse verdiene til riktige datatyper, begynte det å fungere.
Jeg hadde også problemer med MySQL-bruker og rettigheter. Jeg fikk “Access denied” flere ganger før jeg opprettet en egen bruker med riktige privileges. Etter at dette ble fikset, kunne jeg koble til databasen uten problemer.
Skjermbilde: legg inn skjermbilde av funksjonen i bruk her
________________________________________
6.	Sikkerhet og pålitelighet
Bruk av .env og miljøvariabler: Passord og brukernavn lagres trygt i .env-filen, slik at de ikke ligger i koden.
Eksempel: DB_HOST=localhost, DB_USER=flaskuser, DB_PASSWORD=hemmelig, DB_NAME=mat_oppskrift
Bruk av parameteriserte spørringer: %s brukes for å forhindre SQL-injection.
Andre sikkerhetstiltak: Validering av input, feilhåndtering og lukking av databaseforbindelser.
Skjermbilde: legg inn skjermbilde av .env og innstillinger her
________________________________________
7.	Feilsøking og testing
Typiske feil: fikk “Access denied” når brukeren ikke hadde riktige privilegier, fikk også “Template not found” før mappestrukturen var korrekt.
Hvordan løste jeg det: laget riktig MySQL-bruker, testet tilkobling i Python, flyttet HTML-filer til templates-mappen, konverterte datatyper i POST-ruten for å unngå 500-error.
Testmetoder: testet skjemaer manuelt i nettleser, brukte print() for å sjekke dataflyt, sjekket databasen med SELECT * FROM oppskrift.
Skjermbilde: legg inn skjermbilde av testkjøringer her
________________________________________
8.	Konklusjon og refleksjon
Hva lærte jeg: Jeg lærte hvordan Flask fungerer med HTML-skjemaer og hvordan man kobler til MySQL fra Python. Jeg lærte også å bruke .env for sikker lagring av passord og viktigheten av riktige datatyper ved innsending av skjema.
Hva fungerte bra: Tilkoblingen til databasen og bruk av parameteriserte spørringer.
Hva ville jeg gjort annerledes: Jeg ville laget databasen og MySQL-brukeren først for å unngå frustrerende feilmeldinger tidlig.
Hva var utfordrende: Håndtering av MySQL-privilegier, riktig mappestruktur, og feilsøking av 500-error på grunn av datatyper. Løsningen var å teste steg-for-steg, konvertere verdier og sikre riktig brukerrettigheter.
Skjermbilde: legg inn skjermbilde av endelig applikasjon her
________________________________________
9.	Kildeliste
https://www.w3schools.com/python/
https://flask.palletsprojects.com/
Egen kode fra undervisningen

