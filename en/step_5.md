## Add rocks

In this step, you'll add rocks — obstacles your duck has to swim around. The rocks move in the background, which makes it look like the duck is swimming.

> [!TASK]
>
> Add a new sprite for your rocks — draw one with the paint tools, or choose one from the library.
>
> ![The Choose a Sprite menu.](images/choose-sprite.png){:width="300"}

> [!TIP]
>
> The rocks in the example are the rock emoji, copied and pasted into a text box in the Paint tab.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> The rocks are made from **clones** — copies of the sprite. Start the script with a `green flag`{:class="block3events"}, hide the original sprite, and create a clone.
>
> ```blocks3
> when green flag clicked
> hide
> create clone of (myself v)
> ```

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Add a `when I start as a clone`{:class="block3control"} script. Send each rock to a random spot, then show it.
>
> ```blocks3
> when I start as a clone
> go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
> show
> ```

> [!TASK]
>
> You can also give each rock a random size.
>
> ```blocks3
> when I start as a clone
> go to x: (pick random (-240) to (240)) y: (pick random (-180) to (180))
> +set size to (pick random (20) to (100)) %
> show
> ```

**Test:** Click the green flag a few times. Each rock appears at a different size and spot on the stage.

The rocks need to appear while the duck is swimming using the arrow keys. To do that, trigger the clone with a key press instead of the green flag.

> [!TASK]
>
> Wrap the `create clone of (myself v)`{:class="block3control"} in an `if () then`{:class="block3control"} block, and drop in a `key () pressed?`{:class="block3sensing"} set to **any**.
>
> ```blocks3
> when green flag clicked
> hide
> +if <key (any v) pressed?> then
> create clone of (myself v)
> end
> ```

> [!TASK]
>
> To keep it going, wrap that in a `forever`{:class="block3control"} loop and add a short random `wait`{:class="block3control"} so you don't get hundreds of rocks at once.
>
> ```blocks3
> when green flag clicked
> hide
> +forever
> if <key (any v) pressed?> then
> create clone of (myself v)
> end
> +wait (pick random (1) to (3)) seconds
> end
> ```

**Test:** Press the arrow keys. Rocks appear at random spots, with a 1–3 second wait between each one.
