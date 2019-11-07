# text k posterovej prezentácii projektu "SMART HOUM"


## Moje meno je Dušan a toto je Peter a toto je náš projekt Smart Houm.


## Dušky
Smart Home. Čo je to Smart Home? Je to domácnosť, ktorá je ovládateľná klasicky, alebo smartfónom, počítačom.Nami vytvorený projekt je teoreticky použiteľný na akomkoľvek zariadeni.Ovládateľný odkiaľkoľvek loálne, s úpravou odkiaľkoľvek s pripojením na wifi a nainštalovaným webovým prehliadačom. Tým pádom môžete ovládať takmer všetky funkcie domu odkiaľoľvek. Web stránka je prístupná odkiaľkoľvek, vždy po ruke, na zápästí vďaka smart hodinkám. Smart houmu umožňuje automatizáciu, čiže reakcia domácnosti na určité preddefinované situácie. To znamená, že ráno vás spolu s budíkom môže zobudiť aj slnečné svetlo cez automatické závesy a vôňa čaju alebo kávy. Po príchode do garáže sa Vám otvorí garážová brána a po odchode z domu sa automatizovaný vysávač postará o upratanie podlahy.

## Riša
 Pre náš projekt sme vytvorili intuitívnu webstránku, na ktorej je možné ovládanie svetiel domu, otváranie/zatváranie garážových dverý, nastavenie automtického, prípadne mauálneho zatvorenia/otvorenia zapnutia/vypnutia záclon a svetidiel. "SmartTV" sa stará o zobrazenie teploty spolu s kúrením a klimatizáciou. Na web stránke každé tlačidlo mení farbu podľa stavu zariadenia. Napríklad ak sú svetlá v polohe automaticky, tlačidlo automaticky svieti na červeno. Vďaka tomuto nie je potrebné  kontrolovať či sú dvere na garáže naozaj zatvorené, alebo či ste nechali zapnuté svetlá v kuchyni. Stačí na mobile jedným ťuknutím otvoriť stránku a máte prehľad o všetkom.

## Dušky
Teraz by sme Vám priblížili jadro domu. Tým je Arduino spolu z hlavným servrom. Čo je vlastne to Arduino? Je to malý počítač s množstvom programovateľných digitálnych a analógových vstupov/výstupov. Servrom môže byť akýkoľvek počítač. Na to sme použili vyradený, no funkčný miniatúrny počítač. Na ňom beží linux-ová distribúcia Arch-Linuxu. Server automaticky nabehne po zapnutí počítača, vďaka skriptom a SystemD v Arch-Linuxe. Počítač je nakonfigurovaný tak, aby sa nedal len tak jednoducho zneužiť. Je v ňom aktivovaný účinný firewall. Taktiež má server obmedzený prístup na niektoré stránky, ktoré by mohli byť zdrojom škodlivého kódu. Je to vyriešené pridaním obsiahleho zoznamu stránok, ktoré majú nastavené hostovské meno a ip na 0.0.0.0 a 127.0.0.1. Vďaka tomuto sa počítač snaží po zadaní určitej adresy, ktorá sa nachádza v zozname pripojiť sám na seba a to vyústi do chyby v poripojení.

## Riša
Na tomto serveri je spustený nodejs server s doplnkom npm, vďaka ktorému funguje webstránka, ku ktorej má užívateľ prístup cez bezdrótové, ale aj ethernetové pripojenie v každom kúte domu. Kód webstránky je napísaný v HTML, CSS a JavaScripte. Serverová časť a aj užívateľské prostredie je urobené od základu na mieru.
Návod na spustenie sa nachádza na Githube.

## Dušky
- Na model bolo potrebné vymyslieť jednoduchý, ale odolný mechanizmus na otváranie, zatváranie garážových dverí. Mechanika je urobená zo závitovcej tyče, DC motora, ložiska, tiahla a brány. Na určenie polohy brány sú použité mechanické koncové spínače. Arduino vyhodnocuje na základe spínačov polohu brány. Ak sa brána nachádza v stave zatvorená, arduino vie, že je zatvorená, potvrdí to na displeji i na web stránke. Ale keď sa nachádza v medzi polohe, kde nemá presnú polohu brány, tak vypíše, že brána pracuje.
- Ďalej tu máme osvetlenie. Použili sme naň 12V LED pás. Svetlá majú 3 nastaviteľné polohy: zapnúť/vypnúť/automatika. Automatický mód funguje pomocou senzoru okolitého jasu. Údaje zo senzora spracúva Arduino, a na základe týchto údajov pomocou relé svetlá vypne alebo zapne.
- Automatické závesy. Tie fungujú iba v automatickom režime, to znamená že ak sa úroveň okolitého osvetlenia dostane nad určitú hranicu, tak sa závesy automaticky zatvoria a keď sa uroveň jasu dostane pod určitú hranicu, tak sa otvoria.

## Riša
- Do projektu sme chceli pridať ohrev,klimatizovanie miestnosti. Pre túto možnosť funkciu je v kóde zabudoavná logika pre nastavenie zariadenie. Aktuálne vám vieme len v ruke ukázať mechaniku. Ale ak by sme ju správne pripojili, tak by fungovala. No z dôvodu poruchy jedného z TEC (peltierových) článkov by efekt nebol až tak viditeľný. Táto možnosť je z toho dôvodu momentálne len teoretická. Ohrev/klimatizovanie malo fungovať  za pomoci prúdenia teplého alebo studeného vzduchu z TEC (peltierových) článkov cez otvory v podlahe do miestnosti.

## Dušky
- Na zobrazovanie hodnôt priamo v dome sme použili 3.2" farebný LCD displej. Voláme ho "SmartTV". Ten dokáže zobraziť všetky údaje, ktoré aj webstránka, no neumožňuje ovládanie. Pre ušetrebie výpočtového výkonu je prekresľovaná iba určitú časť obrazovky a ostatné časti ostávajú statické.

## Riša
Programovanie. Obľúbená téma.
Programovanie prebiehalo v prostredí Vscode. Aj cez výhrady k politike firmy Microsoft. Uznávam, že tento program je naozaj dobrý.
Program je zjednodušený, prehľadný  a rozsiahlo komentovaný.Bolo to našim cieľom. Priebežne pracujeme na pridaní rôznych zariadení, napríklad monitor kvality vzduchu, alebo monitor jednotlivých plynov v okolitom vzduchu, monitor humidity/vlhkosti.
Ako to však celé funguje? Arduino je prepojené so serverom pomocou univerzálnej sériovej linky. Zariadenia si vymieňajú každých 100 milisekúnd telegramy. Stránka okrem zobrazovania príchodzích informácií užívateľovi taktiež vyhodnocuje logiku príkazov, aby sa zbytočne neposielali explicitne. Toto riešenie je možné použiť aj v skutočnom dome.
