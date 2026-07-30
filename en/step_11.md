## Add the hook

In this step, you'll add a hook — a hazard your duck has to dodge. Get caught and the game is over.

> [!TASK]
>
> ![The hook sprite.](images/hazard-sprite.png){:width="150"}
>
> Right-click your `collectable duck` sprite and duplicate it. Rename the copy `hook`.
>
> ![Duplicating a sprite.](images/duplicate-sprite.gif){:width="450"}

> [!TASK]
>
> Change its costume to a hook.
>
> ![Choosing a costume.](images/chose-a-costume.png){:width="300"}

> [!TASK]
>
> The hook shouldn't score points. In its `touching (player v)?`{:class="block3sensing"} check, delete the `change [Score v] by (1)`{:class="block3variables"} block and change the sound to one that sounds like getting caught.
>
> ```blocks3
> when I start as a clone
> forever
> if <touching (player v)?> then
> start sound (Rip v)
> delete this clone
> end
> end
> ```

> [!TASK]
>
> Now make the game end when the hook catches your duck. Swap the `delete this clone`{:class="block3control"} block for a `stop (all v)`{:class="block3control"} block.
>
> ```blocks3
> when I start as a clone
> forever
> if <touching (player v)?> then
> start sound (Rip v)
> stop [all v]
> end
> end
> ```

**Test:** Swim into a hook. The game stops.

> [!TIP]
>
> To make the hooks trickier to dodge, give each one a little drift of its own: in the clone script, `point in direction (pick random (-180) to (180))`{:class="block3motion"} and add `move (3.2) steps`{:class="block3motion"} inside the loop.
