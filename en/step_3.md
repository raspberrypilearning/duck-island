## Bob on the water

In this step, you'll make your duck bob on the water.

Start by making the duck go up and down when a key is pressed.

> [!TASK]
>
> ![The player sprite.](images/player-sprite.png){:width="150"}
>
> Add a second `green flag`{:class="block3events"} with a `forever`{:class="block3control"} loop and an `if else`{:class="block3control"} block inside.
>
> ```blocks3
> when green flag clicked
> forever
> if <> then
> else
> end
> end
> ```

> [!TASK]
>
> Drag a `key pressed`{:class="block3sensing"} block into the `if`{:class="block3control"} and choose **any** from the drop-down list.
>
> ```blocks3
> when green flag clicked
> forever
> + if <key (any v) pressed?> then
> else
> end
> end
> ```

> [!TASK]
>
> In the `if`{:class="block3control"} part, make your duck bob quickly while a key is pressed.
>
> ```blocks3
> when green flag clicked
> forever
> if <key (any v) pressed?> then
> +change y by (3)
> +wait (0.1) seconds
> +change y by (-3)
> +wait (0.1) seconds
> else
> end
> end
> ```

> [!TASK]
>
> The idle bob uses the same blocks, just smaller and slower. Right-click the blocks you just made to duplicate them, and drop the copy into the `else`{:class="block3control"} part.
>
> ![Duplicating the blocks.](images/duplicate-blocks.gif){:width="450"}


> [!TASK]
>
> Change the values so the idle bob is smaller and slower.
>
> ```blocks3
> when green flag clicked
> forever
> if <key (any v) pressed?> then
> change y by (3)
> wait (0.1) seconds
> change y by (-3)
> wait (0.1) seconds
> else
> +change y by (1)
> +wait (0.3) seconds
> +change y by (-1)
> +wait (0.3) seconds
> end
> end
> ```

**Test:** Click the green flag. Your duck bobs gently on its own, and faster while it swims.
