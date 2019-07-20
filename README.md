# Intro To Web
* [Description](#description)
* [Part I: Getting Started](#part-I:-Getting-Started)
  * [Getting Started in Web Design](#getting-started-in-web-design)
  * [How the Web Works](#how-the-web-works)
  * [some Big Concepts You Need To Know](#some-big-concepts-you-need-to-know)
* [Part II: HTML for Structure](#part-II:-html-for-structure)
  * [Creating a Simple Page](#creating-a-simple-page)
  * [Marking Up Text](#marking-up-text)
  * [Adding Links](#adding-links)
  * [Adding Images](#adding-images)
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
## Adding Links
* To add a link, place content between `<a></a>` anchor tags. 
  * `href` attribute allows you to specify which document to link to
    * if Linking to a page on the web, you MUST provide the protocol (ex `http://`)
* Relative pathnames
  * You can have pathnames relative to the document that contains the link OR you can have pathnames that start at the root directory
  * A root directory starts from the root directory by using `/` at the start of the pathname
    * Because this type of link starts at the root, it works from any document on the server, regardless of which subdirectory it is located in
* Linking to a specific point in a page
  * This is known as linking to a document fragment.
  * First assign the target element in the document a unique `id`. This is a Fragment Identifier 
  * Then create a link using `<a href="#uniqueId">Link to unique element</a>`.
* Linking to a fragment in another document
  * Do this by adding the fragment name to the end of the URL
  * `<a href="index.html#uniqueId">Link to a fragment in another document.</a>`  
* Opening links in a new browser window
  * use the `target` attribute in the anchor element. Set the value of target to `_blank` to open a new window upon click
  * you can also name the target window such as "display" or "newWin" as long as the name does not start with an underscore. If you set `target="display"` for all your links, all the links will open up in the same window
* Putting email in html allows spambots to target your email. Consider encrypting the address using JavaScript
* Telephone Links - this allows mobile users to directly call
  * Use the `tel: ` protocol (ex: `<a href="tel: +01-800-555-2121">Call us!</a>`) Be sure to include the international country code
  * You could then use CSS to hide the link for non-mobile devices 
## Adding Images
* Images that appear as decoration (in the background of the header or a patterned border around an element) should be added through CSS
* Images that are part of the content appear in HTML
* The `src` and `alt` attributes are required for images
  * `alt` provides alternate text to display if the image is not available
  * the value of `alt` can be `null`
* Take advantage of caching for less trafic for the server
  * The browser downloads an image and stores it in the disk cahce. If an image is used repeatedly, be sure the `src` attribute for each image points to the same URL on the server, this allows the server to just use the cache.
* SVG images - vector based images
  * They are in text so they are faster to download than bitmapped images
  * resizing of vectors allows for responsive layout
  * Allows for animation
  * You can easily add interactivity with JavaScript
  * you may need to add server support for SVG images
* SVGs can be embedded with the `img` element
  * `<img src="/images/circle.svg" alt="">`
  * If you do this, you cannot apply style to the SVG or add interactivity
* Using the SVG inline
  * Downside: inline SVG is not cached by the server
```
<p>This summer, try making pizza
 
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 72 72" width="100" height="100">  
    <circle fill="#D4AB00" cx="36" cy="36" r="36"/>  
    <circle opacity=".7" fill="#FFF" stroke="#8A291C" cx="36.1" cy="35.9" r="31.2"/>  <circle fill="#A52C1B" cx="38.8" cy="13.5" r="4.8"/>  <circle fill="#A52C1B" cx="22.4" cy="20.9" r="4.8"/>  
    <circle fill="#A52C1B" cx="32" cy="37.2" r="4.8"/>  <circle fill="#A52C1B" cx="16.6" cy="39.9" r="4.8"/>  
    <circle fill="#A52C1B" cx="26.2" cy="53.3" r="4.8"/>  
    <circle fill="#A52C1B" cx="42.5" cy="27.3" r="4.8"/>  
    <circle fill="#A52C1B" cx="44.3" cy="55.2" r="4.8"/>  
    <circle fill="#A52C1B" cx="54.7" cy="42.9" r="4.8"/>  
    <circle fill="#A52C1B" cx="56" cy="28.3" r="4.8"/> 
</svg>

 on your grill.</p>
```
* Embedding SVG with the `<oblject></object>` element
  * The `object` tag specifies the media type and points to the file using the `data` attribute
  * If the `data` cannot be displayed any content within the `object` tags gets rendered
```
<object type="image/svg+xml" data="pizza.svg">
    <img src="pizza.png" alt="pizza"/>
</object>
```
  * HOWEVER, some browsers download both the SVG as well as the content. We can circumvent this by using a `div` and CSS within the `object` tag
```
<object type="image/svg+xml" data="pizza.svg">
    <div style ="background-image: url(pizza.png); width 100px; height: 100px;" role="img" aria-label="pizza">
</object>
```
* Using SVGs as background images with CSS
  * Setting the background image of the header to an SVG
```
header {
    background-image: url(/images/decorative.svg);
}
```
* Responsive Images - you provide multiple images and the browser decides which is most appropriate
  * `srcset` - attribute for `img` tag, it allows developers to specify a list of image source options for the browser to choose from
    * The value of `srcset` is a comma-separated list of options, where each item in the list has the URL of an image and an `x-descriptor` that specifies the target device pixel ratio
    * `<img src="image-URL" alt="" srcset="image-URL #x, image-URL #x"/>`
    * The `src` attribute is still required to specify the default image for 1x pixel ratio
    * HOWEVER, x descriptors select an image w/o regard for dimensions of the viewport. So x descriptors should be used for images that stay the same pixel dimensions regardless of the screen size (ex: logos, social media badges, etc)
  * `w-descriptor` -  



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