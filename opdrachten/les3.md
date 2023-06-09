# Les 3

## Opdracht 1 - Basisproject Laravel

### Tonen van een View

- Maak een HomeController aan in de terminal
  ```
  php artisan make:controller HomeController
  ```
- Maak in de map `resources/views` een nieuw [blade-bestand](https://laravel.com/docs/10.x/blade) aan genaamd `home.blade.php`.
- Plaats hier een basisbestand met HTML en een welkomsttekst. 
- Maak de `index` functie aan in de `HomeController` en zorg dat de view geladen wordt.
- Zorg er in de [routes](https://laravel.com/docs/10.x/routing) voor dat `/home` afgevangen wordt er een verwijzing is naar de juiste controller.

### Informatie doorgeven aan de View

- Open de `HomeController` en ga naar de index functie. 
- Geef extra informatie mee aan de view bij de regel `return view('home');`
- Maak boven deze regel een variabele aan waar je tekst of de datum van vandaag in opslaat. 
- Stuur deze variabele mee als tweede parameter met de `compact()` functie .

### informatie vanuit de URL doorsturen naar de View

Maak de welkomsttekst op de homepagina persoonlijk door je naam vanuit de url mee te geven aan de View. De homepagina toont vervolgens _Hallo [Jouw naam]_

- In je browser voer je straks de volgende URL in: http://127.0.0.1:8000/home/jouw%20naam
- Je mag gewoon met spaties werken, de browser zal dit omzetten naar %20
- Zorg er in de route voor dat [extra informatie](https://laravel.com/docs/10.x/routing#route-parameters) in de URL opgevangen kan worden. 
- In de [`HomeController`](https://laravel.com/docs/10.x/controllers) zal je deze informatie als parameter moeten opvangen.
- Net als in de vorige opdracht kan je de informatie uit de parameter doorsturen naar de View. 
- Toon de informatie in [`home.blade.php`](https://laravel.com/docs/10.x/blade).

## Opdracht 2 - User Stories

- Beschrijf de werking en de functionaliteit van je applicatie. 
  - Denk in User Stories, taken en stakeholders.
- Stel de prioriteit vast met de MoSCoW methode. 
  - Maak het jezelf niet te moeilijk en begin met makkelijke taken. Begin niet met de login, maar volg de praktijkonderdelen uit de lessen. Vertaal bijvoorbeeld eerst [opdracht 1](https://github.com/HR-CMGT/PRG05-2023-2024/blob/main/opdrachten/les3.md#opdracht-1---basisproject-laravel) naar jouw eigen systeem.
  - Gebruik ter referentie toelichting_praktijkopdracht.pdf
- Maak hiervan een planning voor de komende weken.



## Opdracht 3 - ERD
Doorloop de user stories van je project en bepaal aan de hand van deze taken welke informatie je wilt gaan opslaan in de database. 
Maak een ERD in bijvoorbeeld [Miro](https://miro.com/nl/), [Lucidchart](https://www.lucidchart.com/pages/landing) of [draw.io](https://www.drawio.com/)

Hou rekening met de volgende onderdelen: 
1. Zorg dat je data maar op 1 plek wordt opgeslagen. Dus bijvoorbeeld de adresgegevens van een klant maar in 1 tabel.
2. Wanneer er sprake is van een 1-op-veel relatie, let dan goed op de primairy en foreign keys.
3. Wanneer er sprak is van een veel-op-veel relatie dat je een koppeltabel moet maken. 
4. Gebruik Engelse naamgeving.
5. Naam van de tabel heeft kleine letters en is in meervoud.
6. Wanneer een veld meerdere woorden bevat zijn de woorden gescheiden voor een underscore (`remember_token`).
