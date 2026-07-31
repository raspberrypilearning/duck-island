## Clear the rocks

In this step, you'll delete each rock once it drifts off the stage, so your game keeps running smoothly. You'll build this as a `disappear`{:class="block3custom"} block.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Select **Make a Block** and name it `disappear`{:class="block3custom"}.

> [!TASK]
>
> Under `define disappear`{:class="block3custom"}, add an `if () then`{:class="block3control"} with `delete this clone`{:class="block3control"} inside.
>
> ```blocks3
> define disappear
> if <> then
> delete this clone
> end
> ```

> [!TASK]
>
> Drag an `and`{:class="block3operators"} block into the `if`{:class="block3control"}. In the left side, put a `key (right arrow v) pressed?`{:class="block3sensing"}.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <>> then
> delete this clone
> end
> ```

> [!TASK]
>
> In the right side of the `and`{:class="block3operators"}, drag a `() < ()`{:class="block3operators"} block. Put `x position`{:class="block3motion"} on the left and `-240` on the right.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <(x position) < (-240)>> then
> delete this clone
> end
> ```

> [!TASK]
>
> Call your `disappear`{:class="block3custom"} block under `move`{:class="block3custom"} in the clone loop.
>
> ```blocks3
> when I start as a clone
> appear
> forever
> move
> +disappear
> end
> ```

**Test:** Swim to the right. When rocks reach the left of the stage, they disappear.

> [!TASK]
>
> Duplicate the `if`{:class="block3control"} block for the other three edges, changing the key, the x/y, and the numbers.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <(x position) < (-240)>> then
> delete this clone
> end
> +if <<key (left arrow v) pressed?> and <(x position) > (240)>> then
> delete this clone
> end
> +if <<key (up arrow v) pressed?> and <(y position) < (-180)>> then
> delete this clone
> end
> +if <<key (down arrow v) pressed?> and <(y position) > (180)>> then
> delete this clone
> end
> ```

**Test:** Swim around for a while. Rocks disappear once they drift off any edge, and your game keeps running smoothly.
