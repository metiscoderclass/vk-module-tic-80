# Beginnen met de TIC-80 computer

Als je de TIC-80 net hebt opgestart begin je in een scherm waar je begint met commando’s typen. Hier kun je je spellen laden en opslaan en starten. Als het goed is heb je bij deze workshop een bestand gekregen wat **workshop.tic** heet.

Typ eerst **folders** (en druk op ENTER) om het mapje waar je **.tic** bestanden opslaat te openen. Kopiëer **workshop.tic** daar naartoe. Je kunt het <a href="https://drive.google.com/file/d/1kRkRpX-rVb5qadnAMTpsMbAfFVi1Hmwe/view?usp=sharing">hier</a> downloaden.

![](.gitbook/assets/5.png)

Vervolgens typ je **load workshop** om het bestand te laden.
Om het spelletje te starten typ je **run**, of je drukt op **Ctrl-R** of ⌘**-R**.

Als je op **ESC** drukt ga je naar de code editor waar je kunt programmeren, en met nog een keer **ESC** ga je weer terug.

![](.gitbook/assets/6.png)

Als je je spel wilt bewaren, typ je **save**.

# 1. Laat de kikker bewegen

![](.gitbook/assets/7.png)

Als we beginnen zien we een kikker op het scherm, maar de kikker kan nog niet bewegen.

| 👉 | Zorg dat als je op PIJLTJE OMHOOG op je toetsenbord drukt, de kikker OMHOOG beweegt. |
| :--- | :--- |

Ergens in de functie **rekenen()** kijken we met een **if** of er een knop ingedrukt wordt (met de functie **btnp()**). Als dat zo is, dan moeten we iets gaan doen om de positie van de kikker te veranderen. Wat moet hier komen?
```lua
if btnp(0) then
 -- OPDRACHT 1
 -- Wat moet hier komen?
end
```
Denk na over de grootte van de stappen. 8 of 16 zijn getallen die ik goed vind werken, maar je mag natuurlijk kiezen wat je zelf wil!

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F4A1;</th>
      <th style="text-align:left">
        <p><b>Tip</b>
        </p>
        <p>Geef <b>kikker.y</b> een nieuwe waarde, door een getal op te tellen of af
          te trekken van de oude <b>kikker.y</b>. Denk goed na of de Y coordinaat
          lager of hoger moet worden!</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table><table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F9E0;</th>
      <th style="text-align:left">
        <p><b>Extra</b>
        </p>
        <p>Als je de overkant haalt zie je een tekst. Pas de tekst aan om jezelf
          eens passend te feliciteren.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table><table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F9E0;</th>
      <th style="text-align:left">
        <p><b>Extra</b>
        </p>
        <p>Kun je de kikker ook weer naar beneden laten bewegen als je op PIJLTJE
          OMLAAG duwt?</p>
        <p>(tip: kijk op het laatste blad naar de lijst van functies)</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

# 1. Laat de kikker bewegen (uitleg)

Omdat de Y as naar beneden loopt, moet de waarde van **kikker.y** _lager_ worden om de kikker _omhoog_ te laten lopen. Ik vind stapjes van 8 pixels goed werken:
```lua
if btnp(0) then
 kikker.y = kikker.y - 8
end
```
Als je ook terug uit wilt kunnen lopen, ze je dit eronder:
```lua
if btnp(1) then
 kikker.y = kikker.y + 8
end
```
**btnp(1)** omdat 1 het nummer is van de knop PIJLTJE OMLAAG, en **kikker.y + 8** omdat **+** ervoor zorgt dat de kikker naar beneden beweegt.

# 2. Achtergrond toevoegen

![](.gitbook/assets/8.png)

De omgeving van de kikker is nu een beetje saai. Laten we de kikker eens iets geven om naartoe te rennen. Bijvoorbeeld: een vijvertje om lekker in te zwemmen!

Als je in de editor op MAP EDITOR (F3) klikt, kom je in een scherm waar je de achtergrond kan tekenen. De kaart bestaat uit een heleboel tegels van 8x8 pixels.

| 👉 | Zorg dat er een achtergrond onder de kikker getekend wordt. |
| :--- | :--- |


Je kunt wat je getekend hebt in de MAP EDITOR in code op het scherm tekenen door op de juiste plek een aanroep naar de **map()** functie neer te zetten.

Waar moet die functie komen denk je? In **rekenen()** of in **tekenen()**?

Zoek de **map()** functie op op het spiekbriefje (achterin) en kijk goed welke parameters die functie nodig heeft, en in welke volgorde.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F4A1;</th>
      <th style="text-align:left">
        <p><b>Tip</b>
        </p>
        <p>Als je het hele scherm wilt vullen, deel je het aantal pixels in het scherm
          door de grootte van een tegel om het aantal tegels uit te rekenen.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table><table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F9E0;</th>
      <th style="text-align:left">
        <p><b>Extra</b>
        </p>
        <p>Teken vooral een andere/leukere achtergrond als je wilt. Door op SHIFT
          te drukken kun je andere tegels kiezen om mee te tekenen.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

