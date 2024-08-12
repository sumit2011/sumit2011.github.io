# CSS Part 1

***Navigation system works on the concept of linked list.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## 1. Introduction
### What is CSS?
Cascading Style Sheet, often abbreviated as CSS is a stylesheet language used to describe the look and formatting of a document written in HTML.

### Why use CSS?
* **CSS** allows you to apply different styles to different elements in your HTMML document.
* It gives you control over the visual presentation of your site and helps to separate the design from the content.
* Improves site maintenance, ensure consistency, and allows for site-wide changes with minimal effort.

### Basic CSS Syntax
A CSS rule-set consists of a selector and a declaration block. The selector points to the HTML element you want to style, and the declaration block contains one or more declarations separated by semicolon.
```css
selector {
    property: value;
}
```
### Applying CSS to HTML
* **inline CSS** : With this method, you use the style attribute directly within an HTML tag to apply CSS.
* **Internal CSS** : This involves placing CSS rules within `<style>` tags in the HTML document's `<head>` section.
* **External CSS** : This is the most common way to apply CSS. Styles are placed in a separate .css file which is then linked to the HTML document using the `<link>` element.

### Inline CSS
Inline CSS is used to apply a unique style to a single HTML element. It uses the style attribute of an HTML element. This method of insertion applies the CSS rules directly into the HTML file.
```html
<p style="color:blue;">This is a paragraph with inline css.</p>
```
{{< admonition type=success title="output of above HTML code" open=true >}}
<p style="color:blue;">This is a paragraph with inline css.</p>
{{< /admonition >}}

### Internal CSS
Internak CSS, also known as embedded CSS, is used to apply CSS to a whole HTML page. The CSS rules are put in a `<style>` block in the `<head>` section of the HTML file.
```html
<style>
    p {
        color: red;
    }
</style>
```
### External CSS
External css involves creating a separate .css file and linking it to your HTML document. This method of insertion aids in minimizing code redundancy and promotes reusability.\
Example:
1. First create an external css file inside your project folder.(styles.css)
```css
p{
    color: green;
}
```
2. Then, link this css file to your HTML document.
```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <p>This is a paragraph with external css.</p>
    </body>
</html>
```

### CSS Comments
Comments in CSS are used to explain your code and can help you and others understand the purpose of the code. All CSS comments start with `/*` and end with `*/`, and anything between these will be ignored by the browser.
```css
/* this is a single line comment */

    /* 
    this is a 
   multi-line comment 
    */

p{
    color: blue;
    font-size: 20px;
    margin: 30px;
}
```

## 2. CSS Selectors
### CSS selectors
Selectors are the means by which CSS identifies which HTML elements to style. Here are some basic types of selectors:
* **Tag selectors** : Selects HTML elements based on the element (tag) name.
* **ID selectors** : Selects a specific element based on its unique ID.
* **Class selectors** : Selects elements based on their class attribute.
* **Attribute selectors** : Selects elements based on an attribute or attribute value.
* **Pseudo-class selectors** : Selects elements based on a certain state.
* **Pseudo-elements selectors** : Select elements based on their position in the document.


### CSS properties and values
Once you've selected an element, you can apply styles to it using properties and values. Properties are what you want to style, and values are the styles that you apply to those properties.\
Here's how you can use the different types of selectors in CSS:
* Tag Selector
* Class Selector
```css
/* Tag Selector */
p {
    color: blue;
}
/* Class Selector */
.my-class {
    font-size: 20px;
}
```
### CSS selectors
* ID Selector
* Universal Selector
* Attribute selector
* Pseudo-class selectors
```css
/* ID Selector */
#myID {
    background-color: yellow;
}
/* Universal Selector */
*{
    margin: 0;
    padding: 0;
}

/* Attribute selector */
[type="text"] {
    border: 1px solid
    green;
}
/* Pseudo-class selectors */
p:hover {
    color: blue;
}
```
### CSS combinators
In CSS, combinators are used to explain the relationship between two selectors. There are four different combinators in CSS:
* descendant selector (space)
* child selector (>)
* adjacent sibling selector (+)
* general sibling selector (~)
```css
/* descendant selector (space) */

div p {
    background-color: yellow;
}

/* child selector (>) */
div > p {
    background-color: blue;
}

/* adjacent sibling selector (+) */
div + p {
    background-color: red;
}

/* general sibling selector (~) */
div~p {
    background-color: green;
}
```

