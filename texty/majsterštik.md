---
title:
- Scenár k projektu AMAVET Smat HOUM (2.0)
author:
- Peter Riša, Dušan Šúňava
---


# Ciele projektu

**Jednoduchosť**
**Bezplatnosť**
**Dostupnosť**
**Škálovateľnosť**
**OpenSource**


# Povedzme si čo je to Smart Home
Smart Home je domácnosť, ktorá obsaheje zariadenia, ktoré ponúkajú majiteľovi zariadení určitú kontrolu nad funkciami domu a to buď z mobilného zariadenia, alebo počítača. Termín automatizácia pomenúva deje, ktoré sa vykonávajú bez prítomnosti človeka.



# Základná myšlienka projektu
Základnou myšlienkou projektu bolo vytvoriť model inteligentnej domácnosti. K tomu sme doplnili možnosť zobrazovania informácií v reálnom čase ako na web stránke, tak lokálne formou "Smart TV. Podarilo sa nám to.



# Ako sme to urobili?
 Na stavbu domu sme použili OSB dosky, plexisklo, farbu a skrutky. Model sme postavili relatívne rýchlo, dlhšie trvalo naprogramovať software. Aby nám fungovalo riadenie zariadení a monitorovanie senzorov sme potrebovali nejaké zariadenie s množstvom digitálnych aj analógových vstupov/výstupov. Na túto úlohu sme zvolili Arduino Mega 2560, kvôli neprekonateľnému pomeru cena/funkcie. Ako server, ktorý robí uzol medzi užívateľom a zariedeniami sme zvolili Raspberry Pi 3 B+. Potrebovali sme len malé zariadenie na ktorom pobeží NodeJS server. Vivinuli sme taktiež jednoduchú web stránku, ktorou vieme ovládať všetko v modeli.



# Funkcie domu

## Web stránka
Jednoduchá stránka vytvorená pomocou HTML, JavaScriptu.
Má jednoduché a intuitívne prostredie. Zámerne má tmavšie prostredie.
Farba tlačidiel sa mení v závislosti od stavu prisláchajúcich koncových polôh, resp. stavu zariadenia.

## Ovládanie garáže
Garáž sa ovláda pomocou webovej stránky bežiacej na servri.
Mechanika je urobená zo závitovej tyče, DC motora, ložiska, tiahla a samotnej brány.
Motor roztáža závitovú tyč, na ktorej je tiahlo, ktoré pohybuje s bránou.
Aby sme docielili zatváranie aj otváranie, bolo nutné motor prepólovať. Prepólovanie funguje pomocou PWM drivera L298N.

## Automatické svietenie/tienenie
Svetlá majú tri možnosti fungovania: zapnúť / vypnúť / automatika. Ovládanie prebieha pomocou web stránky.
Spínanie funguje pomocou relé, ovládané Arduinom.

## Zobrazovanie kodnôt
Zobrazovanie hodnôt sa odohráva na 3.2" displeji, ktorý je napojený na Arduino.
Displej zobrazuje stav svetiel, okolitý jas, otvorenie/zatvorenie garáže, nastavenú teplotu a aktuálnu teplotu okolia.
Prekreslovanie hodnôt sa deje iba pri zmene stavu.

## Ohrev/klimatizovanie miestnosti
V kóde projektu je zabudovaná logika pre nastavenie ohrevu/klimatizovania miestnosti. Táto možnosť je momentálne len teoretická, lebo z dôvodu poruchy jedného z dvoch peltierových článkov nebolo možné dosiahnuť viditeľný efekt na teplotu miestnosti.
Ohrev/klimatizovanie malo prebiehať pomocou peltierových článkov, na ktorých by sa nachádzali chladiče zo starých procesorov. ZA pomoci prúdenia vzduchu z ventilátorov by bol do miestnosti vháňaný vzduch.
Táto možnosť je vo vývoji.



# Programovanie
Programovanie prebiehalo v prostredí VScode. Neskôr sme prešli z Raspberry Pi na X86 platformu. Bolo to z dôvodu potreby vyžšieho výkonu. Začali sme vyvíjať projekt na dialku. Na zariadení Raspberry by kompilácia projektu a následné nahratie do Arduina trvala nesmierne dlho.

## Rozvetvenie projektu

### projekt je rozvetvený na 2 podprojekty

 1. časťou je "dom_displej", ktorá je určená pre platformu Arduino. Obsahuje kompletný kód v jazyku C, nevyhnutné knižnice, a schémy. Projekt je prehľadný a jednoduchý

 2. časťou je "pi_server". Táto časť má na starosti samotný server, ktorý beží na serveri. Obsahuje dokumentáciu, príručku ako ho spustiť, samotný kód stránky aj servera.

## Projekty na platforme GitHub
### Odkaz: https://github.com/peterrisa/AMAVET



# Ako to funguje?
Arduino sme prepojili zo servrom pomocou "telegramov". Tieto telegramy si zariadenia vymieňajú každých 100 milisekúnd pomocou USB linky (konzoly). Vebová stránka zobrazuje príchodzie informácie užívateľovi. Stránka taktiež vyhodnocuje logiku príkazov, aby sa napríklad zbytožne neposlal príkaz zatvoriť garáž 2 krát.

ako pomáha ekológii, zmenšenie domov, zmena filozofie ľudí



# Budúcnosť projektu
- modularita a podpora pre rôzne druhy zariadení a senzorov
- jednoduché programovanie zariadení
- pridanie obsiahlych knižníc s návodmi
- uľahčenie programovania  bežným ľuďom