# 2. Achtergrond toevoegen (uitleg)

Je roept **map()** als volgt aan om het hele scherm te vullen met de achtergrond:
```lua
map(0, 0, 30, 17)
```
0, 0 is omdat je vanaf de eerste tegel op de kaart wilt beginnen met tekenen (positie in tegelcoordinaten).

30, 17 zijn het aantal tegels in de breedte en in de hoogte. Het scherm is 240 pixels breed en 136 pixels hoog, dus 240 pixels breed gedeeld door 8 pixels per tegel = 30 tegels, en 136 pixels / 8 pixels per tegel = 17 tegels.

Het is belangrijk in welke volgorde je alle tekenopdrachten geeft, omdat de latere over de eerste heentekenen. De **map()** moet dus vóór de **spr()** waarmee de kikker getekend wordt, anders zie je de kikker niet meer!

![](.gitbook/assets/9.png)

# 3. Het eerste obstakel

Het spel is nu natuurlijk wel erg makkelijk, je kan zó naar de overkant lopen! Tijd om een obstakel toe te voegen.

Als je in de editor op SPRITE EDITOR (F2) klikt, zie je dat we ook plaatjes van auto’s hebben, maar in het spel is er nog geen auto te bekennen.

| 👉 | Zorg dat de auto op het scherm getekend wordt. |
| :--- | :--- |


