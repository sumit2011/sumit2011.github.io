# HTML Basics

***Navigation system works on the concept of linked list.***
<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}
## 1. Introduction:
### What is HTML?
* **HTML**, which stands for Hypertext Markup Language. It is the standard markup language used in creating web pages. It is the backbone of any website and is used to format the content on the web page.
* Web pages created with HTML can include text, images, links, forms, audio, video and more.
* HTML is not a programming language, meaning it does not have logic like if...else statements or loops. It is a markup language and is used to structure content on the web.

### What is a website?
A website is essentially a folder which contains HTML, CSS and javascript documents as well as images, videos, audios, texts and more...
### Basic HTML structure
```html
<!DOCTYPE html>
<html>
    <head>
        <title>My first webpage</title>
    </head>
    <body>
        <h1>welcome to my site!</h1>
        <p>this is the content of the webpage.</p>
    </body>
</html>
```
### Basic HTML syntax
* standard HTML Elements
* Self closing HTML Elements
```html
<h1>Some text</h1>


<img src="path-to-image.jpg" />
```
## 2. HTML elements

### Heading and paragraphs
**HTML** provides six levels of headings, from `<h1>` to `<h6>`. These tags are used to create headings of different sizes and provide a visual hierarchy to your content.

The `<p>` tag is used to define paragraphs of text. It separates blocks of text and helps maintain readability and organization.
```html
<h1>This is a h1 heading</h1>
<h2>This is a h2 heading</h2>
<h3>This is a h3 heading</h3>
<h4>This is a h4 heading</h4>
<h5>This is a h5 heading</h5>
<h6>This is a h6 heading</h6>
<p>This is a paragraph of text.</p>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<h1>This is a h1 heading</h1>
<h2>This is a h2 heading</h2>
<h3>This is a h3 heading</h3>
<h4>This is a h4 heading</h4>
<h5>This is a h5 heading</h5>
<h6>This is a h6 heading</h6>
<p>This is a paragraph of text.</p>
{{< /admonition >}}

### Lists
HTML offers two types of lists: ordered lists `<ol>` and unordered lists `<ul>`. Ordered lists are used for items with a specific order or sequence, while unordered lists are used for items without a particular order. Each list item is defined using the `<li>` tag.
```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
{{< /admonition >}}

### Tables
Tables `<table>` are used to organize tabular data. They consist of rows `<tr>` and cells `<td>`. Tables help present data in a structured format.
```html
<table>
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
{{< admonition type=success title="output of above HTML code" open=false >}}
<table>
    <tr>
        <td>Cell 1</td>
        <td>Cell 2</td>
    </tr>
    <tr>
        <td>Cell 3</td>
        <td>Cell 4</td>
    </tr>
</table>
{{< /admonition >}}

### Divs
The `<div>` element is a versatile container that allows you to group and style sections of your webpage. It provides flexibility in organizing and styling content. It is primarily used for creating sections and grouping elements.
```html
<div>
    <h2>Section Title</h2>
    <p>This is another paragraph inside a div.</p>
</div>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<div>
    <h2>Section Title</h2>
    <p>This is another paragraph inside a div.</p>
</div>
{{< /admonition >}}

### Span
The `<span>` element is a versatile inline container that allows you to group and style specific sections of text or inline elements. It is primarily used for targeting and styling specific sections of text or inline elements within your HTML content.
```html
<p>
    HTML is <span style="color:red;">awesome</span>!
    <span style="color:red;">Span elements</span>can be used for inline styling.
</p>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<p>
    HTML is <span style="color:red;">awesome</span>!
    <span style="color:red;">Span elements</span>can be used for inline styling.
</p>
{{< /admonition >}}


### Comments in HTML
**Comments** in HTML allow you to leave notes in yout code that are ignored by the browser.
```html
<!-- this comment explains what the following code does.-->
<p>this paragraph contains some text.</p>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<!-- this comment explains what the following code does.-->
<p>this paragraph contains some text.</p>
{{< /admonition >}}

