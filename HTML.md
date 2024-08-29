<h1 align="center">HTML</h1>

- In 1989, _Tim Berners-Lee_ established the World Wide Web (www); in 1991, he created the first version of HTML.
- HTML (HyperText Markup Language) was created by **Tim Berners-Lee** in 1991 as a standard for creating web pages.
- Language of Web, used for the creation of websites.
- We use HTML tags to define the look and feel of a website.
- Used for defining the layout of a page - A barebone page structure.
  - Example: Skeleton of a body.
- **Hypertext** -> linking of texts with other documents
- **Markup Language** -> language that utilizes a specific set of tags

### Need CSS & JavaScript

 ![alt text](image-7.png)
- **`CSS`** is primarily used for styling and formatting HTML elements on a webpage. It controls the visual presentation of the content.
  - Example: Setting the background color, adjusting the font size, defining the layout of elements using flexbox or grid, adding animations or transitions, etc.
- **`JavaScript`** is used for adding interactivity and dynamic behavior to HTML pages. It enables developers to manipulate the HTML structure, respond to user actions, and modify CSS styles dynamically.
  - Example: Implementing a carousel that automatically scrolls through images, fetching data from an API and updating the webpage with the results, etc.

### Need of `index.html`?

- `index.html` serves as the default landing page for a website or web application. It's commonly used as the entry point for accessing a website's content.
- Reasons:
  - The web server looks for an `index.html` file in the root directory by default. If found, this file is served to the user as the initial webpage they see.
  - Used to organize and structure the main content of a website. It can contain links to other pages and other menus.
  - Search engines like Google often prioritize indexing the content of the `index.html` file when crawling websites. A well-optimized `index.html` page can improve a website's visibility hence better for SEO (Search Engine Optimization).

### A Basic HTML Page
![alt text](image-1.png)

 <!-- Update Image -->

- A tag is like a container for either content or other HTML tags.
  **`HTML Document --> Browser --> Rendered Page`**
- Most of the HTML elements have opening and closing tags with content in between opening and closing tags.
- Some HTML tags have no content so they are called empty elements. eg: `<br>`
- We can either use the `.html` or `.htm` extension
- `<!-- HTML Comment -->` used as comment in HTML pages
- Case insensitive i.e. `<H1>` is same as `<h1>`

### HTML Element

- Building blocks used to create the structure and content of a web page & consist of a start tag, content, and an end tag.
- Represent various types of content such as text, images, videos, forms, and more.
- They provide the structure and semantics necessary for web browsers to render web pages correctly.
  - `Block-level elements`:
  1. Start on a new line and occupy the full width available to them.
  2. Create a "block" of content on the webpage.
     `eg: <div>, <p>, <h1> to <h6>, <ul>, <ol>, <li>, <table>, <form>, <header>, <footer>, <section>, <article>, and <nav>`
  - `Inline elements`:
  1. Do not start on a new line and only take up as much width as necessary.
  2. Allow content to flow alongside each other within the same line.
     `eg: <span>, <a>, <strong>, <em>, <img>, <input>, <button>, <label>, <abbr>, <code>, and <br>`

### HTML Attributes

- Provide additional information about HTML elements which are typically included within the opening tag of an element.
- Modifies the behavior, and appearance, or provides metadata about the element.
- Example:
  - `id`: Specifies a unique identifier for an element
  - `href`: Specifies the URL of a hyperlink
  - `src`: Specifies the URL of the image source

<h3 align="center">Tags in HTML</h3>

#### `Heading Tag`:

- In HTML, heading tags(`h1` to `h6`) are used to define headings or titles for sections of a webpage
- Provide structure and hierarchy to the content, allowing users and search engines to understand the organization of the page.

```html
<h1>Level 1 Heading</h1>
<h2>Level 2 Heading</h2>
<h3>Level 3 Heading</h3>
<h4>Level 4 Heading</h4>
<h5>Level 5 Heading</h5>
<h6>Level 6 Heading</h6>
```

- It's important to use heading tags because Overusing or misusing it can lead to confusion for both users and search engines.

#### `Paragraph Tag`

- Used to add paragraph to an HTML page.
- Used to structure and format blocks of text within a webpage.

```html
<p>Paragraph Tag</p>
```

#### `Anchor Tag`

- Anchor tags, represented by the `
<a>` and are used to create hyperlinks on web pages.
- Hyperlinks allow users to navigate between different web pages or sections within the same page.

```html
<a href="https://www.example.com">Link Text</a>
--> opens link in same tab
<a href="https://www.example.com" target="_blank">Link Text</a>
--> opens in link in new tab
<a href="https://www.example.com" target="_top">Link Text</a>
--> Opens document in the full body of the window
<a href="https://www.example.com" target="_self_">Link Text</a>
--> opens document in the same window or tab (default behavior)
<a href="https://www.example.com" target="_parent">Link Text</a>
--> opens the linked document in the parent frame
```

