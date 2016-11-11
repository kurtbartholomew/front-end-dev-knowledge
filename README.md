#Front-end Job Interview Questions And Answers

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)

#### General Questions:

* What did you learn yesterday/this week?
 - How to use python function decorators in Flask to define routes
* What excites or interests you about coding?
 - The ability to design and pull your ideas from your head into the work for someone
   else to experience and enjoy
* What is a recent technical challenge you experienced and how did you solve it?
 - Figuring out how to test a user's tests with my own tests. I did this by separating
   out the test lines and running each of them through scenarios where they should
   cause a failure and then scenarios where they should pass. From there, I send
   messages back to the user to explain to them the scenario in which it failed and
   how to correct it.
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
 - UI considerations: Nav bar on top, links are underlined, vertical scrolling,
   no parallax effect, no carousel, responsive to small screens and high pixel
   ration screens. As few dropdowns as possible (hopefully none). Roles properly
   labeled for screen readers. Icons/links far enough apart to easily hit with
   mouse or finger.
 - Performance considerations: As few DNS lookups as possible, images put together
   as spritemaps, js and css both concatenated and minified, assets potentially
   loading from different subdomains to download multiple in parallel, all assets
   are gzipped, all images appropriately sized, css and js is not blocking load
   of page, and most important css is inlined to allow quick load of page with
   enhancement styles coming after
 - SEO: Load up those meta tags in the head with appropriate description words
 - Maintainability: Properly structured and modular css, intelligent use of
   css classes instead of ids, preferable use of vanilla javascript over jQuery,
   modular code structure with variable names that make sense and the use of
   semantic html like <section> and <aside>
 - Technology considerations: Assume the user is using a mobile device. Build out
   from there, making considerations for larger phones, small tablets, large tablets
   and laptop/desktop computers. Create css rules that scale properly for retina
   screens (double the number of pixels) so images don't look like garbage. Think
   about images you are serving and how long they take to download on average.
   Use roles, alt text, and tabbing copiously to make the page accessible to
   screen readers.
* Talk about your preferred development environment.
 - IntelliJ, WebStorm, SublimeText3 or Vim aided by automated build and testing tools like gulp or grunt
* Which version control systems are you familiar with?
 - git and svn
* Can you describe your workflow when you create a web page?
 - Decide on purpose of page
 - Decide on requirements and user stories
 - Sketch out general layout comp (Photoshop or Sketch)
 - Design review comp with others
 - Decide on general states of webpage and how to navigate between them
 - Decide if you need a separate mobile page or if responsive works.
 - Choose a serif and san-serif font to use throughout the page
 - Create mockup via Sketch
 - Design review mockup with others
 - Once design has been cemented, move on to implementation
 - Cement base semantic html structure
 - Create base css for positioning
 - Put in content placeholders
 - Write javascript as needed for interactions, data modeling and view management
 - Write tests for service and data model layers
 - Experiment with color combinations and fonts
 - Check with users regularly to get visual and behavioral feedback
 - Structure and modularize CSS to prevent a giant mess later
 - Finalize design with users
* If you have 5 different stylesheets, how would you best integrate them into the site?
 - Concatenate all the stylesheets and minify the result. Serve that
 - Move the common rules to the same stylesheet and remove from the others
 - Conditionally load the necessary stylesheets with inline js if no other choices
* Can you describe the difference between progressive enhancement and graceful degradation?
* How would you optimize a website's assets/resources?
 - Sprite Maps
 - JS/CSS Concatenation and Minification
 - Image Zipping
 - Caching of assets via CDN
 - Inline JS/CSS where needed
* How many resources will a browser download from a given domain at a time?
 - Earlier browsers like IE7 allow for 2 concurrent connections and later
   browsers like Chrome and Mozilla typically around 6
  * What are the exceptions?
    - Domain Partitioning (using static subdomains to load more assets concurrently)
    - SPDY (is not locked into TCP connection design, which prevents concurrency)
* Name 3 ways to decrease page load (perceived or actual load time).
 - Concatenate and minify scripts
 - Reduce DNS lookups
 - Load scripts asynchronously
* If you jumped on a project and they used tabs and you used spaces, what would you do?
 - Use tabs because it's your responsibility to follow established style