## 3. CSS Specificity
### Calculate specificity
1. Inline styles: An inline style attribute present on an element will override any styles in external stylesheets and will have the highest level of specificity.
2. IDs: Each unique ID will add to the specificity.
3. Classes, pseudo-classes, and attributes: Each unique class, pseudo-class, or attribute will add to the specificity.
4. Elements and pseudo-elements: Each unique element or pseudo-element will add to the specificity

The specificity is calculated as follows:
* 1000 for inline styling
* 100 for each ID value
* 10 for each class value (or pseudo-class or attribute selector)
* 1 for each element selector or pseudo-element
```css
body #content .data {
    background-color: blue;
}
```
Equal specificity: the latest rule wins - If the same rule is written twice into the external style sheet, then the latest rule wins:
```css
h1 {color: blue;}
h1 {color: red;}
```

## 4. Absolute and Relative Units
### Absolute units
Absolute units are fixed-length units. They represent a physical measurement and don't scale based on any other factors like the size of the viewport or parent element.\
The absolute units in CSS are:
* Pixels (px)
* Points (pt)
* Inches (in)
* Centimeters (cm) and Millimeters (mm)
* Picas (pc)
### Relative units
Relative units are scaled quantities. They are relative to another length value, like the size of the viewport or the size of the parent element.\ Relative units in CSS are:
* Percentages (%)
* Viewport Width (vw)
* Viewport Height (vh)
* em
* rem
* Viewport Minimum (vmin)
* Viewport Maximum (vmax)

## 5. CSS Colors
### Named colors
CSS has a predefined set of named colors.
```css

color: red;
color: orange;
color: tan;
color: rebeccapurple;
color: transparent;

/* Example usage: */
p {
color: red;
}
```
### HEX Values
Hexadecimal (HEX) color values are based on the combination of red, green, and blue (RGB) values in a base-16 format. A HEX color code starts with a hash # followed by 6 characters - two for red, two for green, and two for blue.\
Example usage:
```css
body {
    background-color: #FF5733; /* A shade of orange */
}
```

### RGB Values
Colors can be defined using the rgb function, where values for red, green, and blue are provided in the range of 0-255.\
Example usage:
```css
div {
    color: rgb(0,0,0); * This is black *
}
```
### RGBA Values
RGBA is similar to RGB but has an additional value for alpha (A) representing opacity. The alpha value is between 0 (completely transparent) and 1 (fully opaque).\
Example usage:
```css
div {
    background-color: rgba(0, 0, 0, 0.5); /* Semi-transparent black */
}
```
### HSL Values
HSL stands for Hue, Saturation, and Lightness. It offers a more intuitive way to pick colors.\
Example:
```css
button { 
    background-color: hsl (120, 100%, 50%); /* Pure green */
}
```
### HSLA Values
Like RGBA, HSLA includes an alpha value for opacity.\
Example:
```css
button {
    background-color: hsla(120, 100%, 50%, 0.5);
}
```

## 6. CSS Box Model

### The Box Model
In CSS, each HTML element is considered as a box that consists of margins, borders, padding, and the actual content. This is known as the "box model".
* **Content**
* **Padding**
* **Border**
* **Margin**

<img src="images.png" alt="test image">

### Controlling Box Model Properties
It's important to note that by default, the total width and height of an element is calculated as:
>* Total width = width + left padding + right padding + left border + right border + left margin + right margin
>* Total height = height + top padding + bottom padding + top border + bottom border + top margin + bottom margin

