# Slovak

## Čo je smart dom

Začnime s tým čo je to smart home:

Je to domácnosť ovládaná inteligentnými zariadeniami, ktoré sa starajú o automatizáciu
Domáca automatizácia znamená, že jednotlivé technológie v dome spolu navzájom komunikujú a vytvárajú prostredie presne podľa predstáv užívateľa. Zariadenia dokážu spolu komunikovať a tým riadiť vykurovací systém, rekuperáciu, tienenie (žalúzie) a osvetlenie, dokonca zavlažovanie a zabezpečovací systém.

Mal by plniť 3 základné funkcie:
###     1. šetriť energie - príklad: elektrickú - robotické vysávač, automatické svietenie, tienenie...

###     2. komfort

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

# English

## What is a smart house

Let's start with what smart home is:

It's a home controlled by smart devices that take care of automation
Home automation means that the various technologies in the house communicate with each other and create an environment exactly according to the user's wishes. The devices can communicate with each other and thus manage the heating system, heat recovery, blinds and lighting, even irrigation and alarm system.

It should fulfill 3 basic functions:
### 1. save energy - example: electric - robotic vacuum cleaner, automatic lighting, shielding ...

### 2. comfort

### Security - Suspicious Activity Alerts

these functions are achieved through automation

The heart of home automation is the control unit with which other technologies and a variety of sensors communicate.
Interestingly, the devices not only communicate with the control unit, but also with each other for efficient operation. This system can work for months without intervention.


## AMAVET - SMART HOUM 2.0

### How does our model work?

The brain of the project is [Arduino Mega 2560] () - a small computer that handles sensor communication with the server. It is designed to redraw information on the display.
A small, economical computer is used as a server running a simple website. It has enough power to meet our needs. He takes care of the communication between the website and Arduin.

To start the project, we needed to select a platform to build our model on. Arduino seemed to be the easiest solution. We connected Arduino to a computer and used it as a server.

In our case, Arduino communicates with the servers via a USB bus, exchanging information every 100ms. The response to clicking any button on the Web page and taking action is 200ms. Such a response is sufficient for this project.

The mechanics of the garage are interesting. It works thanks to the engine and driver on the engine, which can be set the speed of opening and closing the garage. The engine knows when to stop thanks to limit switches.

The automatic light-shading function is made possible by the ambient brightness sensor, which measures the brightness level in%. If the brightness level falls below 20%, the lights turn on. When the light reaches 40%, the blinds are closed. This achieves a uniform level of brightness in the house. In our country it is just a sample.

### What our model offers

The model offers the possibility of remote control of lights, opening / closing the garage

Automatic switching on lights, shading based on ambient brightness

Displays real-time status data for the end sensors in real-time

Mechanics for heating, cooling the house

Possibility to display the current temperature

modularity of

Communication is resolved by means of "telegrams", which exchange Arduino and Server
 

### Model features

I'm working on signing up, now anyone can log in to the system, if I had more time, I could implement it

All sensors, stops, motors are connected to Arduino. As we have already mentioned Arduino communicates using "telegrams", this way of communication has proved to be very convenient and simple to implement.

Another element that I would implement is an "air quality" sensor that monitors certain gases in the air around the sensor. The sensor analyzes the gases in the air