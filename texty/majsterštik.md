---
title:
- Scenár k projektu AMAVET Smat HOUM (2.0)
author:
- Peter Riša, Dušan Šúňava
---


# Ciele projektu

## Jednoduchosť
## Bezplatnosť
## Dostupnosť
## Škálovateľnosť

# Budúcnosť projektu

# Povedzme si čo je to Smart Home
Smart Home je domácnosť, ktorá obsaheje zariadenia, ktoré ponúkajú majiteľovi zariadení určitú kontrolu nad funkciami domu a to buď z mobilného zariadenia, alebo počítača. Termín automatizácia pomenúva deje, ktoré sa vykonávajú bez prítomnosti človeka.

# Základná myšlienka projektu
Základnou myšlienkou projektu bolo vytvoriť model inteligentnej domácnosti. Podarilo sa nám to. Pridali sme do modelu "Smart TV"kde sa zobrazujú v reálnom čase polohy koncových spínačov

# Ako sme to urobili?
Na stavbu domu sme použili OSB dosky, plexisklo, farbu skrutky.Model sme postavili relatívne rýchlo, dlhšie trvalo naprogramovať software. Aby nám fungovalo riadenie zariadení a monitorovani esenzorov sme potrebovali nejaké zariadenie s množstvom digitálnych aj analógových výstupov. Zvolili sme na túto úlohu Arduino Mega 2560, kvôli neprekonateľnému pomeru cena/možnosti. Ako server, ktorý robí uzol medzi užívateľom a zariedeniami sme zvolili Raspberry Pi 3 B+. Potrebovali sme len malé zariadenie na ktorom pobeží NodeJS server. Vivinuli sme taktiež jednoduchú web stránku, ktorou vieme ovládať všetko v modeli. Programovanie prebiehalo v prostredí VScode. Projekt je rozvetvený na 2 časti. 1. je časť "dom_displej", korá je určená pre platformu Arduino. Obsahuje kompletný kód v jazyku C, nevyhnutné knižnice,

# Ako to funguje?
Arduino sme prepojili zo servrom pomocou "telegramov". Tieto telegramy si zariadenia vymieňajú každých 100 milisekúnd pomocou USB linky (konzoly). Vebová stránka zobrazuje príchodzie informácie užívateľovi. Stránka taktiež vyhodnocuje logiku príkazov, aby sa napríklad zbytožne neposlal príkaz zatvoriť garáž 2 krát.

ako pomáha ekológii, zmenšenie domov, zmena filozofie ľudí

# Budúcnosť projektu
- modularita a podpora pre rôzne druhy zariadení a senzorov
- jednoduché programovanie zariadení
- pridanie obsiahlych knižníc s návodmi
- uľahčenie programovania  bežným ľuďom
