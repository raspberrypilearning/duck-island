## Verplaats de rotsen

De rotsen bewegen over het speelvel, waardoor het lijkt alsof je eendje zwemt.

> [!TASK]
>
> ![De rots sprite.](images/obstacle-sprite.png){:width="150"}
>
> Maak een variabele met de naam `snelheid van de rots`{:class="block3variables"}.
>
> ![Een variabele aanmaken.](images/make-variable.png){:width="250"}

> [!TASK]
>
> Zet de snelheid op `3` aan het begin van het `groene vlag`{:class="block3events"} script.
>
> ```blocks3
> when green flag clicked
> +set [snelheid van de rots v] to (3)
> hide
> forever
> if <key (willekeurig v) pressed?> then
> create clone of (mijzelf v)
> end
> wait (pick random (1) to (3)) seconds
> end
> ```

> [!TASK]
>
> Selecteer **Maak een blok** en noem het `beweeg`{:class="block3myblocks"}.
>
> ![Een blok maken.](images/make-block.png){:width="250"}

> [!TASK]
>
> Onder `definieer beweeg`{:class="block3myblocks"}, voeg je een `als dan`{:class="block3control"} toe voor de \*\*pijltje links \*\* toets ingedrukt, en een `verander x met`{:class="block3motion"} met daarin`snelheid van de rots`{:class="block3variables"}.
>
> ```blocks3
> define move
> if <key (pijltje links v) pressed?> then
> change x by (snelheid van de rots)
> end
> ```

> [!TASK]
>
> Voeg nog een `als dan`{:class="block3control"} toe voor de **pijltje omlaag**, met een `verander y door`{:class="block3motion"} en daarin de`snelheid van de de rots`{:class="block3variables"} variabele.
>
> ```blocks3
> define beweeg
> if <key (pijltje links v) pressed?> then
> change x by (snelheid van de rots)
> end
> +if <key (pijltje omlaag v) pressed?> then
> change y by (snelheid van de rots)
> end
> ```

> [!TASK]
>
> Voeg een `herhaal`{:class="block3control"} lus toe onderaan het `wanneer ik als kloon begin`{:class="block3control"} script. Ga opnieuw naar het `Mijn blokken`{:class="block3myblocks"} menu en sleep je `beweeg`{:class="block3myblocks"} blok erin.
>
> ```blocks3
> when I start as a clone
> verschijn::custom
> +forever
> beweeg::custom
> end
> ```

**Test:** Houd de **pijltje naar links** of de **pijltje naar beneden** toets ingedrukt. De rotsen drijven rond en het lijkt alsof je eendje zwemt.

> [!TASK]
>
> De **pijltje naar rechts** toets moet de rots de andere kant op laten bewegen. Voeg een `als dan`{:class="block3control"} blok toe voor de rots, en een `verander x met`{:class="block3motion"}, maar deze keer gebruik je een `() - ()`{:class="block3operators"} operator om de `snelheid van de rots`{:class="block3variables"} van `0` af te halen.
>
> ```blocks3
> define beweeg
> if <key (pijltje linksv) pressed?> then
> change x by (snelheid van de rots)
> end
> if <key (pijltje omlaag v) pressed?> then
> change y by (snelheid van de rots)
> end
> +if <key (pijltje rechts v) pressed?> then
> change x by ((0) - (snelheid van de rots))
> end
> ```

> [!TASK]
>
> Doe hetzelfde voor het **pijltje omhoog**: een `verander y met`{:class="block3motion"} die de `snelheid van de rots`{:class="block3variables"} van `0` afhaalt.
>
> ```blocks3
> define beweeg
> if <key (pijltje links v) pressed?> then
> change x by (nelheid van de rots)
> end
> if <key (pijltje omlaag v) pressed?> then
> change y by (nelheid van de rots)
> end
> if <key (pijltje rechts v) pressed?> then
> change x by ((0) - (nelheid van de rots))
> end
> +if <key (pijltje omhoog v) pressed?> then
> change y by ((0) - (nelheid van de rots))
> end
> ```

**Test:** Houd een pijltjestoets ingedrukt. De stenen moeten in alle richtingen de goede kant op schuiven, zodat het lijkt alsof je eend aan het zwemmen is.
