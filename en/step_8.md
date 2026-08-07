## Clear the rocks

In this step, you'll delete each rock once it drifts off the stage, so your game keeps running smoothly. You'll build this as a `disappear`{:class="block3myblocks"} block.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Select **Make a Block** and name it `disappear`{:class="block3myblocks"}.
>
> ![Making a block.](images/make-block.png){:width="250"}

> [!TASK]
>
> Under `define disappear`{:class="block3myblocks"}, add an `if then`{:class="block3control"} and drag an `and`{:class="block3operators"} block into it.
>
> ```blocks3
> define disappear
> if <<> and <>> then
> end
> ```

> [!TASK]
>
> In the left side of the `and`{:class="block3operators"}, put a `key pressed`{:class="block3sensing"} set to the **right arrow**.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <>> then
> end
> ```

> [!TASK]
>
> In the right side of the `and`{:class="block3operators"}, drag a `less than`{:class="block3operators"} block.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <() < ()>> then
> end
> ```

> [!TASK]
>
> Put `x position`{:class="block3motion"} on the left and `-240` on the right.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <(x position) < (-240)>> then
> end
> ```

> [!TASK]
>
> Add a `delete this clone`{:class="block3control"} inside the `if`{:class="block3control"}.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <(x position) < (-240)>> then
> +delete this clone
> end
> ```

> [!TASK]
>
> Under `move`{:class="block3myblocks"} in the clone loop, drag in your `disappear`{:class="block3myblocks"} block.
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
> Duplicate the `if`{:class="block3control"} block for the other 3 edges, changing the key, the x/y, and the numbers.
>
> ```blocks3
> define disappear
> if <<key (right arrow v) pressed?> and <(x position) < (-240)>> then
> delete this clone
> end
> +if <<key (left arrow v) pressed?> and <(x position) > (240)>> then
> delete this clone
> end
> +if <<key (down arrow v) pressed?> and <(y position) > (180)>> then
> delete this clone
> end
> +if <<key (up arrow v) pressed?> and <(y position) < (-180)>> then
> delete this clone
> end
> ```

**Test:** Swim around for a while. Rocks should disappear once they drift off any edge, and your game should keep running smoothly.

> [!DEBUG]
>
> Depending on the size and position of your obstacle costume, you might need to adjust the edge numbers. If your rocks vanish too soon, or stick to the edge, try slightly smaller or larger numbers (for example `-220` or `-260` instead of `-240`).
