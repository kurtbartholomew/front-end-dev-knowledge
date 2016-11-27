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
 - How fourier transforms work
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
   - Your css can be the same physically (into partials) as it is logically (one for nav, one for footer, etc.)
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
 - Event delegation is associated with event listeners. The basic idea is that instead of placing an event listener on a potentially ridiculous amount of child elements, one is placed on a parent element. As events bubble up the DOM, this event listener qualifies the sources of the events with some sort of conditional (typically an element selector). If the element qualifies positively, the event is handled with the event listener function.
* Explain how `this` works in JavaScript
 - this can mean several different things depending on the manner in which code is invoked but in most cases, it typically means the object and associated scope in which code is currently being executed (execution context). An example would be if a global function is being invoked in a browser, window (or equivalent representation of the root document) would be the reference held in "this".
* Explain how prototypal inheritance works
 - On almost all constructs in Javascript exists a reference to a collection of basic methods and variables. This is called the prototype of an object. All non-primitive objects (everything that is not a number) inherit from the Object prototype. From that prototype, other object types such as arrays inherit from the prototypes for their more complex data structures.
* What do you think of AMD vs CommonJS? CommonJS is a bit easier to understand and use in terms of modularity using the require and exports constructs but it seems to have its place more on the server side with node. AMD and its define construct seem to fit better on the client side but considering the popularity of libraries like browserify (using CommonJS syntax) vs that of Require.js (using more AMD syntax), CommonJS-like constructs seem more likely. This can be seen in the CommonJS-like form of ES2015's import function.
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
  - You can't immediately invoke a function declaration.
  * What needs to be changed to properly make it an IIFE?
  - Put the declaration inside parentheses "(function foo(){})();". That would evaluate correctly.
* What's the difference between a variable that is: `null`, `undefined` or undeclared?
  - "null" is a falsy value representing the lack of an initialized value purposefully set by the coder.
  - "undefined" is a falsy value representing the lack of an initialized value for any object, declared or not
  - "undeclared", while existing conceptually, is not implemented. When a variable is declared but not initialized and attempts to be referenced, it will deliver an "undefined" value
  * How would you go about checking for any of these states?
    - Existence of variables can be checked by more verbose (variable1 === undefined || variable === null) or a simpler but more error prone if(variable1)
* What is a closure, and how/why would you use one?
 - A closure is an execution context that possibly contains functions and/or variables that are accessible to code further down the stack. In other words, a persistent local variable scope that can be accessed by subsequently created scopes.
 - Closures are useful to allow the use of caching or counting mechanisms.
* What's a typical use case for anonymous functions?
 - Anonymous functions are great in a couple different scenarios:
  1. a function returns another function, the returned function would make no sense to be declared
  2. a function is used in a functional context, ie map or reduce
  3. a function is passed along as an object through several contexts
* How do you organize your code? (module pattern, classical inheritance?)
 - I find using closured modules to decorate an overall object with namespaces is most useful. I try to use inheritance sparingly since it is very easy to create confusing hierarchies.
* What's the difference between host objects and native objects?
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
 - The former simply executes the function. The latter creates a new object, sets its prototype to Person, sets this to the object's execution context, executes its constructor and returns the object.
* What's the difference between `.call` and `.apply`?
 - Call executes a function in the context of the object passed as the first argument and uses the remaining arguments as is.
 - Apply executes a function in the context of the object passed as the first argument and expects an array as the second argument. This array becomes the arguments array for the newly executing function
* Explain `Function.prototype.bind`.
 - Bind returns a function that will always execute in the context of the object passed as the first argument
* When would you use `document.write()`?
 - Only if I ever wanted to rewrite the contents of a page as a whole, which is almost never. Using it is typically a poor choice.
* What's the difference between feature detection, feature inference, and using the UA string?
 - Feature detection is directly checking for the existence and possible execution of features themselves
 - Feature inference is checking variables or other status constructs that allow you to infer what the availability of an API is
 - Using the UA string means attempting to map User Agent type and version to an available set of features (this is usually a bad idea since UA strings can be spoofed pretty easily)
* Explain AJAX in as much detail as possible.
 - (Asynchronous Javascript and XML) is an http request usually of type GET or POST sent to a specified url. The use of this kind of request does not require the loading of a page. An average use of this kind of request is to hit an endpoint on a server and return data to be used to update a portion of the page via Javascript. As with the any http request, it can return any range of errors and error codes. The request fires events based on the status of the request such as onreadystatechange. When these events are caught, the response payload (either error or data) is handled as per the function assigned to it.
