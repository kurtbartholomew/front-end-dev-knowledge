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
 - SEO: TBD
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
 - sublime text with a number of plugins, webstorm, or vim
* Which version control systems are you familiar with?
 - git and svn
* Can you describe your workflow when you create a web page?
 - Sketch out general layout (Sketch or Balsamiq)
 - Decide on purpose of page
 - Decide on general features like navbar, sidebars, and footer.
 - Decide if you need a separate mobile page or if responsive works.
 - Create general containers (navbar, sidebars, footer, main containers)
 - Choose a serif and san-serif font to use throughout the page
 - Position containers
 - Put in content placeholders
 - Experiment with color combinations and fonts
 - Check with users regularly to get visual and behavioral feedback
 - Structure and modularize CSS to prevent a giant mess later
 - Finalize design with users
* If you have 5 different stylesheets, how would you best integrate them into the site?
 - Concatenate all the stylesheets and minify the result. Serve that
 - Move the common rules to the same stylesheet and reduce the side of the others
 - Conditionally load the necessary stylesheets with inline js if no other choices
* Can you describe the difference between progressive enhancement and graceful degradation?
* How would you optimize a website's assets/resources?
 - Sprite Maps
 - JS/CSS Concatenation and Minification
 - Image Zipping
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
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
* What does CORS stand for and what issue does it address?

#### HTML Questions:

* What does a `doctype` do?
* What's the difference between standards mode and quirks mode?
* What's the difference between HTML and XHTML?
* Are there any problems with serving pages as `application/xhtml+xml`?
* How do you serve a page with content in multiple languages?
* What kind of things must you be wary of when design or developing for multilingual sites?
* What are `data-` attributes good for?
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
* What is progressive rendering?
* Have you used different HTML templating languages before?

#### CSS Questions:

* What is the difference between classes and ID's in CSS?
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
* Describe Floats and how they work.
* Describe z-index and how stacking context is formed.
* Describe BFC(Block Formatting Context) and how it works.
* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites, and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* How would you approach fixing browser-specific styling issues?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Are you familiar with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Describe pseudo-elements and discuss what they are used for. 
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?

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