### Block and inline elements
Block-Level Elements:
* Block-level elements start on a new line and occupy the full width available by default.
* Examples of block-level elements include `<div>, <p>, <h1> to <h6>, <ul>, <li>, and <section>`.
* Block-level elements create a visual block or box-like structure.
* Block-level elements can contain other block-level and inline-level elements.
* They are commonly used for structuring and grouping content, creating sections, and adding vertical spacing.

Inline-Level Elements:
* Inline-level elements do not start on a new line and only occupy the necessary width to render their content.
* Examples of inline-level elements include `<span>, <a>, <strong>, <em>, <img>, and <input>`.
* Inline-level elements flow within the surrounding text and do not create line breaks.
* Inline-level elements cannot contain block-level elements but can contain other inline-level elements.
* They are commonly used for styling or adding emphasis within a line of text or to create inline links or images.

## 3. HTML Attributes
### Attribute basics
* All HTML elements can have attribute, but some attributes can be applied to all elements and some are specific to particular elements.
* Attributes provide additional information about elements.
* Attributes are always specified in the start tag.
* Attributes usually come in name/value pairs like: `name="value"`.
* Attributes values ate case sensitive, which means that `class="some-name"` is not the same as `class="some-Name"`.

### Class attribute
The **class** attribute is used to assign a specific class to an element. It is primarily used for styling purposes.
```html
<h1 class="main-heading">This is a h1 heading.</h1>
```
### ID attribute
The **id** attribute provides a unique identifier for an element on a webpage. It allows to target and manipulate specific elements using JavaScript and CSS.
```html
<h1 id="main-heading">This is a h1 heading</h1>
```
Each **id** must be unique within the HTML document.

### Src attribute
The **src** attribute is used with `<img>` tag to specify the source URL of an image. It enables you to display images on your webpage.
```html
<img src="images/image1.jpg" />
```
### Alt attribute
The **alt** attribute is used with the `<img>` tag to provide alternative text for an image. It is displayed if the image fails to load or for accessibility purpose, enabling screen readers to describe the image to visually impaired users.
```html
<img src="images/image1.jpg" alt="my image" />
```
### Href attribute
The **href** attribute is used with `<a>` tag to specify the destination URL or location of a hyperlink. It allows you to create clickable links that navigate to other web pages or sections within the same page.
```html
<a href="https://www.example.com/about.html" >About</p>
```
### Title attribute
The **title** attribute specifies extra information about the element.
The information is most often shown as a tooltip text when the mouse moves over the element.
```html
<a href="https://www.example.com/about.html" title="This is an about page">About</p>
```

### Style attribute
The **style** attribute specifies an inline style for an element. It will override any style set globally, eg. styles specified in the `<style>` tag or in an external style sheet.
The **style** attribute can also be used in any HTML element.
```html
<h1 style="color:blue; text-align:center; ">this is a header.</h1>
<p style="color:green;">This is a paragraph.</p>
```

