# Javascript Grundforløb

1. [Introduktion](#introduction)
2. [Referencer, dokumentation](#ref)
3. [Igang med JavaScript](#igang)
    1. [Start/Slut JavaScript](#start)
    2. [Placering af scripts](#placering)
        1. [Inline Scripting](#inline)
        2. [JavaScript via fil](#ekstern)
    3. [console.log('En uundværlig partner')](#console)
    4. [Kommentarer](#comment)
4. [Skrive til Html Elementer](#print)
    1. [Dom manipulation](#manipulation)
        1. [Den originale](#original)
        2. [Den moderne](#moderne)
    2. [Udskriv Tekst og Html](#printText)
    3. [Styling, Classes og Element](#styling)
5. [Variabler](#variabler)
6. [Datatyper](#datatyper)
    1. [Primitive datatyper](#primitive)
        1. [Strings](#primitive-strings)
        2. [Numbers](#primitive-numbers)
        3. [Booleans](#primitive-booleans)
        4. [Undefined](#primitive-undefined)
    2. [Specielle datatyper](#datatyper-specielle)
        1. [Object](#datatyper-specielle-object)
        2. [Array](#datatyper-specielle-array)
7. [Funktioner](#functions)
8. [Events](#events)
9. [Struktur](#structure)
    1. [Aritmetiske Opreatorer](#arrit-opp)
    2. [Sammenlignende operatorer](#arrit-com)
    3. [Logiske operatorer](#arrit-log)
    4. [Else/If](#arrit-else)
    5. [Switch](#arrit-switch)
10. [Arrays](#arrays)
11. [Objekter](#objects)
12. [Loops, Løkker](#loops)
    1. [For Loop](#loops-for)
    2. [While Loop](#loops-while)
    3. [For-In Loop](#loops-forin)
13. [Appendix](#appendix) 
    1. [Opgaver](#appendix-assignments) 
    2. [Klik maskine](#appendix-clickMachine) 

## 1. Introduktion <a name="introduction"></a>

Dette, er kompendium er under udarbejdelse med det formål, at give relevante og brugbare eksempler på hvordan man kan anvende Javascript i forbindelse med udarbejdelsen af dynamiske hjemmesider og applikationer.

Vi vil udelukkende komme til, at beskæftige os med det mest basale inden for sproget. Mange af de eksempler i vil blive præsenteret for i starten af dette kompendium, vil i måske ikke kunne se det smarte ved her i første omgang. 
De har kun til formål at lære os det mest basale og vi vil komme til at arbejde med noget mere brugbart jo længere vi kommer frem i kompendiet. Alt information i denne vil blive fulgt op af undervisning og skal mest betragtes som reference.

Javascript giver mulighed for at oprette:

* Galleri af billeder
* Burger menu funktionalitet.
* Arbejde med Cookies
* Arbejde med tid
* Validering af input
* og meget mere...

Man kan skrive JavaScript i hvilken som helst editor/ide. Vi benytter Visual Code men du er velkommen til at benytte den enditor du ønsker.

## 2. Referencer, Dokumentation. <a name="ref"></a>

Det er klart den elektroniske udgave gør det nemmere. Jeg vil overtid tilføje direkte reference under hver afsnit. Men eller søg på de pågældende sider efter nøgleord.

[https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)     
[https://www.w3schools.com/js/](https://www.w3schools.com/js/)      
[https://www.codecademy.com/](https://www.codecademy.com/)

# 3. Igang med JavaScript <a name="igang"></a>
## 3.1 Start/Slut JavaScript <a name="start"></a>

Det første man skal gøre når man ønsker at benytte JavaScript, er at fortælle 
browseren hvor og hvad der skal fortolkes som JavaScript.

Det gør man ved at indkapsle sin kode mellem 2 script tags, som vist i nedenstående eksempel.

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>I gang med Javascript</title>
    </head>
    <body>

        <script>

            /*
            
            Alt her imellem bliver fortolket af browseren som javascript.
            
            */

        </script>
    </body>
</html>
```

I kan dog godt løbe ind i steder hvor der man starter sine script som vist herunder.
Dette er dog ikke nødvendigt længere men blot en oplysning da i vil se dette mange steder. Vil vil benytte første udgave i resten af dette kompendium.

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>I gang med Javascript</title>
    </head>
    <body>

        <script type="text/javascript">

            /*
                Alt her imellem bliver fortolket af browseren som javascript.

            */
            
        </script>
    </body>
</html>
```
## 3.2 Placering af scripts. <a name="placering"></a>

### 3.2.1 Inline Scripting.
Man kan placere sine scripts direkte i en HTML fil. Dette kan være i mellem sidens ```<head></head>``` eller ```<body></body>``` tags. Man kalder det for *inline scripting* når man har sin kode sammen med sin HTML. Der kan være forskellige årsager til hvorvidt man placerer scripts, det ene eller det andet sted. I langt de fleste tilfælde vil man vælge at placere sine script-tags i bunden af siden lige før ```</body>``` tag lukkes. Grunden til dette er, at når ens HTML side er kørt, så vil browseren læse filen fra top til bund. Fuldstændigt på samme måde som når vi læser en bog. Så her vil det være smart, at vores side, først indlæser vores tekster, billeder osv. inden den loader vores JavaScript. På den måde vil brugerne af vores hjemmeside, få en følelse af at siden loader hurtigere, da den visuelt viser elementer som det første.

Scripts som er i sidens ```<head></head>``` tag vil blive afviklet, inden resten af siden køres. Denne placering af scripts bruges ofte til at vise en pop-up meddelelse til brugeren, inden resten af sidenvises. Dette kunne f.eks. være at vise en vigtig besked til brugerne af hjemmesiden.


```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>I gang med Javascript</title>
        <script>
            /*
                Man kan placere sit script tag i vores <head> tag.
            */
        </script>
    </head>
    <body>
        <script>
            /*
            
                Og / Eller kan man placere sit script tag i vores <body> tag.
            
            */
        </script>
    </body>
</html>
```

### 3.2.2 JavaScript via fil - Ekstern script. <a name="extern"></a>
Hvis man kun ønsker at benytte sig af få simple scripts, så kan de sagtens indsættes i én fil evt. sammen med ```HTML``` og ```CSS```. Hvis man derimod har mange eller mere komplicerede scripts, vil det være en fordel at gemme dem i en separat JavaScript fil. Det har den fordel, at adskille koder, tags og sprog fra hinanden. Det resultere i en langt bedre struktur og overblik over sine projekter. Dette kaldes for et eksternt script.

```HTML 
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>I gang med Javascript</title>
    </head>
    <body>

        <script src="../../../src/ekstern_script_fil.js"></script>

    </body>
</html>
```

## 3.3 console.log('En undværlig partner')

```
console.log('skriv en besked til consollen')
```      
Bruges til at teste, udvikle og fejlfinde JavaScript kode. Console.log er kun for/til udviklere som os.

Vi vil komme til at benytte denne funktionalitet meget, og det er en fordel i læringsfasen at man benytter den til at opnå en større forståelse for hvad der sker i koden.

Du kan åbne consollen og læse beskeden ved trykke F12 i det fleste browsere. Men kært barn har mange genveje, så det tager vi i undervisningen.

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <title>I gang med Javascript</title>
</head>
<body>

    <script>
    
        let name = 'Peter'
        console.log('Skriv en besked til Consollen og udskriv variablens værdi', name);

    </script>

</body>
</html>
```

## 3.4 Kommentarer.

Det er altid en god idé at skrive kommentarer is sin kode.
Vi gør det både for vores egen og for vores medudvikleres skyld.

Man kan hurtigere gennemskue koden når man har forklaringe tilknyttet. Du kan lave én-linies kommentar og eller en kommentar-blok.

Her er begge måder illustreret.

```HTML
<!DOCTYPE html>
<html lang="da">
<head>
    <title>Kommentarer</title>
</head>
<body>

    <script>

        // Her kommentere vi på en enkelt linie.
        console.log('Kommentar på en linie')
    
        /*
            Her kommentere vi på flere linier.
            Således kan vi lave en fyldig beskrivelse af
            vore funktioner og metoder.
        */
        console.log('Kommentar på flere linier')
    </script>
</body>
</html>
```

# 4. Skrive til Html Elementer <a name="print"></a>

Når det handler om at skrive til Html Elementer så er dette en stor del af vores arbejde. Ihvertfald er det en fordel at allerede her i starten tager fat på dette. Vi vil først beskrive hvordan vi kan få fat i vores HTML elementer og derefter hvordan vi skriver noget indhold i vores HTML dokumenter. Det er noget vi vil benytte meget og vi benytter det i, stort set, alle eksempler i dette dokument. Men det vil blive beskrevet nedenfor.

Refernece til Document Api
[https://developer.mozilla.org/en-US/docs/Web/API/Document](https://developer.mozilla.org/en-US/docs/Web/API/Document)

## 4.1 Dom manipulation <a name="manipulation"></a>

Når vi ønsker at udskrive JavaScript (tekst, billeder, layout osv) til vores browser, har vi forskellige muligheder.

Men lige inden vi begynder på det. Så skal vi se på en JavaScript funktionalitet, som giver os mulighed for at få fat i *HTML elementer* i vores *HTML dokumenter*.

Herunder ser vi et DIV element i vores HTML dokument. Elementet er et ```<div></div>``` element og elementet har et id *attribut* og id atrtibutten er lig med "output". 

Html:
```html
<div id="output"></div>
```
I vores javascript kan vi ved hjælp af document api´et og dermed **querySelector**, få fat i vores ovenstående HTML element og skriver 'Ny tekst i output'. 

Vi opretter en variable som indeholder vores element og vi kan på elementet benytte textContent til at sætte en ny tekst. 

Javascript:
```javascript
let output = document.querySelector('#output');
output.textContent = 'Ny tekst i output';
```

Forventet resultat i HTML:
```html
<div id="output">Ny tekst i output</div>
```

Vi vil gennemgå dette grundigt i undervisningen. Ovenståene funktionalitet vil blive brugt i de eksempler der er i dette dokumenet og derfor er det en fordel at vi lære det grundlæggende i starten. Det er sjovere når man kan skrive sin resultater ud.

Der er mange måder man kan få fat i de forskellige elementer på og man kan i første omgang dele dem op i to.
Den originale og den moderne. Begge er "lige gode" og det er en god idé at lære dem.

Herunder er to templates som viser det basale. Vi vil arbejde med dem i undervisningen.

### 4.1.1 Den originale <a name="original"></a>

* [getElementById()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById)
* [getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByClassNamed)
* [getElementsByName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByName)
* [getElementsByTagName()](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementsByTagName) 

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Dom Manipulation</title>
    </head>
    <body>

        <h2>Overskrift</h2>
        
        <p id="elementId"></p>
        <p class="text01"></p>
        <p name="text02"></p>
        
        <p class="text"></p>
        <p class="text"></p>
        <p class="text"></p>
        <p class="text"></p>
        <p class="text"></p>

        <script>
        
            let newHeadline = document.getElementsByTagName('h2')[0];
            newHeadline.innerHTML = 'Ny overskrift';
        
            let newTextById = document.getElementById('elementId');
            newTextById.innerText = 'Ny tekst';

            let newTextByClass = document.getElementsByClassName('text01')[0];
            newTextByClass.innerText = 'Ny tekst';

            let newTextByName = document.getElementsByName('text02')[0];
            newTextByName.innerText = 'Ny tekst'

            let newTextByClassNameArray = document.getElementsByClassName('text');

        
            for(let i = 0; i < newTextByClassNameArray.length; i++) {

                newTextByClassNameArray[i].innerHTML = 'Tekst ' + i + 
                + ' indsat vi getElementsByClassName og et for loop';

            }
        
    
        </script>

    </body>
</html>

```

### 4.1.2 Den Moderne. <a name="moderne"></a>

* [querySelector()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
* [querySelectorAll()](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Dom Manipulation</title>
    </head>
    <body>
        <h2>Overskrift</h2>

        <p id="elementId"></p>
        <p class="text01"></p>
        <p name="text02"></p>
        <p test="text03"></p>
        
        <p class="text"></p>
        <p class="text"></p>
        <p class="text"></p>
        <p class="text"></p>
        <p class="text"></p>

        <script>
        
            let newTextByQuerySelectorId = document.querySelector('#elementId');
            newTextByQuerySelectorId.innerText = 'Ny tekst'

            let newTextByQuerySelectorClass = document.querySelector('.text01');
            newTextByQuerySelectorClass.innerText = 'Ny tekst'

            let newTextByQuerySelectorName = document.querySelector('[name="text02"]');
            newTextByQuerySelectorName.innerText = 'Ny tekst'

            let newTextByQueryAttribut = document.querySelector('[test="text03"]');
            newTextByQuerAttribut.innerText = 'Ny tekst'

            let newTextByQuerySelectorAllTexts = document.querySelectorAll('.text');
            newTextByQuerySelectorAllTexts.forEach((element, index) => {

                element.innerText = 'Ny tekst ' + index;

            });
    
        </script>

    </body>
</html>

```

## 4.2 Udskriv Tekst og Html <a name="printText"></a>

***De oftest benyttede metoder*** er via ```textContent```, ```innerText``` og ```innerHTML```.
For at benytte disse skal man have fat i det eller de elementer man vil skrive til.

```textContent``` benyttes hvis du vil sætte eller hente alt, uanset anvendelse, tekst til eller fra dit element.
```innerText``` benyttes hvis du vil sætte eller hente ren tekst til eller fra dit element.
```innerHTML``` benyttes hvis du vil sætte eller hente HTML formateret indhold til eller fra dit element.

Her benytter vi en indbygget "DOM Selector" ```document.querySelector``` som hjælper os med at finde de enkelte elementer i dom træet.
I dette tilfælde finder vi vores output container som er et div element med et id.

Vi opretter en variabel som vi kalder ```output``` og giver den værdien ```document.querySelector('#output')```.
Nu har vi adgang til vores output dom element og kan begynde at skrive til den. Vi skriver ved hjælp at ```textContent``` og sætter en ny tekst værdi.

Vi vil benytte disse metoder i dette dokument fremadrettet.

Afprøv dette i dit eget projekt.

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Dom Manipulation</title>
    </head>
    <body>

        <div id="output">Output Container</div>
        
        <script>
        
            let output = document.querySelector('#output');
            output.textContent = 'Ny tekst i output';
        
        </script>

    </body>
</html>
```

Forventet resultatat:
```HTML
Ny tekst i output
```

## 4.3. Styling, Classes og Element <a name="styling"></a>

Som en introduktion til vores dom ```element``` er der specielt 2 metoder som vi benytte her i starten. Og vi benytter dem når vi gerne vil tilføje css, enten iform af direkte ```styling``` eller ved at benytte en ```class```, en klasse. 


Lad os tage ovestående eksempel og tilføje ```style```, altså css til selve elementet.

Vedhjælp af ```outpu.style``` kan vi sætte de forskllige css egenskaber der er tilrådighed. De adskiller sig ved at benytte ```camelCase``` her modsat i selve css. Så css ```background-color``` er lig med javascript ```backgroundColor```. 

```HTML
<!DOCTYPE html>
<html lang="da">
<head>
    <title>Dom Manipulation</title>
</head>
<body>

    <div id="output">Output Container</div>
    
    <script>
    
        let output = document.querySelector('#output');
        output.textContent = 'Ny tekst i output';

        output.style.backgroundColor = 'red';
        output.style.color = 'white';
        output.style.padding = '20px';
        output.style.fontWeight = 'bold';
      
    </script>

</body>
</html>
```

Vi kunne også istedet for at tilføje styles direkte, tilføje ovenstående styling, som en ```class```. Det gør vi ved at benytte output elements ```classList``` som indholder de klasser der er tilføjet og giver os mulighed for at tilføje og fjerne klasser, og sågar undersøge hvorvidt den allerede har en pågældende klasse.

Herunder tilføjer vi klasse ```red-box``` som er defineret i vores stylesheet ovenfor.

Og vi ender med samme resultat som det forrige eksempel.

```HTML
<!DOCTYPE html>
<html lang="da">
<head>
    <title>Dom Manipulation</title>

    <style>
        .red-box {
            background-color: red;
            color: white;
            padding: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div id="output">Output Container</div>
    
    <script>
    
        let output = document.querySelector('#output');
        output.textContent = 'Ny tekst i output';
        output.classList.add('red-box');
      
    </script>

</body>
</html>
```

# 5. Variabler <a name="variabler"></a>

Variabler bruges til at gemme informationer i. De bliver typisk billedliggjort som en kasse, hvori man kan putte forskellige ting ned i. Deres eneste formål er at mærke og gemme data i hukommelsen. Disse dara kan derefter bruges til forskellige formål. Her er listet nogle forskellige forslag til hvad man kan gemme i variabler.

* Information fra input felter.
* Produkter fra en webshop,
* Priser på en vare.
* Billeder og billede information.
* Bruger oplysninger
* Skærmstørrelser.
* Alder
* Osv osv...

Når man opretter en variabel så kaldes det at erklære / deklarere en variabel. Dvs. Man opretter en variable og tildeler den en værdi.
variabler kan være globale og lokale. De Globale variabler er de variabler der tilgængelig for alt kode. De lokale variabler er kun tilgængelige for lokale funktioner.

Der findes 3 forskellige måder at deklarere en variable. ```var```, ```let``` og ```const```.

```var``` og ```let``` udfylder stort set samme rolle men der er nuancer som vi ikke vil bruge tid på nu. Men vi vil benytte ```let``` i det kompendium da det udrydder nogle af de udfordringer der har været med at benytte og forstå ```var``` i forskellige situationer. ```const``` benyttes i de situationer hvor du ikke ønsker at man kan overskrive din variable. dvs tildele variablen en ny værdi.

Vi benytter *textContent* til at udskrive værdien af ```name``` variablen.

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Variabler</title>
</head>
<body>

    <div id="output"></div>
    
    <script>

        let name = 'Peter';
        let sex = 'male'
        let age = 25;
        let isMarried = false;

        let output = document.querySelector('#output');
        output.textContent = 'name:' + name;
   
    </script>
</body>
</html>
```

# 6. Datatyper <a name="datatyper"></a>

Én ting som er vigtig at forstå når vi benytter JavaScript (eller andre programmerings sprog), er at vi arbejder med forskellige datatyper. Hvis vi f.eks. ønsker at lægge 2 tal sammen så skal vi benytte os af typen ```number```. hvis vi vil udskrive tekst til siden, så er det datatypen ```string``` vi skal benytte. Herunder er en kort forklaring på de 8 datatyper vi kommer til at arbejde med løbende.

6 Primitive Datatyper og 2 Specielle Data typer.

## 6.1 Primitive datatyper <a name="datatyper-primitive"></a>

### 6.1.1 Strings. <a name="datatyper-primitive-strings"></a>
```javascript
let todo = 'Lære at udvikle kode.';
```
String er en primitiv data type. De består af karaterere (Bogstaver, Mellemrum, Tal, og Symboler) omkranset af enkelt ' eller dobbel anførselstegn "

### 6.1.2 Numbers <a name="datatyper-primitive-numbers"></a>
```javascript
let amount = 6;
let price = 4.50;
```
Number er en primitiv data type. Det kan være et heltal (integer) eller decimal tal (float)
Alle tal kan være negative eller positive.

### 6.1.3 Booleans <a name="datatyper-primitive-booleans"></a>
```javascript
let lateToSchool = true;
```
Boolean er primitive data type. De kan være enten ```true``` eller ```false```.
Booleans benyttes ofte til at afgøre hvad der skal ske i koden, er brugeren logget ind? Sandt eller falsk?.

### 6.1.4 Undefined <a name="datatyper-primitive-undefined"></a>
```javascript
let lateToSchool;
```
Undefined er primitive data type. Den fortæller os at der findes en variable men værdien er ikke tildelt.

## 6.2 Specielle datatyper <a name="datatyper-specielle"></a>

### 6.2.1 Object <a name="datatyper-specielle-object"></a>
```javascript
let person = {
    name: 'Margrethe',
    surname: 'Alexandrine Þórhildur Ingrid',
    birthYear: 1940,
    actualYear: new Date().getFullYear(),
    age: () => {
        this.actualYear - this.birthYear
    }
}
```

Object er en kompleks datatype, der giver mulighed for at gemme forskellige typer data. Det kan være ```string```, ```number```, ```boolean``` eller komplekse datatyper som ```arrays```, ```functions``` og andre objekter.

### 6.2.2 Array <a name="datatyper-specielle-array"></a>
```javascript
let names = ['Peter', 'Hanne', 'Max', 'Bart']
```

Et array er en bestemt type object der bruges til at gemme flere værdier i én variabel. Man kalder også et arry for et list-object, og det bliver oftest benyttet, hvor man f.eks. ænsker en  listevisning. Alle værdierne heri (også kaldet elementerne) har en numerisk position, kendt som dens indeks, og den kan indeholde data fra alle datatypenumre, ```string```, ```number```, ```boolean```, ```functions``` og endda andre ```arrays```. Et array indeks starter fra 0.

# 7. Funktioner <a name="functions"></a>

## 7.1 Hvad er en funktion. <a name="functions-what"></a>

En funktion er en smart måde at "genbruge" kode på. Hvis man eksempelvis har en bestemt kode, som man benytter ofte. Så kan man i stedet for at skrive hele koden hver gang man skal bruge den, så kan man i stedet for lave en funktion til at udføre opgaven.

Så en af grundende til at benytte funktioner er man åndgår repititioner, da en enkelt funktion kan afvikles igen og igen.

Man har mulighed for at give forskellige parameter til sin funktion, dem skriver man imellem paranteserne efter funktions-navnet. 

```JavaScript 
function funktionsNavn(parameter1, parameter2){}
```
Parametre fungerer ligesom variabler, og de kan indeholde forskellige værdier som i kan se i eksemplet herunder.

```HTML
<!DOCTYPE html>
    <html lang="da">
    <head>
        <title>Funktioner</title>
    </head>
    <body>
        
        <div id="output"></div>

        <script>

            let output = document.querySelector('#output');
        
            function contacts(name, surname, age) {

                output.innerHTML += '<p>' + name + ' ' + surname + ' er ' + age + ' år gammel</p>'
            
            }
        
            contacts('Hanne', 'Christensen', '22');
            contacts('Mikkel', 'Hansen', '32');
            contacts('Peter', 'Jensen', '18');
            
        </script>
    </body>
</html>
```

I ovenståenede eksempel har vi oprettet en ```constacts``` function som tage imod tre paratmeterer. Navne, Efternavn og alder.

Selve funtionen udskriver et ```<p></p>``` tag med vores parametere og tekst sat sammen. Fordi det er HTML vi udskriver benytter vi ```innerHTML```.

Vi benytter ovenikøbet ```+=``` så vi sikre os at hvergang vi skriver til vores ouput overskriver vi ikke det der står i forvejen vi lægger til.

Så når vi derefter kalder funktionen 3 gange:
```javascript
    contacts('Hanne', 'Christensen', '22');
    contacts('Mikkel', 'Hansen', '32');
    contacts('Peter', 'Jensen', '18');
```

Så bliver resultatet som HTML:
```
<p>Hanne Christensen er 22 år gammel</p>
<p>Mikkel Hansen er 32 år gammel</p>
<p>Peter Jensen er 18 år gammel</p>
```

Og resultatet i browseren.
```
Hanne Christensen er 22 år gammel
Mikkel Hansen er 32 år gammel
Peter Jensen er 18 år gammel
```

# 8. Events <a name="events"></a>

Events er en stor del af dynamisk javascript og giver os mulighed for at lytte på alle de handlinger vores bruger foretager sig på hjemmesiden eller i applikationen.

Det kan være 
* klik på en knap
* vælge et element i en select boks
* Åbne et vindue
* Godkende en formular
* Forstørre eller formindske browser vinduet
* Scroller med sin mus 
* osv osv. 

Kort sagt alle de handlinger en bruger fortager sig, kan vi stort set "lytte med" på, og reagere og kalde en funktion hvis vi vil.

Der findes mange forskellige events og vi vil arbejde med flere forskellige undervejs. Men vi tager udgangspunkt i et ```click``` event. Dvs. vi vil reagere når en bruger klikker på et element.


Den helt simple model er at tilføje en ```onclick=""``` attribut på det element man ønsker at have en klik funktionalitet.

I nedenstående eksempel udskriver vi i ```consollen``` når man klikker på ```<div></div>``` elementet.

```HTML
 
    <div onclick="console.log('Du har klikket på mig')">Klik På Mig</div>

```

På sammen måde vil vi også kunne kalde en funktion og få nøjagtig samme resultat i ```consollen```.

```HTML
 
    <div onclick="clickMe()">Klik På Mig</div>

    <script>

        function clickMe() {
            console.log('Du har klikket på mig');
        };

        
    </script>

```

Men man kan også med fordel samle hele script funktionalitet og flytte onclick funktionaliteten væk fra HTML koden.

Vi gør det ved hjælp af ```addEventListener``` som tager imod to parameter.

1. Event Navnet
2. Funktionen vi vil kalde.

I dette tilfælde vil vi kalde ```click``` eventet og køre ```clickMe()``` funktionen. Og vi har nu samlet vores funktionalitet et sted og hvores markup/html et andet. Vi har separeret koden. 

```HTML
 
    <div class="box">Klik På Mig</div>

    <script>

        let boxElement = document.querySelector('.box');
        boxElement.addEventListener('click', clickMe);

        function clickMe() {
            console.log('Du har klikket på mig');
        };

        
    </script>

```

# 9. Struktur <a name="structure"></a>

Nu skal vi se nærmere på hvordan vi bygger en fornuftig struktur i vores kode, samt hvilke kontrol-strukturer vi kan anvende. Strukturen skal være med eil at gøre det nemmere at overskue vores kode. Først skal vi dog lige stifte bekendskab med forskellige operatorer som ofte bliver benyttet i denne sammenhæng.

De første afsnit 8.1, 8.2 og 8.3 lister forskellige opratorer. Derefter vil i se dem blive brugt i de kommenede eksempler.

## 9.1 Aritmetiske operatorer

Vi benytter disse operatorer når vi skal regne.

```javascript
+ Plus
5 + 5

- Minus
10 - 5

* gange
5 * 10

/ division
10 / 5

Modulo, afgiver en rest iforhold til division. 10 % 5 = 0, 10 % 6 = 4, 
10 % 5
```

## 9.2 Sammenlignende operatorer.

Vi benytter disse operatorer når vi skal sammenligne om noget er større, mindre eller lig med hinanden.

```javascript
A større end B
A > B

A større end eller lig med B
A >= B

A mindre end B
A < B

A mindre end eller lig med B
A <= B

A er strict/"strengt" lig med B
A === B

A er loose/"løst" lig med "A"
A == "A"

A er forskellig fra B
A !== B
```

## 9.3 Logiske operatorer.

Vi benytter disse operatorer når vi skal sammenligne tal, tekst, funktioner, objecter osv.

```javascript
&& = AND = OG
a && b = a OG b.

|| = OR
a || b = a ELLER b.

! = NOT = IKKE
!a = IKKE a
```

## 9.4 If/Else

Et naturligt sted at bruge ovenståene operatore er i forbindelse med  if/else.

En "IF"-struktur er en måde at kontrollere om forskellige betingelser er ```true``` eller ```false```.
Skal man oversætte det til dansk kam man sige at ***HVIS*** ( if ) dette er sandt, så udfør en handling ***ELLERS*** ( else ) så udføre vi en anden handling. Prøv eventuelt at ændre ***a*** til at være større end ***b*** og se hvad der bliver udskrevet i ```consollen```.

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Struktur</title>
    </head>
    <body>

        <script>

            let a = 1;
            let b = 2;

            if(a < b) {

                console.log('Dette udsagn er sandt: ' + a + '<' + b);

            } else {
                
                console.log('Dette udsagn er falsk: ' + a + '<' + b);

            }
            
        </script>

    </body>
</html>
```

udover ```if``` og ```else``` kan man også benytte udtrykket ```else if```. der på dansk kan oversættes til ***ELLER HVIS*** som vil kræve at man afvikler endnu en handling.


## 9.5 Switch

Hvis man har rigtig mange kriterier i en if/else struktur, kan det meget let bliver uoverskueligt at læse. Man kan derfor benytte sig af en ```switch``` i stedet for. Den har fuldstændig samme fundtionalitet som ```if/else```, men er langt mere læsevenlig. I eksemplet herunder, har vi en terning som skal udskrive en bestemt værdi, afhængig af hvad vi har angivet.

```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Struktur</title>
    </head>
    <body>

        <div id="output"></div>

        <script>

            let output = document.querySelector('#output');

            let cube = 6;

            switch (cube) {
                case 1:
                    output.textContent = 'Du slog 1';
                    break;
                case 2:
                    output.textContent = 'Du slog 2';
                    break;
                case 3:
                    output.textContent = 'Du slog 3';
                    break;
                case 4:
                    output.textContent = 'Du slog 4';
                    break;
                case 5:
                    output.textContent = 'Du slog 5';
                    break;
                case 6:
                    output.textContent = 'Du slog 6';
                    break;
                default:
                    output.textContent = 'Der er sket en fejl';
                    break;
            }
            
        </script>
    </body>
</html>

```

# 10. Arrays <a name="arrays"></a>

Et array har samme formål som en variable, nemlig at opbevare data. Den væsenttligste forskel er at en variable kun kan indeholde én værdi. Et array har derimod plads til mange værdier og hvert element kan være af forskellig datatype. Dvs. ét array både kan indeholde ```string```, ```number```, ```boolean```, ```functions``` og endda andre ```arrays``` osv.

Alle elementer i et array, består altid af en nøgleværdi (key) og en indholdsværdi (value). Også kaldt et Key-Value Pair.
Hvis vi f.eks. opretter et array med 4 indholdsværdier, så vil det første element få tildelt nøgleværdien [0] da et array ALTID starter fra 0. De resterende ekementer vil så få nøgleværdierne [1], [2], [3]. Disse nøgleværdier skal vi benytte, når vi ønsker at tilgå et bestemt element. Et array bliver også kaldt et list-objekt, da man typisk benytter det, til at opbevare / udskrive en liste af elementer. Det kunne f.eks. være navne, bilmærker, produkter osv.

Herunder opretter vi er array med navnet ```names```, og tildeler det 4 indholdsværdier.
```HTML 
<!DOCTYPE html>
<html lang="da">
<head>
    <title>Arrays</title>
</head>
<body>

   <div id="output"></div>

        <script>

        let output = document.querySelector('#output');
        
        let names = [
            'Peter', 
            'Hans', 
            'Marcus', 
            'Hanne'
        ];

        // Udskriver alle elementer i vores Array
        output.innerHTML += '<p>Names: ' + names + '</p>';
    
        // Udskriver det første element i vores array.
        output.innerHTML += '<p>The first name in the array is: </p>' + names[0]);

    </script>

</body>
</html>
```

# 11. Objekter <a name="objects"></a>

Nu til et emne som *kan* fovirre ritgit mange, nemlig objecter. Måske har i allerede hørt om OOP
(objekt-orienteret programmering), og ellers høre i om det nu. Det betyder blot at man tænker object-orienteret. Altså man forsøger at opdele sin kode i objekter de steder hvor det giver mening.

Ofte når man eksemplificere objekter tager man udgangs punkt i en bil, men objekter er som regle noget som kendetegnes ved fælles egenskaber.

Hvis vi ser på en bil som objekt. Så har den som udgangspunkt mange ting tilfælles med alle biler. F.eks har bilen et ```bilmærke```, ```modelnavn```, ```årgang``` og```farve```. Det samme gælder produkter i en web-shop, der handler det om størrelser, farver, priser osv osv. Når et produkt har mange fælles egenskber et det oplagt at vi taler om et objekt, et *produkt objekt*.

Fælles for disse egenskber er at de er **nøgleværdier** (*key values*) i vores objekter.

Herunder har vi taget udgangspunkt i vores bil. Vi har oprettet et ```let car = {}``` objekt. *Tuborgklamme*, *Akkolade*, *Mustaches*, *curly brackets* ```{}```, er de tegn vi bruger til at oprette et object. Så ```let car = {}``` gør ```car``` til et objekt.

```javascript
let car = {
    brand: 'BMW',
    model: 'X8',
    year: 2017,
    color: 'red'
}
```

Vi har oprettet fire nøgleværdier, ```brand```, ```model```, ```year``` og ```color```.

```HTML 
<!DOCTYPE html>
<html lang="da">
<head>
    <title>Objekter</title>
</head>
<body>

   <div id="output"></div>

    <script>

        let output = document.querySelector('#output');

        let car = {
            brand: 'BMW',
            model: 'X8',
            year: 2017,
            color: 'red'
        }

        // Udskriver alle elementer i vores Array
        
        output.innerHTML += '<div><b>' + car.brand + '</b>'
            + '<br/>' + car.model + ' ( ' + car.year + ' ) <br/>color : ' + car.color;
      
    </script>

</body>
</html>

```

Resultat som html:
```HTML
<div><b>BMW</b><br>X8 ( 2017 ) <br>color : red</div>
```

Resultat i browseren:
```
BMW     
X8 ( 2017 )     
color : red
```

Objekter kan også være mere kompliceret da alle værdier i et object kan antage alle datatyper. Og dermed kan et objekt indeholde mange andre objekter, arrays, funktioner osv. Altså både simple og komplekse data typer.

Herunder er et eksempel på et lidt mere komplekst objekt. Dette objekt indeholder en ```method``` altså en metode. Denne metode er en funktion der benytte objektets egen nøgleværdier ```birthYear``` og ```actualYear``` til at skabe resultatet for en tredie nøgleværdi som i dette tilfælde er vores metode ```age```.  

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Objekter</title>
    </head>
    <body>

        <div id="output"></div>

        <script>

            let output = document.querySelector('#output');

            let person = {
                name: 'Margrethe',
                surname: 'Alexandrine Þórhildur Ingrid',
                birthYear: 1940,
                actualYear: new Date().getFullYear(),
                age() {
                    return this.actualYear - this.birthYear
                }
            }

            output.innerHTML ='<div>' + person.name + ' ' + person.surname 
            + ' (' + + person.age() + ')</div>';
        
        </script>

    </body>
</html>
```

Resultat:
```
Margrethe Alexandrine Þórhildur Ingrid (81)

```


# 12. Loops, Løkker - Igen og Igen og...<a name="loops"></a>

Bruges til at køre den samme kode igen og igen, og hver gang med en anden værdi. I JavaScript findes der 6 forskellige *loops* (løkker) som bliver brugt i forskellige situationer og med forskellige datatyper.

Her vil vi demonstrere et par grundliggende metoder der anvendes til at loop´e.

## 12.1 For loop<a name="loops-for"></a>

Et ```for``` loop. løber igennem kode et antal gange. 

En ```for``` metode bruger ***3 kriterier *** adskildt af et ```;``` tegn. 
1. En variable (```let = i```).
2. En betingelse (```i < 10```).
3. Hvad gør vi hver gang vi har været igennem én gang (```i++```).

```javascript
for(let i = 0; i < 10; i++) {

    console.log(i)          

}
```

Herunder opretter vi en variable ```i``` (*kunne i princippet navngives hvad som helst men ```i``` er oftes brugt og er underforstået = index*) som  ***1.kriterie***. I ***2. kriterie*** har vi en betingelse, så længe ```i < 10``` (*i er mindre end 10*) så skal vi udføre ***kriterie 3.*** ```i++``` som tæller ```i``` op med 1 (*```i = i + 1```*) for hver eneste loop.

Dermed bliver loopet udført 0, 1, 2, 3, 4... antal gange osv.

```HTML
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Løkker</title>
    </head>
    <body>

        <div id="output"></div>

        <script>

            let output = document.querySelector('#output');

            for(let i = 0; i < 10; i++) {

                output.innerHTML += 'i = ' + i + '<br>';
                
            }
        
        </script>

    </body>
</html>

```

Resultat:
```
i = 0
i = 1
i = 2
i = 3
i = 4

i = 5
i = 6
i = 7
i = 8
i = 9
```

Et for-loop bliver ofte også brugt til at gennemløbe et array.
Her har vi udskiftet ***2. kriterie*** med længden af vores resultat. Således bliver vores betingelse 
```i < 3``` da antallet af elementer i vores array er 3.

I outputtet skriver vi ```fruit[i]``` og dermed får vi udskrevet hvert element i vores array.
```fruit[0]```, ```fruit[1]```, ```fruit[2]```.


```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>Løkker</title>
    </head>
    <body>

        <div id="output"></div>

        <script>

            let fruit = ['apples', 'oranges', 'bananas']
            let output = document.querySelector('#output');
   
            for(let i = 0; i < fruit.length; i++) {

                output.innerHTML += fruit[i] + '<br>';
                
            }
     
        </script>

    </body>
</html>
```

Resultat:
```
apples
oranges
bananas
```

## 12.2 While Loop<a name="loops-while"></a>

While loop benytter et **kriterie**.

Selve *betingelsen* for hvor længe (```while/så længe```) den skal løbe/køre - fortsætte.
Og til forskel fra ```for``` loopet så fortæller vi inde i selve ```while``` kroppen, hvad der skal ske hver eneste gang *betingelsen* er opfyldt. I dette tilfælde vil løber vi igennem et array af tal ```while/så længe``` tallene i arrayet er mindre end vores limit. Vores limit har vi sat til 6.


```HTML
<!DOCTYPE html>
<html lang="da">
    <head>
        <title>Løkker</title>
    </head>
    <body>

        <div id="output"></div>

        <script>

            let output = document.querySelector('#output');

            let i = 0;
            let limit = 6;
            let numbers = [1, 2, 3, 4, 5, 6, 9];

            while(numbers[i] < limit) {
                 output.innerHTML += numbers[i] + '<br>';
                i++;
            }
        
        </script>

    </body>
</html>

```
Resultat:
```
1
2
3
4
5
```

## 12.3 For-In Loop<a name="loops-forin"></a>

Et for-in loop adskille sig ved at den loope igennem ```properties``` på et ```object```.
Herunder løber vi igennem vores funktions eksempel og udskriver hver ***key/nøgleværdi*** i objectet og så udskriver vi selve typen af den ***værdi*** der er tildelt vores ***key/nøgleværdi*** (*f.eks. name: 'Margrethe'*).

Så herunder siger vi, (```for```) hver nøgleværdi (```key```) i (```in```) vores objekt (```person```) 
så udskriv ```key``` altså nøgleværdien, derefter ```person[key]```, altså objekt[nøgleværdi] og fordi vi benytter ```typeof``` foran vores ```person[key]``` så udskrive vi typen af ```person[key]```.

Derfor bliver resultatat af ```typeof name``` = ```string``` da "Margrethe" er en streng.

```javascript
for (key in person) {

    output.innerHTML += 'key i person: ' + key + '<br>type:' + typeof person[key] + '<br><br>';

}
```

```HTML
<!DOCTYPE html>
<html lang="da">
<head>
    <title>Løkker</title>
</head>
<body>

    <div id="output"></div>

    <script>

        let output = document.querySelector('#output');

        const person = {
            name: 'Margrethe',
            surname: 'Alexandrine Þórhildur Ingrid',
            birthYear: 1940,
            actualYear: new Date().getFullYear(),
            age() {
                return this.actualYear - this.birthYear
            }
        }

        for (key in person) {

            output.innerHTML += 'key i person: ' + key + '<br>type:' + typeof person[key] + '<br><br>';

        }

    </script>

</body>
</html>

```

Resultat:

```
key i person: name
type:string

key i person: surname
type:string

key i person: birthYear
type:number

key i person: actualYear
type:number

key i person: age
type:function
```

## 13. Appendix. <a name="appendix"></a>

### 13.1 Opgaver. <a name="appendix-assignments"></a>

*Her vil der være en række opgaver som kan tages i brug i forbindelse med tilhørende afsnit. dette er ikke færdiggjort endnu. Og vi vil oftest bruge de tekplates der er i selve komendiet og arbejde udfra dem.*

[Afsnit 4. Dom Manipulation - Get Elements](./assignments/assignment-dom-manipulation.md).

### 13.2 Klik maskine (clickMachine). <a name="appendix-clickMachine"></a>

Klik maskinen, er vores applikation som vi bygger undervejs, for at bringe de forskellige aspekter af det vi har lært i spil. Det hjælper at se hvordan de forskellige funktionaliteter kan benyttes og det er først når de kombineres at man kan se hvor brugtbart det hele er.

Vi vil vende frem og tilbage til klik maskinen undevejs.

[Dokumentation og templates til klik-maskinen](./click-machine/click-machine.md)

### 13.2.1 Klik maskine - Klik mig, events. <a name="appendix-clickMachine"></a>

...undervej


