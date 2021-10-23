# The Box Model

### The default layout of CSS, or Normal Flow, uses the Box Model.

Everything in CSS has a box around it

**There are two types of boxes**

* block boxes
* inline boxes

**Boxes have an two types of displays**

* inner display type
* outer display type

<br>

## Normal Flow

The default layout of a web page's box model is

<br>

## Box Types & Components

### Block Type

If a box has an outer display type of block, then:

* The box will break onto a new line.
* The box will extend in the inline direction to fill the space available in its container. In most cases this means that the box will become as wide as its container, filling up 100% of the space available.
 * The width and height properties are respected.
* Padding, margin and border will cause other elements to be pushed away from the box
* HTML elements like ```<h1>``` and ```<p>``` use block as their outer display type by default.

### Inline Type

If a box has an outer display type of inline, then:
* The box will not break onto a new line.
* The width and height properties will not apply.
* Vertical padding, margins, and borders will apply but will not cause other inline boxes to move away from the box.
* Horizontal padding, margins, and borders will apply and will cause other inline boxes to move away from the box.
* HTML elements like ```<a>```, ```<span>```, ```<em>```, and ```<strong>``` use inline as their outer display type by default.

### Inline-Block Type

If a box has an outer display type of inline-block, then:
* The box will behave like the inline type
* The box will have block-style padding and margin

<br>

## Parts of the Box

Making up a block box in CSS

Content box:
* The area where your content is displayed, which can be sized using properties like width and height.
Padding box:
* The padding sits around the content as white space; its size can be controlled using padding and related properties.
Border box:
* The border box wraps the content and any padding. Its size and style can be controlled using border and related properties.
Margin box:
* The margin is the outermost layer, wrapping the content, padding, and border as whitespace between this box and other elements. Its size can be controlled using margin and related properties.

Example:

<img src="../images/box-model1.png">
<img src="../images/box-model2.png">

<br>

## Border-Box

Regular box-sizing places the height and width on the /content/ inner portion, not the box edges.

To apply content sizing to the box edge, use:

``` css
        .box {
            box- sizing:border- box;
        }
```

<br>
To apply content sizing to all boxes on the page:

``` css
        html {
            box- sizing: border- box;
        }
        *, *::before, *::after {
            box- sizing: inherit;
        }
```

\-\- more information on this at [this blog](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice)

<br>

## Inner and Outer Types