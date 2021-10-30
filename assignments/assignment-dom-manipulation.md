#[Dom manipulation](../readme.md)

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

        <div class="box box-green"><!-- indsæt tekst --></div>
        <div class="box box-green"><!-- indsæt tekst --></div>

    </section>
    


    <script>

        /*
            
            Opret en variable og tildel den en værdi i form af vores dom element.
            Jeg har oprettet den første.

        */
        let idBoxElement = document.getElementById('idBox');
        idBoxElement.innerText  = 'idBox';

    </script>

</body>
</html>
```