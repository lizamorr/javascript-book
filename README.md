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

### Chapter 3 / Functions, Methods & Objects
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
  
### Chapter 4 / Decisions & Loops
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

### Chapter 5 / Document Object Model 
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
  
