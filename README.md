# Click and Drag to Scroll

A click and drag slider effect. Built for Wes Bos' [JavaScript 30](https://javascript30.com/) course.

[![Screenshot of the Click and Drag page](https://res.cloudinary.com/gerhynes/image/upload/v1518469513/Screenshot-2018-2-12_Click_and_Drag_yzlume.png)](https://gk-hynes.github.io/click-and-drag/)

## Notes

When you click down, you want to add a class of `active` to the slider, and figure out where you clicked down. Then when you move your mouse the div will scroll the same amount.

First, select the slider, i.e. the `items` div.

Let `isDown` equal `false`. This is your flag variable, which will be `true` or `false` depending on whether you are clicking.

Create two variables, `startX` and `scrollLeft`. They will be assigned values in the events.

Attach event listeners for `mousedown`, `mouseup`, `mouseleave`, and `mousemove`.

When someone mouses down, take the `isDown` variable and set it to `true`.

When the mouse leaves the area or someone mouses up, set `isDown` to `false`.

Inside the mousemove function, if `isDown` is `false`, `return`. This will stop the function from running.

When you mousedown add a class of `active` to the slider. When the mouse leaves or someone mouses up, remove this class.

When you click down, you need to know where that anchor point is. This is what `startX` is for.

Pass the event to the mousedown function. You need to know where the user clicks inside of the slider, not on the page in general (to account for margin etc.).

`startX = e.pageX - slider.offsetLeft;`

You also need to figure out where the initial scroll was when you started it. This is what `scrollLeft` is for.

`scrollLeft = slider.scrollLeft;`

Inside the mousemove function call `e.preventDefault()` to avoid accidentally selecting text inside the slider.

At this point you know where the cursor is when you initially click down. You also want to know where it is every time you move it left or right.

`const x = e.pageX - slider.offsetLeft;`

The walk is equal to the `x` value minus the value of `startX`. This tells you how far you have moved from the initial position.

Finally, to scroll the slider, set `slider.scrollLeft` equal to `scrollLeft - walk;`.
