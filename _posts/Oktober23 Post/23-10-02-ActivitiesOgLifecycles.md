---
title: Activities & Lifecycles
date: 02.10.2023 12:00
categories: [Appudvikling]
tags: [appudvikling]
---
### Activities

En activity viser et enkelt vindue i appen, hvor brugeren kan interagere. 
Det kan være alt fra en simpel skærm med en knap til en mere kompleks skærm med flere interaktive elementer.
Hver activity har en ui, som vises ud fra en XML-fil kaldet "layout". Denne visuelle komponent udgør ui’en, 
som brugeren ser og interagerer med.

### Lifecycles

Lifecycles er hvordan en activity opfører sig i løbet af dens levetid, fra det øjeblik den oprettes til det øjeblik, 
den bliver ødelagt. De er vigtige, da de giver mulighed for at styre, hvad der sker på forskellige tidspunkter, 
f.eks. når en bruger går væk fra appen og vender tilbage senere.

Vigtige stadier i en activitys livscyklus:

 - onCreate(): Dette kaldes, når activity'en først oprettes. Det er normalt her, 
   man initialiserer ting som ui’en og andre vigtige ressourcer.
 - onStart(): Dette kaldes, når activity'en bliver synlig for brugeren, 
   men den er endnu ikke i forgrunden og brugeren kan ikke interagere med den.
 - onResume(): Dette kaldes, når activity'en er i forgrunden og klar til brugerinteraktion.
 - onPause(): Dette kaldes, når en anden activity er ved at blive startet, 
   og den nuværende activity går i baggrunden.
 - onStop(): Dette kaldes, når activity'en ikke længere er synlig for brugeren.
 - onDestroy(): Dette kaldes, når activity'en bliver ødelagt og ryddet op. Dette kan ske, 
   når brugeren afslutter appen eller når systemet frigiver ressourcer.


Der er også to andre tilstande, onRestart() og onSaveInstanceState(), som kan være nyttige i visse situationer.

Android-systemet kan ødelægge og genoprette activities på grund af ting som skærmrotation eller lavt hukommelsesforbrug. 

<div style="text-align: left">
  <img src="/assets/images/Appudvikling/activity_lifecycle.png" alt="Something went wrong loading the image." width="200" height="400"/>
</div>
