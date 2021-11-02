# Betingelser, Events og styling

## Rød Cirkel.
1. Hvis værdien er 1
    1. skift cirklens baggrundsfarve til grøn
    2. Udskriv værdien + "Success"
2. Hvis værdien er 5.
    1. Skift farven på cirklen til sort.
    2. Skift tekst-farven til hvid.
    3. Udskriv værdien + "Success"
3. Hvis værdien er over 10.
    1. Skift farven på cirklen til gul.
    2. Skift tekst-farven til sort.
    3. Udskriv værdien + "Success"
4. Hvis værdien er over 15.
    1. Skift farven på cirklen til lilla.
    2. Skift tekst-farven til hvis.
    3. Udskriv værdien + "Start forfra"
    4. Nulstil værdien.

**Generelt skal cirklen være rød med hvid tekst og udskrive selve værdien.**

## Grøn Cirkel.
1. Hvis værdien er under 200
    1. skift cirklens baggrundsfarve til blå
    2. Skift tekst-farven til hvid.
    3. Udskriv værdien + "Er mindre end 200"
2. Hvis værdien er 200 eller derover, men under 400.
    1. Skift farven på cirklen til sort.
    2. Skift tekst-farven til hvid.
    3. Udskriv værdien + "Er større end 200 og mindre end 400"
2. Hvis værdien er over 400.
    1. Skift farven på cirklen til rød.
    2. Skift tekst-farven til hvid.
    3. Udskriv værdien + "Er større end 400"

## Gul Cirkel      
Husk boksen/cirklen er 200 pixels i højde og bredde som udgangspunkt.

1. I cirklen vil vi gerne udskrive boksen størrelse: (200 + den værdi vi tæller op eller ned) + "px".
2. Når vi scrolle op skal værdien forøges.
3. Når vi scroller ned skal værdien formindskes. 
2. Ændre tekst størrelsen til 30px.
3. Ændre tekst-farven til hvid.

Eventuelt:
1. Forstør boksen når vi scroller op. (undersøg: style, height, width) 
2. Fomindsk boksen når vi scroller ned. (undersøg: style, height, width) 

## Lilla Cirkel        
1. Vi lytter på hvert eneste keyboard tryk. Og denne funktion bliver "kørt".
2. Vi vil bare udskrive hvad vi har trykket på, men vi vi gerne vide om det er et tal eller noget andet.
3. Se console.log ovenfor, prøv at undersøg hvad der sker, udskriv værdierne hver for sig.
4. Hvis det IKKE er tal = Udskriv i cirklen : "Du har trykket " + hvad der er klikket
5. Hvis det ER tal = Udskriv i cirklen : "Du har trykket et tal " + det tal der er trykket.

## Blå Cirkel      
Lige nu, "lytter" vi på alt hvad der bliver skrevet i input feltet.
Når vi skriver "kode" så  rammer vi koden lige ovenfor.

Vi vil gerne kunne skrive følgende kommandoer og når vi gør det, 
ændre vi den pågældende cirkels farver.

1. changeGreen
2. changeRed
3. changeYellow
4. changePurple
5. ChangeMe

Fælles for alle er at de ændre den pågældende cirkel til:
    1. Sort baggrund
    2. Hvid tekst.

Denne cirkel skal ændres til det "sort" når vi skrive changeMe.
Men eller skal den forblive blå.

