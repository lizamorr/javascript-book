# JavaScript & JQuery
## Interactive front-end web development by Jon Duckett

### Chapter 1 / The ABC of Programming:
- A script is a series of instructions that the computer can follow in order to achieve a goal.
  - Each time a script tuns, it might only use a subset of all the instructions.  
  - To approach writing a script, break down your goal into a series of tasks and then work out each step needed to complete a task (flowchart).
  - To write a script, it is best to keep JavaScript code it its own file (.js).
  - The HTML `<script>` element is used in HTML pages to tell the browser to load the JavaScript file path
  - If you view the source code of the page in the browser, the JavaScript will not have changed the HTML, because the script works with the model of the web page that the browser has created.
- Computers create models of the world using data.
  - Objects can have: properties that tell us about the object; methods that perform tasks using the properties of that object; events which are triggered when a user interacts with the computer.
  - Web browsers use HTML markup to create a model of the web page. Each element creates it own node (type of object).
  - To make web pages interactive, you write code that uses the browser's model of the web page.
  
### Chapter 2 / Basic Javascript Instructions:
- A script is made up of a series of statements.
- Scripts contain very precise instructions.
- Variables are used to temporarily store pieces of information used in the script.
- Arrays are special types of variables that store more than one piece of related information.
- JavaScript distinguishes between numbers, strings, and Boolean values.
- Expressions evaluate into a single value.
- Expressions rely on operators to calculate a value.

### Chapter 3 / Functions, Methods & Objects:
- Functions consist of a series of statements that have been grouped together because they perform a specific task.
- Methods are the same as functions, except methods are created inside (and are part of) an object.
- Parameters are used when the function is declared.
- Arguments are used when calling a function.
- Use anonymous functions and IIFES (immediately invoked function expressions) when code only needs to be run once.
- Local or function-level variables are created in side a function and can only be used in that function.
- Global variables are created outside a function and can be used anywhere within the script. They are stored in memory for as long as the web page is loaded into the web broswer.
- An object is a series of variables and functions that represent something from the world around you.
  - Variables are known as properties of the object
  - Functions are known as the methods of the object
- If you want to access items via property name or key, use an object (must be unique); if the order of the items is important, use an array.
- Objects created with literal notation are good when are you are storing/transmitting data between applications and for global or configuration objects that set up information for the page.
- Objects created with constructors are good when you have lots of objects used with similar functionality within a page and when a complex object might not be used in code.
- Arrays are objects but the key for each value is its index number.
- Three groups of built-in objects:
  - Browser Object Model: creates a model of the browser tab or window; the topmost object is the window object
  - Document Object Model (DOM): creates a model of the current web page; the topmost object is the document object, which represents the page as whole.
  - Global JavaScript Objects: group of individual objects that relate to different parts of the JavaScript language (String, Number, Boolean, Date, Math, Regex)
- 6 Data Types:
  - Simple/Primitive: String, Number, Boolean, Undefined, Null
  - Complex: Object (arrays, functions)
  
### Chapter 4 / Decisions & Loops:
- Comparison operators
  - `==` is equal to vs `===` is strict equal to; strict compares two values to check that both the data type and value are the same.
  - `===, !==, ==, !=, <, >, <=, >=` are used to ompare two operands
- Logical operators aloow you to combine more than one set of comparison operators.
- Conditional statements allow your code to make decisions about what to do next.
- `if...else` statements allow you to run one set of code if a condition is true, and another if it is false.
- `switch` statements allow you to compare a value against possible outcomes and also provides a default option if none match.
- Data types can be coerced from one type to another.
- All values evaluate to either truthy or falsy.
- Therea re three types of loop: `for`, `while`, and `do...while`; each represents a set of statements.

### Chapter 5 / Document Object Model: 
- The browser represents the page using a DOM tree.
- DOM trees have four types of nodes: document nodes, element nodes, attribute nodes, and text nodes.
- You can select element nodes by their `id` or `class` attributes, by tag name, or using CSS selector syntax.
- Whenever a DOM query can return more than one node, it will always return a `NodeList`.
- From an element node, you can contain multiple text nodes and child elements that are siblings of each other.
- When you select a text node, you can retrieve or amend the content of it using the `nodeValue` property.
- Use `textContent` over `innerText` to collect or update just the text that is in the containing element and its children.
- The `innerHTML` property can access and amend the contents of an element, including any child elements; it is unsafe to use compared to DOM manipulation.
  - Cross-Site Scripting Attacks or XXS: gives attacker access to the DOM, form data, cookies, session tokens, access accounts
  - Validate input going to the server:
    1. Browser requests pages from and sends form data to web server.
    2. Web server collects information from the browser and passes it to a database.
    3. Database stores information created by website admins and users.
    4. As your data leaves the database, all potentially dangerous characters should be escaped.
    5. Make sure that you are only inserting content generated by users into certain parts of the template files.
    6. Do not create DOM fragments containing HTML from untrusted sources. It should only be added as text once it has been escaped.
- DOM manipulation can be safer than `innerHTML`, but requires more code and can be slower; allows you to create element `createElement()` and text nodes `createTextNode()`, and then attach them `appendChild()` to the DOM tree or remove them (store element, store parent, remove the element from containing element).
- In older browsers, implementation of the DOM is inconsistent (why jQuery is popular).
- Browsers offer tools for viewing the DOM tree.

