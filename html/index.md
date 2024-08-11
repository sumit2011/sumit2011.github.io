# HTML Basics

***Navigation system works on the concept of linked list.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}
## 1. Introduction:

## 4. HTML Links
### Text links
text links are created using `<a>` anchor tag. The text within the anchor tags become clickable, directing users to the specified URL. To create a text link, use the following format:
```html
<a href="destination_url"> Link Text </a>

```

### Image links
We can also create link using images. To make an image clickable, place the `<img>` tag within the `<a>` tags. Here is the format:
```html
<a href="destination_url" >
    <img src="image_source" alt="Image Description />
</a>
```

### Absolute URL
an absolute URL specifies the complete web address, including the protoclol (https://).
```html
<a href="https://www.google.com" title="visit google">visit google.com</a>
```

### Relative URl
A Relative URL specifies the path to the file or location relative to the current webpage.
example: "about.html" or "../contact.html"
```html
<a href="contact.html">contact</a>
```

### Linking to a specific page section
To link to a specific section within the same webpage. you can use anchor links. Anchor links allow user to jump directly to a particular section by clicking on a link. They are created using the id attribute to identify the target with a preceding # symbol
Example:
```html
<a href="#section2">Go to section 2</a>

<!-- in this case, the id attribute section2 should be assigned to the target section -->

<section id="section2" >
    <h2>Section 2</h2>
    <p>this is the second section of the webpage.</p>
</section>

```


### Linking to a specific page section on another page
```html
<a href="./about-page.html#section2">
    Go to section 2 on the about page
</a>

```

### Additional Link Attribute
* target : Specifies how the link opens. for example, you can set target="_blank" to open the link in the new tab or window.
* download : Specifies that the linked resourse should be downloaded when clicked. it is commonly used for file downloads.

```html
<a href="https://www.example.com/some-pdf.pdf"
    target="_blank"
    download>
    Download pdf
</a>
```

## 5. HTML Lists
### Unordered lists
Unordered lists `<ul>` are used to present items without a specific order or sequence. Each item in the list is defined using `<li>` (list item) tag.
```html
<ul>
    <li>item 1</li>
    <li>item 2</li>
    <li>item 3</li>
</ul>
```
### Ordered lists
Ordered lists`<ol>` are used for items that have specific order or sequence. Like unordered lists, each item is defined using `<li>` tag.
```html
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```
### Nested lists
HTML allows you to nest lists within lists to create hierarchical structures. This is achieved by placing a complete list structure inside an individual list item `<li>`. this technique is useful for creating subcategories or multi-level lists.
```html
<h2>Nested Lists</h2>
<ul>
    <li>list item 1
        <ul>
            <li>list item 1.1</li>
            <li>list item 1.2</li>
            <li>list item 1.3</li>
        </ul>
    </li>
    <li>list item 2</li>
    <li>list item 3</li>
</ul>
```
### Styling lists
HTML lists can be customized and styled using css styles, you can change the apperance of list markers, adjust spacing, and create unique visual representations.
```css
ul {
    list-style-type: square;
    margin-left: 20px;
}

ol {
    list-style-type: upper-roman;
    margin-left: 30px;
}
```

## 6. HTML Tables
### Basic table structure
Tables in HTML are created using the `<table>` element. Inside the `<table>` element, we have rows defined by the `<tr>` (table row) element. Within each row we define table headers using the `<th>` (table header) element or table cells using the `<td>` (table data) element.
```html
<h2>Basic Table Structure</h2>
    <table>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
        <tr>
            <td>Cell 1</td>
            <td>Cell 2</td>
        </tr>
        <tr>
            <td>Cell 3</td>
            <td>Cell 4</td>
        </tr>
    </table>
```
### Table headers
Table headers `<th>` are used to define the headings of each column in a table. By default, table headers are bold and centered. They help provide context and improve the readability of the table.
```html
<h2>Table headers</h2>
<table>
    <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Phone</th>
    </tr>
    <!-- more rows -->
</table>
```
### Table cells
Table cells `<td>` hold the actual data within a table. Each cell corresponds to a specific row and column intersection. Table cells provide the content for each column in the table.
```html
<table>
    <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Phone</th>
    </tr>
    <tr>
        <td>sumit</td>
        <td>sumit2011kmr@gmail.com</td>
        <td>6202757997</td>
    </tr>
    <tr>
        <td>sumit</td>
        <td>sumit2011kmr@gmail.com</td>
        <td>6202757997</td>
    </tr>
</table>

```
### Styling tables
You can customize the apperance of tables using css. by applying css styles to the `<table>`, `<th>`, and `<td>` elements, you can change the table's layout, font, color, spacing and more.
```CSS
table {
    border-collapse: collapse;
    width: 100%;
}

td, th {
    padding: 8px;
    border: 1px solid black;
}

th {
    background-color: lightgray;
}

td {
    text-align: center;
}
```

## 7. HTML Forms

## 8. HTML Media Elements

## 9. HTML Semantics

## 10. HTML Styles
