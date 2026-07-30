## Clear the rocks off-screen

Rocks that drift off the edge are still there behind the scenes, slowing your game down. In this step, you'll delete each rock once it leaves the stage.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> In the rock's `when I start as a clone`{:class="block3control"} loop, delete the clone once it drifts off the edge. Start with the `right arrow`{:class="block3sensing"}: when you're heading right and the rock's `x position`{:class="block3motion"} has passed the left edge, delete it.
>
> ```blocks3
> when I start as a clone
> forever
> +if <<key (right arrow v) pressed?> and <(x position) < (-240)>> then
> delete this clone
> end
> end
> ```

**Test:** Swim to the right for a while. Rocks that drift off the left edge disappear.

> [!TASK]
>
> Now add the other three edges to the same loop.
>
> ```blocks3
> when I start as a clone
> forever
> if <<key (right arrow v) pressed?> and <(x position) < (-240)>> then
> delete this clone
> end
> +if <<key (left arrow v) pressed?> and <(x position) > (240)>> then
> delete this clone
> end
> +if <<key (up arrow v) pressed?> and <(y position) < (-180)>> then
> delete this clone
> end
> +if <<key (down arrow v) pressed?> and <(y position) > (180)>> then
> delete this clone
> end
> end
> ```

**Test:** Swim around for a while. Rocks disappear once they drift off any edge, and your game keeps running smoothly.
