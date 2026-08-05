## Move the rocks

The rocks move across the stage, which makes it look like your duck is swimming. 

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Make a variable called `rock speed`{:class="block3variables"}.
>
> ![Making a variable.](images/make-variable.png){:width="250"}

> [!TASK]
>
> Set the speed to `3` at the start of the `green flag`{:class="block3events"} script.
>
> ```blocks3
> when green flag clicked
> +set [rock speed v] to (3)
> hide
> forever
> if <key (any v) pressed?> then
> create clone of (myself v)
> end
> wait (pick random (1) to (3)) seconds
> end
> ```

> [!TASK]
>
> Select **Make a Block** and name it `move`{:class="block3myblocks"}.
>
> ![Making a block.](images/make-block.png){:width="250"}

> [!TASK]
>
> Under `define move`{:class="block3myblocks"}, add an `if then`{:class="block3control"} for the **left arrow**, and a `change x by`{:class="block3motion"} with `rock speed`{:class="block3variables"} in it.
>
> ```blocks3
> define move
> if <key (left arrow v) pressed?> then
> change x by (rock speed)
> end
> ```

> [!TASK]
>
> Add another `if then`{:class="block3control"} for the **down arrow**, with a `change y by`{:class="block3motion"} and `rock speed`{:class="block3variables"}.
>
> ```blocks3
> define move
> if <key (left arrow v) pressed?> then
> change x by (rock speed)
> end
> +if <key (down arrow v) pressed?> then
> change y by (rock speed)
> end
> ```

> [!TASK]
>
> Add a `forever`{:class="block3control"} loop at the bottom of `when I start as a clone`{:class="block3control"}. Go to the `My Blocks`{:class="block3myblocks"} menu again, and drag your `move`{:class="block3myblocks"} block inside it.
>
> ```blocks3
> when I start as a clone
> appear
> +forever
> move
> end
> ```

**Test:** Hold the **left** or **down** arrow. The rocks drift and it looks like your duck is swimming.

> [!TASK]
>
> The **right arrow** needs to move the rock the opposite way. Add an `if then`{:class="block3control"} for it, and a `change x by`{:class="block3motion"} — but this time use a `() - ()`{:class="block3operators"} operator to take `rock speed`{:class="block3variables"} away from `0`.
>
> ```blocks3
> define move
> if <key (left arrow v) pressed?> then
> change x by (rock speed)
> end
> if <key (down arrow v) pressed?> then
> change y by (rock speed)
> end
> +if <key (right arrow v) pressed?> then
> change x by ((0) - (rock speed))
> end
> ```

> [!TASK]
>
> Do the same for the **up arrow**: a `change y by`{:class="block3motion"} that takes `rock speed`{:class="block3variables"} away from `0`.
>
> ```blocks3
> define move
> if <key (left arrow v) pressed?> then
> change x by (rock speed)
> end
> if <key (down arrow v) pressed?> then
> change y by (rock speed)
> end
> if <key (right arrow v) pressed?> then
> change x by ((0) - (rock speed))
> end
> +if <key (up arrow v) pressed?> then
> change y by ((0) - (rock speed))
> end
> ```

**Test:** Hold an arrow key. The rocks slide the right way in every direction — it looks like your duck is swimming.
