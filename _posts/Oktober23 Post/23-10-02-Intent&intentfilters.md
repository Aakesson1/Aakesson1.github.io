---
title: Intent & Intent filters
date: 02.10.2023 14:00
categories: [Appudvikling]
tags: [appudvikling]
---
## Intent

Et intent er et beskedobjekt, som bruges til at anmode om en bestemt handling fra Android-systemet. 
Det kan være handlinger som at starte en ny aktivitet, starte en tjeneste, udsende en broadcast mm.

For eksempel, hvis man vil åbne en ny UI i appen, kan man bruge en Intent til at anmode om, 
at Android-systemet starter en ny aktivitet. Det bruges f.eks. således:

```kotlin
val intent = Intent(this, MenuActivity::class.java) 
startActivity(intent)
```
Her bliver der lavet et nyt intent, som fortæller at man vil starte akviteten MenuActivity. 
Derefter bruges startActivity()-metoden til at udføre anmodningen.

## Intent Filters
Intent Filters er en måde at specificere, hvilke typer af hændelser eller meddelelser en komponent som f.eks.
en aktivitet er interesseret i at modtage. 
De bruges mest til at gøre appen i stand til at reagere på intents fra andre apps eller systemet.

For eksempel, hvis appen er i stand til at vise billeder, 
skal den have et intent filter, som fortæller at den er interesseret i at modtage intents, 
som anmoder om at vise billeder.

Her er et eksempel på hvordan et intent filter kan se ud i AndroidManifest.xml-filen:

```xml
<activity android:name=" .MenuActivity">
          <intent-filter> 
                         <action android:name="android.intent.action.MAIN" /> 
                         <category android:name="android.intent.category.LAUNCHER" /> 
          </intent-filter> 
</activity> 
```
Det betyder at når brugeren starter appen, vil Android-systemet sende en android.intent.action.MAIN-handling. 
Da MenuActivity har et intent filter, der matcher denne handling, 
vil systemet starte denne aktivitet som hovedaktiviteten.