### Chapter 6 / Events:
- Events are teh browser's way of indicating when something has happened (such as when a page has finished loading or a button has been clicked).
- Binding is the process of stating which event you are waiting to happen, and which element you are waiting for that event to happen upon.
- Three ways to bind an event to an element: HTML event handlers < Traditional DOM event handlers < DOM level 2 event listeners.
  - HTML event handlers (do not use) do not separate the HTML from JS (`onblur="checkUsername()"`)
  - Event handlers: `element.onevent = functionName;`
  - Event listeners: `element.addEventListener('event', functionName [, Boolean])`; the () are removed from the function because they would indicate that the function should run as the page loads (rather than when the event fires); use `attachEvent` for IE8 and older.
- When an event occurs on an element, it can trigger a JavaScript function; when this function then changes the web page in some way, it feels interactive because it has responded to the user.
- You can use event delegation to monitor for events that happen on all of the children of an element. 
- The most commonly used events are W3C DOM events, although there are others in the HTML5 specification as well as browser-specific events.

### Chapter 7 / JQuery:
- jQuery is a JavaScript file you include in your pages.
- Once included, it makes it faster and easier to write cross-browser JavaScript, based on two steps:
  - Using CSS-style selectors to collect one or more nodes from the DOM tree.
  - Using jQuery's built in methods to work with the elements in that selection.
- jQuery's CSS-style selector syntax makes it easier to select elements to work with. It also has methods that make it easier to traverse the DOM.
- jQuery makes it easier to handle events because the event methods work across all browsers.
- jQuery offers methods that make it quick and simple to achieve a range of tasks that JavaScript programmers commonly need to perform.
- Put scripts before the closing `</body>` tag so it is not blocking other things from downloading and the DOM has already loaded by the time the script is executed.

### Chapter 8 / Ajax & JSON:
- Ajax refers to a group of technologies (Asynchronous JavaScript And XML) that allow you to update just one part of the page (rather than reload a whole page).
- To create an Ajax request, browsers use the `XMLHttpRequest` object.
- You can incorporate HTML, XML, or JSON data into your pages. 
- To load JSON from a different domain, you can use JSONP but only if the code is from a trusted source.
- jQuery has methods that make it easier to use Ajax.
- `.load()` is the simplest way to load HTML into your pages and allows you to update just a part of the page.
- `.ajax()` is more powerful and more comples.
- It is important to consider how the site will work if the user does not have JavaScript enabled, or if the page is not able to access the data from server.

### Chapter 9 / APIS:
- APIs are used in browsers, scripts, and by websites that share functionality with other programs or sites.
- APIs let you write code that will make a request, asking another program or script to do something.
- APIs also specifiy the format in which the response will be given.
- To use an API on your website, you will need to inclide a script in the relevant web pages.
- An API's documentation will usually feature tables of objects, methods, and properties. 
- Web storage (HTML5 storage) lets you store data in the browser:
  - `localStorage` data is stored when you close a window/tab and all open windows/tabs can access the data
  - `sessionStorage` is more suited to information that changes frequently and/or is personal and should not be viewed by other users of the device
- Providing you know how to create an object and call its methods, access it properties, and respond to its events, you should be able to learn any JavaScript API.

### Chapter 10 / Error Handling & Debugging:
- Debugging is the process of finding errors; it involves a process of deduction.
- The console helps narrow down the area in which the error is located, so you can try to find the exact error. 
- JavaScript has 7 different types of errors; each creates its own error object, which can tell you its line number and gives a description of the error.
- If you know that you many get an error, you can handle it gracefully using the `try, catch, finally` statements. 

### Chapter 11 / Content Panels:
- Content panels offer ways to show more content within a limited area. 
- Popular types of content panels include accordions, tabs, photo viewers, modal windows, and sliders. 
- As with all website code, it is advisable to separate content (HTML), presentation (CSS), and behavior (JavaScript) into different files. 
- You can create objects to represent the functionality you want.
- You can turn functions into jQuery plugins that all you to re-use code and share it with others. 
- Immediately invoked function expressions (IIFEs) are used to contain scope and prevent naming collisions. 

### Chapter 12 / Filtering, Searching & Sorting:
- Arrays are commonly used to store a set of objects.
- Arrays have helpful methods that all you to add, remove, filter and sort the items they contain.
- Filtering lets you remove items and only show a subset of them based on selected criteria. 
- Filters often rely on custom functions to check whether items match your criteria.
- Search lets you filter based upon data the user enters. 
- Sorting allows you to reorder the items in an array.
- If you want to control the order in which items are sorted, you can use a compare function.
- To support older browsers, you can use a shim script. 

### Chapter 13 / Form Enhancement & Validation:
- Form enhancements make your form easier to use. 
- Validation lets you give users feedback before the form validation.
- HTML5 inputs and their validation messages look different in various browsers. 
- You can use JavaScript to offer the same functionality as the new HTML5 elements in all browsers. 
- Libraries like jQuery UI help create forms that look the same across different browsers. 
- Regular expressions help you find patterns of characters in a string.
