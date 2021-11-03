# Introduktion - Betingelser, Events og styling

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

                <div class="box box-red">Mouse Click</div>

                <div class="box box-blue">
                    <input id="blueInput" placeholder="indtast"/>
                </div>

            </div>
        </div>

        <script>

            // Cirkle Elementer
            let boxRedElement = document.querySelector('.box-red');
            let boxBlueElement = document.querySelector('.box-blue');
            let blueInput = document.querySelector('#blueInput');


            // Variabler
            let countRed = 0;

            
            // Events
            boxRedElement.addEventListener('click', activateRed);
            boxBlueElement.addEventListener('input', activateBlue);

            /*
            
                her har vi de funktioner som vi kalder fra vores events listeners ovenover.

            */

            // Når vi klikker på rød.
            function activateRed() {

                countRed++;

                if(countRed === 1) {

                    boxRedElement.style.backgroundColor = 'black';
                    boxRedElement.style.color = 'white';
                    boxRedElement.innerHTML = `${countRed} = Success`;
                    
                } else if (countRed === 3) {

 
                    boxRedElement.style.backgroundColor = 'pink';
                    boxRedElement.style.color = 'white';
                    boxRedElement.innerHTML = `${countRed} = Success`;
                    

                } else {

                    boxRedElement.style.backgroundColor = 'yellow';
                    boxRedElement.style.color = 'white';
                    boxRedElement.innerHTML = `${countRed} = Success`;
                    
                }

            }

            function activateBlue(event){

                if(event.target.value === 'kode') {

                    boxBlueElement.style.backgroundColor = 'green';

                }

            }
  
  </script>
    </body>
</html>
```