# Dom Manipulation.

[TIlbage](../readme.md).

Ved hjælp af QuerySelector og/eller getElementById sæt tekst ind i de tomme bokse.

Kopiér nedenstående template.

```HTML
<!DOCTYPE html>
<html lang="da">
<head>
    <title>Get Elements</title>
    <style>

        body {

            font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
            background-color: slategrey;
            color : #ffffff;
        }

        .section-container {

            display: flex;
            justify-content: center;
            align-items: center;    
            flex-direction: column;

        }

        .box, #idBox1, #idBox2  {
            
            display: flex;
            justify-content: center;
            align-items: center;    
            color: white;
            font-size: 22px;
            width: 100px;
            height: 100px;
            border: 2px white solid; 
            margin : 10px;
            user-select: none;
             
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

    <section class="section-container">
        
        <h1>Indsæt tekst i boksene.</h1>

        <div id="idBox" class="box box-yellow"><!-- indsæt tekst --></div>

        <p>Indsæt via QuerySelector og/eller getElementById</p>

        <div id="idBox1" class="box box-red"><!-- indsæt tekst --></div>
        <div id="idBox2" class="box box-red"><!-- indsæt tekst --></div>

        <p>Indsæt tekst via QuerySelector og/eller getElementsByClassName</p>

        <div class="box box-green"><!-- boks 1 --></div>
        <div class="box box-green"><!-- boks 2 --></div>

        <a href="events_click.html">Events Click 1</a>
        <a href="events_click_udvidet.html">Events Click Udvidet</a>

    </section>
    
    <script>

        /*
            
            Opret en variable og tildel den en værdi i form af vores dom element.
            Jeg har oprettet den første.

        */
        let idBoxElement = document.getElementById('idBox');
        idBoxElement.innerText  = 'idBox';

        let idBoxElement1 = document.getElementById('idBox1');
        idBoxElement1.innerText  = 'idBox1';

        let idBoxElement2 = document.querySelector('#idBox2');
        idBoxElement2.innerText  = 'idBox2';
    
        let greenBoxes = document.getElementsByClassName('box-green');
        greenBoxes[0].innerText = "box 1";
        greenBoxes[1].innerText = "box 2";

        // Denne funktionalitet er den samme som ovenfor.
        // let greenBoxes = document.querySelectorAll('.box-green');
        // greenBoxes[0].innerText = "box 1";
        // greenBoxes[1].innerText = "box 2";
        
    </script>

</body>
</html>
```