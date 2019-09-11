# AMAVET

Projekt AMAVET bol vytvorený ako následovník školského projektu "Smart Houm". Cieľom celého projektu bolo demonštrovať použitie modulov Arduino na riadenie zariadení v domácnosti. Dielčia časť Pi_server rieši HTTP komunikáciu užívateľa a komunikuje s Arduinom cez sériovú linku. Odosiela povely a tiež monitoruje stav ovládaných periférií. Časť Dom_displej sa stará o zobrazovanie informácií na malom 3.2" displeji.

## Vývojová verzia projektu pi_server a dom_displej
### pi_server
[pi_server](https://github.com/risapav/pi_server) - server s web stránkou
### dom_displej 
[dom_displej](https://github.com/peterrisa/dom_displej)- kód bežiaci na doske Arduino, riadenie senzorov 

## Predslov
Projekt bol vytvorený v prostredí [PlatformIO IDE](https://platformio.org/). Najprv bol vyvíjaný v multifunkčnom editore [Atom](https://atom.io/). Kedže Atom v čase vývoja mal množstvo bugov, plynule vývoj prešiel do prostredia [Vscode](https://code.visualstudio.com/), aj napriek výhradám voči politike firmy Microsoft, ktorá je tvorcom prostredia Vscode. Musím uznať, že Vscode je špičkový software. Umožňuje integrovať množstvo nástrojov a užitočných doplnkov pre urýchlenie vývoja rôznych typov aplikácií.
