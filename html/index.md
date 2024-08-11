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
### Select dropdowns
Select dropdowns `<select>` provide users with a list of options from which they can choose. Supports multiple selection with the multiple attribute. To define default option, use selected attribute on `<option>` element
```html
<select name="country"> <option value="usa" selected>USA</option>
    <option value="canada">Canada</option>
    <option value="uk">UK</option>
</select>
```
### Textarea
The `<textarea>` element is used in HTML to create a multi-line text input field that the user can type into.
```html
<textarea name="message" rows="3" cols="50">Default message</textarea>
```
### File upload
The `<input type="file"/>` element renders a control for selecting and uploading files.
```html
<input type="file" name="FileUpload"/>
```
Specific attributes:
* **accept** - Specifies the types of files that the server accepts (image/png, image/jpeg).
* **multiple** - Enables the uploading of multiple files at once
```html
<input type="file" name="FileUpload" accept="image/png, image/jpeg" multiple />
```

### Buttons
Buttons `<button>` allow users to perform actions within the form, such as submitting the form or resetting input fields.
```html
<button type="submit">Submit</button>
<button type="reset">Reset</button>
```
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

### Video
Video content can be embedded using the `<video>` element. It allows you to provide video files playable directly on your webpages.
Example:
```html
<video controls>
    <source src="video.mp4" type="video/mp4">
    Your browser does not support the video element.
</video>
```

### Svg
SVGs, or Scalable Vector Graphics, are used to include vector-based images in your HTML document. They are resolution-independent and can scale without loss of quality, which makes them ideal for graphics like logos or icons.
Example:
```html
<svg width="50" height="50">
    <circle cx="25" cy="25" r="20" stroke="black" stroke-width="3" fill="red" />
</svg>
```
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
### Enhancing accessibility
Provide meaningful alternative text (alt) for images to describe their content to users who rely on screen readers or when the image cannot be displayed. For video and audio content, include captions, transcripts, or audio descriptions to make them accessible to users with hearing impairments.
Example:
```html
<img src="https://placehold.co/600x400"
    alt="Description of the image"
    title="Additional information about the image" />
```
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
