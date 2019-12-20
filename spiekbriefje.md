# Spiekbriefje
Je hoeft heus niet alles uit je hoofd te leren. Op dit blad kun je opzoeken hoe alle details ook weer werken.

## Functies

De TIC-80 heeft een aantal ingebouwde functies die je kunt gebruiken om spelletjes mee te maken. Een lijst van alle functies kun je vinden op [https://github.com/nesbox/TIC-80/wiki](https://github.com/nesbox/TIC-80/wiki).

**cls(color)** -- Vul het hele scherm met het kleurnummer in **color** (kleurnummers tussen 0 en 15).

**map(x, y, w, h, sx, sy)** -- Teken de tegels van de kaart op het scherm. Begin te tekenen bij tegel **(x, y)** op de kaart, en teken **w** tegels breed en **h** tegels hoog. **sx** en **sy** mag je weglaten. Als ze gegeven zijn, zijn dat pixelcoördinaten op het scherm om te tekenen.

**spr(id, x, y, colorkey, scale, flip, rotate, w, h)** -- Teken de sprite met nummer **id** op het scherm op **(x, y)**. De kleur met nummer **colorkey** wordt doorzichtig getekend. **scale**, **flip** en **rotate** veranderen hoe de sprite getekend wordt op het scherm. **w** en **h** geven aan hoeveel vakjes naast elkaar en boven elkaar getekend moeten worden.

**btn(id)/btnp(id)** -- Of er een knop ingedrukt is. Met **btn()** kun je de knop vasthouden, met **btnp()** moet je hem eerst loslaten. Knoppen hebben nummers:

0 = omhoog, 1 = omlaag, 2 = links, 3 = rechts

4 = Z, 5 = X, 6 = A, 7 = S

**print(text, x, y, \[color\])** -- Print de tekst op de aangegeven plek.

(Een volledige lijst is te vinden op [https://github.com/nesbox/TIC-80/wiki](https://github.com/nesbox/TIC-80/wiki))