* Describe how you would create a simple slideshow page.
 - Create container1 with 100% the height and width of the body
 - Create another container2 inside container1 to hold all the slides. The
   display of it should be set to inline
 - Within container3, place any number of containers each with a width of 
   container1 and a slide in each of the containers
 - Simulate the sliding on click, enter or left/right arrow by shifting the
   absolute positioning of container2 one screen width left or right
* If you could master one technology this year, what would it be?
 - Go
* Explain the importance of standards and standards bodies.
 - Without them, maintainability would drop sharply due to new developers being
   unable to participate without significant onboarding, lots of downtime due
   to style differences between team members, slower tools since they can't be
   optimized for idiomatic syntax, and individual platforms would require an
    incredible amount of work to learn and develop for.
* What is Flash of Unstyled Content? How do you avoid FOUC?
 - The page renders before your styles are applied
 - Make sure to put your stylesheet links in the head of the document
* Explain what ARIA and screenreaders are, and how to make a website accessible.
 - ARIA stands for Accessible Rich Internet Applications
 - ARIA is a collection of attributes used on DOM nodes that allow programs to parse the DOM tree and find useful information for visually challenged users that are relayed to them via sound output. An example of this would be a role attribute defined as "menu" and items within defined as "menuitem". These would be parsed and read aloud for the user as a menu to choose from.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
 Pros:
  - CSS animations use GPU if available while relatively few js animations can
  - CSS animations can be much more hardware accelerated
  - CSS transforms and opacity changes can be done on a different thread
 Cons: 
  - CSS animations cannot really use seperate threads for changes involving DOM reflows
  - CSS animations under high load can occur improperly due to concurrency and scheduling issues with multiple threads
  - Unable to stop CSS animations in the middle of a tween typically
  - CSS animation keyframes are onerous to implement
  - CSS animations do not work in IE9 or earlier
  - CSS animations are limited in terms of curve animations
* What does CORS stand for and what issue does it address?
  - Cross Origin Resource Sharing. This prevents scripts from creating requests to domains other than the domain that the page is currently being served from. This functions to prevent other websites from using cookies containing user info to fraudulently impersonate them and interact with your server.

#### HTML Questions:

* What does a `doctype` do?
 - Doctypes inform the layout engine of the browser what type of validation it should use to validate and parse the html content resulting from the request for your web page
* What's the difference between standards mode and quirks mode?
 - On a basic level, standards mode is the layout engine attempting to adhere to the specification set within the doctype of the document. Quirks mode is set to handle older browser specifications that would typically break under standards mode. Historically, IE's quirks mode basically ran IE5.5 specification, though quirks mode among browsers has been converging.
* What's the difference between HTML and XHTML?
 - XHTML is a typically stricter HTML with more xml syntax. This was a kind of stepping stone from HTML4 to HTML5. Namespaces were allowed in XHTML and certain html structures as well as CSS were not available in XHTML. In XHTML, every tag had to be closed and node attributes cannot be omitted (anchor tags have to have an href attribute).
* Are there any problems with serving pages as `application/xhtml+xml`?
 - Potential problems are that a user could be using a browser that cannot or does not parse xml correctly. Also, any malformed xml will not be skipped but instead cause the browser to abort loading the page.
* How do you serve a page with content in multiple languages?
 - Include a lang="**" attribute at the root of the document for a single language and multiple languages can be enabled by using lang="**" on containing dom elements. This can also be extended to pages that the browser will visit by putting an hreflang="**" attribute on the element.
* What kind of things must you be wary of when design or developing for multilingual sites? It is important to think about things like character encoding (typically UTF-8 in a meta tag), directionality of text (typically dir="rtl" or dir="ltr"), font sizing based on language and the length of words (typically asian languages will be shorter pictographs while languages like German will be longer)
* What are `data-` attributes good for?
 - Data attributes are good for storing highly granular data that can be retrieved later not just through javascript but that is also accessible through CSS.
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
 - Semantic HTML constructs such as <aside>, <section> and <blockquote>. Additional and important API's that have also been added are things like the <video> and <audio> API's, the Geolocation API, the introduction of <canvas> and <svg> for graphics, web workers for parallel processing and additional caching with localstorage.
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
 - Cookies are simple text documents with a name and value pair as well as expiration/protocol attributes. They must be under 4kb and are sent to the server on every request. They can be either deleted on session close or persistent based on their expiration attribute. SessionStorage and localStorage are HTML5 constructs for storing data under 5MB (this restriction is per domain for localStorage and per domain per tab or window for sessionStorage). Neither are sent to the server automatically and their contents are typically accessed via javascript.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
 - Once the HTML layout engine parser finds a plain <script> tag, parsing will cease until the script is downloaded and executed. The "async" attribute continues parsing while the script downloads but stops parsing and executes the script when the download finishes. The "defer" attribute tells the layout engine to fully parse the document and download the script before executing the script.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
 - Generally, placing css links in the head of the document will prevent a flash of unstyled content (incorrect positioning, lack of content, sizing issues, etc) however it can be useful to place non-critical styles such as fancier fonts after the main document to allow for smaller windows of blank content