### Box Sizing
CSS offers a property called **box-sizing** which can change this calculation. If you set `box-sizing: border-box;`, any padding or border specified in CSS will be included in the width or height of the element.
```html
<div class="box1">Hello, world!</div>
<div class="box2">Hello, world!</div>
<style>
.box1 {
    width: 200px;
    padding: 10px;
    border: 5px solid black;
    margin: 20px;
}
.box2 {
    box-sizing: border-box;
    width: 200px;
    padding: 10px;
    border: 5px solid black;
    margin: 20px;
}
</style>
```
{{< admonition type=success title="output of above HTML code" open=true >}}
<div class="box1">Box 1</div>
<div class="box2">Box 2</div>
<style>
.box1 {
    width: 200px;
    padding: 10px;
    border: 5px solid black;
    margin: 20px;
}
.box2 {
    box-sizing: border-box;
    width: 200px;
    padding: 10px;
    border: 5px solid black;
    margin: 20px;
}
</style>
{{< /admonition >}}


### Width and Height
The width and height properties set the width and height of an element.\
Example:
```css
div {
    width: 500px;
    height: 200px;
}
```
### Min/Max Variations
The max-width and min-width properties set the maximum and minimum widths of an element, while the max-height and min-height set the maximum and minimum heights.\
Example:
```css
div {
    width: 100%;
    min-width: 300px;
    max-width: 600px;
    min-height: 150px;
    max-height: 300px;
}
```
### CSS Margins
Margins are used in CSS to create space around elements, outside of any defined borders. With CSS, you have full control over the margins. There are properties for setting the margin for each side of an element (top, right, bottom, and left).\
Example:
```css
p {
    margin-top: 50px;
    margin-right: 150px;
    margin-bottom: 100px;
    margin-left: 200px;
}
/* Shorthands: */
p {
    margin: 50px 150px 100px 200px; /* top right bottom left */
}
p {
    margin: 50px 150px; /* vertical horizontal */
}
```
### CSS Borders
**Borders** in CSS can be applied to most elements within HTML. They can be used to define a boundary around an element, for visual appeal, or to separate different sections of a webpage.\
Example:
```css
p {
    border-style: solid; /* style of the border */
    border-width: 1px; /* width of the border */
    border-color: red; /* color of the border */
}
/* Shorthand: */
p {
    border: 1px solid red;
}
```
{{< admonition type=success title="output of above HTML code" open=true >}}
<p class="box3">this is a paragraph of text. </p>
<style>
.box3 {
    border-style: solid; /* style of the border */
    border-width: 1px; /* width of the border */
    border-color: red; /* color of the border */
}
/* Shorthand: */
.box3 {
    border: 1px solid red;
}
</style>
{{< /admonition >}}

### CSS Padding
**Padding** is the space that's inside the element between the element and the border. Padding goes around all four sides of the content and you can target and change the padding for each side with CSS (just like the margin).\
Example:
```css
p {
    padding-top: 50px;
    padding-right: 150px;
    padding-bottom: 100px;
    padding-left: 200px;
}
    
/* Shorthand: */
p {
    padding: 50px 150px 100px 200px;
}
```

## 7. CSS Floats

### Floating
The CSS float property is used to push an element to the left or right, allowing other elements to wrap around it.
Floating elements are taken out of the normal flow of a document and shifted to the left or right as far as they can go.

### Using the float property
The **float** property can have one of the following values:
* left
* right
* none
```html
<div style="width: 400px">
    <img src="home.png" style="float:left; padding-right:10px;" alt="test image" width="200" />
    <p> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis odio reiciendis, libero tempora saepe, quae maiores officia expedita temporibus, doloribus dolor eveniet asperiores. Quos molestiae recusandae eos est nulla. Unde.
    </p>
</div>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<div style="width: 400px">
    <img src="home.png" style="float:left; padding-right:10px;" alt="test image" width="200" />
    <p> Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis odio reiciendis, libero tempora saepe, quae maiores officia expedita temporibus, doloribus dolor eveniet asperiores. Quos molestiae recusandae eos est nulla. Unde.
    </p>
</div>
{{< /admonition >}}

### Clearing Floats
When you use the **float** property, you may encounter issues where elements overlap or layout is broken. To prevent these issues, You can use the **clear** property.
* none
* left
* right
* both

### using css overflow to clear floats
The **overflow** property with the value hidden can also be used to clear floats, if you apply it to the parent element of a floated element like in the example below.

```css
.container {
    overflow: hidden;
}
```

