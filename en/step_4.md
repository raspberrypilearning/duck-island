## Add the rocks

In this step, you'll add rocks — obstacles your duck has to swim around.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Add a new sprite for your rocks — draw one, or choose one from the library.
>
> ![The Choose a Sprite menu.](images/choose-sprite.png){:width="300"}

> [!TASK]
>
> The rocks are made from **clones**. Start the script with a `green flag`{:class="block3events"}.
>
> ```blocks3
> when green flag clicked
> ```

> [!TASK]
>
> Rocks should sit behind your duck. Add a `go to back layer`{:class="block3looks"} block.
>
> ```blocks3
> when green flag clicked
> go to back layer
> ```

> [!TASK]
>
> Add a `forever`{:class="block3control"} loop with an `if () then`{:class="block3control"} block inside.
>
> ```blocks3
> when green flag clicked
> go to back layer
> +forever
> if <> then
> end
> end
> ```

> [!TASK]
>
> Make a new rock whenever a key is pressed. Add a `key (any v) pressed?`{:class="block3sensing"} block to the `if`{:class="block3control"}, and a `create clone of (myself v)`{:class="block3control"} block inside it.
>
> ```blocks3
> when green flag clicked
> go to back layer
> forever
> if <key (any v) pressed?> then
> +create clone of (myself v)
> end
> end
> ```

> [!TASK]
>
> Add a short random `wait`{:class="block3control"} so you don't get hundreds of rocks at once.
>
> ```blocks3
> when green flag clicked
> go to back layer
> forever
> if <key (any v) pressed?> then
> create clone of (myself v)
> end
> +wait (pick random (1) to (3)) seconds
> end
> ```

**Test:** Click the green flag and press any key. New rocks start appearing — they're all in one spot for now, but you'll scatter them in the next step.

> [!TASK]
>
> Now you've seen the rocks appear, add a `hide`{:class="block3looks"} so the original sprite stays out of sight. You'll make the clones show up properly in the next step.
>
> ```blocks3
> when green flag clicked
> go to back layer
> +hide
> forever
> if <key (any v) pressed?> then
> create clone of (myself v)
> end
> wait (pick random (1) to (3)) seconds
> end
> ```