* What is progressive rendering?
 - Progressive rendering (also called a critical rendering path) is the idea that a page should display content immediately and progressively load more instead of leaving a user with a blank page until all the content is delivered at once.
* Have you used different HTML templating languages before?
 - Yes, I've used Mustache/Handlebars, Jade, Underscore and HAML

#### CSS Questions:

* What is the difference between classes and ID's in CSS?
 - Id is typically for identifying a single DOM element while classes are more for applying styles across a number of elements
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
 - Resetting the CSS typically means setting all css properties to their base values (this could mean 0, "none", "static", "inherit", "12px", etc.) and therefore starting with a blank slate. Normalizing involves deciding on a standard for css attributes present in the user-agent css of major browsers and implementing that standard. My choice between the two depends on whether I'm implementing it or not. If not, I would choose normalizing since it means less focus on making baseline css decisions and less boilerplate. Resetting would be much less verbose if I was implementing it though.
* Describe Floats and how they work.
 - Floating an element means to adhere an element to a particular direction while still allowing the document content to flow around it. Resizing a floated element will cause the content around the element to move appropriately.
* Describe z-index and how stacking context is formed.
 - Z-index is the attribute used to define occlusion of elements (that is elements being displayed above or in front of other elements). The stacking context is formed by the hierarchical nature of the DOM. Elements closer to the root element in terms of hierarchy have their z-index evaluated with a higher priority than those within their children. Z-index is not used at all on elements that are statically positioned.
* Describe BFC(Block Formatting Context) and how it works.
 - BFC refers to the the specification of block level elements adhering to the left side of their container. It is used to provide rules for positioning within a block as well as the clearing of elements the come after floated elements.
* What are the various clearing techniques and which is appropriate for what context?
 - A "clear: both" CSS attribute can be added to a DOM element directly proceeding the floated element (usually an empty div). This is easy but semantically poor.
 - Add "overflow" CSS attribute to a parent DOM element. This is also simple but can unnecessarily clutter CSS rules.
 - Use an :after psuedoselector with {content: ".",visibility: "hidden",display: "block", height: 0, clear: "both"}. This is the most commonly accepted way to implement a "clearfix" but also runs into compatibility problems with its psuedoselector.
* Explain CSS sprites, and how you would implement them on a page or site.
 - A CSS sprite is an image that contains several images used in a page. This allows the use of a single dns lookup instead of one for every image. To utilize a CSS sprite, you'll typically need to use some utility to concatenate the images together. From there, the elements that you want to utilize the images for will use the sprite as a background image (with no repeat). Each specific element will have specific background position and height attributes to display the proper portion of the sprite corresponding to the correct image.
* What are your favorite image replacement techniques and which do you use when?
 - If I really had to use IR techniques (I feel as though their purpose is obfuscated for subsequent developers), I would use either the text indent method {text-indent: 100%, overflow: hidden} or font method {font: 0/0 a;color: transparent;text-shadow:none}. I have no real opinion on when to use which.
* How would you approach fixing browser-specific styling issues?
 - My approach is to typically use a css normalizer or css reset. From there, I do my best to make sure that forms and fonts are as uniform as possible. After that, its simply a matter of making sure that the appropriate browser prefixes are applied to style rules that need them. Special cases may exist in regards to box model differences between browsers, especially IE<=9. There has to be a logical decision made on whether or not the company has to support those versions and the CSS quirks they carry with them.