## 4. HTML Links
### Text links
Text links are created using `<a>` anchor tag. The text within the anchor tags become clickable, directing users to the specified URL. To create a text link, use the following format:
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
An absolute URL specifies the complete web address, including the protoclol (https://).
```html
<a href="https://www.google.com" title="visit google">visit google.com</a>
```

### Relative URL
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


{{< admonition type=success title="output of above HTML code" open=false >}}
<ul>
    <li>item 1</li>
    <li>item 2</li>
    <li>item 3</li>
</ul>
{{< /admonition >}}

### Ordered lists
Ordered lists`<ol>` are used for items that have specific order or sequence. Like unordered lists, each item is defined using `<li>` tag.
```html
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>
{{< /admonition >}}

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

{{< admonition type=success title="output of above HTML code" open=false >}}
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
{{< /admonition >}}

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
{{< admonition type=success title="output of above HTML code" open=false >}}
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
{{< /admonition >}}

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
{{< admonition type=success title="output of above HTML code" open=false >}}
<h2>Table headers</h2>
<table>
    <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Phone</th>
    </tr>
    <!-- more rows -->
</table>
{{< /admonition >}}

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
{{< admonition type=success title="output of above HTML code" open=false >}}
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
{{< /admonition >}}

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
### Form structure
Forms are created using the `<form>` element. Inside the `<form>` element, we define form controls such as input fields, checkboxes, radio buttons, dropdowns, and buttons.
Example:
```html
<form action="/submit" method="POST">
    <!-- Form controls go here -->
</form>
```


Methods for submitting form data: GET and POST
### Labels
Label elements provide a descriptive text label for form controls, such as input fields, checkboxes, and radio buttons.
Associating labels with form controls improves usability by providing visual and interactive cues.
```html
<form action="/submit" method="POST">
    <label for="username">Username:</label>
    <input type="text" id="username"/>
</form>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<form action="/submit" method="POST">
    <label for="username">Username:</label>
    <input type="text" id="username" placeholder="Enter your username"/>
</form>
{{< /admonition >}}

### Input fields
Input fields `<input/>` allow users to enter data. They can be used for various types of user input, such as text, numbers, dates, emails, and more.
```html
<input type="text" name="username" placeholder="Enter your username"/>
```
Variations of the textbox input field:
* **text** - Renders a simple textbox
* **email** - Renders a textbox for inputting emails
* **password** - Renders a textbox for inputting passwords
* **number** - Renders a textbox for inputting numbers
* **date** - Renders a textbox for inputting dates
* **time** - Renders a textbox for inputting time

### Input fiels attributes
Attributes for all textbox variation elements:
* **value** - default value
* **placeholder** - placeholder text
* **maxlength** - maximum character length
* **disabled** - disables the input, values will not be submitted
* **readonly** - disables the input, values will be submitted
* **size** - visible width of an input element
* **required** - specifies a required field which the user must fill
Attributes for number, date and time:
* **min** - Defines the minimum value
* **max** - Defines the maximum value
The step attribute is specific to the number and time fields and specifies a stepping interval.

### Checkbox and radio buttons
Checkboxes (`<input type="checkbox" />`) and radio buttons (`<input type="radio" />`) allow users to select multiple options (checkboxes) or choose a single option from a group (radio buttons). To specify default selection, you can use the checked attribute.
```html
<input type="checkbox" name="option1" value="Option 1" checked /> Option 1
<input type="checkbox" name="option2" value="Option 2"/> Option 2
<input type="radio" name="choice" value="Choice 1" checked /> Choice 1
<input type="radio" name="choice" value="Choice 2"/> Choice 2
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<input type="checkbox" name="option1" value="Option 1" checked /> Option 1
<input type="checkbox" name="option2" value="Option 2"/> Option 2
<input type="radio" name="choice" value="Choice 1" checked /> Choice 1
<input type="radio" name="choice" value="Choice 2"/> Choice 2
{{< /admonition >}}

### Select dropdowns
Select dropdowns `<select>` provide users with a list of options from which they can choose. Supports multiple selection with the multiple attribute. To define default option, use selected attribute on `<option>` element
```html
<select name="country"> <option value="usa" selected>USA</option>
    <option value="canada">Canada</option>
    <option value="uk">UK</option>
</select>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<select name="country"> <option value="usa" selected>USA</option>
    <option value="canada">Canada</option>
    <option value="uk">UK</option>
</select>
{{< /admonition >}}

### Textarea
The `<textarea>` element is used in HTML to create a multi-line text input field that the user can type into.
```html
<textarea name="message" rows="3" cols="50">Default message</textarea>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<textarea name="message" rows="3" cols="50">Default message</textarea>
{{< /admonition >}}

### File upload
The `<input type="file"/>` element renders a control for selecting and uploading files.
```html
<input type="file" name="FileUpload"/>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<input type="file" name="FileUpload"/>
{{< /admonition >}}

Specific attributes:
* **accept** - Specifies the types of files that the server accepts (image/png, image/jpeg).
* **multiple** - Enables the uploading of multiple files at once
```html
<input type="file" name="FileUpload" accept="image/png, image/jpeg" multiple />
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<input type="file" name="FileUpload" accept="image/png, image/jpeg" multiple />
{{< /admonition >}}

### Buttons
Buttons `<button>` allow users to perform actions within the form, such as submitting the form or resetting input fields.
```html
<button type="submit">Submit</button>
<button type="reset">Reset</button>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<button type="submit">Submit</button>
<button type="reset">Reset</button>
{{< /admonition >}}

### GET request
* GET requests are primarily used to retrieve data from a server. When a client sends a GET request, it asks the server to provide a representation of a specific resource.
* Data in a GET request is appended to the URL as query parameters.

* GET requests are visible in the browser's address bar, making them less secure for sensitive data transmission.

### POST request
* POST requests are used to send data to the server to create or modify resources. When a client sends a POST request, it includes the data in the request body.
* POST requests are not visible in the browser's address bar, providing better security for sensitive data transmission.
* Data in a POST request is included in the request body.
### Difference and usecases
The main differences between POST and GET requests can be summarized as follows:
* GET requests are used for data retrieval, while POST requests are used for data submission or modification.
* GET requests append data to the URL as query parameters, while POST requests include data in the request body.
* GET requests are visible in the browser's address bar, while POST requests are not.

Use GET requests when:
* Retrieving data from the server.
* Accessing public information that does not require sensitive data.
* Sending lightweight data or parameters.

Use POST requests when:
* Submitting form data or user input.
* Modifying data on the server.
* Sending sensitive data that should not be visible in the URL or browser history.

## 8. HTML Media Elements
### Images
As already mentioned, images are displayed using the `<img>` element. They enhance the visual appeal and convey information on your webpages.
Example:
```html
<img src="image.jpg" alt="Description of the image"/>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<img src="image.jpg" alt="Description of the image"/>
{{< /admonition >}}

Here are some commonly used image formats:
* JPEG: It's best for photographs or images with lots of colors. JPEGs can be compressed considerably, which can result in a faster load time.
* PNG: It's ideal for images that require transparency and higher quality. PNGs are usually larger than JPEGs and should be used sparingly.
* SVG: Ideal for vector graphics as they are resolution-independent and typically smaller in file size.
* WebP: A modern image format that provides superior lossless and lossy compression for images on the web.

### Audio
Audio content can be embedded using the `<audio>` element. It allows you to provide audio files playable directly on your webpages.
Example:
```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
</audio>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
</audio>
{{< /admonition >}}

### Video
Video content can be embedded using the `<video>` element. It allows you to provide video files playable directly on your webpages.
Example:
```html
<video controls>
    <source src="video.mp4" type="video/mp4">
    Your browser does not support the video element.
</video>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<video controls>
    <source src="video.mp4" type="video/mp4">
    Your browser does not support the video element.
</video>
{{< /admonition >}}

### Svg
SVGs, or Scalable Vector Graphics, are used to include vector-based images in your HTML document. They are resolution-independent and can scale without loss of quality, which makes them ideal for graphics like logos or icons.
Example:
```html
<svg width="50" height="50">
    <circle cx="25" cy="25" r="20" stroke="black" stroke-width="3" fill="red" />
</svg>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<svg width="50" height="50">
    <circle cx="25" cy="25" r="20" stroke="black" stroke-width="3" fill="red" />
</svg>
{{< /admonition >}}

### Iframes
An iframe is used to embed another HTML document within the current one. You can use this to include content from another website, like a YouTube video or a map from Google Maps.
Example:
```html
<iframe src="https://www.youtube.com/embed/ScMzIvxBSi4"
    title="YouTube video"
    width="600"
    height="400">
</iframe>
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<iframe src="https://www.youtube.com/embed/ScMzIvxBSi4"
    title="YouTube video"
    width="600"
    height="400">
</iframe>
{{< /admonition >}}

### Enhancing accessibility
Provide meaningful alternative text (alt) for images to describe their content to users who rely on screen readers or when the image cannot be displayed. For video and audio content, include captions, transcripts, or audio descriptions to make them accessible to users with hearing impairments.
Example:
```html
<img src="https://placehold.co/600x400"
    alt="Description of the image"
    title="Additional information about the image" />
```
{{< admonition type=success title="output of above HTML code" open=false >}}
<img src="https://placehold.co/600x400"
    alt="Description of the image"
    title="Additional information about the image" />
{{< /admonition >}}

## 9. HTML Semantics

### Header
The `<header>` element represents the introductory or navigational content at the top of a webpage or a specific section within a webpage.
```html
<header>
    <h1>Welcome to my website</h1>
    <nav>
        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/contact">Contact</a>
    </nav>
</header>
```

### Navigation
The `<nav>` element represents a section of a webpage that contains navigation links allowing users to navigate through different areas or pages of a website.
```html
<nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/contact">Contact</a>
</nav>
```

### Main
The `<main>` element represents the main content of a webpage. It should contains unique content that is directly related to the purpose or central topic of the webpage.
```html
<main>
    <h1>About us</h1>
    <p>Welcome to our website</p>
</main>
```

### Article
The `<article>` element represents a self contained composition that can be independently distributed or reused. it can represent blog posts, news article, forum, posts and more.
```html
<article>
    <h2>10 Tips to become successful web developer.</h2>
    <p>Here are 10 essential tips.....</p>
</article>
```

### Section
The `<section>` element represents a standlone section within a document or a thematic grouping of content. It helps to organize and structure the content of a webpage.
```html
<section>
    <h2>Our Services</h2>
    <p>We offer a wide range of services...</p>
</section>
```

### Aside
The `<aside>` element represents content that is related to the main content of a webpage. It can contain sidebars, pull quotes, advertisements or other supporting information.
```html
<aside>
    <h3>Related Articles</h3>
    <ul>
        <li><a href="/article1">Article 1</a></li>
        <li><a href="/article2">Article 2</a></li>
        <li><a href="/article3">Article 3</a></li>
    </ul>
</aside>
```

### Footer
THe `<footer>` element represents the footer or the bottom section of a webpage. It typically contains the copywrite information, links to legal documents and contact details.
```html
<footer>
    <p>&copy; 2023 sumit. All rights reserved.</p>
    <nav>
        <a href="/privacy">Privacy Policy</a>
        <a href="/terms">Terms and Services</a>
    </nav>
</footer>
```
## 10. HTML Styles
### CSS Syntax
CSS consists of rulesets that define how HTML elements should be styled. A ruleset consists of a selector and one or more property-value pairs.
Examole:
```css
selector {
    property: value;
    property: value;
    /* more properties */
}
```
### Applying styles-Selectors
To apply styles to HTML elements you can use different type of selectors.

* **Tag selector**
A tag selector slects elements based on their HTML tag name.
* **Class selector**
A class selector selects elements based on the presence of a specific class attribute value.
* **Id selector**
An Id selector selects a specific elements based on the unique ID attribute value.
```css
p {
    color: blue;
}

.my-class {
    font-weight: bold;
}

#my-id {
    background-color: yellow;
}
```

### Applying styles-Types
To apply styles to HTML you can use different CSS types
* **Inline CSS**
Inline css is used to apply a unique style to a singl HTML element. It uses the style attribute of an HTML element. This method of insertion applies the CSS rules directly into the HTML file.
```html
<p style="color: blue;"> this is a paragraph with inline css.</p>
```

* **Internal CSS**
Internal css also known as embedded css. it is used to a whole HTML page. The CSS rules are put in a `<style>` block in the `<head>` section of the HTML file.\
Example:
```html
<style>
    p {
        color: red;
    }
