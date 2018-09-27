# Javascript cs50

```javascript
function hello() {
                alert('Hello!');
            }
```

Funcitons in JS are trigger by events:

-   onclick
-   onmouseover
-   onkeydown
-   onkeyup
-   onload
-   onblur
-   ...





### querying

```javascript
function hello() {
                document.querySelector('h1').innerHTML = 'Goodbye!';
            }
```

-   `document` is a variable in JS that refers to the web page
-   `querySelector`: a js function that search through the web page for selectors. Only selects the first matched element.
-   then, we are accessing `innerHTML` property of the `h1` element. That property refers to the content between two tags of that element.

```javascript
domument.querySelector('tag')
document.querySelector('#id')
document.querySelector('.class')
```



Use ` in js to identify the content between is a formatted string.





### a way to factor out JS out of HTML

`EventListener`

```javascript
<script>

            document.addEventListener('DOMContentLoaded', function() {
                document.querySelector('button').onclick = count;
            });

            let counter = 0;

            function count() {
                counter++;
                document.querySelector('#counter').innerHTML = counter;

                if (counter % 10 === 0) {
                    alert(`Counter is at ${counter}!`);
                }
            }

</script>
```

`.addEventListener()` takes two arguments:

1.  name of the event that we are listening to 

2.  a function

    `document.querySelector('button').onclick` : pass the `count` function to the `onclick` attribute of `button`, but doesn't call it right away. The function`count` is being called only when the botton is onclicked.





### Variables

-   const: a constant, can not be changed later;
-   let: out of the double curly braces where the variable is defined in, the variable no longer exists
-   var: if will always exist in the function that the variable is defined in.





### Style

`document.querySelector('#hello').style.color = 'blue';`

`.style` get the attribute, then developers can modify any of the css attributes after it.







```html
<script>
    document.addEventListener('DOMContentLoaded', function() {
        document.querySelectorAll('.color-change').forEach(function(button) {
            button.onclick = function() {
                document.querySelector('#hello').style.color = button.dataset.color;
            };
        });
    });
</script>
        

<button class="color-change" data-color="red">Red</button>
<button class="color-change" data-color="blue">Blue</button>
<button class="color-change" data-color="green">Green</button>
```

**Explaination**: for each of the elements from `color-change` class, run a function and take the input as `button`. Set the `onclick` attribute of each element / `button` to a function that runs when `onclick` is fired. 

### querySelectorAll

it returns an array of all the elements that matched;

`.forEach()` : a build-in function for js, run a function for each element of the array

###Data-element: 

Syntax: `data-something` inside any opening tag as additional property

`.dataset`: the way to access html data-element in JS

`.color`: take that one particular color





### JS: Arrow Functions

```javascript
() => {
    alert("Hello, world");
}

x => {
    alert(x);
}

x => x * 2
```

-   there is no word `function`
-   the varible inside ( ) is the variable taken into this function
-   More succinct, more concise





### Arrow Functions v.s traditional function

```javascript
<script>
    document.addEventListener('DOMContentLoaded', () => {

    // Change the color of the heading when dropdown changes
    document.querySelector('#color-change').onchange = function() {
        document.querySelector('#hello').style.color = this.value;
    };

});
</script>
   
<select id="color-change">
    <option value="black">Black</option>
	<option value="red">Red</option>
</select>
```

Key word `this` is refering to the object of the function that is bonded to. Here, `this` refers to `document.querySelector('#color-change')`.

However, it works only when we are using the traditional way to bond a function to a value, not the arrow function way.





### A comprehensive example

```javascript
<!DOCTYPE html>
<html>
    <head>
        <script>
            document.addEventListener('DOMContentLoaded', () => {
    
                document.querySelector('#submit').disabled = true;
    
                document.querySelector('#task').onkeyup = () => {
                    if (document.querySelector('#task').value.length > 0)
                        document.querySelector('#submit').disabled = false;
                    else
                        document.querySelector('#submit').disabled = true;
                };

                document.querySelector('#new-task').onsubmit = () => {

                    const li = document.createElement('li');
                    li.innerHTML = document.querySelector('#task').value;
                    document.querySelector('#tasks').append(li);
                    document.querySelector('#task').value = '';
                    document.querySelector('#submit').disabled = true;

                    return false;
                };
    
            });
        </script>
        <title>Tasks</title>
    </head>
    <body>
        <h1>Tasks</h1>
        <ul id="tasks">
        </ul>
        <form id="new-task">
            <input id="task" autocomplete="off" autofocus placeholder="New Task" type="text">
            <input id="submit" type="submit">
        </form>
    </body>
