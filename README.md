# Intro To Web
* [Description](#description)
* [Part I: Getting Started](#part-I:-Getting-Started)
  * [Getting Started in Web Design](#getting-started-in-web-design)
  * [How the Web Works](#how-the-web-works)
  * [some Big Concepts You Need To Know](#some-big-concepts-you-need-to-know)
* [Part II: HTML for Structure](#part-II:-html-for-structure)
  * [Creating a Simple Page](#creating-a-simple-page)
  * [Marking Up Text](#marking-up-text)
* [Further Reading](#further-reading)

# Description
Notes and projects following along to the book [Learning Web Design by Jennifer Robbins](https://www.amazon.com/Learning-Web-Design-Beginners-JavaScript/dp/1449319270)

# Part I: Getting Started
## Getting Started in Web Design
* Website creation roles
  * Content Wrangling
    * [Information architecture](#information-architecture): organizes content for ease of findability. 
    * [Content strategy](#content-strategy): Makes sure all text supports the brand identity
* Design: 
  * [UX and UI](#ux-and-ui)
    * First, design how the site works, the goal, how visitors move through it.
    * Goal: make site as easy efficient and delightful to use as possible
    * User research and testing reports: helps understand the needs, desires, and limitations of users
    * User testing is usually done at each phase of the design process
    * Wireframe Diagrams: shows structure of webpage, indicates how screen real estate is split up (omits colors, fonts, etc)
    * Site Diagram: indicates structure of site as a whole, how individual pages relate to one another
    * Storyboards and user flow charts: traces a users path through the site
  * Visual (graphic) design
    * Creates the “look and feel” of the site
    * Mock-ups (created in Photoshop - esque software) are used to present a visual design to clients and stakeholders
    * Since sites appear on different screen sizes, designers prefer to discuss visual identity (colors, fonts, image style, etc) that’s not tied to a desktop view (ex: style tiles or element collage)
* Code Slinging
  * Frontend development
    * Authoring/Markup (HTML) - authoring prepares content, marks up the content with HTML tags that describe the content and its function
    * Styling (CSS) - Describes how the content should look, also allows creation of responsive design
    * [JavaScript](#javascript) and DOM scripting - adds interactivity to web pages
      * AJAX (asynch JS and XML) is also important to know
  * Backend Development
    * Focus on the server, apps and databases (forms processing, content management systems, etc.)
    * Need server-side programming languages (PHP, Ruby, .NET, Python, or JSP)
    * Need to know how to work with databases (mySQL, Oracle, SQL server)
* Other Roles: product manager, project manager, SEO specialist, multimedia producers
## How the Web Works
Internet vs Web
* Internet is an international network of connected computers. The purpose is to share information
  * There are protocols in place to standardize how we transfer data
* Web (World Wide Web) is a means of information transfer
  * Uses the HTTP protocol (aka HyperText Transfer Protocol)
Servers - software on a computer that allows computers to communicate
* Servers wait for request for info, and then retrieve and send that info back
  * Servers often use Apache server software
IP address (Internet Protocol) and DNS (domain Name System)
* IP address - Assigned to every device connected to the internet
* DNS - allows humans to easily identify an internet-connected device.
  * Think of DNS like a pointer to an IP address
Web addresses (URLs)
* URL is made up of the protocol, the site name, the absolute path to the document/resource
  * http:// is the protocol
  * www (hostname) . example . com (domain name) (all together is the name of the site)
  * /2018/samples/first.html (directory path + document) (all together is the absolute path)
## Some Big Concepts You Need to Know
[Progressive enhancement](#progressive-enhancements) - allows you to deal with the ever evolving web technologies
* Design the minimum requirements, then add improvements for the enhanced devices
* Make sure basic functionality works without JavaScript
Responsive Web Design - provides appropriate layouts to devices based on the size of the viewport
# Part II: HTML for Structure
## Creating a Simple Page
Basics of page production
1. Start with content - write up raw text content
2. Give the document structure -  Add HTML elements in
3. Identify text elements - describe the content using appropriate HTML
4. Add images
5. Add CSS

Basic HTML document structure
```
<!DOCTYPE html>
<html>

    <head>
        <meta charset="utf-8">
        <title>Titlehere</title>
    </head>

    <body>
    Page content here
    </body>

</html>
```
* `charset="utf-8"` defines the document as using unicode
* What is the DOM (Document Object Model)
  * The relationships created between the elements (exemplified through the HTML markup and nesting)
* Block elements and inline elements are treated differently in the browser
* Empty elements (ex: `<img />`) have no content
* Attributes have syntax
  * `attributename="value"`
* Validatig a document means to check that the markup follows HTML standards
## Marking Up Text
* Assign an element to all the text in the document
* Use `<hr/>` to indicate that one topic has completed and another one is beginning
  * DON'T use `<hr/>` as a decorative line. Use CSS for that instead.
* Lists
  * For ordered lists, you can specify the list start at a number other than 1 using the `start` attribute (ex: `<ol start="17">`)
  * Description lists are used for name value pairs (terms and definitions, questions and answers)
  * `dl` element is allowed to contain only `dt` and `dd` elements
  * `dt` elemnts can have multiple `dd` elements; and `dd` elements can contain any type of flow content
```
<p> We illustrate a description list below: </p>
<dl>
    <dt>This is a term</dt>
    <dd>This is a definition</dd>

    <dt>Another term </dt>
    <dd>Another definition</dd>
</dl>
```
```
<dl>
    <dt>This is a term</dt>
    <dd>This is a definition</dd>
    <dd>This is a second definition</dd>

    <dt>Another term </dt>
    <dd>Another definition</dd>
    <dd><p>A second definition</p>
        <p>This time with paragraphs</p>
    </dd>
</dl>
```
* Longer Quotations, use `<blockquote></blockquote>`
  * Content within `<blockquotes>` should be contained in other elements
```
<blockquote>
    <p>Notice that this text is in a paragraph element.</p>
</blockquote>
```
* Preformatted text, `<pre></pre>` used when character spacing is semantically significant (ex: poems)
* Figures `<figure></figure>` identifies content that illustrates or supports some point in the text
  * `figure`s may contain images, video, code, text, or a table
  * `<figcaption></figcaption>` allows you to add a caption either above or below the `figure`
```
<figure>
    <pre>
        <code>
            body {
                background-color: #000;
                color: red;
            }
        </code>
    </pre>
</figure>

<figcaption> An example of how to use figure and pre HTML elements. </figcaption>
```
* Organzing Page Content (main, header, footer, section, article, nav, aside, and address)
  * Main content `<main></main>` - identifies the primary content of a page or application
    * The content of a `main` element should be unique to that page. No sidebars, headers, etc. 
    * Each page should have only one `main` and it should not be nested within an `article`, `aside`, `header`, `footer`, or `nav`
    * `main` can and should include other elements within it.
  * Headers and Footers `<header></header>` `<footer></footer>`
    * headers and footers can include any elements 
    * you cannot, however, next other `header`s or `footer`s within them
    * you can create multiple `footer`s in a page, setting a `footer` for other sectioning elements (`section`, `article`, etc)
  * Sections and Articles `<section></section>` `<article></article>`
    * if the content is self contained use `article` instead of `section`
    * if the grouping of the elements is simply to provide a hook for styling, use the generic `div` element
  * Aside (sidebars) `<aside></aside>`- tangentially related material
    * Can include other elements within (think of a side bar with links and lists)
  * Navigation `<nav></nav>` - identifies primary navigation for a site
    * Can include other elements within it (ex: containing a `ul` in `nav` element)
  * Addresses `<address></address>` - used to create an area for contact info
    * generally placed at the end of the document
* Inline Elements
  * For `abbr` element, the `title` attribute provides the unabbreviated version or in the case of acronyms, the full title
    * `<abbr ttile="Points">pts.</abbr>`
    * `<abbr title="American Type Founders">ATF</abbr>`
![inLineElements](/data/inLineElements.png)
* Generic Elements `<div></div>` and `<span></span>`
  * `div` indicates a division of content, you may be able to use `section` now instead
  * `span` same as `div` but used for phrases/words
  * you can give these elements meaning/context with `id` and `class` attributes
  * the `id` attribute - assigns a <em>unique</em> identifier to an element, the value of `id` must be used only once in the document
  * the `class` attribute - classifies elements into conceptual groups, can be shared by multiple elements
* Escape characters - using characters reserved for HTML (ex: <)
  * use the named entity & lt; or its numeric equivalent & #060;


# Further Reading
### Information Architecture
* Information Architecture: For the Web and Beyond, by Louis Rosenfeld and Peter Morville (O’Reilly).

### Content Strategy
* Content Strategy for the Web, 2nd Edition, by Kristina Halvorson and Melissa Rich (New Riders)

### UX and UI
* The Elements of User Experience: User-Centered Design for the Web and Beyond by Jesse James Garrett (New Riders) 
* Don’t Make Me Think, Revisited: A Common Sense Approach to Web Usability by Steve Krug (New Riders)
* The Design of Everyday Things by Don Norman (Basic Books) 
* About Face: The Essentials of Interaction Design, 4th Edition by Alan Cooper, Robert Reimann, David Cronin, and Christopher Noessel (Wiley) 
* Designing Interfaces, 2nd Edition by Jenifer Tidwell (O’Reilly)
* 100 Things Every Designer Needs to Know about People by Susan Weinschenk (New Riders) 
* Designing User Experience: A Guide to HCI, UX and Interaction Design by David Benyon (Pearson)

### JavaScript
* Learning JavaScript by Ethan Brown (O'Reilly)

### Progressive Enhancements
* Adaptive Web Design: Crafting Rich Experiences with Progressive Enhancement, 2nd Edition, by Aaron Gustafson (New Riders). 
* The Uncertain Web: Web Development in a Changing Landscape by Rob Larson (O’Reilly). 
* Designing with Progressive Enhancement by Todd Parker, Patty Toland, Scott Jehl, and Maggie Costello Wachs (New Riders)