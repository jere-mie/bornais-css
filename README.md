# bornais-css
A CSS framework made to be more versatile than Bootstrap, but semantically similar<br>
Based on Flex Box and CSS Grid

## The Grid System
Bornais.css supports two different ways to align content:
* The frow class, for single-row content (based on flex box)
* The bgrid class, for multi-row content (based on CSS Grid)

**Note: Whenever you see `screen-size` in a class name, you may use any of the following:**
* lg: works for devices with screen width 992px and above
* md: works for devices with screen width 768px and above
* sm: works for devices with screen width 576px and above
* xs: works for devices with any screen width

### frow (Single Line Content)
To align single line content using frow, you must create a div with class "frow-`screen-size`", like so:
```html
<div class="frow-md">
    <!-- CONTENT GOES HERE -->
</div> 
```

Next, you must place children inside the div, giving them the f-`screen-size`-`num` class<br>
Note that `num` is any number from 1-6, whereby it describes the relative ratio of the width of the element to the other elements.<br>
For example:
```html
<div class="frow-md">
    <div class="f-md-1">Box 1</div>
    <div class="f-md-2">Box 2</div>
    <div class="f-md-1">Box 3</div>
</div> 
```
In the above example, the ratio of widths between the boxes is 1:2:1, where Box 2 is twice the width as box 1.

### bgrid (Single Line Content)
To align multi line content using bgrid, you must create a div with class "bgrid", as well as "bgrid-`screen-size`-`num`", where `num` refers to the number of columns in the grid (1-12 are acceptable).<br>
For example, the following code creates a grid with 3 columns:
```html
<div class="bgrid bgrid-md-3">
    <!-- CONTENT GOES HERE -->
</div> 
```

Next, you must place children inside the div.<br>
If the children will all be the same width, then no further action is necessary.<br>
For example:
```html
<div class="bgrid bgrid-md-3">
    <div>Box 1</div>
    <div>Box 2</div>
    <div>Box 3</div>
    <div>Box 4</div>
    <div>Box 5</div>
    <div>Box 6</div>
</div> 
```
In the above example, a grid with three columns is created, where three elements fit on each row of the grid.<br>
This results in a 2 (height) by 3 (width) grid of boxes, all evenly spaced.<br><br>

Now, it is also possible to give children additional classes to allow them to span more than one row/column.<br>
Using the "w-`screen-size`-`num`" and "h-`screen-size`-`num`" classes, you can make an element span `num` columns, or `num` rows (or both! <br>
Note: `num` can be any number from 1-12 in this case<br>
For example:
```html
<div class="bgrid bgrid-md-3">
    <div class="w-md-2">Box 1</div>
    <div>Box 2</div>
    <div class="h-md-3">Box 3</div>
    <div>Box 4</div>
    <div class="w-md-3 h-md-4">Box 5</div>
    <div>Box 6</div>
</div> 
```
In the above example:
* Box 1 has a width of 2
* Box 3 has a height of 3
* Box 5 has a width of 3 and a height of 4