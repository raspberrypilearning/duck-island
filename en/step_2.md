## Move the duck

In this step you will make the duck move in different directions with the arrow keys.

> [!TASK]
>
> Open the [starter project](STARTER_PROJECT_LINK){:target="_blank"}. Your duck is already on the stage.

> [!TASK]
>
> Open the **Costumes** tab to see your duck's costumes. These are labelled **front**, **back**, **left**, and **right**.
>
> ![The Costumes tab.](images/tab_costumes.png){:width="450"}

> [!TIP]
>
> If you'd rather use your own sprite, **choose**, **paint**, or **upload** one. It needs a costume for each direction: `front`, `back`, `left`, and `right`.

> [!TASK]
>
> ![The player sprite.](images/player-sprite.png){:width="150"}
>
> First set up the starting position. Add a `green flag`{:class="block3events"}, bring the duck to the front, face it `front`, and put it in the middle of the stage.
>
> ```blocks3
> when green flag clicked
> go to front layer
> switch costume to (front v)
> go to x: (0) y: (0)
> ```

> [!TASK]
>
> Make the duck look like it's moving by turning it to face the way it swims. Add a `forever`{:class="block3control"} loop with an `if () then`{:class="block3control"} block inside, and drop in a `key () pressed?`{:class="block3sensing"} block set to **left arrow**.
>
> ```blocks3
> when green flag clicked
> go to front layer
> switch costume to (front v)
> go to x: (0) y: (0)
> +forever
> if <key (left arrow v) pressed?> then
> end
> end
> ```

> [!TASK]
>
> Inside the `if`{:class="block3control"}, add a `switch costume to (left v)`{:class="block3looks"} so the duck faces left.
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
> Do the same for the other three keys: `right arrow` → `right`, `up arrow` → `back`, and `down arrow` → `front`.
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
> switch costume to (back v)
> end
> +if <key (down arrow v) pressed?> then
> switch costume to (front v)
> end
> end
> ```

> [!TIP]
>
> You can right-click a block to duplicate it.
>
> ![Duplicating the blocks.](images/duplicate-blocks.gif){:width="450"}

**Test:** Press the arrow keys. Your duck turns to face the way it's swimming.
