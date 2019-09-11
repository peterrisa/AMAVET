## Čo je smart dom

Začnime s tým čo je to smart home:

Je to domácnosť ovládaná inteligentnými zariadeniami, ktoré sa starajú o automatizáciu
Domáca automatizácia znamená, že jednotlivé technológie v dome spolu navzájom komunikujú a vytvárajú prostredie presne podľa predstáv užívateľa. Zariadenia dokážu spolu komunikovať a tým riadiť vykurovací systém, rekuperáciu, tienenie (žalúzie) a osvetlenie, dokonca zavlažovanie a zabezpečovací systém.

Mal by plniť 3 základné funkcie:
###     1. šetriť energie - príklad: elektrickú - robotické vysávač, automatické svietenie, tienenie...

###     2. komfort - 

###     3. zabezpečenie - upozornenia na podozrivú aktivitu

tieto funkcie sú docielené vďaka automatizácii

Srdcom domácej automatizácie je riadiaca jednotka, s ktorou komunikujú ostatné technológie a celý rad senzorov.
Zaujímavé je to, že zariadenia nekomunikújú iba s riadiacou jednotkou, ale aj medzi sebou, čím je dosiahnuté efektívne fungovanie. Takto nastavený systém dokáže fungovať aj mesiace bez zásahu.


## AMAVET - SMART HOUM 2.0

### ako funguje náš model?

Mozgom projektu je [Arduino Mega 2560]() - malý poočítač, ktorý sa stará o komunikáciu senzorov zo serverom. Má za úlohu prekresľovať informácie na displeji.
Ako server, na ktorom beží jednoduchá web stránka, je použitý malý úspornáý počítač. Má dostatok výkonu na naše potreby. Stará sa o komunikáciu medzi web stránkou a Arduinom.  

Na začiatok projektu sme potrebovali vybrať nejakú platformu, na ktorej by sme začali budovať náš model. Ako najjednoduchšie riešenie sa zdalo Arduino. Arduino sme pripojili k počítaču a zároveň sme ho pužili ako server.

V našom prípade Arduino komunikuje zo serverom pomocou USB zbernice pri čom si každých 100ms vymieňajú informácie. Odozva od kliknutia na ľubovoľné tlačidlo na Web stránke a vykonaniu akcie je 200ms. Takáto odozva je na tento projekt dostatočná.

Zaujímavo je urobená mechanika garáže. Tá dunguje vďaka motoru a driveru na motor, ktorm je možné nastaviť rýchlosť otvárania, zatvárania garáže. Motor vie kedy má zastaviť vďaka koncový spínačom.

Automatika svietenia, tienienia funguje vďaka senzoru okolitého jasu, ktorý meria hladinu jasu v %. Ak sa úroveň jasu dostane pod 20%, tak sa zapnú svetlá. Ak svetlo dosiahne úroveň 40%, tak sa zavrú žalúzie. Tým je dosiahnutá rovnomerná úroveň jasu v dome. U nás to je len na ukážku.

### čo ponúka náš model

Model ponúka možnosť vzdialeného riadenia svetiel, otvárania/zatvárania garáže

Automatické zapínanie svetiel, tienenie na základe okolitého jasu

V reálnom čase zobrazuje na displeji a aj na stránke údaje o stave koncových senzorov

Mechaniku na ohrev, chladenie domu

Možnosť zobrazovať aktuálnu teplotu

Modularitu

Komunikácia je vyriešená pomocou "telegramov" ktoré si medzi sebou vymieňa Arduino a Server
 



### funkcie modelu

Pracujem na vývoji možnosti prihlásenia sa, momentálne sa vie prihlásiť do systému ktokoľvek, ak by som mal viac času, vedel by som to implementovať

Všetky senzory, dorazy, motory sú zapojené do Arduina. Ako sme už zmienili Arduino komunikuje pomocou "telegramov", tento spôsob komunikácie sa ukázal ako veľmi vhodný a jednoduchý na implementáciu.

Ďalším prvkom, ktorý by som implementoval je senzor "kvality" vzduchu, ktorý monitoruje určité plyny vo  vzduchu okolo senzoru. Senzor analyzuje plyny vo vzuchu 