</style>
```

* **External CSS**
External css involves creating a separate .css file and linking it to your HTML document. This method of insertion adds in minimizing code redundancy and promotes reusability.\
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

### Cascading and specificity
CSS follows a cascading and specificity model. which means that multiple styles can be applied to an element, and the most specific style takes precedence.
**Inline Styles :** Inline styles are applied directly to individual HTML elements using the style attribute.\
Example:
```html
<p style="color: red;">this is a red paragraph.</p>
```

**Specificity :** The specificity of a selector determines its priority when conflicting styles are applied. inline styles have the highest specificity, followed by ID selectors, class selectors and tag selectors.

### Common CSS properties
* **CSS** provides a wide range of properties to control the appearance of HTML elements.
* **color** : Specifies the text color.
* **background-color** : Sets the background color.
* **font-family** : Defines the font family to use for text.
* **font-size** : Specifies the font size.
* **margin** : Controls the outer spacing of an element.
* **padding** : Sets the inner spacing of an elemet.
* **border** : Defines the border style,width and color.\
Example:
```css
h1 {
    color: blue;
    font-family: Arial, sans-serif;
    margin-bottom: 20px;
    padding: 10px;
    border: 1px solid black;
}
```

## 11. HTML Best Practices

### Use proper indentation and formatting
Proper indentation and formatting make your HTML code more readable and easier to understand. Indent nested elements to clearly represent their hierarchy and use consistent spacing and line breaks.\
Example:
```
<!DOCTYPE html>
<html>
    <head>
        <title>My Web Page</title>
    </head>
    <body>
        <header>
            <h1>Welcome</h1>
        </header>
        <main>
            <p>This is the main content.</p>
        </main>
        <footer>
            <p>&copy; 2023 My Webpage</p>
        </footer>
    </body>
