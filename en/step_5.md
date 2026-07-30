## Place the rocks

In this step, you'll make each new rock appear at a random place.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Add a `when I start as a clone`{:class="block3control"} script. Give each rock a random size, send it to a random spot, then show it.
>
> ```blocks3
> when I start as a clone
> set size to (pick random (20) to (100)) %
> go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
> show
> ```

**Test:** Hold an arrow key. Rocks of different sizes pop up all around.

> [!TASK]
>
> Make each rock appear at the edge the duck is swimming towards, so they drift in from the side. Add these checks to the end of the clone script.
>
> ```blocks3
> when I start as a clone
> set size to (pick random (20) to (100)) %
> go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
> show
> +if <key (right arrow v) pressed?> then
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

**Test:** Swim in one direction. New rocks appear from that edge of the stage.
