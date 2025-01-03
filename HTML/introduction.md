# Introduction

HTML is the standard markup language for Web pages.

## What is HTML?

- HTML stands for Hyper Text Markup Language
- HTML is the standard markup language for creating Web pages
- HTML describes the structure of a Web page
- HTML consists of a series of elements
- HTML elements tell the browser how to display the content
- HTML elements label pieces of content such as "this is a heading", "this is a paragraph", "this is a link", etc.

## HTML Page Structure

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>HTML Document</title>
    <link rel="stylesheet" href="styles.css" />
    <script src="script.js" defer></script>
  </head>

  <body>
    <header>
      <h1>Welcome to My Website</h1>
      <nav>
        <ul>
          <li><a href="#">Home</a></li>
          <li><a href="#">About</a></li>
          <li><a href="#">Services</a></li>
          <li><a href="#">Contact</a></li>
        </ul>
      </nav>
    </header>

    <main>
      <section>
        <h2>Introduction</h2>
        <p>This is an example of a simple HTML document structure.</p>
      </section>

      <section>
        <h2>Content Section</h2>
        <p>More content goes here.</p>
      </section>
    </main>

    <footer>
      <p>&copy; 2025 Your Website Name. All rights reserved.</p>
    </footer>
  </body>
</html>
```

`<!DOCTYPE html>`: Declares the document type as HTML5.

`<html lang="en">`: Specifies the language of the document.
`<meta charset="UTF-8">`: Ensures the correct encoding of characters.
`<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Makes the page responsive on different screen sizes.
`<title>`: The title of the document that appears in the browser tab.
External files: The `link` for external CSS and script for JavaScript.
`<header>`: Contains navigation and introductory elements.
`<main>`: The primary content section.
`<footer>`: Footer section for copyright and other footer info.

## What is an HTML Element?

An HTML element is defined by a start tag, some content, and an end tag:

example:

```html
<h1>Heading</h1>
```

The start tag <h1> contains the word 'Heading' as its element content, and </h1> is the end tag.
