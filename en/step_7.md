## Make the rocks drift




START HERER

Instead of the duck moving, the rocks slide past it, which makes it look like your duck is swimming.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Make a `rock speed`{:class="block3variables"} variable and set it to 3 at the start of the rock's `green flag`{:class="block3events"} script.
>
> ```blocks3
> when green flag clicked
> +set [rock speed v] to (3)
> ```

> [!TASK]
>
> At the bottom of the `when I start as a clone`{:class="block3control"} script, add a `forever`{:class="block3control"} loop. Start with one direction: when the `right arrow`{:class="block3sensing"} is pressed, move the rock left by `rock speed`{:class="block3variables"}.
>
> ```blocks3
> when I start as a clone
> +forever
> if <key (right arrow v) pressed?> then
> change x by ((0) - (rock speed))
> end
> end
> ```

**Test:** Hold the right arrow. The rocks slide left — it looks like your duck is swimming to the right.

> [!TASK]
>
> Now add the other three directions to the same `forever`{:class="block3control"} loop.
>
> ```blocks3
> when I start as a clone
> forever
> if <key (right arrow v) pressed?> then
> change x by ((0) - (rock speed))
> end
> +if <key (left arrow v) pressed?> then
> change x by (rock speed)
> end
> +if <key (down arrow v) pressed?> then
> change y by (rock speed)
> end
> +if <key (up arrow v) pressed?> then
> change y by ((0) - (rock speed))
> end
> end
> ```

**Test:** Hold an arrow key. The rocks slide past — it looks like your duck is swimming.

> [!TIP]
>
> Press right and the rocks move left, which makes it feel like the duck is heading right. That opposite movement is what creates the illusion.
