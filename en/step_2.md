## Create your duck

In this step you will make the duck move with arrow keys.

> [!TASK]
>
> Open the [starter project](STARTER_PROJECT_LINK){:target="_blank"}. Your duck is already on the stage.

> [!TASK]
>
> Open the **Costumes** tab to see your duck's costumes: `front`, `back`, `left`, and `right`.
>
> ![The Costumes tab.](images/tab_costumes.png){:width="300"}

> [!TIP]
>
> If you'd rather use your own sprite, it needs a costume for each way it can face: `front`, `back`, `left`, and `right`.

> [!TASK]
>
> Start with the duck's starting position. Add a `green flag`{:class="block3events"} block that brings it to the front, faces it `front`, and puts it in the middle of the stage.
>
> ```blocks3
> when green flag clicked
> go to front
> switch costume to (front v)
> go to x: (0) y: (0)
> ```

> [!TASK]
>
> We make the duck look like it's moving by turning it to face the way it swims. Add a `forever`{:class="block3control"} loop that checks each arrow key and switches to the matching costume.
>
> Here's the `left arrow`{:class="block3sensing"} one — do the same for `right arrow` (right), `up arrow` (back), and `down arrow` (front).
>
> ```blocks3
> when green flag clicked
> go to front
> switch costume to (front v)
> go to x: (0) y: (0)
> +forever
> if <key (left arrow v) pressed?> then
> switch costume to (left v)
> end
> end
> ```

**Test:** Press the arrow keys. Your duck turns to face the way it's swimming.
