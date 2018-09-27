#Javascript, jQuery and Ajax



### Hello, name

```html
<!DOCTYPE html>

<html>
    <head>

        <title>hello</title>
    </head>
    <body>
        <p id=sayhello></p>
        <script>

        let name = prompt("what is your name");
        if(name != null){
            document.getElementById("sayhello").innerHTML = "Hello, " + name;
        }
        else{
            alert("enter your name")
        }

        </script>
    </body>
</html>
```

-   `.innerHTML` : write inside the html page
-   `prompt()`
-   `alert()`



### Math with JS

```html
<script>
        let a = "Steven";
        let myAge = 23;
        let balance = 12341.343443;
        document.write("5 + 4 = ", 5 + 4, "<br>");
        document.write("<p>this is a paragraph</p>");
        document.write("Monthly Payment : ", (balance / 12).toFixed(2), "<br>")

        let randNum = 5;

        document.write("rand++ = ", randNum++, "<br>")
        document.write("++rand = ", ++randNum, "<br>")

        // Math.abs() / cell / floor / round / log / log10 / max / min / pow / sqrt
</script>
```

-   `.toFixed(2)`: round it to 2 decimal places
-   Math build-in functions: Math.abs() / cell / floor / round / log / log10 / max / min / pow / sqrt



### String

```html
<script>
        let randStr = "this" + "is" + "a" + "long string";
        document.write("String Length", randStr.length + "<br>");
        document.write("Index of \"long\"", randStr.indexOf("long"), "<br>");
        document.write(randStr.slice(7, 11), "<br>");
        document.write(randStr.replace("long ", "short"), "<br>");
        document.write("At Index 2 ", randStr.charAt(2), "<br>");
        document.write(randStr.toUpperCase(), "<br>");
        document.write(randStr.toLowerCase(), "<br>");
</script>
```

`.length()`

`.indexOf()`

`.slice()`

`.replace()`

`.charAt()`

`.toUpperCase()`

`.toLowerCase()`



### Double Equals vs. Triple Equals

When using triple equals `===` in JavaScript, we are testing for **strict** equality. This means both the **type** and the **value** we are comparing have to be the same.

```javascript
'hello world' === 'hello world'
// true (Both Strings, equal values)

true === true
// true (Both Booleans, equal values)

77 === '77'
// false (Number v. String)

77 == '77'
// true
```





### for <key> in <object>

```javascript
// key is iterating through the values in object

let obj = {name : "Steven", age : 34, Address : "harvard dunster"}
// an object is key-value pairs

for (let key in obj)   // object can be a funtion
{
	... 
    object[key]
}
```



### for <value> in <array>

```javascript
for (let value of array)  // of is functionally the same as in in python
{
	... 
}
```



### array

```javascript
<script>
    let a = ["js", "python", 234, 2]
    document.write(a[0], "<br>")
    a[3] = "overriding"
    document.write(a, "<br>")
</script>

//js
//js,python,234,overriding
```





### if, else

```javascript
if (x < y)
{
	... 
}
else if (x > y)
{
	... 
}
else 
{
	... 
}
```



### loop

```javascript
do
    {
		...
    }
while(true)
    
while (true)
	{
		... 
    }    
```



### function

```javascript
function inArray(array, value){
                for(i=0; i < array.length; i++){
                    if(array[i] === value){
                        return true;
                    }
                }
                return false;
            }

            a = [5, 5, 6, 6 ,2, 4]

            document.write("In Array : ", inArray(a, 4), "<br>")
```





### Object

Objects can also have **methods**.

Methods are **actions** that can be performed on objects.

Methods are stored in properties as **function definitions**.

| Property  | Property Value                                            |
| --------- | --------------------------------------------------------- |
| firstName | John                                                      |
| lastName  | Doe                                                       |
| age       | 50                                                        |
| eyeColor  | blue                                                      |
| fullName  | function() {return this.firstName + " " + this.lastName;} |

```javascript
// this is how we define an object in js
let quote = {
    name: "Netflix, Inc.",
    price: 391.43,
    symbol: "NFLX"
};
```







# jQuery

### Introduction

**jQuery** is a lightweight, "write less, do more", **JavaScript library.**

jQuery takes a lot of common tasks that require many lines of JavaScript code to accomplish, and wraps them into methods that you can call with a single line of code.

jQuery also simplifies a lot of the complicated things from JavaScript, like AJAX calls and DOM manipulation.

The jQuery library contains the following features:

-   HTML/DOM manipulation
-   CSS manipulation
-   HTML event methods
-   Effects and animations
-   AJAX
-   Utilities



###jQuery Syntax, jQuery Selector

The jQuery syntax is tailor-made for **selecting** HTML elements and performing some **action** on the element(s).

Basic syntax is: **$(selector).action()**

-   A $ sign to define/access jQuery
-   A (*selector*) to "query (or find)" HTML elements
-   A jQuery *action*() to be performed on the element(s)



**The element selector **`$("p")`

example

```javascript
$(document).ready(function(){
    $("button").click(function(){
        $("p").hide();
    });
});
```



**The #id Selector**`$("#test")`



**The .class Selector** `$(".test")`





### More examples~

**`$(document) == jQuery(document) == document.getElementById('quote')`**



```
function greet()
            {
                alert(`hello, ${document.getElementById("name").value}!`);
            }
```

${ }: **subsitute value**s,占位符

Quote: 必须使用``



**`document.getElementById("demo").onsubmit()`**

`documen`t: global variable of the file

`getelementbyid`: choosing the tag by id

`.onsubmit()`: the condition of that tag(chosen by id)





###What are Events?

All the different **visitor's actions** that a web page can respond to are called events.

An event represents the precise moment when something happens.

Examples:

-   moving a mouse over an element
-   selecting a radio button
-   clicking on an element

| Mouse Events | Keyboard Events | Form Events | Document/Window Events |
| ------------ | --------------- | ----------- | ---------------------- |
| click        | keypress        | submit      | load                   |
| dblclick     | keydown         | change      | resize                 |
| mouseenter   | keyup           | focus       | scroll                 |
| mouseleave   |                 | blur        | unload                 |

**Event Handlers**

```
click
mousedown
mouseup
mouseover
drag
keypress
load
unload
change
submit
focus
touchmove
...
```



To assign a click event to all paragraphs on a page, you can do this:`$("p").click();`



The next step is to define what should happen **when the event fires.** You must pass a function to the event:

```javascript
$("p").click(function(){

  // action goes here!!

});
```



`$(document).ready()`

The `$(document).ready()` method allows us to **execute** a function when the document is **fully loaded.** 



`focus()`

The ` focus()` method **attaches an event handler function to an HTML form field.**

The function is executed when the form field gets focus:

Example:

```javascript
$("input").focus(function(){

    $(this).css("background-color", "#cccccc");

});
```





###jQuery html() Method

```javascript
$("button").click(function(){
    $("p").html("Hello <b>world</b>!");
});
```



The `html()` method **sets or returns the content (innerHTML) of the selected elements.**

When this method is used to **return** content, it returns the content of the FIRST matched element.

​	(An intuitive sense: if there is no parameter of `.html()`, it will be used as a value-return method)

When this method is used to **set** content, it overwrites the content of **ALL** matched elements





### When submitting the form with js function

False: does not submit

True: submit





# JSON: JavaScript Object Notation

```json
{
    "name": "Netflix, Inc.",
    "price": 391.43,
    "symbol": "NFLX"
    "staff":
    	{
    		"ceo": "jharvard"
    		"cfo": "harvardj"
		}
}
```





# AJAX: Asynchronous Javascript And XML

**AJAX is not a programming language.**

**AJAX is a technique for accessing web servers from a web page.**

By sending data asynchronously, the JavaScript does not have to wait for the server response, but can instead:

-   execute other scripts while waiting for server response
-   deal with the response after the response is ready



AJAX just uses a combination of:

-   A browser built-in XMLHttpRequest object (to request data from a web server)
-   JavaScript and HTML DOM (to display or use the data)

AJAX is a misleading name. AJAX applications might use XML to transport data, but it is equally common to transport data as **plain text or JSON text.**



###The XMLHttpRequest Object

All modern browsers support the XMLHttpRequest object.

The XMLHttpRequest object can be used to exchange data with a server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.



###Create an XMLHttpRequest Object

` let variable = new XMLHttpRequest();`

```javascript
xhttp.open("GET", "demo_get.asp?t=" + Math.random(), true);
xhttp.send();

xhttp.open("GET", "demo_get2.asp?fname=Henry&lname=Ford", true);
xhttp.send();i
```

```javascript
xhttp.open("POST", "demo_post2.asp", true);
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xhttp.send("fname=Henry&lname=Ford");
```



### Or, 

Use `$.getJSON` in jQuery