</html>
```

**HTML properties**: we can access to any of the html properties of selected elements

1.  `document.querySelector('#submit').disabled = true;`

    The `disabled` html property of the selected element 

2.  `if (document.querySelector('#task').value.length > 0)`

    The `value` html property of this element would be a string, then we call the `string` attribute of this particular string in javascript

3.  `const li = document.createElement('li');`

    Create a html element(tag) in javascript

4.  `li.innerHTML = document.querySelector('#task').value;`

    set the 'innerHTML' property of this HTML tag to something.

5.  `document.querySelector('#tasks').append(li);`

    append something after this HTML element

6.  By default, when a html form is submitted, this entire page would be reloaded because the information in the form will be send to somewhere else. **`return false`** would stop the page from reloading.

7.  ```javascript
    document.querySelector('#new-task').onsubmit = () => {
                        // Stop form from submitting
                        return false;
                    };
    ```





### Local storage

```javascript
<script>

            // Set starting value of counter to 0
            if (!localStorage.getItem('counter'))
                localStorage.setItem('counter', 0);

            // Load current value of  counter
            document.addEventListener('DOMContentLoaded', () => {
                document.querySelector('#counter').innerHTML = localStorage.getItem('counter');

                // Count every time button is clicked
                document.querySelector('button').onclick = () => {
                    // Increment current counter
                    let counter = localStorage.getItem('counter');
                    counter++;

                    // Update counter
                    document.querySelector('#counter').innerHTML = counter;
                    localStorage.setItem('counter', counter);
                }
            });

</script>
```

**Local storage is stored based on domain name, so there will not be conflicts the variable have common name from different sites.**





### Ajax



####创建 XMLHttpRequest 对象

`let variable = new XMLHttpRequest();`



####向服务器发送请求

如需将请求发送到服务器，我们使用 XMLHttpRequest 对象的 open() 和 send() 方法：

```javascript
xmlhttp.open("GET","ajax_info.txt",true);

xmlhttp.send();
```

 open(*method*,*url*,*async*)   规定请求的类型、URL 以及是否异步处理请求。

-   *method*：请求的类型；GET 或 POST
-   *url*：文件在服务器上的位置
-   *async*：true（异步）或 false（同步） 

send(*string*)  将请求发送到服务器。

-   *string*：仅用于 POST 请求



####服务器响应

如需获得来自服务器的响应，请使用 XMLHttpRequest 对象的 responseText 或 responseXML 属性。

| responseText | 获得字符串形式的响应数据。 |
| ------------ | -------------------------- |
| responseXML  | 获得 XML 形式的响应数据。  |



####回调函数

XMLHttpRequest 对象的 onload 回调函数是在异步请求加载完成后所执行的函数，当JavaScript 监测到请求的数据全部传输完成后就会触发该函数。



还有一些误解需要澄清一下，

1.  window.onload 回调函数其实是在页面加载完成后（包括图片内容的显示）才会执行，并不是页面加载的等待过程中就执行。
2.  request.open() 并没有发送请求，只是设置一些参数，在 send() 时才会发送（注意不要漏写这条语句），发送后就会进入 readyState 监听状态，当 readyState 的值有改变就会执行 onreadystatechange 回调函数，当异请求的步数据接收完成（即 readyState 变为 4）后就会执行 onload 回调函数（注意仅在 XHR2 中有效）。





### Socket.IO: A javascript library



