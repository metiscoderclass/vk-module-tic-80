# Lua

De TIC-80 wordt geprogrammeerd in Lua. Dat is een programmeertaal net als Python of JavaScript. Hij ziet er misschien net iets anders uit dan je gewend bent van andere programmeertalen, maar hij werkt eigenlijk precies hetzelfde. Je hebt ook variabelen, een **if** en **functies**, en een manier om commentaar te schrijven.

## Commentaar

Alles wat achter twee streepjes staat, hoort niet bij je programma. Dat heet “commentaar”, en kun je gebruiken om aan jezelf en aan anderen uit te leggen hoe je programma werkt. Bijvoorbeeld:
```lua
 --- Dit programma werkt supergoed!
```

## Functies aanroepen

Functies zijn opdrachten die je aan de computer kan geven om iets te doen, of vragen die je aan de computer kunt stellen. Zoals bijvoorbeeld: “teken deze sprite op deze op deze plek” (met de functie **spr()**) of “heeft de speler op een knop gedrukt?” (met de functie **btnp()**).

Als je een functie wilt aanroepen (dus een opdracht wilt geven), schrijf je de naam van de functie en daarachter haakjes. Meestal heeft een functie _parameters,_ die schrijf je dan tussen de haakjes. Bijvoorbeeld:
```lua
print(“Hallo”, 0, 0)
```
Op de laatste bladzijde van dit boekje vind je een lijst van alle functies die je nodig hebt voor deze workshop.

## Variabelen

Een variabele is een manier om een naam aan een waarde te koppelen. Variabelen kun je veranderen en ook weer uitlezen, bijvoorbeeld als je een functie aanroept:

```lua
regel = 5
regel = regel + 10
print(“Dit staat op regel 15”, 0, regel)
```

## if/then
Een **if** is een manier om een stukje code alleen uit te voeren in speciale gevallen. Bijvoorbeeld als de speler op een knop drukt, of als een variabele groter is dan een bepaalde drempelwaarde. Een **if** schrijf je als **if … then … end**.

Als je het volgende stukje code steeds opnieuw uitvoert heeft **teller** de waardes 1, 2, 3, 1, 2, 3, 1, 2, 3… enzovoorts:
```lua
teller = teller + 1

if teller > 3 then
 teller = 1
end
```
Gewapend met deze kennis ben je klaar om te beginnen!
