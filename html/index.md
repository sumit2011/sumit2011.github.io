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
### Example
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>04_HTML_Links</title>
</head>
<body>
    <div>
        <a href="index.html">Home</a>
        <a href="contact.html">contact</a>
        <a href="about.html">about</a>
        <a href="news/news.html">news</a>
    </div>
    <div>
        <h1>HTML Links</h1>
        <hr/>

        <h2>this is an external link</h2>
        <a href="https://www.google.com" title="visit google">visit google.com</a>
        <hr/>

        <h2>this is an external link which opens in the new tab</h2>
        <a href="https://www.google.com" title="visit google" target="_blank">visit google.com</a>
        <hr/>

        <h2>this is an image link</h2>
        <a href="https://sumit2011.github.io" title="visit sumit's site" target="_blank">
            <img src="bg.jpeg" height="230px" width="230px"/>
        </a>
        <hr/>

        <h2>this is a download link</h2>
        <a href="./resume.pdf" download >Download pdf</a>
        <br/><hr/>

        <a href="#section 1">section 1</a>
        <a href="#section 2">section 2</a>
        <hr/>

        <div id="section 1">
            <h2>text section 1</h2>
            <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's 
                standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a ty
                pe specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
                remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing
                 Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions 
                 of Lorem Ipsum.
                Why do we use it?
                
                It is a long established fact that a reader will be distracted by the readable content of a page when looking
                at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as
                opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing 
                packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum'
                will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by
                accident, sometimes on purpose (injected humour and the like).
            </p>
        </div>

        <div id="section 2">
            <h2>text section 2</h2>
            <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's 
                standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a ty
                pe specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, 
                remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing
                 Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions 
                 of Lorem Ipsum.
                Why do we use it?
                
                It is a long established fact that a reader will be distracted by the readable content of a page when looking
                at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as
                opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing 
                packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum'
                will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by
                accident, sometimes on purpose (injected humour and the like).
            </p>
        </div>

        <a href="#">back to top</a> 

    </div>
</body>
</html>
```

## 5. HTML Lists

## 6. HTML Forms

## 7. HTML Media Elements

## 8. HTML Semantics

## 9. HTML Styles
