---
title: Refactoring
date: 27.10.2023 12:00
categories: [Appudvikling]
tags: [nolek,projekt,appudvikling,prototype]
---
## Refactoring
Efter en længere kamp med at få kotlin til at tilskrive til min Onboard database, 
så gik jeg i gang med at omskrive alt kode, hvilket har gjort at en del ting er blevet bedre og mere brugervenligt i appen.

Det har desværre ikke gjort noget for at tilskrive til min onboard databae på den måde jeg gerne vil.

### Nyt Layout

Med denne refactoring, hvor jeg har flyttet store dele af min kode, fra XML kode og over til Jetpack Compose, 
har jeg fået lavet en app som ser mere app agtig ud. Derudover så havde jeg problemet med XML koden, 
at den var ikke responsive på skærmstørrelse, hvilket jeg havde slåset med noget tid. 

Hvis jeg skiftede device, så passede appen ikke til skærmen, da jeg havde opsat det efter en bestemt skærmstørrelse.
Det var ligemeget hvor mange wrap_content og match_parent jeg brugte så virkede det bare ikke.

Men med denne refactoring til jetpack compose, så har jeg også formået at få det til at virke, så nu ændre hele appen størrelse,
så det passer med skærmen appen bliver brugt på, hvilket er en sejr.

