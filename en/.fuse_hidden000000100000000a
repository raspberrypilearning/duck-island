## Rocks on the edge

The rocks need to look like they're drifting in from off the stage. In this step, you'll add to your `appear`{:class="block3custom"} block so each rock starts at the edge the duck is swimming towards.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> In your `appear`{:class="block3custom"} block, add an `if () then`{:class="block3control"} with a `key (right arrow v) pressed?`{:class="block3sensing"} check, and set the rock's x to 240 so it starts at the right edge.
>
> ```blocks3
> define appear
> go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
> set size to (pick random (20) to (100)) %
> show
> +if <key (right arrow v) pressed?> then
> set x to (240)
> end
> ```

**Test:** Swim right. Rocks appear from the right-hand edge, with the 1–3 second delay you set earlier.

> [!TASK]
>
> Do the same for the other three directions.
>
> ```blocks3
> define appear
> go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
> set size to (pick random (20) to (100)) %
> show
> if <key (right arrow v) pressed?> then
> set x to (240)
> end
> +if <key (left arrow v) pressed?> then
> set x to (-240)
> end
> +if <key (down arrow v) pressed?> then
> set y to (-180)
> end
> +if <key (up arrow v) pressed?> then
> set y to (180)
> end
> ```

**Test:** Swim in different directions. New rocks appear from the edge you're heading towards.
