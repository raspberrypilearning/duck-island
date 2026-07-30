## Stop at the rocks

Right now your duck swims straight through the rocks. In this step, you'll make the rocks block its path. 

> [!TASK]
>
> ![The duck sprite.](images/player-sprite.png){:width="150"}
>
> Make four variables: `block right`{:class="block3variables"}, `block left`{:class="block3variables"}, `block up`{:class="block3variables"}, and `block down`{:class="block3variables"}. Untick their checkboxes so they don't show on the stage.

> [!TASK]
>
> On your `player` sprite, under the switch costume, add an `if () else`{:class="block3control"} block with a `touching (obstacle v)?`{:class="block3sensing"} check inside. Set that direction's block variable to 1 if it's touching a rock, otherwise 0.
>
> Here's the `right arrow`{:class="block3sensing"} one — do the same for left, up, and down.
>
> ```blocks3
> if <key (right arrow v) pressed?> then
> switch costume to (right v)
> +if <touching (obstacle v)?> then
> set [block right v] to (1)
> else
> set [block right v] to (0)
> end
> end
> ```

> [!TASK]
>
> Now go to your `rock` sprite. Make each rock only drift when that direction isn't blocked. Add `and (block ...) = (0)` to each `if`{:class="block3control"} in the drift loop.
>
> ```blocks3
> when I start as a clone
> forever
> if <<key (right arrow v) pressed?> and <(block right) = (0)>> then
> change x by ((0) - (rock speed))
> end
> if <<key (left arrow v) pressed?> and <(block left) = (0)>> then
> change x by (rock speed)
> end
> if <<key (down arrow v) pressed?> and <(block down) = (0)>> then
> change y by (rock speed)
> end
> if <<key (up arrow v) pressed?> and <(block up) = (0)>> then
> change y by ((0) - (rock speed))
> end
> end
> ```

**Test:** Swim into a rock. Your duck stops instead of sliding through it.