## Pink Cirkel
1. Sæt Cirklens Bagrundsfarve = hvad der er valgt via ```<select>``` boksen.
2. Tilføj 10 farver til select boksen. (se html´en).
3. Brug console.log for at finde ud af hvad parameteret "event" indeholder. 
4. Kig eventuelt på activateBlue Funktionen se om du kan bruge noget.

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Event Maskiner</title>
        <style>

            body {

                font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
                background-color: slategrey;
                margin: 0;
                box-sizing: border-box;
            }

            .click-machine-container {

                text-align: center;
                color: #ffffff;

            }

            .box-container {

                display: flex;
                justify-content: center;
                align-items: center;    

            }

            .box {

                display: flex;
                justify-content: center;
                align-items: center;

                margin: 10px;
                color: white;

                font-size: 18px;
                width: 200px;
                height: 200px;

                border: 2px white solid;
                border-radius: 100px; 

                user-select: none;
                box-shadow: 2px 7px 5px #333;

            }

            .box-red {
                background-color: red;
            }

            .box-green {
                background-color: green;
            }

            .box-yellow {
                background-color: yellow;
                color: black;
            }

            .box-purple {
                background-color: purple;
            }

            .box-blue {
                background-color: blue;
            }
            .box-pink {
                background-color: pink;
            }

            input {
                width: 80%;
                height:30px;
                text-align: center;
                border-radius: 6px;
                border-color: transparent;
                border : 0;
                /* background-color: transparent; */
                font-size: 18px;
            }

            input:focus {
                border-color: transparent;
            }

            input:focus-visible {
                border-color: transparent;
                border : 0;
                outline: none;
            }

            input:active {
                border-color: transparent;

            }

            select {
                text-align: center;
                font-size: 18px;
                border-radius: 6px;
                height:30px;
                outline: none;
                width: 80%;
            }

        </style>
    </head>
    <body>

        <div class="click-machine-container">
            <h1>Event & Betingelser - Maskiner.</h1>
            <div class="box-container">

                <div class="box box-red">Event "click"</div>
                <div class="box box-green">Event "mousemove"</div>
                <div class="box box-yellow">Event "wheelscroll"</div>
                <div class="box box-purple">Event "Key"</div>
                <div class="box box-blue">
                    <input id="blueInput" placeholder="indtast"/>
                </div>
                <div class="box box-pink">
                    <select id="pinkSelect">
                        <option>vælg</option>
                        <option>red</option>
                        <option>black</option>
                    </select>
                </div>

            </div>
        </div>

        <script>

            /*
            
                Her sætter vi alle variabler op.
                Jeg har sat dem op fordi denne opgave handler om det der sker i vores funktioner.

                Du må gerne tilføje/ændre, det vigtigste er at du søger en løsning og at du bruger tiden
                på at forstå og ikke nødvendigvis at nå langt.

                Slet bare opgave formuleringerne i hver funktion de er tilgængelige der hvor du kopieret denne template.

            */

            // Cirkler.
            let boxRedElement = document.querySelector('.box-red');
            let boxGreenElement = document.querySelector('.box-green');
            let boxYellowElement = document.querySelector('.box-yellow');
            let boxPurpleElement = document.querySelector('.box-purple');
            let boxBlueElement = document.querySelector('.box-blue');
            let boxPinkElement = document.querySelector('.box-pink');

            // Input Elementer - Dette er referencer til input elementerne.
            // Se HTML elementer ovenfor. I blue og pink box.
            let blueInput = document.querySelector('#blueInput');
            let pinkSelect = document.querySelector('#pinkSelect');

            // Counters/tællere.
            let countRed = 0;
            let countGreen = 0;
            let countYellow = 0;
        
            // Cirkel Events - Her Aktivere vi de forskellige funktioner alt efter event.

            boxRedElement.addEventListener('click', activateRed);
            boxGreenElement.addEventListener('mousemove', activateGreen);
            boxYellowElement.addEventListener('mousewheel', activateYellow);
            boxBlueElement.addEventListener('input', activateBlue);
            boxPinkElement.addEventListener('input', activatePink);

            // Keyboard Event
            window.addEventListener('keydown', activatePurple);

            // Når vi klikker på rød.
            function activateRed() {

                countRed++;

                if(countRed === 1) {

                    boxRedElement.style.backgroundColor = 'green';
                    boxRedElement.innerHTML = `${countRed}<br/>Success`;

                }

                // Undersøg denne console.
                // console.log('countRed', countRed);

                /*
                    1. Hvis værdien er 1
                        1. skift cirklens baggrundsfarve til grøn
                        3. Udskriv værdien + "Success"

                    2. Hvis værdien er 5.
                        1. Skift farven på cirklen til sort.
                        2. Skift tekst-farven til hvid.
                        3. Udskriv værdien + "Success"
 
                    2. Hvis værdien er over 10.
                        1. Skift farven på cirklen til gul.
                        2. Skift tekst-farven til sort.
                        3. Udskriv værdien + "Success"

                    2. Hvis værdien er over 15.
                        1. Skift farven på cirklen til lilla.
                        2. Skift tekst-farven til hvis.
                        3. Udskriv værdien + "Start forfra"
                        4. Nulstil værdien.

                    Generelt skal cirklen være rød med hvid tekst og udskrive selve værdien.
                */

            }

            // Når vi flytter musen over grøn.
            function activateGreen() {
                
                countGreen++;

                // Undersøg denne console.
                // console.log('countGreen', countGreen);

                /*
                    1. Hvis værdien er under 200
                        1. skift cirklens baggrundsfarve til blå
                        2. Skift tekst-farven til hvid.
                        3. Udskriv værdien + "Er mindre end 200"

                    2. Hvis værdien er 200 eller derover, men under 400.
                        1. Skift farven på cirklen til sort.
                        2. Skift tekst-farven til hvid.
                        3. Udskriv værdien + "Er større end 200 og mindre end 400"
 
                    2. Hvis værdien er over 400.
                        1. Skift farven på cirklen til rød.
                        2. Skift tekst-farven til hvid.
                        3. Udskriv værdien + "Er større end 400"
                */

            }
       
            // Nå vi Mus Scroller i Gul
            function activateYellow(event) {

                // Prøv at udskrive denne consol.
                // console.log('activateYellow :: Event parameter', event.deltaY);

                /*
                    Husk boksen/cirklen er 200 pixels i højde og bredde som udgangspunkt.

                    1. I cirklen vil vi gerne udskrive boksen størrelse: (200 + den værdi vi tæller op eller ned) + "px".
                    2. Når vi scrolle op skal værdien forøges.
                    3. Når vi scroller ned skal værdien formindskes. 
                    2. Ændre tekst størrelsen til 30px.
                    3. Ændre tekst-farven til hvid.

                    Eventuelt:
                    4. Forstør boksen når vi scroller op. (undersøg: style, height, width) 
                    5. Fomindsk boksen når vi scroller ned. (undersøg: style, height, width) 
        
                */

            }
       
            // Når vi klikker tasterne på vores keyboard.
            function activatePurple(event) {

                // Prøv at udskrive denne console log.
                // console.log('activatePurple :: Event parameter', event.code, event.keyCode, event.key, isNaN(event.key));
                
                /*

                    1. Vi lytter på hvert eneste keyboard tryk. Og denne funktion bliver "kørt".
                    2. Vi vil bare udskrive hvad vi har trykket på, men vi vi gerne vide om det er et tal eller noget andet.
                    3. Se console.log ovenfor, prøv at undersøg hvad der sker, udskriv værdierne hver for sig.
                    4. Hvis det IKKE er tal = Udskriv i cirklen : "Du har trykket " + hvad der er klikket
                    5. Hvis det ER tal = Udskriv i cirklen : "Du har trykket et tal " + det tal der er trykket.
            
                */
            }

             // Når vi skriver i vores input.
            function activateBlue(event) {

                // Prøv at udskrive denne console log og skriv noget i input feltet.
                // console.log('activateBlue :: Event parameter', event.target.value);

                if(event.target.value === 'kode') {

                    boxBlueElement.style.backgroundColor = 'black';
                    boxBlueElement.style.color = 'white';

                }

                /*
                
                    Lige nu, "lytter" vi på alt hvad der bliver skrevet i input feltet.
                    Når vi skriver "kode" så  rammer vi koden lige ovenfor.

                    Vi vil gerne kunne skrive følgende kommandoer og når vi gør det, 
                    ændre vi den pågældende cirkels farver.

                    1. changeGreen
                    2. changeRed
                    3. changeYellow
                    4. changePurple
                    5. ChangeMe

                    Fælles for alle er at de ændre den pågældende cirkel til:
                        1. Sort baggrund
                        2. Hvid tekst.

                    Denne cirkel skal ændres til det "sort" når vi skrive changeMe.
                    Men eller skal den forblive blå.
                    
                */

            }
  
            // Når vi vælger et element
            function activatePink(event) {

                /*
                
                    1. Sæt Cirklens Bagrundsfarve = hvad der er valgt via <select> boksen.
                    2. Tilføj 10 farver til select boksen. (se html´en).
                    3. Brug console.log for at finde ud af hvad parameteret "event" indeholder. 
                    4. Kig eventuelt på activateBlue Funktionen se om du kan bruge noget.

                */

            }
  </script>
    </body>
</html>
```