Net als voor de kikker, hebben we ook al een object voor de auto (het heet, toepasselijk genoeg, **auto**!). Net als bij de kikker moet de auto wel op het scherm getekend worden. Dat doe je met de **spr()** functie. Je moet de **spr()** functie vertellen welke sprite (of sprites) hij moet tekenen, en waar. Alle sprites hebben een nummer, dat je kan vinden door er op te klikken in de SPRITE EDITOR (staat achter de \# links).

Zoek op hoe de **spr()** functie werkt (spiek maar lekker bij hoe de kikker getekend wordt), en teken de auto ook op het scherm. Let op het spritenummer en de afmetingen van de auto.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F4A1;</th>
      <th style="text-align:left">
        <p><b>Tip</b>
        </p>
        <p>Om bij het aantal tegels te komen moet je (helaas!) een heleboel parameters
          opgeven die we eigenlijk helemaal niet nodig hebben. Daar moet je dan maar
          even getallen invullen die niets veranderen.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table><table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F9E0;</th>
      <th style="text-align:left">
        <p><b>Extra</b>
        </p>
        <p>Als je het spel te makkelijk vindt, zoek dan op waar de snelheid van de
          auto geregeld wordt en laat hem sneller rijden.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

# 3. Het eerste obstakel (uitleg)

De **spr** aanroep is erg lang, en een heleboel parameters doen er niet toe. Hij ziet er zo uit:
```lua
spr(33, auto.x, auto.y, 1,1,0,0,4,2)
```
Dit is wat ze allemaal betekenen:
```
id=33 -- is het spritenummer van de rode auto

x,y=auto.x, auto.y -- zijn de pixelcoordinaten van de auto

colorkey=1 -- de eerste 1 zorgt ervoor dat de kleur met nummer 1 doorzichtig getekend wordt. Kijk maar eens wat er gebeurt als je dit verandert in 6.

scale=1 -- de tweede 1 zorgt ervoor dat de tekening op normale grootte wordt getekend. Kijk maar eens wat er gebeurt als je dit verandert in 2.

flip=0 -- we willen de tekening niet spiegelen

rotate=0 -- we willen de tekening niet draaien

w,h=4,2 -- de auto is 4 tegels breed en 2 tegels hoog
```
# 4. Botsen (“collission detection”)

![](.gitbook/assets/10.png)

We hebben een kikker, we hebben een auto… maar er gebeurt niets als de auto de kikker raakt. Dat is een beetje saai zo!

| 👉 | Zorg dat je het spel verliest als je door de auto geraakt wordt. |
| :--- | :--- |


TIC-80 weet niks van wat dingen voorstellen. Het enige wat de computer weet is dat jij wat plaatjes op een bepaalde plaats op het scherm getekend hebt, maar niet dat die dingen een speler of een obstakel zijn. Wat jij als programmeur dus moet doen is bijhouden waar elk object op het scherm staat en hoe groot het is, en met een berekening kijken of ze elkaar aanraken.

De code om te kijken of de kikker met de auto gebotst is staat al in het programma:
```lua
-- Zijn we gebotst met de auto?
if bots(kikker, auto) then
 kikker_kan_bewegen = false

end
```
Maar de functie **bots()** is nog niet ingevuld:
```lua
-- Geeft terug of rechthoeken r en s elkaar aanraken

function bots(r, s)
 return false
end
```
Deze functie gaan we invullen.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F4A1;</th>
      <th style="text-align:left">
        <p><b>Tip</b>
        </p>
        <p>Dit stukje is best wel lastig! Als je het leuk vindt om dit uit te puzzelen,
          dan mag dat. Maar je mag de functie <b>bots()</b> ook behandelen als een
          balpen: iemand anders heeft hem al voor je gemaakt en jij gebruikt hem
          gewoon. Als je dat wilt doen, kun je hem gewoon overtypen van de volgende
          bladzijde.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

Er zijn verschillende manieren om collission detection te doen. Wat wij gaan doen is de kikker en auto behandelen als rechthoeken. Die rechthoeken noemen we **r** en **s**, en ze hebben allebei een (x, y) als linkerbovenhoek en een breedte (w) en hoogte (h). De vraag is, overlappen de rechthoeken elkaar?

![](.gitbook/assets/11.png)
![](.gitbook/assets/12.png)

Dit schrijven we op als een stel vergelijkingen tussen de zijdes van **r** en **s**. De functie komt er ongeveer zo uit te zien: (maar niet precies zo, want dit antwoord is fout!)
```lua
function bots(r, s)
 return r.x + r.w &gt; s.x
    and r.y + r.h &lt; s.y
    and ...
end
```
Teken op een kladblaadje een aantal rechthoeken in verschillende posities ten opzichte van elkaar (links, rechts, boven onder, wel of niet overlappend) om een gevoel te krijgen voor de gevallen waar je aan moet denken.

Tip: er zijn meerdere goede antwoorden, één ervan werkt zo:
```lua
function bots(r, s)
 return linkerkant R is links van rechterkant S
    and bovenkant R is boven onderkant S
    and rechterkant R is rechts van linkerkant S
    and onderkant R is onder bovenkant S
end
```

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F9E0;</th>
      <th style="text-align:left">
        <p><b>Extra</b>
        </p>
        <p>Zorg dat je goed kan zien dat de kikker overreden is. Dit doe je door
          een ander plaatje te gebruiken als de kikker getekend wordt. Je hebt dus
          een variabele nodig om bij te houden welk plaatje gebruikt moet worden.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

# 4. Botsen (Uitleg)
Laten we eens kijken naar de hint van wat we moeten berekenen:

    linkerkant R is links van rechterkant S

“is links van” betekent “kleiner dan” &lt;

    linkerkant R < rechterkant S

“linkerkant R” is r.x

    r.x < rechterkant S

“rechterkant S” is s.x + s.w

    r.x < s.x + s.w

Als we dat voor alle zijdes doen, komt **bots()** er zó uit te zien:
```lua
function bots(r, s)
 return r.x < s.x + s.w
 and r.y < s.y + s.h
 and r.x + r.w > s.x
 and r.y + r.h > s.y
end
```
# 5. Meer auto’s

![](.gitbook/assets/13.png)

We kunnen nu in ieder geval botsen, maar het spel is nog steeds wel een beetje makkelijk met maar één auto.

| 👉 | Voeg een tweede auto toe (liefst op de andere rijbaan, maar overal mag). Zorg natuurlijk ook dat je door die auto geraakt kan worden. |
| :--- | :--- |


De makkelijkste manier om een tweede auto toe te voegen is om alles te kopiëren wat er geschreven is voor de eerste auto, en dat dan aan te passen. Om te beginnen heb je een nieuwe variabele nodig, en daarna kopieer je de andere regels ook.
<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F9E0;</th>
      <th style="text-align:left">
        <p><b>Extra</b>
        </p>
        <p>Misschien is het nog leuker als de twee auto&#x2019;s niet even snel rijden.
          Probeer dat eens!</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table><table>
  <thead>
    <tr>
      <th style="text-align:left">&#x1F9E0;</th>
      <th style="text-align:left">
        <p><b>N&#xF3;g meer auto&#x2019;s (geavanceerd)</b>
        </p>
        <p>Twee auto&#x2019;s is leuk, maar als je steeds meer auto&#x2019;s toe
          wilt voegen wordt het wel erg veel werk om steeds meer variabelen toe te
          voegen. Als je een <b>lijst</b> van objecten bijhoudt, kun je zoveel auto&#x2019;s
          als je wilt hebben zonder dat het meer code kost.</p>
        <p>Lijsten in Lua werken zo:</p>
        <p>-- Nieuwe lege lijst voor auto&apos;s</p>
        <p>autos = {}</p>
        <p>-- Voeg auto&apos;s toe aan de lijst</p>
        <p>table.insert(autos, {x=112, y=83, w=32, h=16})</p>
        <p>table.insert(autos, {x=0, y=15, w=32, h=16})</p>
        <p>-- Doe iets met iedere auto</p>
        <p>for i, auto in pairs(autos)</p>
        <p>spr(1, auto.x, auto.y, ... )</p>
        <p>end</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>