#### `Image Tag`

- Used to embed an image into a webpage.
- Self-closing tag, meaning it does not have a closing tag.

```html
<img src="example.jpg" alt="Example Image" title="This is an example image" />

--> alt: provides alternative text for the image which displayed whenever the
image doesn't loads.
```

#### `Bold, Italic and Underline Tags`

```html
<b> For Bold </b>
<i> For Italic </i>
<u> For Underline </u>
```

#### `Line Break Tag`

```html
<br />
```

#### `Big & Small Tag`

- We can make the texts a bit larger and a bit smaller using big and small tags respectively.

#### `<hr> Tag`

- Used to create a horizontal ruler and often used to separate the context.

#### `Subscript & Suoerscript Tag`

![alt text](image-3.png)

#### `pre Tag`

- Used to define preformatted text
- It preserves both spaces and line breaks within the text, displaying it exactly as it appears in the HTML code.

![alt text](image-4.png)

#### `div tag`

- It is a block-level element, used to define a division or section
- Used to group together and style a set of elements, or to create layout structures within a webpage.
- Always take full width.

#### `span Tag`

- It is an inline-level element used to apply styles or scripting to a specific portion of text within a larger block of content
- Unlike the `<div>` tag, which is a block-level element and creates a block-level container, the `<span>` tag does not create a new line or block-level container
- Commonly used when you want to apply styles or scripting to a specific portion of text within a larger block of content, without affecting the overall structure of the document

### Creating a Page Layout:

- With using the right tag in right place, results in a better page ;ayout, betterr indexing by search engines and better user experiences
- Use the `<header>`, `<main>` & `<footer>` tags effectively. This represennts the correct layout of a website

![alt text](image-5.png)

### Lists

- Used to display content which represent a list

```md
For Unordered List

<ul>
    <li>Home</li>
    <li>About</li>
    <li>Contact Us</li>
</ul>

Way to customise the bullet-points:
  (1) disc
  (2) circle
  (3) square

<ul type="square"> 
   <li>Notebook</li>
   <li>Marker</li>
</ul>

For Ordered List

<ol>
 <li>Mango</li>
 <li>Orange</li>
 <li>Litchi</li>
</ol>

Way to customise the bullet points:
(1) Uppercase Roman Numerals: type="I"
(2) Lowercase Roman Numerals: type="i"
(3) Arabic Numerals: type="1" (default)
(4) Lowercase Alphabetical Letters: type="a"
(5) Uppercase Alphabetical Letters: type="A"

<ol type="A" start="3">
 <li>Pen</li>
 <li>Pencil</li>
</ol>

For Definition List:

(1)<dl> is the container for the list.
(2)<dt> defines the terms that you want to explain.
(3)<dd> contains the definitions or explanations for the terms.


<h1>HTML Definition List</h1>
<dl>
 <dt>HTML</dt>
  <dd>HyperText Markup Language: The standard language for creating web pages.</dd>

 <dt>CSS</dt>
  <dd>Cascading Style Sheets: A stylesheet language used for describing the look and formatting of a document written in HTML.</dd>

 <dt>JavaScript</dt>
   <dd>A programming language commonly used in web development to add interactive features.</dd>
</dl>
```

### Tables

- The `<table>` tag is used to define tables in HTML
- It is used to format and display tabular data

```html
<tr>
  --> Used to display Table Row
  <td>
    --> Used to display Table Data
    <tr>
      --> Used in place of table data for displaying table headers
      <caption>
        --> Used to add a captionto the table
        <thead>
          --> Used to wrap table head (
          <caption>
            +
            <tr>
              +
              <td>
                )
                <tbody>
                  --> Used to wrap the table body
                </tbody>
              </td>
            </tr>
          </caption>
        </thead>
      </caption>
    </tr>
  </td>
</tr>
```

### Colspan Attribute:

- Used to create cells spanning multiple columns
- Two types:
  - Rowspan: Table cell to span multiple rows 
  - Colspan: Table cell to span multiple columns
![alt text](image-10.png)
```html

<th colspan="3">Nishant</th>
--> Spans 3 Columns
```

### HTML Forms

- Used to collect input from the user from tag is used for the same

```html
<form>Elememt of the Form</form>
```

#### Input Element

- Can be of type text, checkbox, radio, button amd submit. We also have a `file` type

#### Textarea Element

- Defines a multi-line text input columns and rows & Attribute can be used to size the textarea

#### Select Element

- Defines a drop down list