</html>
```
### Use semantic HTML elements
Utilize semantic HTML elements to provide meaning and structure to your content. Semantic elements like `<header>, <nav>, <main>, <article>, <footer>` convey the purpose and role of each section, enhancing accessibility and search engine optimization.\
Example:
```html
<header>
    <h1>Welcome</h1>
</header>
<main>
    <article>
        <h2>About Us</h2>
        <p>We are a company dedicated to...</p>
    </article>
</main>
<footer>
    <p>&copy; 2023 My Webpage</p>
</footer>
```
### Provide descriptive and accessible text alternatives
For images, videos, and other non-text content, always include descriptive alternative text (alt attribute) to provide information about the content for users who cannot see it. Use concise and meaningful descriptions that convey the purpose or context of the content.\
Example:
```html
<img src="image.jpg" alt="Description of the image" />
```
### Separate structure and presentation
Separate the structure (HTML) from the presentation (CSS) and behavior (JavaScript) of your webpages. Keep your HTML code focused on defining the content and structure, while styling and interactivity are handled through external CSS and JavaScript files.\
Example:
```html
<link rel="stylesheet" href="styles.css"/>
<script src="script.js"></script>
```
### Optimize performance
To improve website performance, minimize the use of unnecessary elements, attributes, and external resources. Use efficient techniques like compressing images, combining and minifying CSS and JavaScript files, and leveraging browser caching.\
Example:
```html
<link rel="stylesheet" href="styles.css"/>
<script src="script.js"></script>
```
### Validate your HTML
Regularly validate your HTML code using online validation tools or browser developer tools. Validating ensures that your code adheres to the HTML specifications and helps identify any errors or potential compatibility issues.
Example:
```html
<!DOCTYPE html>
<html>
<!-- HTML code goes here -->
</html>
```
### Optimize images
The first step in optimizing images is choosing the correct file format.
* **JPEG**: It's best for photographs or images with lots of colors. JPEGs can be compressed considerably, which can result in a faster load time.
* **PNG**: It's ideal for images that require transparency and higher quality. PNGs are usually larger than JPEGs and should be used sparingly.
* **SVG**: Ideal for vector graphics as they are resolution-independent and typically smaller in file size.
* **WebP**: A modern image format that provides superior lossless and lossy compression for images on the web.
* **Resize Images**: Images should be resized to fit the layout of your website.
* **Image Compression**: Compression reduces the file size without noticeably degrading the quality of the image below an acceptable level.
* **Use CSS Sprites**: CSS sprites combine multiple images into one single image, which can significantly reduce HTTP requests and improve load times.
* **Lazy Loading**: Lazy loading is a technique that delays the loading of non-critical or non-visible content until the point of need.
* **Use a CDN**: Content Delivery Networks (CDNs) can cache your images across a network of servers worldwide, making your site faster for users around the globe.

## 12. ARIA Labels
Enhancing Accessibility in web development
### Understanding ARIA Labels
ARIA labels are used to provide additional infomation to assistive technolory, such as screen readers, enabling a better user experiance for individuals with disabilities.\
Example:
```html
<button aria-label="Delete item">X</button> 
```

### Understanding ARIA roles and properties
ARIA roles define the purpose or type of an element, while ARIA properties provide additional properties or characteristics to describe the element further.\
Example:
```html
<div role="tablist">
    <button role="tab" aria-selected="true" id="tab1">Tab 1</button>
    <button role="tab" aria-selected="false" id="tab1">Tab 2</button>
