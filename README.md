[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# jQuery and DOM 

## Objectives

By the end of this, developers should be able to:

- Diagram the DOM.
- Reference jQuery documentation when learning a new technique.
- After selecting a DOM node, reach another node using traversal.
- Get data from the DOM using jQuery.
- Put data into the DOM using jQuery.
- Use event listeners and handlers for user interaction

## Preparation

1. Fork and clone this repository.
1. Create a new branch, `training`, for your work.
1. Checkout to the `training` branch.

## The Document Object Model (DOM)

The DOM is a (potentially) large object that describes the structure of our
content. Since it's an object, we can use normal techniques to get and set data!
In the browser, the DOM is represented by the `document` object. This
object represents all elements on the webpage and is the entry point for
accessing those elements. A list of all methods/properties of the document
object can be found [here](https://developer.mozilla.org/en-US/docs/Web/API/Document).
JS specifies some built-in methods that make using the DOM easier. Remember! The
DOM **is not** the source code.

## Demo: Diagram the DOM

Demo translating a wireframe into a tree diagram.

![dom](https://github.com/wdi-infinity/lesson-week_02-day_03-dom/blob/master/DOM-Model-00-01.png?raw=true)

## Lab: Diagram the DOM

1. Consultant: Give wireframe
1. Developer: Draw a tree diagram
1. Consultant: Draw the solution
1. Discussion and questions

## Demo: The Document Object

```js
// returns a representation of the current html document
document

// returns a representation of the body element
document.querySelector('body')

// use document object to change style
document.querySelector('body').style.backgroundColor = 'red'
```

## jQuery

jQuery is a popular JavaScript library that simplifies many developer tasks such
as:

- DOM manipulation
  - select
  - traverse
  - effects and animation
- Event handling
- AJAX calls

The "query" in jQuery means "a request for information". We can make
queries (retrieve and put data into the DOM) using jQuery by way of selectors:

```js
// longhand syntax
jQuery('p')

// shorthand syntax
$('p')

// use modern CSS selectors
$('.my-targeted-class')
$('#my-targeted-idd')
$('.my-parent-class .my-child-class')

const myBoxElement = $('.box')
```

## What Is jQuery

[jQuery](https://api.jquery.com/) is a cross-browser JavaScript library designed to simplify the client-side scripting of HTML.

*	“Cross browser” - works the same in all* browsers.

*	Allows:
	*	Document traversal
	*	CSS Manipulation
	*	Event Handling
	*	Animation
	*	and more!

<img width="1000" alt="jquery-dom" src="https://user-images.githubusercontent.com/5384023/51519572-6a2c5880-1e32-11e9-99a0-000e18b63417.png">


## Including jQuery

Adding jQuery to your website

1.  Download and link to the file
```html
<script src="js/jquery-3.3.1.min.js"></script>
``` 

2.  Link to a remote version (CDN)

```html
<script src="https://code.jquery.com/jquery-3.3.1.js"></script>
``` 
## jQuery Syntax vs DOM Syntax

__Syntax:__ Spelling and grammar rules of a programming language.


Note:
Like with any language, there are formal rules around how to write it. This is the syntax.

<img width="1000" alt="jquery-select" src="https://user-images.githubusercontent.com/5384023/51520047-c0e66200-1e33-11e9-9d73-04d2d582e45b.png">

<img width="1000" alt="jquery-css-select" src="https://user-images.githubusercontent.com/5384023/51520072-d3609b80-1e33-11e9-90f0-3798bb5b4966.png">

### $

The Dollar Sign

```js
// longhand syntax
jQuery('p')

// shorthand syntax
$('p')

// use modern CSS selectors
$('main .title > .sub-title')
```

[jQuery Cheat Sheet](https://oscarotero.com/jquery/) provides us with a list of selector types we can use.  Notice how they are the same as our CSS selectors.

### Lab: jQuery Selectors

<img width="800" alt="screen shot 2019-01-22 at 10 23 23 am" src="https://user-images.githubusercontent.com/5384023/51586809-b2f61700-1eef-11e9-89d2-973da0751213.png">

Open [exercise/jquery-selectors/index.html](exercise/jquery-selectors/index.html) in your browser. 

Open [exercise/jquery-selectors](exercise/jquery-selectors/) folder in your text editor.

Complete the exercises in [exercise/jquery-selectors/main.js](exercise/jquery-selectors/main.js).  You will see the results in the browser console.

Read more about [jQuery selectors](https://learn.jquery.com/using-jquery-core/selecting-elements/)

## Manipulating the DOM

<img width="800" alt="screen shot 2019-01-22 at 10 24 49 am" src="https://user-images.githubusercontent.com/5384023/51586815-b4274400-1eef-11e9-9e04-f587b0d2eb23.png">

<img width="806" alt="screen shot 2019-01-22 at 10 25 24 am" src="https://user-images.githubusercontent.com/5384023/51586819-b6899e00-1eef-11e9-8897-9f845871a209.png">

### Getters

Once we select an element, we may want to get information from it like the text in the element or the value in a form.  jQuery provides us with methods that we can use to get information from an element.

**Example 1**
```html
<h1>Hello World</h1>
```
```js
$('h1').text() // Hello World
```

**Example 2**
```html
<ul>
    <li>Riyadh</li>
    <li>Boston</li>
    <li>Jeddah</li>
</ul>
```
```js
$('ul').html() // ??
```

### Setters

When we select an element, may want to change the information like update the text in the element or add html to an element.  jQuery provides us with methods that we can use to set information of an element.

**Example 1**
```html
<h1>Hello World</h1>
```
```js
$('h1').text('Goodbye World')
```

**Example 2**
```html
<ul>
    <li>Riyadh</li>
    <li>Boston</li>
    <li>Jeddah</li>
</ul>
```
```js
$('ul').html('<li>Home Town</li>') 
```

Notice the pattern of getters and setters.
```js
// GET
$('h1').text()
// SET
$('h1').text('Goodbye World')

// GET
$('ul').html() 
// SET
$('ul').html('<li>Home Town</li>') 
```

Read more about [jQuery DOM manipulation methods](https://learn.jquery.com/using-jquery-core/manipulating-elements/)

[jQuery Cheat Sheet](https://oscarotero.com/jquery/) provides us with a list of manipulation methods we can use.  

Discuss the difference between
- [.text()](http://api.jquery.com/text/)
- [.html()](http://api.jquery.com/html/)
- [.append()](http://api.jquery.com/append/)
- [.prepend()](http://api.jquery.com/prepend/)
- [.after()](http://api.jquery.com/after/)
- [.before()](http://api.jquery.com/before/)

We can also manipulate our html attributes or css properties with jQuery.

**Example 1**
```html
<img src='https://picsum.photos/200/300'>
```
```js
// GET
$('img').attr('src') // 'https://picsum.photos/200/300'

// SET
$('img').attr('src', 'https://picsum.photos/200/100')
```

**Example 2**
```html
<p id='main-text'>Hello World</p>
```
```js
// GET
$('p').attr('id') // 'main-text'

// SET
$('p').attr('id', 'new-class') 
```

Discuss the difference between
- [.attr()](http://api.jquery.com/attr/)
- [.css()](http://api.jquery.com/css/)
- [.addClass()](http://api.jquery.com/addClass/)
- [.removeClass()](http://api.jquery.com/removeClass/)
- [.toggleClass()](http://api.jquery.com/toggleClass/)
- [.hasClass()](http://api.jquery.com/hasClass/)

### Lab: Manipulate the DOM

Open [exercise/jquery-manipulate/index.html](exercise/jquery-manipulate/index.html) in your browser. 

Open [exercise/jquery-manipulate](exercise/jquery-manipulate/) folder in your text editor.

Complete the exercises in [exercise/jquery-manipulate/main.js](exercise/jquery-selectors/main.js).  You will see the results in the browser.

## DOM Events and Event Handlers

The DOM emits 'events' when users interact with the browser. Event handlers
'listen' for DOM events emitted from the DOM node they are 'attached' to, and run
code when that event happens. Some common events that we might want to use event
handlers on are `'click'`, `'mouseover'`, `'focus'`, or user keystrokes.
[Full list of DOM events](https://developer.mozilla.org/en-US/docs/Web/Events).


<img width="800" alt="screen shot 2019-01-23 at 9 40 11 am" src="https://user-images.githubusercontent.com/5384023/51587830-264d5800-1ef3-11e9-8b4d-0474fd76447a.png">

If you'd like to see more events, check out the [full list of DOM events](https://developer.mozilla.org/en-US/docs/Web/Events).  Many are consistent throughout various browsers but some are specific to a browser.

jQuery has methods we can use for specific events like `.click()`.  However, the preferred way to do events with jQuery is by using the [`.on()`](http://api.jquery.com/on/) method.

```js
function printHello () {
    console.log('Hello');
}

$('h1').on('click', printHello);
```

We can combine events and other jQuery methods to build our interactive web pages.

```js
function changeBackground () {
    $('body').css('background-color', 'red');
}

$('h1').on('click', changeBackground);
```

We can listen for hover events:
```js
function increaseFont () {
    $('h1').css('font-size', '100px');
}

$('h1').on('hover', increaseFont);
```

We can listen for forms submitting:

```html
<form>
   <input type='text'>
   <input type='submit' value='Submit Form'>
</form>
```
```js
function printUserInput (event) {
    event.preventDefault()
    let userInput = $('input:first-child').val();
    console.log(userInput)
}
$('form').on('submit', printUserInput)
```

What is the `event` key word?


### Demo: event.target

Open the console in chrome and paste the following code in.

```js
$('h1').on('click', function(event){
  console.log('event is', event)
})
```

How would we access specific attributes of that event? Try adding this code
now as well:

```js
$('h1').on('click', function(event){
  console.log('event.target is ', event.target)
})
$('h1').on('click', function(event){
  console.log('event.type is ', event.type)
})
```

### Lab: jQuery Events

Open [exercise/jquery-events/index.html](exercise/jquery-events/index.html) in your browser.

Open [exercise/jquery-events/](exercise/jquery-events/) folder in your text editor.

Complete the exercises in [exercise/jquery-events/main.js](exercise/jquery-events/main.js). You will see the results in the browser console.

### Lab: Color Scheme Picker

Open [exercise/color-scheme-picker/index.html](exercise/color-scheme-picker/index.html) in your browser.

Open [exercise/color-scheme-picker/](exercise/color-scheme-picker/) folder in your text editor.

Complete the exercises in [exercise/color-scheme-picker/js/main.js](exercise/color-scheme-picker/main.js). You will see the results in the browser console.

### Lab: Traffic Light

Open [exercise/traffic-light/index.html](exercise/traffic-light/index.html) in your browser.

Open [exercise/traffic-light/](exercise/traffic-light/) folder in your text editor.

Complete the exercises in [exercise/traffic-light/js/main.js](exercise/traffic-light/main.js). You will see the results in the browser console.

## jQuery Animations

<img width="800" alt="screen shot 2019-01-22 at 10 25 37 am" src="https://user-images.githubusercontent.com/5384023/51586821-b8536180-1eef-11e9-9ff3-1a0b98e57f46.png">

Discuss and experiment with
- [.hide()](https://api.jquery.com/hide/)
- [.show()](https://api.jquery.com/show/)
- [.toggle()](https://api.jquery.com/toggle/)
- [.fadeIn()](https://api.jquery.com/fadeIn/)
- [.fadeOut()](https://api.jquery.com/fadeOut/)
- [.slideUp()](https://api.jquery.com/slideUp/)
- [.slideDown()](https://api.jquery.com/slideDown/)
- [.animate()](https://api.jquery.com/animate/)

### Lab: jQuery Animations
Open [exercise/jquery-animations/index.html](exercise/jquery-animations/index.html) in your browser.

Open [exercise/jquery-animations/](exercise/jquery-animations/) folder in your text editor.

Complete the exercises in [exercise/jquery-animations/main.js](exercise/jquery-animations/main.js). You will see the results in the browser console.

Read more about [jQuery effects and animations](https://api.jquery.com/category/effects/)

View the [jQuery cheatsheet](https://oscarotero.com/jquery/)

## Best Practice

When attaching a `click` handler (or any handler), opt for the
`.on('click', function(){})` version over the `.click(function(){})` version.
The reason is `.on('click', )` accepts more arguments so we can be more specific
with our handlers. See [.click()](https://api.jquery.com/click/) vs.
[.on()](https://api.jquery.com/on/).

## Gotchas

- Beware the difference between jQuery setters and getters.
- Beware the difference between `.html()`, `.text()`, and `.val()`.
- Beware treating jQuery objects as arrays. They aren't!
- Beware attaching click handlers in a loop. It won't work, and it isn't
    necessary, because when you use `.on('click')` jQuery will attach the
    eventHandler on every single node in the jQuery object.

## Additional Resources

- [jQuery API Documentation](https://api.jquery.com/)
- [Live DOM tree viewer](https://software.hixie.ch/utilities/js/live-dom-viewer/)
- [jQuery Reference Cheatsheet](https://oscarotero.com/jquery/)
- [Printable jQuery Cheatsheet](http://htmlcheatsheet.com/jquery/)

1. All content is licensed under a CC­BY­NC­SA 4.0 license.
1. All software code is licensed under GNU GPLv3. For commercial use or
    alternative licensing, please contact legal@ga.co.
