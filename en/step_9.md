## Block the duck

Right now your duck swims straight through the rocks. In this step, you'll make the rocks block its path.

> [!TASK]
>
> ![The player sprite.](images/player-sprite.png){:width="150"}
>
> In the **player** sprite, make four variables: **right blocked**, **left blocked**, **up blocked**, and **down blocked**. Untick their checkboxes so they don't show on the stage.
>
> ![Making a variable.](images/make-a-variable.png){:width="250"}

You made this `switch costume`{:class="block3looks"} script for the right arrow in step 2:

```blocks3
if <key (right arrow v) pressed?> then
switch costume to (right v)
end
```

> [!TASK]
>
> Under the `switch costume`{:class="block3looks"}, add an `if else`{:class="block3control"} block. Drag in a `touching?`{:class="block3sensing"} and choose **obstacle**.
>
> ```blocks3
> if <key (right arrow v) pressed?> then
> switch costume to (right v)
> +if <touching (obstacle v)?> then
> else
> end
> end
> ```

> [!TASK]
>
> When it's touching a rock, add a `set right blocked`{:class="block3variables"} block and set it to `yes`.
>
> ```blocks3
> if <key (right arrow v) pressed?> then
> switch costume to (right v)
> if <touching (obstacle v)?> then
> +set [right blocked v] to [yes]
> else
> end
> end
> ```

> [!TASK]
>
> Add a `wait 0.5 seconds`{:class="block3control"} after it.
>
> ```blocks3
> if <key (right arrow v) pressed?> then
> switch costume to (right v)
> if <touching (obstacle v)?> then
> set [right blocked v] to [yes]
> +wait (0.5) seconds
> else
> end
> end
> ```

> [!TASK]
>
> Do the same in the `else`{:class="block3control"}: add a `set right blocked`{:class="block3variables"} block and set it to `no`.
>
> ```blocks3
> if <key (right arrow v) pressed?> then
> switch costume to (right v)
> if <touching (obstacle v)?> then
> set [right blocked v] to [yes]
> wait (0.5) seconds
> else
> +set [right blocked v] to [no]
> end
> end
> ```

> [!TIP]
>
> The `wait 0.5 seconds`{:class="block3control"} gives you a moment to change direction after bumping into a rock.

> [!TASK]
>
> Do the same for the other three arrow keys, using **left blocked**, **up blocked**, and **down blocked**.

Now add the block variables to the rock, so it stops moving when it's blocked.

> [!TASK]
>
> ![The rock sprite.](images/obstacle-sprite.png){:width="150"}
>
> Go to your **rock** sprite. In the `move`{:class="block3myblocks"} block, add an `and`{:class="block3operators"} block, and drag the `key pressed`{:class="block3sensing"} into the left box.
>
> ```blocks3
> define move
> +if <<key (right arrow v) pressed?> and <>> then
> change x by ((0) - (rock speed))
> end
> ```

> [!TASK]
>
> Drag an `equals`{:class="block3operators"} block into the `and`{:class="block3operators"}.
>
> ```blocks3
> define move
> if <<key (right arrow v) pressed?> and <() = ()>> then
> change x by ((0) - (rock speed))
> end
> ```

> [!TASK]
>
> Put **right blocked** on the left and `no` on the right, so the rock only moves when the right arrow is pressed and the right isn't blocked.
>
> ```blocks3
> define move
> if <<key (right arrow v) pressed?> and <(right blocked) = [no]>> then
> change x by ((0) - (rock speed))
> end
> ```

> [!TASK]
>
> Duplicate and do the same for each of your arrow keys.
>
> ```blocks3
> define move
> if <<key (right arrow v) pressed?> and <(right blocked) = [no]>> then
> change x by ((0) - (rock speed))
> end
> +if <<key (left arrow v) pressed?> and <(left blocked) = [no]>> then
> change x by (rock speed)
> end
> +if <<key (down arrow v) pressed?> and <(down blocked) = [no]>> then
> change y by (rock speed)
> end
> +if <<key (up arrow v) pressed?> and <(up blocked) = [no]>> then
> change y by ((0) - (rock speed))
> end
> ```

**Test:** Swim into a rock. Your duck stops instead of sliding through it.