</div>
<div role="tabpanel" aria-labelledby="tab1">Tab 1 content...</div>
<div role="tabpanel" aria-labelledby="tab2" hidden>Tab 2 content...</div>
```

### Common use cases for ARIA Labels
* Describing complex or interactive elements:
```html
<div role="button" aria-haspopup="true" aria-label="open menu">Menu</div>
```
* Enhancing link texts:
```html
<a href="/profile" aria-label="view sumit's profile">sumit kr</a>
```
* Describing images and Non-text content:
```html
<button aria-label="settings">
    <img src="settings-icon.png" alt="desc of image">
</button>
```

### Implementing ARIA Labels
* Use the aria-label attribute.
* Leverage ARIA roles and properties.
* Keep labels concise and descriptive.
* Test with assistive technologies.

## 13. SEO for html
### HTML Meta tags
Meta tags in HTML are typically used within the `<head>` section of an HTML document to define metadata about the page.

The following are key meta elements:
* <meta charset="UTF-8">
* <meta name="description" content="Free Web tutorials">
* <meta name="keywords" content="HTML,CSS,JavaScript">
* <meta name="author" content="Sumit Kr">
* <meta name="viewport" content="width=device-width, initial-scale=1.0">
* <meta http-equiv="refresh" content="30">
* <meta name="robots" content="noindex,nofollow">\
Example:
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta name="description" content="this is a tutorial about HTML" />
        <meta name="keywords" content="Home, relevent, page, content, keywords" />
        <meta name="author" content="Sumit Kumar" />
    </head>
    <body>
        <h1>Welcome to my website</h1>
        <p>this is a paragraph.</p>
    </body>
</html>
```

