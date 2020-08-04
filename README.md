# JAVASCRIPT BASICS

## Javascript Functions
1. Function Declaration
   ```javascript
    function fn_name(args) {
      return args;
    }
   ```
2. Function assigned to Variable
   ```javascript
    var var_name = function fn_name(args) {
      return args;
    }
   ```
   OR

   ```javascript
    var var_name = function (args) {
      return args;
    }
   ```
3. Callback Functions
   A JavaScript Callback Function is a function that is passed as a parameter to another JavaScript function.
   ```javascript
    function fn_name(args) {
      return args;
    }

    setTimeout(fn_name, 4000);
   ```
4. ES6: Arrow Functions
   ```javascript
    var_name = () => {
       return "Something";
    }
   ```

   If the function has only one statement, and the statement returns a value, you can remove the brackets and the return keyword
   ```javascript
    var_name = () => "Something";
   ```

   Pass parameter in parenthesis
   ```javascript
    var_name = (param1, param2) => "Something" + param1 + " " + param2;
   ```
   
   Skip parenthesis if only one parameter
   ```javascript
    var_name = param => "Something" + param;
   ```
   

## Document Object Model (DOM)
1. [What is DOM?](https://www.w3schools.com/js/js_htmldom.asp)
   The items on HTML page
2. Modify DOM elements
   Obtain ID of the element using `document.getElementById("name-of-id-as-in-html-file")`.
   ```javascript
    var target1 = document.getElementById("target-1");
    target1.innerHTML = "target-1 is the id of some element in html and we changed the text";
    target1.style.color = "red";
    var h3 = document.createElement("h3");
    h3.innerHTML = "<p>Create new h3 element</p>";
    document.body.append(h3);
   ```

## [JQuery](https://code.jquery.com/)
1. Import JQuery to use it: download latest version's minified script.
   OR copy from below and paste in html file
   ```javascript
    <script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
   ```
2. JQuery for DOM Modification
   ```javascript
    var target1 = $("##target-1");
    target1.text("Target 1 has been found!");
    target1.css({"color": "red", "backgroundColor": "orange"});
   ```
3. AJAX: Asynchronous JavaScript And XML
   AJAX stands for Asynchronous JavaScript and XML. AJAX is a new technique for creating better, faster, and more interactive web applications with the help of XML, HTML, CSS, and Java Script. Ajax uses XHTML for content, CSS for presentation, along with Document Object Model and JavaScript for dynamic content display.

## Iterate Array
   Common Array:
   ```javascript
    const array = ['some', 'words', 'in', 'the', 'array'];
   ```

1. forEach
   ```javascript
    complete_string = '';

    array.forEach(function(array_element){
       complete_string = complete_string + " " + array_element;
    })
   ```
2. map(), filter(), reduce()

   `map()` returns an array result after applying the inner function on all the array elements.
   ```javascript
    var new_array = array.map((array_element) => array_element.length>2);
   ```
   then the `new_array = [true,true,false,true,true]`

   `filter()` will filter out and return the result according to the function applied.
   ```javascript
    var new_array = array.filter((array_element) => array_element.length>2);
   ```
   then the `new_array = [some,words,the,array]`

   `reduce()` method reduces the array to a single value.
   ```javascript
    var new_array = array.reduce((complete_string, array_element) => complete_string = complete_string+ " " + array_element);
   ```
   then the `new_array = some words in the array`

## Object oriented Javascript
1. object and properties. 
   ```javascript
    var var_name = {
        attr_name: "attr",
        fn_name: function() { return this.attr_name;}
    }
   ```
   NOTE: `this`
2. Access using var_name
   ```javascript
    console.log(var_name.fn_name())
   ```
3. Pre-ES6
   ```javascript
    var var_name = function(attr) {
        this.attr = attr;
        this.fn_name = function() { return this.attr}
    }
    var another_var = new var_name("some_attr");
   ```
4. Post-ES6
   ```javascript
    class class_name {
        constructor(attr) {
            this.attr = attr;
            fn_name() { return this.attr}
        }
    }
    var another_var = new var_name("some_attr");
   ```

## Promises
1. [What is it?](https://javascript.info/promise-basics)
2. Writing a promise:
   A function to find even Numbers
   ```javascript
    function isEven(x) {
        if (x!2 == 0) {
            return true;
        }
        else{
            return false;
        }
    }
   ```
   Promise Wrapper
   ```javascript
    function promiseEven(x){
        var promise = new Promise(
            function(resolve, reject) {
                isEven(x) ? resolve(x + " is Even.") : reject(Error(x + " is not Even"));
            }
        );
    }
   ```
   Handlers
   ```javascript
    function evenResolved(result) {
        log("Success: " + result);
    }

    function evenRejected(error) {
    log("Rejected: " + error.message);
    }
   ```
   Calling- 2 ways to call: 2nd one better for chaining
   ```javascript
    promiseEven(42).then(evenResolved, evenRejected);

    promiseEven(95)
        .then(evenResolved)
        .catch(evenRejected)
        .finally(console.log("finally is optional"));
   ```
   
   # ES6 Basics
   
   ## let vs var
   
   ## const and immutable
