---
title: Problemer med App opbygningen
date: 27.10.2023 12:00
categories: [Appudvikling]
tags: [nolek,projekt,appudvikling,prototype]
---
## Problemer med App opbygningen

Efter jeg lavede onboard databasen, og begyndte at sammensætte tingene, så stødte jeg ind i et problem. 
Jeg lavede til at starte med appen, til at bruge switches hvor man så kunne sætte true/false, og hvis false, så skulle man skrive en begrundelse.
Problemet ligger i at hvis man gør det på den måde, så vil mange instanser i databasen være meget forskellige, hvilket kan skabe problemer,
samt forvirring angående fremsøgning og analyse af dataen. 

Jeg begyndte derfor at udtænke en anden løsning, hvor i man kunne tage et punkt ad gangen. Efter man har svaret på det,
vil det så blive vidersent til databasen. Man sender derfor ikke testobjekter men enkelte testresultater.

Jeg tror denne løsning er nemmere at implementere i databasen, og nemmere at bruge i praksis.
