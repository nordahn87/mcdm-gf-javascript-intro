# Klik Maskinen.

**Klik Maskinen** er en lille applikation hvor vi løbende forsøger at benytte de ting vi lære i små intervaller.

Fordi JavaScript består af en masse "bibliotekter" og ofte er alle "starter" tutorials, små isoleret eksempler, så det kan være svært at se hvordan sammenhængen er.

Vi stræber ikke efter den optimale applikation det handler mere om at bevæge os imod en optimal applikation.

Der vil ikke være ret meget dokumentation herinden, foruden templates, det vil foregå i undervisningen, sammenholdt med kompendiet.

1. [Klik mig](#clickMe)
    1. [Klik mig - Console](#clickMe-console)
    2. [Klik mig - Function](#clickMe-function)
2. [Der tælles](#counting)
    1. [Tæller klik](#counting-arit)
    2. [Opgave - Functions](#counting-opg-0)
    3. [Opgave - Fælles Reset](#counting-opg-0)
3. [Der sættes betingelser](#conditions)
    1. [If/Else](#conditions)

## 1. Klik mig <a name="clickMe"></a>

Under afsnit 1. arbejder vi med.

* Variabler.
* Funktioner.
* Få fat i Elementer.
* Og en lille smule Event.

### 1.1 Klik mig - Console <a name="clickMe-console"></a>

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>klik Maskine</title>

        <style>

            body {

                font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
                background-color: slategrey;
                margin: 0;

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

                font-size: 22px;
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

        </style>
    </head>
    <body>

        <div class="click-machine-container">
            <h1>Klik Maskine</h1>
            <div class="box-container">

                <div class="box box-red" onclick="console.log('Du har klikket elementet')">Klik Mig!</div>

            </div>
        </div>

    </body>
</html>
```

### 1.2 Klik mig - Function <a name="clickMe-function"></a>

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Klik Maskine</title>

        <style>

            body {

                font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
                background-color: slategrey;
                margin: 0;

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

                font-size: 22px;
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

        </style>
    </head>
    <body>

        <div class="click-machine-container">
            <h1>Klik Maskine</h1>
            <div class="box-container">

                <div class="box box-red" onclick="clickMe()">Klik Mig!</div>

            </div>
        </div>

        <script>

            function clickMe() {
                
                console.log('Du har klikket elementet');
             
            };
    
            
        </script>
    </body>
</html>
```

## 2. Der tælles. <a name="counting"></a>

Under afsnit 2. arbejder vi med.

* Mere med Variabler.
* textContent, innerHTML, innerText
* Functions.
* Aritmetik.
* Elementer.
* Event Listeners.

### 2.1 Tæller klik - Function <a name="counting-arit"></a>
```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Dom Manipulation</title>

        <style>

            body {

                font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
                background-color: slategrey;
                margin: 0;

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

                font-size: 22px;
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

        </style>
    </head>
    <body>

        <div class="click-machine-container">
            <h1>Klik Maskine</h1>
            <div class="box-container">

                <div class="box box-red" onclick="countRedBoxClicks()"></div> +
                <div class="box box-green"></div> =
                <div class="box box-yellow"></div>

            </div>
        </div>

        <script>

            let boxRedElement = document.querySelector('.box-red');
            let redCount = 0;
            
            boxRedElement.textContent = redCount;
        
            function countRedBoxClicks() {
                
                redCount += 1;
                boxRedElement.textContent = redCount;
             
            };
    
            
        </script>
    </body>
</html>

```

### 2.2 Opgave - Functions <a name="counting-opg-0"></a>

1. Tilføj 'klik' funktionalitet til den grønne boks, og tæl de grønne klik for sig selv.
2. For hvert 'klik' på både rød og grøn, kald en funktion du selv laver, der udskriver et samlet resultat af grøn og rød i den gule boks. 

### 2.3 Fælles Opgave

1. Vi tilføjer en 'nulstils' knap så vi kan nulstille vores maskine.
2. I den forbindelse flytter vi onclick til addEventListener og taler lidt om den.
3. VI prøve f.eks at benytte forskellige events på de rød og grøn cirkel.

## 3. Der sættes betingelser. <a name="conditions"></a>

Under afsnit 3. arbejder vi med.

* Betingelser if/else
* Styling
* classList

### 3.1 If/Else
1. Vi skal arbejde med if/else og styling.
2. Switch

```HTML 
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Dom Manipulation</title>

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

                font-size: 22px;
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

        </style>
    </head>
    <body>

        <div class="click-machine-container">
            <h1>Klik Maskine</h1>
            <div class="box-container">

                <div class="box box-red"></div> +
                <div class="box box-green"></div> =
                <div class="box box-yellow"></div>

            </div>
            <div class="action-container">
                <button class="button">RESET</button>
            </div>
        </div>

        <script>


            let boxRedElement = document.querySelector('.box-red');
            let boxGreenElement = document.querySelector('.box-green');
            let boxYellowElement = document.querySelector('.box-yellow');
            let resetButton = document.querySelector('.button');

            let redCount = 0;
            let greenCount = 0;
            let yellowResult = 0;
            
            // Add Event Listener
 
            boxRedElement.textContent = redCount;
            boxGreenElement.textContent = greenCount;
            boxYellowElement.textContent = yellowResult;
        
            function countRedBoxClicks() {
                
                redCount += 1;
                boxRedElement.textContent = redCount;
                printYellowResult();
            };
    
            function countGreenBoxClicks() {
                
                greenCount += 1;
                boxGreenElement.textContent = greenCount;
                printYellowResult();
             
            };

            function printYellowResult() {
                
                yellowResult = redCount + greenCount;
                boxYellowElement.textContent = yellowResult;

                if(yellowResult < 10) {

                    boxYellowElement.style.borderColor = 'white';
                    boxYellowElement.style.color = 'black';

                } else if(yellowResult > 10 && yellowResult < 20) {

                    boxYellowElement.style.borderColor = 'red';
                    boxYellowElement.style.color = 'red';

                } else if (yellowResult > 20) {

                    boxYellowElement.style.borderColor = 'purple';
                    boxYellowElement.style.color = 'purple';

                }

            };

            
            function reset() {
                
                greenCount = 0;
                redCount = 0;
                boxGreenElement.textContent = greenCount;
                boxRedElement.textContent = redCount;

                printYellowResult();
   
            } 


            boxRedElement.addEventListener('click', countRedBoxClicks);
            boxGreenElement.addEventListener('click', countGreenBoxClicks);
            resetButton.addEventListener('click', reset);
        




        </script>
    </body>
</html>
```