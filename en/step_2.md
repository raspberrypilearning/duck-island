## Move the duck

In this step you will make the duck look like it is moving with the arrow keys.

> [!TASK]
>
> Open the [starter project](https://scratch.mit.edu/projects/1365698888/editor){:target="_blank"}. Your duck is already on the stage.

> [!TASK]
>
> Open the **Costumes** tab to see your duck's costumes. These are labelled up, down, left, and right.
>
> ![The Costumes tab.](images/tab_costumes.png){:width="450"}

> [!TIP]
>
> If you'd rather use your own sprite, **choose**, **paint**, or **upload** one. It needs a costume for each direction: up, down, left, and right.

> [!TASK]
>
> ![The player sprite.](images/player-sprite.png){:width="150"}
>
> First set up the starting position. Add a `green flag`{:class="block3events"}, bring the duck to the front with `go to front layer`{:class="block3looks"}, face it down, and put it in the middle of the stage.
>
> ```blocks3
> when green flag clicked
> go to front layer
> switch costume to (down v)
> go to x: (0) y: (0)
> ```

> [!TASK]
>
> Make the duck look like it's moving by turning it to face the way it swims. Add a `forever`{:class="block3control"} loop with an `if then`{:class="block3control"} block inside, and drop in a `key pressed`{:class="block3sensing"} block set to `left arrow`{:class="block3sensing"}.
>
> ```blocks3
> when green flag clicked
> go to front layer
> switch costume to (down v)
> go to x: (0) y: (0)
> +forever
> if <key (left arrow v) pressed?> then
> end
> end
> ```

> [!TASK]
>
> Inside the `if`{:class="block3control"}, add a `switch costume`{:class="block3looks"} so the duck faces left.
>
> ```blocks3
> forever
> if <key (left arrow v) pressed?> then
> +switch costume to (left v)
> end
> end
> ```

> [!TASK]
>
> Do the same for the other three keys: `right arrow`{:class="block3sensing"} → right, `up arrow`{:class="block3sensing"} → up, and `down arrow`{:class="block3sensing"} → down.
>
> ```blocks3
> forever
> if <key (left arrow v) pressed?> then
> switch costume to (left v)
> end
> +if <key (right arrow v) pressed?> then
> switch costume to (right v)
> end
> +if <key (up arrow v) pressed?> then
> switch costume to (up v)
> end
> +if <key (down arrow v) pressed?> then
> switch costume to (down v)
> end
> end
> ```

> [!TIP]
>
> You can right-click a block to duplicate it.
>
> ![Duplicating the blocks.](images/duplicate-blocks.gif){:width="450"}

**Test:** Press the arrow keys. Your duck turns to face the way it's swimming.