* How do you serve your pages for feature-constrained browsers?
 - The assumption I will make here is that this means earlier browser versions or mobile browser versions in which many modern day API's do not exist. There are two real strategies that I believe you can use. One would be to either provide the functionality through polyfills that use javascript to implement native functionality API's like Geolocation. The other would be to use resources to find what API's can be used without compatibility issues (such as caniuse.com).
* What are the different ways to visually hide content (and make it available only for screen readers)?
 - This question is very similar to that of image replacement techniques. I would simply employ the same techniques without using a background image. An additional way I didn't talk about previously would be to use the rectangle clip method {clip: rect(0,0,0,0);height:0,width:0,border:0}}, though that could run into compatibility issues.
* Have you ever used a grid system, and if so, what do you prefer?
 - Yes, grid systems are pretty common now-a-days. I typically prefer to use frameworks with less excess baggage like Skeleton, but I have used Foundation and Bootstrap's grid system in the past.
* Have you used or implemented media queries or mobile specific layouts/CSS?
 - Yes, I prefer to design for mobile form factors first. Typically this means designing for width constraints of <720 (mobile), >720 (tablet) and >1000 (desktop). By this, I mean I prefer to create a responsive layout that works for desktop, tablet and mobile. I understand that this is not always possible and sometimes mobile needs its own layout, but I find it preferable to avoid that if possible.
* Are you familiar with styling SVG?
 - No
* How do you optimize your webpages for print?
 - I usually have a separate css file for print. The considerations I make are:
   - for the removal of non-critical graphics and images
   - avoid tables since they break oddly in many cases
   - remove navigation links and normalize fonts
* What are some of the "gotchas" for writing efficient CSS?
 - Psuedoselectors and regex selectors carry performance overhead with them
 - Overqualified selectors (selectors with additional unneeded parts like ".menu li a span") cause performance overhead and create specificity issues (these are also called multiple descendant selectors)
 - CSS selectors are executed from right to left. This means if you have a very generic tag as the key selector, the selector will still be slow even if you have an id as the first tag.
 - Id's tend to be the fastest selectors while universal tags are the slowest (though compared to the others, this is pretty minor)
* What are the advantages/disadvantages of using CSS preprocessors?
 - Advantages:
   - Your css can be the same phyiscally (into partials) as it is logically (one for nav, one for footer, etc.)
   - Mixins provide you with the ability to reuse previously established styles
   - Variables allow you to declare things like font color in a single place and reuse it
   - Calculations allow you to calculate combinations of variables at compilation time and use those rules
   - Nesting allows you to properly style elements and their children in a more succinct format
 - Disadvantages:
   - Setup can be onerous.
   - Maps are typically required for use in browsers to see the CSS in a readable format
   - Abstractions can also cause terribly overqualified selectors
   - The compiled file can be much larger and more unreadable than a CSS file created manually
* How would you implement a web design comp that uses non-standard fonts?
 - TBD
* Explain how a browser determines what elements match a CSS selector.
 - The browser processes selectors from right to left, using the rightmost selector as the key selector. It traverses the tree, finding an appropriate node, and then attempts to evaluate the rest of the selector by looking up the dom tree to verify the containing elements match the remaining selectors. If not, it moves onto subsequent matches for the key selector.
* Describe pseudo-elements and discuss what they are used for. 
 - Psuedo-elements are CSS3 constructs that allows the styling of more granular parts of a targeted element like ::first-line, ::first-letter, ::before and ::after.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
 - The box model is how the browser (more specifically the rendering engine) calculates visual positioning of elements. It is typically made up of content, padding, border and margin (from innermost to outermost). Common differences between most box models involves calculating the height and width of an element. Historically the box model has not included padding and border in calculation of height and width, though in recent years, this has changed to include them. (Funny enough, IE was the pioneer of the inclusion of padding and border).
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
 - The above mentioned css causes the rendering engine to include padding and border in height and width calculations. This means no longer having to do additional calculations for those properties to properly set dimensions.
* List as many values for the display property that you can remember.
 - none
 - inherit
 - block
 - inline
 - inline-block
* What's the difference between inline and inline-block?
 - The former does not respect margin and padding (in accordance with non-block level elements). The latter respects them but does not use a new line like typical block level elements.
