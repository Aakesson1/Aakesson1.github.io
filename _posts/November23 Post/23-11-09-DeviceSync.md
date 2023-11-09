---
title: DeviceSync
date: 06.11.2023 12:00
categories: [Database]
tags: [nolek,projekt,appudvikling,prototype,database]
---
### DeviceSync

Jeg fandt ud af der jeg undersøgte realm, at MongoDB Atlas har integreret device sync, hvilket jeg tænkte var super smart.

Jeg besluttede mig derfor at kigge mere på det, og finde ud af hvordan det virkede, og hvordan jeg kunne bruge det i min app. 
Jeg troede det ville være nemt, da dokumentationen fik det til at lyde,
som om man bare sætter sit application id ind og så laver den automatisk en forbindelse.
Det vidste sig ikke være så nemt i praksis.
men jeg fik eksperimenteret med mange forskellige muligheder.

Til sidst fandt jeg ud hvordan jeg kunne få skabt forbindelse, der var to problemer som gjorde at jeg ikke kunne få det
til at virke. 

#### kompatibilitet

Det første problem jeg stødte ind, var at MongoDB laver et skema, for hvordan DeviceSync skal være konfigureret. 
Jeg troede at jeg havde fået lavet det skema ens på både min backend og frontend, og jeg fik en del hovedpine, 
over hvorfor det bare ikke kunne lade sig gøre. Jeg lavede en del eksperimenter, hvor jeg sad og rodede i log filerne og debuggede,
for at se om jeg kunne se hvor fejlen lå. Efter en del tid fandt jeg en linje i min log, hvor den skrev

``` LogCat
2023-11-06 11:20:23.981 7154-7190 REALM com.example.nolekapp W [Core] Connection[3]: Session[3]: 
Error integrating bootstrap changesets: Failed to transform received changeset: Schema mismatch: 
Property 'ownerId' in class 'TestResultat' is nullable on one side and not on the other.
```
Det var heldigvis nok til at jeg kunne finde fejlen, som der også står i loggen. så havde jeg under migrationen, 
lavede om på skemaet i MongoDB Atlas til at ownerId var blevet nullable, men i min app var dettte ikke tilfædet,
da jeg brugte det id til at query de dokumenter, som det id havde lagt ind. Det er klart dette skaber forvirring, 
for synkroniseringen mellem de to databaser.

#### Authentication

Det andet problem jeg stødte på, var at jeg havde brug for noget user authentication, for at kunne tilgå databasen. 
Det problem løste jeg med at tillade min app service at blive tilgået af en anonym bruger, 
jeg kunne derefter oprette brugeren som anonym når man prøvede at tilgå database elementet. 
Senere ændrede jeg dog denne funktion til at brugeren bliver oprettet ved opstart af appen.

Jeg kunne også have lavet en login funktion med forskellige former for authentication som f.eks. email, google eller JWT tokens, 
men da det ikke var en del af problemstillingen, så smed jeg hurtigt den idé væk, da jeg vidste at det ville tage meget tid,
af min allerede pressede tidsplan, da jeg ville skulle opsætte en ny form for authentication, og lære hvordan man bruger den i kotlin,
derudover er der også hele den UI komponent som skal oprettes.
Det er dog nogen som senere kan laves, hvis jeg når at blive færdig med den grundlæggende app før tidsplanen.