### Microdata
Microdata is a specific type of syntax that can be added to HTML to create machine readable data from the contents of a webpage.

Microdata uses a set of new HTML arrribute to embed structured data within existing HTML content. The attribute are:
* **itemscope** : This attribute is a boolean attribute that declares a new item.
* **itemtype** : This attribute declares what kind of item is being defined. It works in conjunction with **itemscope**.
* **itemprop** : This attribute is used to add properties to an item.
* **itemid** : This attribute assign a unique identifier to an item, providing a globally unique ID foe the item being marked up.\
Example:
```html
<div itemscope itemtype="http://schema.org/Movie">
    <h1 itemprop="name">Avenger: Endgame</h1>
    <span>Directors:
        <span itemprop="director">Anthony Russo</span>
        <span itemprop="director">Joe Russo</span>
    </span>
    <span itemprop="genre">Action, Adventure, Drama</span>
    <a href="../movies/avengers-endgame.html" itemprop="url">More details</a>
</div>

```

### SEO best practice
By implementing SEO best practice while writing HTML, You can improve the visibility of your web pages in search engine results.

1. Use Semantic HTML Elements
2. Incorporate ARIA Labels
3. Optimize Meta Tags
4. Optimize these meta tags by including relevant keywords
5. Structure Content with Headings
6. Optimize Image Alt Text