* What's the difference between a relative, fixed, absolute and statically positioned element?
 - Statically positioned elements are the default element behavior. Absolutely positioned elements are positioned in relation to a non-statically positioned parent element (this could be either the root element or a more deeply embedded element) based on distance from the 4 sides of the parent element (top,right,left and bottom). Relatively positioned elements are positioned in basically the same way for just their immediate parent. Fixed positioning is oriented based on the viewport of the browser. All non-statically positioned elements typically ignore the padding and margin applied to them.
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
 - Priority is typically referred to in the form of specificity represented as (0,0,0,0). Selectors used in each style rule determines the specificity. Mathematically, the formula is as follows:
   Element selector - (0,0,0,1)
   Class selector - (0,0,1,0)
   Id selector - (0,1,0,0)
   Inline style or important! attribute - (1,0,0,0)
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
 - Foundation and Bootstrap. Most complaints with Foundation and Bootstrap revolve around size. As such, I would simply remove styles that I don't use. (This is offered by both Foundation and Bootstrap in the form of select compilation of css modules). It doesn't completely solve the issue though, so I would also prefer to simply have a grid system and compose the rest of the framework myself for further improvement.
* Have you played around with the new CSS Flexbox or Grid specs?
 - No
* How is responsive design different from adaptive design?
 - Responsive design is the idea of creating a fluid layout that responds to the dimensions of the users viewport appropriately (typically this means transforming between devices) while adaptive design offers different layouts to different devices.
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
 - Yes, retina graphics means dealing with an increased pixel density viewport. This means that graphics that were sharp could become fuzzy and positioning of elements could be unpredictably off. Positioning of elements can be dealt with by using non-pixel based size units such as em, rem or percentage based sizings (which you should really be doing anyway). Images are a bit tougher since higher definition images also mean higher bandwidth overhead. Currently there are CSS media queries like (min-device-pixel-ratio: 2) to target contentious images as well as browser document properties you can monitor via Javascript. To combat the side of images, you can try using webp format and provide a lower quality fallback.
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
 - For animations (which I assume is what you would use translate or change absolute positioning for), CSS animation are not particularly suited in terms of performance. Size transformations and opacity changes work well and those modifications should be defaulted to CSS use, however translate (or potentially translate3d) is more suited for moviing around elements since it allows GPU acceleration not possible with translation via CSS.

#### JS Questions:

* Explain event delegation
* Explain how `this` works in JavaScript
* Explain how prototypal inheritance works
* What do you think of AMD vs CommonJS?
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  * What needs to be changed to properly make it an IIFE?
* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  * How would you go about checking for any of these states?
* What is a closure, and how/why would you use one?
* What's a typical use case for anonymous functions?
* How do you organize your code? (module pattern, classical inheritance?)
* What's the difference between host objects and native objects?
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
* What's the difference between `.call` and `.apply`?
* Explain `Function.prototype.bind`.
* When would you use `document.write()`?
* What's the difference between feature detection, feature inference, and using the UA string?
* Explain AJAX in as much detail as possible.
* Explain how JSONP works (and how it's not really AJAX).
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
* Explain "hoisting".
* Describe event bubbling.
* What's the difference between an "attribute" and a "property"?
* Why is extending built-in JavaScript objects not a good idea?
* Difference between document load event and document ready event?
* What is the difference between `==` and `===`?
* Explain the same-origin policy with regards to JavaScript.
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
* What is `"use strict";`? what are the advantages and disadvantages to using it?
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
* Explain what a single page app is and how to make one SEO-friendly.
* What is the extent of your experience with Promises and/or their polyfills?
* What are the pros and cons of using Promises instead of callbacks?
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
* What tools and techniques do you use debugging JavaScript code?
* What language constructions do you use for iterating over object properties and array items?
* Explain the difference between mutable and immutable objects.
  * What is an example of an immutable object in JavaScript?
  * What are the pros and cons of immutability?
  * How can you achieve immutability in your own code?
* Explain the difference between synchronous and asynchronous functions.
* What is event loop?
  * What is the difference between call stack and task queue?

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
* What tools would you use to test your code's functionality?
* What is the difference between a unit test and a functional/integration test?
* What is the purpose of a code style linting tool?

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
* What are some ways you may improve your website's scrolling performance?
* Explain the difference between layout, painting and compositing.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  * Do Not Track
  * Cache-Control
  * Transfer-Encoding
  * ETag
  * X-Frame-Options
* What are HTTP actions? List all HTTP actions that you know, and explain them.

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?
