# CSS Basics

***Navigation system works on the concept of linked list.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}

## 1. CSS Basics
### What is CSS?
Cascading Style Sheet, often abbreviated as CSS is a stylesheet language used to describe the look and formatting of a document written in HTML.

### Why use CSS?
* CSS allows you to apply different styles to different elements in your HTMML document.
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
### CSS properties and values
### CSS selectors
### CSS combinators
In CSS, combinators are used to explain the relationship between two selectors. There are four different combinators in CSS.

## 3. CSS Specificity

## 4. Absolute and Relative Units

## 5. CSS Colors
### Named colors
CSS has a predefined set of named colors.

{{< admonition type=note title="Note" open=true >}}
{{< /admonition >}}