* Explain how JSONP works (and how it's not really AJAX).
 - JSONP (JSON with Padding) is the process of adding a script tag to the head of the document whose src attribute targets an (usually cross domain) endpoint. The URI used must include a special query string parameter recognized by the server whose endpoint it is reaching. The parameter itself will have the name of a declared function as its assigned value (Example: http://crossdomain.org?callback=fancyCallbackFunction). Data in JSON format will be returned and handled by the callback function. This differs from AJAX because it uses a request directly from an element as opposed to the usage of the XMLHttpRequest construct that AJAX uses.
* Have you ever used JavaScript templating?
 - Yes
  * If so, what libraries have you used?
   - Underscore, Mustache/Handlebars and Jade
* Explain "hoisting".
 - When a variable or object in Javascript is declared, the declaration of the object (but not the assignment) is raised to the top of the current scope, allowing for reference throughout the scope
* Describe event bubbling.
 - When an event occurs in the DOM, that event does happen once. It travels up the DOM tree, firing the event on every parent until it fires on the root document. This is what makes event delegation possible.
* What's the difference between an "attribute" and a "property"?
 - Under the assumption that this means HTML attribute and DOM property, an HTML attribute is a defined part of the HTML specification that gives definition to how HTML will be displayed while a property is the codified representation of that definition within the DOM. (Example: "class" is an attribute of an element and DOMNode.className is a property)
* Why is extending built-in JavaScript objects not a good idea?
 - This leads to unexpected behavior (and probably undocumented) for other developers that would depend on an otherwise stable API. Besides being error-prone, this represents a cognitive overhead that developers will constantly have to deal with.
* Difference between document load event and document ready event?
 - document.ready is a jQuery construct while document.onload is a standard event
 - document.ready fires after the DOM is fully parsed and loaded while document.onload fires only after all content (DOM and all pictures,fonts,etc) is loaded
* What is the difference between `==` and `===`?
 - "==" is the equals operator and "===" is the strict equals operator
 - "==" compares values and uses type coercion to compare different types
 - "===" compares values and does not use type coercion (comparison between different types will fail)
* Explain the same-origin policy with regards to JavaScript.
 - Requests made from a web page must be made to the same domain as the page the user is currently on. (Example: http://google.com cannot make requests to http://pencils.com) This is to prevent cross site scripting attacks that use credentials in cookies or other storage currently stored on the browser to illegitimately access the users still logged in accounts. (An example would be you visit your banking site and access your account. Shortly afterwards, you go to a site that has a hidden request in a link you click that sends an API request to your banking site that would send money to China. Since your credentials are still valid, the request goes through)
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]

var duplicate = function(arrayToBeDuplicated) {
    for(var i = 0; i < arrayToBeDuplicated.length; i++) {
        arrayToBeDuplicated[arrayToBeDuplicated.length] = arrayToBeDuplicated[i];
    }
    return arrayToBeDuplicated;
};
```
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
 - It is called ternary because it handles 3 arguments (ternary in latin means 3 at once). A ternary operator is a shorthand conditional, doing a boolean check on the first argument and assigning either the second or third argument based on the conditional.
* What is `"use strict";`? what are the advantages and disadvantages to using it?
 - Strict mode is useful when attempting to prevent some of the more quirky aspects of Javascript. Examples which it prevents include:
   - Using undeclared variables
   - Deleting objects and variables that are not properties
   - Duplicate parameter names
   - Non-standard formats for numbers and strings (octals and literal escape characters)
   - Using keywords of the language as variable names (eval and arguments)
 - Disadvantages for not using `use strict` usually means a loss of flexibility.
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
```
  for(var i = 0; i <= 100; i++) {
      if(i % 3 && i % 5) { 
        console.log("fizzbuzz"); 
      } else if(i % 3) { 
        console.log("fizz");
      } else if(i % 5) {
        console.log("buzz");
      }
  }
```
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
 - Things in global scope can easily be modified and accessed, allowing for manipulation of important values. In addition, this opens up the program to having accidental collisions when using common variable names, which will lead to unexpected behavior.
* Why would you use something like the `load` event? Does this event have disadvantages? 
 - The on load event is used for the purpose of knowing when a page and all its content is loaded. Unfortunately, this means that all the content (even high resolution pictures) will be downloaded before this is fired, which can vastly increase the amount of perceived latency.
Do you know any alternatives, and why would you use those?
 - Using an event listener to listen for the event "DOMContentLoaded" and waiting until that event is fired to start additional work on the page is a good idea. I prefer this method because it allows the usage of scripts after the DOM has been fully loaded but does not depend on other exterior assets having been loaded.
* Explain what a single page app is and how to make one SEO-friendly.
 - A single page application is an application with a root path that simulates the navigating to separate pages without reloading. These pages are populated and rendered by AJAX requests in the background that retrieve necessary data. To improve the SEO of an SPA, you can potentially render the pages on the server side and only change small portions of the actual pages with data from async requests.
* What is the extent of your experience with Promises and/or their polyfills?
 - I have a good knowledge of Promises and their polyfills. I've used several versions of them in production like bluebird and q.
* What are the pros and cons of using Promises instead of callbacks?
 - Promises can be a bit tricky to understand and the implementation of a polyfill can be complicated but they go a long way to improve asynchronous requests. Firstly, a series of promises changes what some people call the pyramid of death or callback hell to an easily readable process. Second, error handling is vastly improved as the process short-circuits to the first catch instead of having to place error handling in every single callback. Third, the code becomes more declarative in nature and is much easier to understand.
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
 - Languages that transpile to Javascript can be much easier and more terse to write in. It can allow people to be more productive and efficient with less written code. This, however, has the trade-off of having transpiled code that is difficult to read and debug through. Much like minified code, it can be difficult to read and debug because there is not a one to one relationship with the code you actually wrote. Not only that, there can be compatibility issues with older browsers unless you are careful.
* What tools and techniques do you use debugging JavaScript code?
 - Depends on whether it is client side or server side javascript. On client side, dev tools in most major browsers is more than enough. For server side, node inspector is very useful for server debug. Postman or curl is great for testing endpoints. Unit tests are a wonderful way to debug isolated portions of code.
* What language constructions do you use for iterating over object properties and array items?
 - Objects (for - in)
 - Arrays (for, forEach, map, reduce)
 - If libraries and polyfills are included, there are a ridiculous amount of functional constructs available for objects and arrays in underscore and lodash.
* Explain the difference between mutable and immutable objects.
 - A mutable object is one whose properties can be changed while an immutable one cannot.
  * What is an example of an immutable object in JavaScript?
   - An object whose properties are closured and only accessible via declared get functions is would be a good example of immutable. Another option would be to simply define properties with `writable: false`.
  * What are the pros and cons of immutability?
   - You don't have to worry about holding the correct state in an immutable object, but this does mean that you will incur larger overhead creating more copies of data
  * How can you achieve immutability in your own code?
   - As previously mentioned, created properly closured objects allows them access to their own properties without exposing them to changes.
* Explain the difference between synchronous and asynchronous functions.
 - A synchronous operation waits until all instructions are finished running before proceeding while an asynchronous function's code proceeds on, only firing off associated code one a condition has been met (this usually means a response from a remote source)
* What is event loop?
 - A synchronous process in which the runtime waits for messages to be put in a queue to execute functions or other statements.
  * What is the difference between call stack and task queue?
   - The task or message queue keeps track of statements to be executed by the runtime. When a message is retrieved from the queue and run, the associated statement is executed. This creates a stack frame for the associated function call (and its subsequent function calls). Once the statement is done executing (and thus the stack frame is gone), the next item is pulled from the task queue and run.

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
 - Testing typically takes a lot longer to write than the code itself but if written correctly, guards against edge cases and regression
* What tools would you use to test your code's functionality?
 - A base suite of tools like Jasmine or Mocha for testing, additional libraries for stubs and mocks as well as a task runner like grunt or gulp to automate.
* What is the difference between a unit test and a functional/integration test?
 - A unit test tests a small isolated piece of functionality while a functional/integration test typically incudes an entire process like saving a user.
* What is the purpose of a code style linting tool?
 - To assist developers in adhering to a common style of implementation so the entire code base is easily readable to anyone on the team.

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
 - Memory/latency profilers and flamegraphs to keep track of where excessive overhead and bottlenecks are.
* What are some ways you may improve your website's scrolling performance?
 - Attempting to load things asynchronously instead of all at once is important. Reasonable pagination of content allows below the fold content loading to be heavily reduced. Another option is deferring web fonts to load until after the other content has loaded. It is important to give the user content and enhance it instead of giving it all at once if the latter will cause an increased perception of latency.
* Explain the difference between layout, painting and compositing.
 - Layout, painting, and compositing refers to the stages of rendering the HTML in a browser. The rendering engine of a browser first parses and creates a render tree. From there, it uses that information to create a second tree for layout which decides the positioning of elements (this is implemented differently between browsers). From there, the elements are painted on the screen. Lastly, the elements are composited and the layout flow is applied.

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
 - Traditionally, browsers have a limit to the amount of assets they can serve from a single domain. Historically, it has been a single asset at a time, though now it has been increased in later versions of browsers.
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
 - Text in the address bar is parsed.
 - The HTTP Strict Transport Security list is checked to see if the website requires the request to be in HTTPS. The request is changed to HTTPS if only that is accepted.
 - Non-ASCII unicode characters are transformed are encoded into ASCII
 - The browser does a DNS lookup (that is, transforming the host name into an ip address) using the following resources in this order:
     - Local browser cache
     - OS hosts file
     - Local router or ISP's configured top level DNS
 - An Address Resolution Protocol request is broadcast locally to retrieve the IP and MAC address of the default gateway or DNS server
 - Once the reply is retrieved (either from the cache or routing tables), a UDP request is sent to the DNS server to find the entry for the hostname in the address bar
 - If the DNS contacted does not contain the hostname, requests are made up to the top level name server if needed to resolve the hostname to an ip
 - Once the IP is resolved, a UDP request is made requesting a TCP socket stream
 - A packet is created with information like:
   - Destination port
   - Source port
   - Destination IP
   - Source IP
   - Source MAC
   - Source Router MAC
 - Once the packet reaches the destination and uses an initial sequence number with the SYN bit set to true
 - The server sets its own initial sequence number and responds with both SYN and ACK bits set
 - The client begins sending packets with the ACK bit set
 - The server sends back ACK responses
 - Once the interaction is finished, either the server or client send a packet with FIN bit set.
 - The other sends an ACK response packet and then a FIN packet
 - Finally, the original sender of the first FIN packet sends an ACK packet
 - If HTTPS has been used, a TLS handshake must occur before the SYN ACK FIN process:
   - Client sends a message to server with its TLS version, ciphers, and compression methods.
   - Server responds with TLS version, selected cipher/compression and a security certificate
   - Client verifies the certificate against their list of authorities and sends a random alphanumeric string encoded with the public key in the certificate
   - Server decryptes the message with its private key and generates a master key
   - Client generates a master key and sends a hash encrypted with the master key
   - Server creates its own hash and decrypts the client's hash. If they match, it sends a message saying they can communicate.
   - The SYN ACK FIN process from above is started and all data is encrypted using the master key that both sides have
 - Requests received from the server will typically have status headers and if there was no error in the response, an HTML payload.
 - Once the HTML is received, the browser tokenizes/parses the HTML and creates a parse tree.
 - After the HTML and CSS are parsed, a render or frame tree is created which applies styles to the nodes of the tree. Layers and positioning are computed.
 - Finally, the contents of the render tree are composited and painted to the screen.
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
 - Long-Polling is starting a request and keeping it open until a response is received. Websockets instead, establish a persistent TCP connection allowing users to participate in a specific "conversation" of events. Server-Sent events (also called push notifications) are events sent via content stream over a persistent TCP connection and is currently only available via the EventSource browser API.
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
   - Expires sets when a request in the cache becomes stale. Date is the header with which we decide a response's age. Age is the time since the response was created or re-validated by the server. If-Modified headers forces the browser to ignore the cached response if the date exceeds the if-modified header.
  * Do Not Track
   - A request header set to indicate the client does not want persistent tracking cookies sent to their browser
  * Cache-Control
   - More recent response header controlling caching behavior. It revolves around a couple settings:
     - no-store : prevent caching completely
     - private or public : prevent or allow use of intermediate caches
     - max-age : used to calculate expiration
  * Transfer-Encoding
   - A response header allowing for the response to be delivered to the client in different forms. It mostly applies to if and how the response should be compressed.
  * ETag
   - Entity Tags are headers used in both responses and requests. They are related to caching. Servers send ETags in their responses and those etags are used to check if, since the last response, anything has changed with the page being requested. If an Etag in a request matches the Etag generated on the server, it may send a 304 unmodified status, which tells the browser to use the cached response instead.
  * X-Frame-Options
   - A response header allowing, selectively allowing, or preventing the embedding of your content in another page via frames.
* What are HTTP actions? List all HTTP actions that you know, and explain them.
 - GET : Retrieve content from a url endpoint
 - POST : Add or update data via a url endpoint
 - DELETE : Remove data via a url endpoint
 - UPDATE : Explicity update data via a url endpoint (not an basic action)
 - PUT : Explicity replace data via a url endpoint (not a basic action)
 - PATCH : Explicity merge or update data via a url endpoint (not a basic action)
 - OPTIONS : A default that can represent any non-standard action

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```
Answer
```javascript
'1020'
```

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```
Answer
```javascript
var add = function(first, second) {
  var firstNum = first;
  if(second === undefined) {
    return function(secondNum) {
      return firstNum + secondNum;
    }
  }
  return first + second;
};
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
Answer:
```javascript
"goh angasal a m'i"
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```
Answer:
```javascript
"bar"
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
Answer
First alert will display "Hello World".
There will be no second alert since bar is in a closured scope that is not available during the second alert call.

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
Answer
2

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```
Answer
foo.x is undefined

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```
Answer
one
three
two

#### Fun Questions:

* What's a cool project that you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your coffee?
