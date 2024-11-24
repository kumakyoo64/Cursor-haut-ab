# Wenn man den Rahmen öffnet muss man aufpassen, dass der Cursor nicht abhaut...

Ein kleiner Gag, den ich mal im Forum64 gepostet habe: Nach dem Start
des Programms mit SYS49152 macht sich der Cursor bei Inaktivität
selbständig, bewegt sich auf die Rahmenöffnung am linken
Bildschirmrand zu und hüpft durch diese aus dem Bild raus.

![VICE-Screenshot](screenshot.png)

Wenn man schnell genug ist, kann man ihn wieder einfangen, indem man
ihn mit den Cursortasten wieder in den normalen Bildschirm bewegt.

Man kann sogar im Rahmenbereich Text schreiben und das sogar in allen
Farben!

## Was steckt dahinter? ##

Mit Hilfe von Raster-Tricks wird der Rahmen für acht Zeilen geöffnet:
Dort ist jetzt die Hintergrundfarbe und nicht mehr die Rahmenfarbe
sichtbar. Insbesondere sind in diesem Bereich dann aber auch Sprites
sichtbar. Mit Hilfe von vier Sprites wird der Cursor im Rahmen
simuliert.

Drei Sprites werden dabei für die drei Positionen benutzt, an denen
sich der Cursor befinden kann (und auch für den eingegebenen Text).
Das vierte Sprite überdeckt die Rahmenlücke am rechten Rand, da es
nicht möglich ist, den Rahmen nur auf einer Seite zu öffnen.

## Hinweis ##

Das Programm funktioniert nur mit einem PAL-VIC.
