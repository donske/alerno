# Gebruikers (en groepen) aanmaken

Het doel van deze opgave is om de opdrachten en de begrippen met betrekking tot gebruikers en groepen te bestuderen, binnen de context van Linux als een multi-user-systeem.

De VM komt met een default user `hogent` - dat ben jij (nu toch nog)! Log in als deze gebruiker.

## Geef hieronder telkens het commando en de uitvoer

### 1. Wat is het commando om de huidige directory op te vragen? In welke map bevind je jou nu?

- **Commando**: pwd
- **Uitvoer**: /home/hogent

### 2. Wat is het UID van deze gebruiker, wat is de GID?

- **Uitvoer**: UID en GID = 1001

### 3. Maak een nieuwe gebruiker aan met de naam `alice`, zonder specifieke opties. Werk hiervoor met `adduser`

- **Commando**: sudo adduser alice

### 4. Voorzie een geschikt wachtwoord voor deze gebruiker (en vergeet het niet! Noteer het eventueel in je verslag of in de beschrijving van je VM)

>! Spoiler text- **Wachtwoord**: alice123

## Configuratiebestanden voor gebruikersbeheer

### 5. In welk bestand kan je de UID, gebruikersnaam, homedirectory, enz. van alle gebruikers terugvinden?

- **Bestand**: 

### 6. In welk configuratiebestand kan je al de bestaande gebruikersgroepen nakijken, en ook de gebruikers die lid zijn van elke groep?

- **Bestand**: 

### 7. In welk configuratiebestand vind je de wachtwoorden van alle gebruikers?

- **Bestand**: 

## Gebruikersgroepen aanmaken

### 8. Maak een groep aan met de naam `sporten`

- **Commando**: 

### 9. In welk configuratiebestand vind je het GID van deze groep terug?

- **Bestand**: 

### 10. Wat zal het GID zijn van de groepen `zwemmen` en `judo` als je deze nu onmiddellijk zou aanmaken? Maak ze aan en controleer

- **Commando**: 

### 11. Voeg de gebruiker `alice` toe aan de groepen `sporten` en `zwemmen`

- **Commando**: 

### 12. Log in als `alice` door in een terminal het commando `su - alice` (let op de spaties!) uit te voeren

### 13. Zorg er nu voor dat de groep `sporten` de primaire groep wordt van `alice`

- **Commando**: 

### 14. Zorg ervoor dat `alice` uitgelogd is, ga terug naar `root`

### 15. Maak nu de gebruikers in onderstaande tabel aan. Zorg ervoor dat ze al meteen bij aanmaken tot de aangegeven groepen behoren. Kies zelf geschikte wachtwoorden voor deze gebruikers en vergeet ze niet (vul eventueel een kolom toe aan de tabel)

| Gebruikersnaam | Primaire groep | Secundaire groep |
|----------------|----------------|------------------|
| bob            | sporten        | judo             |
| carol          | sporten        | zwemmen          |
| daniel         | sporten        | judo             |
| eva            | sporten        | zwemmen          |

- **Gebruikte commando's**: 

### 16. Verwijder nu de gebruiker `alice` en controleer

- **Commando**: 

### 17. Verwijder `alice` uit de groep `zwemmen` - of liever: zorg dat ze enkel nog in de groep `sporten` zit

- **Commando**: 

### 18. Gebruiker `daniel` gaat een tijdje niet meer sporten. Zorg ervoor dat deze gebruiker tot nader order geen toegang meer kan hebben tot het systeem (zonder het wachtwoord of de gebruiker te verwijderen!)

- **Commando**: 

### 19. Hoe kan je controleren dat `daniel` inderdaad geen toegang meer heeft tot het systeem? In welk bestand kan dat en hoe zie je daar dan dat het account afgesloten is?

- **Bestand**: 

### 20. Gebruiker `daniel` komt terug naar de sportclub. Geef hem opnieuw toegang tot het systeem

- **Commando**: 

### 21. Gebruiker `eva` stopt helemaal met sporten. Verwijder deze gebruiker, maar doe dit zorgvuldig: zorg er in het bijzonder voor dat ook haar homedirectory verwijderd wordt

- **Commando**: 

### 22. Log in als de gebruiker `carol`

### 23. Controleer of je in de “thuismap” bent van deze gebruiker. Maak onder deze map een bestand `test` aan door middel van het commando `touch`

- **Commando**: 

### 24. Probeer nu als gebruiker `carol` je te verplaatsen naar de “thuismap” van `alice`

- **Commando**: 

### 25. Kan je de inhoud van de mappen binnen de thuismap van `alice` bekijken?

- **Antwoord**: 

### 26. Probeer nu als `carol` onder de “thuismap” van `alice` ook een bestand `test` te maken. Lukt dit? Kan je dit verklaren?

- **Antwoord**: 

## Werken als root

### 27. Bekijk de eerste regels van het bestand `/etc/shadow`. Wat bemerk je bij de gebruiker `root`?

- **Antwoord**: 

### 28. Log in als de root-gebruiker met het commando `sudo -i` (let op de spatie!)

- **Commando**: 

### 29. Wat is de home-directory van `root`?

- **Antwoord**: 

### 30. Wat is het UID van deze gebruiker, wat is de GID?

- **Commando**: 
- **Uitvoer**: 

### 31. Stel, nog steeds ingelogd als root, een wachtwoord in voor `root`. Kies een uniek, nieuw wachtwoord

- **Commando**: 

### 32. Merk je de verandering in `/etc/shadow`?

- **Antwoord**: 

### 33. Log in als de root-gebruiker met het commando `su -` (let op de spatie!)

- **Commando**: 

### 34. Log uit, en log opnieuw in met `sudo su -`. Wat wordt er anders?

- **Antwoord**: 

## Jezelf toevoegen en admin maken

### 35. Voeg jezelf (met je eigen gekozen loginnaam) toe aan de VM waarin we werken. Gebruik hiervoor `useradd -m`

- **Commando**: 

### 36. Bewerk `/etc/passwd` zodat je ook bash gebruikt als default shell

- **Commando**: 

### 37. Bekijk `/etc/shadow`. Bemerk dat jijzelf als gebruiker nog geen wachtwoord hebt! Stel het in met `passwd`

- **Commando**: 

### 38. Nu wil je jezelf eveneens administrator van het systeem maken, zodat je met `sudo` beheerstaken kan uitvoeren. Aan welke groep voeg je jezelf hiervoor toe (gezien je niet op RHEL aan het werken bent)?

- **Antwoord**: 

## Eigenaars en groepseigenaars veranderen

### 39. Je maakte hierboven reeds 2 groepen aan met de namen `zwemmen` en `judo`. Maak als root onder `/srv/` twee directories aan met de naam `groep/zwemmen/` en `groep/judo/`. Zorg dat de groepen eigenaar zijn van de overeenkomstige directories en dat `carol` eigenaar is van directory `zwemmen` en `bob` van directory `judo`. Geef de gebruikte commando’s en controleer

```bash
# ls -l groep/
total 8
drwxr-xr-x 2 bob   judo    4096 Sep 24 21:32 judo
drwxr-xr-x 2 carol zwemmen 4096 Sep 24 21:32 zwemmen
