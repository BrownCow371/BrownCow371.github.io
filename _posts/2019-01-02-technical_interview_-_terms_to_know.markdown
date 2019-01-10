---
layout: post
title:      "Technical Interview - Terms to Know"
date:       2019-01-02 12:23:14 -0500
permalink:  technical_interview_-_terms_to_know
---


I recently completed my mock technical interview and was faced with answering rapid fire questions about common programming/JavaScript terms and discovered that I prattle when giving descriptions (which takes away time from the code challenges where one would want more time to work with). Part of the feedback from my interview was to come up with concise (quick) definitions/descriptions for commonly asked about terms. As practice, and for posterity, I’ve put together a list of definitions (with resource links) here.  This is a growing list that I'll continue to add to as I encounter other terms during interviews. 

## CSS
***Sprites*** – combination of multiple images into a single image file to help with performance (several images loaded with a single HTTP request). 
* [https://css-tricks.com/css-sprites/](https://css-tricks.com/css-sprites/)
* [https://www.w3schools.com/css/css_image_sprites.asp](https://www.w3schools.com/css/css_image_sprites.asp) 

***Center a div within a div vertically*** – create parent and child classes and set top and bottom padding equal on parent div 
* [https://vanseodesign.com/css/vertical-centering/](https://vanseodesign.com/css/vertical-centering/)
* [https://jsfiddle.net/hashem/VsakD/8/](https://jsfiddle.net/hashem/VsakD/8/)
* [https://davidwalsh.name/vertical-center-flexbox](https://davidwalsh.name/vertical-center-flexbox)
* [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

***Box Model*** - from the inside to the outside of the box model: content -> padding -> border -> margin
* [https://www.w3schools.com/css/css_boxmodel.asp](https://www.w3schools.com/css/css_boxmodel.asp)
* [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model)

***div vs. p vs. span*** – p and div are block (equivalent to having a line break before and after) elements. Span is an in-line element and usually used for small chunks of HTML (like making one word in a header or paragraph a different color). 
* [http://www.htmldog.com/guides/html/intermediate/spandiv/](http://www.htmldog.com/guides/html/intermediate/spandiv/)
* [https://www.quora.com/What-is-difference-between-span-and-p](https://www.quora.com/What-is-difference-between-span-and-p)

***Block vs. inline*** – block level elements start on a new line. In-line elements will not start a new line. Block elements take up the full width of available space while in-line only consume the amount of space needed for the element.  
* [https://coursework.vschool.io/html-block-vs-inline/](https://coursework.vschool.io/html-block-vs-inline/)

## JavaScript

***Promises*** – an object that represents the eventual completion of an asynchronous operation and its resulting value. 
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
* [https://javascript.info/promise-basics](https://javascript.info/promise-basics)

***Hoisting*** – JavaScript’s default behavior of moving declarations (variables and functions) to the top. This is a result of the JS Engine running through the code the first time and setting aside memory for each declared function/variable. 
* [https://www.w3schools.com/js/js_hoisting.asp](https://www.w3schools.com/js/js_hoisting.asp)
* [https://developer.mozilla.org/en-US/docs/Glossary/Hoisting](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)

***Lexical Scope*** – scope defined at lexing time  - inner and outer scope are determined by WHERE a function or variable is declared…not called/invoked.  
* [https://scotch.io/tutorials/understanding-scope-in-javascript#toc-lexical-scope](https://scotch.io/tutorials/understanding-scope-in-javascript#toc-lexical-scope)
* [https://medium.com/@nickbalestra/javascripts-lexical-scope-hoisting-and-closures-without-mystery-c2324681d4be](https://medium.com/@nickbalestra/javascripts-lexical-scope-hoisting-and-closures-without-mystery-c2324681d4be)
* [https://toddmotto.com/everything-you-wanted-to-know-about-javascript-scope/#lexical-scope](https://toddmotto.com/everything-you-wanted-to-know-about-javascript-scope/#lexical-scope)

***Callbacks*** – functions passed into other functions as arguments
* [https://developer.mozilla.org/en-US/docs/Glossary/Callback_function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)

***Var/Let/Const*** – `var` declarations are globally scoped when a `var `variable is declared outside of a function or within a block (`var` variables are not block-scoped). A `var` variable is function scoped if declared inside a function.  `var` variables can be re-declared and updated (can call `var greeter `twice without an error). `let` and `const` variables cannot be re-declared. They are both block scoped. They also will throw an error if they are declared after they are used in a function (they are still hoisted, but not initialized).  You cannot declare a `const` variable without also assigning it (it cannot be updated). . 
* [https://dev.to/sarah_chima/var-let-and-const--whats-the-difference-69e](https://dev.to/sarah_chima/var-let-and-const--whats-the-difference-69e)
* [https://dzone.com/articles/javascript-difference-between-var-let-and-const-ke](https://dzone.com/articles/javascript-difference-between-var-let-and-const-ke)
* [https://medium.com/javascript-scene/javascript-es6-var-let-or-const-ba58b8dcde75](https://medium.com/javascript-scene/javascript-es6-var-let-or-const-ba58b8dcde75)

***Closures*** – a closure is the combination of a function and the outer scope/environment of that function when it was declared (usually within another function).  Meaning the inner declared function has access to its outer function’s variables, even if the outer function has already returned. 
* [https://www.w3schools.com/js/js_function_closures.asp](https://www.w3schools.com/js/js_function_closures.asp)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)
* [https://medium.com/dailyjs/i-never-understood-javascript-closures-9663703368e8](https://medium.com/dailyjs/i-never-understood-javascript-closures-9663703368e8)
* [https://medium.freecodecamp.org/javascript-closures-simplified-d0d23fa06ba4](https://medium.freecodecamp.org/javascript-closures-simplified-d0d23fa06ba4)

***Equality Operator***  – there are two types…`== ` and `===`. `===` is strict comparison and only true if the values are the same type and the contents match. Type converting comparison `==` will convert the values to the same type before comparing (so “1” and 1 would be `==` but not `===`). 
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators)
* [https://www.w3schools.com/js/js_comparisons.asp](https://www.w3schools.com/js/js_comparisons.asp)

***Event Bubbling*** – when an event happens on an element it first runs the handler on it then on its parent, then up the chain of ancestors. 
* [https://javascript.info/bubbling-and-capturing](https://javascript.info/bubbling-and-capturing)
* [https://www.sitepoint.com/event-bubbling-javascript/](https://www.sitepoint.com/event-bubbling-javascript/)

***Event delegation*** – instead of assigning a handler to each element on a page, if all events are handled in a similar way for similar elements, we add a single handler on the common ancestor. This solves the issue of when the element wasn’t on the page when the page was initially loaded. 
* [https://javascript.info/event-delegation](https://javascript.info/event-delegation)
* [https://medium.com/@bretdoucette/part-4-what-is-event-delegation-in-javascript-f5c8c0de2983](https://medium.com/@bretdoucette/part-4-what-is-event-delegation-in-javascript-f5c8c0de2983)
* [https://davidwalsh.name/event-delegate](https://davidwalsh.name/event-delegate)

***Event Loop*** 
> The event loop is the term given to the process of the waiting for the queue to receive a message synchronously. The increment that the event loop moves in is called a ‘tick’, and every time it ‘ticks’ it checks if the call stack is empty, if so , it adds the top function in the event queue to the call stack and executes it. Once it is finished processing this function it starts ticking again.  – Feargal Walsh

* [https://codeburst.io/what-you-need-to-know-about-the-javascript-event-loop-ee3fc32e59c1](https://codeburst.io/what-you-need-to-know-about-the-javascript-event-loop-ee3fc32e59c1)
* [https://flaviocopes.com/javascript-event-loop/](https://flaviocopes.com/javascript-event-loop/)
* [https://blog.carbonfive.com/2013/10/27/the-javascript-event-loop-explained/](https://blog.carbonfive.com/2013/10/27/the-javascript-event-loop-explained/)

***Prototypal inheritance*** – JavaScript is a prototype-based language  - so instead of having classes that define the blueprints for an object, object properties and methods are shared through a generalized prototype object. All objects in JS inherit Object.Prototype properties and methods (end of the prototype chain). 
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
* [https://www.digitalocean.com/community/tutorials/understanding-prototypes-and-inheritance-in-javascript](https://www.digitalocean.com/community/tutorials/understanding-prototypes-and-inheritance-in-javascript)

***Object-Oriented Programming in JavaScript*** - As noted above, JavaScript is a prototype-based language so Object type properties and methods are acquired through a generalized prototye object. With ES6, developers have the ability to define "Classes" using a class syntax. Note that these classes still define prototype-based classes. 
* [https://javascript.info/class](https://javascript.info/class)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)
* [https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Object-oriented_JS)
*  [https://scotch.io/tutorials/object-oriented-programming-in-javascript](https://scotch.io/tutorials/object-oriented-programming-in-javascript)

***Constructor Functions*** – a constructor function is one that you would use to create a new "object type". You would use the `new` keyword to invoke/create a new object of the same type via the Constructor function. You typically declare the function name with an uppercase word. 

* [https://www.w3schools.com/js/js_object_constructors.asp](https://www.w3schools.com/js/js_object_constructors.asp)
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/constructor)

***Context Binding (call, apply, bind)***  – all three are used to control the invocation context of a function – `call()` and `apply()` allow you to specify the context (“this”) and immediately invoke the function with that value. The difference between the two is that `apply()` only takes two argument, the value you want to pass for “this” and an array of arguments to pass to the function. `bind()` returns a context-bound version of the original function. 
* [https://www.codementor.io/niladrisekhardutta/how-to-call-apply-and-bind-in-javascript-8i1jca6jp](https://www.codementor.io/niladrisekhardutta/how-to-call-apply-and-bind-in-javascript-8i1jca6jp)
* [https://thenewstack.io/mastering-javascript-callbacks-bind-apply-call/](https://thenewstack.io/mastering-javascript-callbacks-bind-apply-call/)

***This*** – refers to object it belongs to – varies based on where it is used. 
* [https://www.w3schools.com/js/js_this.asp](https://www.w3schools.com/js/js_this.asp)
* [https://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/](https://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/)

***Benefits of Strict Mode?***

> Strict mode helps out in a couple ways:
> •	It catches some common coding bloopers, throwing exceptions.
> •	It prevents, or throws errors, when relatively “unsafe” actions are taken (such as gaining access to the global object).
> •	It disables features that are confusing or poorly thought out.
> – John Resig

* [https://lucybain.com/blog/2014/js-use-strict/](https://lucybain.com/blog/2014/js-use-strict/)
* [https://www.toptal.com/javascript/interview-questions](https://www.toptal.com/javascript/interview-questions)

***Variable Scoping*** 
> The scope of a variable is controlled by the location of the variable declaration, and defines the part of the program where a particular variable is accessible.- Ivaylo Gerchev 
> 

***Function and Block Scoping*** – function scopes are created for every function and are often considered to be “local” scopes. Block scopes are what you get with `if` statements, `for` statements, `switch` cases, etc. The `var` keyword doesn’t honor block scope (is global) whereas `let` and `const` honor both function and block scopes. 
* [https://edgecoders.com/function-scopes-and-block-scopes-in-javascript-25bbd7f293d7](https://edgecoders.com/function-scopes-and-block-scopes-in-javascript-25bbd7f293d7)
* [https://medium.com/@josephcardillo/the-difference-between-function-and-block-scope-in-javascript-4296b2322abe](https://medium.com/@josephcardillo/the-difference-between-function-and-block-scope-in-javascript-4296b2322abe)

***Function expressions & declarations*** – function declaration defines a function variable without requiring assignment.  Function expressions are when a function is defined as part of a larger expression syntax (usually via variable assignment)
* [https://javascriptweblog.wordpress.com/2010/07/06/function-declarations-vs-function-expressions/](https://javascriptweblog.wordpress.com/2010/07/06/function-declarations-vs-function-expressions/)

***High order functions*** – functions that take functions as arguments or return them. 
* [https://eloquentjavascript.net/05_higher_order.html](https://eloquentjavascript.net/05_higher_order.html)
* [https://blog.bitsrc.io/understanding-higher-order-functions-in-javascript-75461803bad](https://blog.bitsrc.io/understanding-higher-order-functions-in-javascript-75461803bad)

***First Class-Functions*** – In JavaScript - functions are a special type of object, making them first-class citizens.
* [https://blog.bitsrc.io/understanding-higher-order-functions-in-javascript-75461803bad](https://blog.bitsrc.io/understanding-higher-order-functions-in-javascript-75461803bad)

***Arrow Functions*** – Introduced in ES6 – shorter syntax for defining functions and these functions do not have their own `this`, `arguments` or `super` – cannot be used for constructor functions. 

Syntax:  `const funcName = () => statement` 
* Note - they implicitly return statement if you don’t include `{}` block

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)
* [https://codeburst.io/javascript-arrow-functions-for-beginners-926947fc0cdc](https://codeburst.io/javascript-arrow-functions-for-beginners-926947fc0cdc)

***Functional Programming***  
> Functional programming (often abbreviated FP) is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects. Functional programming is declarative rather than imperative, and application state flows through pure functions. Contrast with object oriented programming, where application state is usually shared and colocated with methods in objects. - Eric Elliott

* [ https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0)

***Arity*** – the number of arguments a function takes.
* [https://en.wikipedia.org/wiki/Arity](https://en.wikipedia.org/wiki/Arity)

***Function Currying*** – the process of breaking down a function into a series of functions that each take a single argument. 
* [https://medium.com/javascript-scene/curry-and-function-composition-2c208d774983](https://medium.com/javascript-scene/curry-and-function-composition-2c208d774983)
* [https://medium.com/@kbrainwave/currying-in-javascript-ce6da2d324fe](https://medium.com/@kbrainwave/currying-in-javascript-ce6da2d324fe)
* [https://hackernoon.com/currying-in-js-d9ddc64f162e](https://hackernoon.com/currying-in-js-d9ddc64f162e)
* [https://www.codementor.io/michelre/currying-in-javascript-g6212s8qv](https://www.codementor.io/michelre/currying-in-javascript-g6212s8qv)
* [https://medium.com/javascript-scene/curry-or-partial-application-8150044c78b8](https://medium.com/javascript-scene/curry-or-partial-application-8150044c78b8)

***Composition functions*** 
> Function composition is a mathematical concept that allows you to combine two or more functions into a new function.

* [https://www.codementor.io/michelre/use-function-composition-in-javascript-gkmxos5mj](https://www.codementor.io/michelre/use-function-composition-in-javascript-gkmxos5mj)
* [https://hackernoon.com/javascript-functional-composition-for-every-day-use-22421ef65a10](https://hackernoon.com/javascript-functional-composition-for-every-day-use-22421ef65a10)
* [https://medium.com/javascript-scene/master-the-javascript-interview-what-is-function-composition-20dfb109a1a0](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-function-composition-20dfb109a1a0)

***Spread Operator*** – syntax `…` Can be used in function arguments, or with array literals or objects. Purpose is to expand an array or object in places where zero or more arguments/elements are expected. 

*Example:* 
```
const array = [1, 2];
const array2 = [...array, 3, 4];
Console.log(array2) // [1, 2, 3, 4]
```
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
* [https://zendev.com/2018/05/09/understanding-spread-operator-in-javascript.html](https://zendev.com/2018/05/09/understanding-spread-operator-in-javascript.html)

***Destructuring*** 
> JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.  - MDN

*Example:* 
```
let [a, b] = [10, 20];

console.log(a);
// expected output: 10

console.log(b);
// expected output: 20

[a, b, ...rest] = [10, 20, 30, 40, 50];

console.log(rest);
// expected output: [30,40,50]
``` 

* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)
* [https://wesbos.com/destructuring-objects/](https://wesbos.com/destructuring-objects/)

***Template Strings/Literals*** – use back-ticks to define string and `${}` define placeholders which can be embedded expressions or variables. 
* [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)

## React
***Virtual DOM and Diffing***– an object that represents the actual DOM. When we render a JSX element every virtual DOM element gets updated and then React compares the Virtual DOM to a snapshot of the Virtual DOM before the update.  React figures out which Virtual DOM elements have changed (Diff Algorithm) –then ONLY updates those objects in the Real DOM. 
* [https://www.codecademy.com/articles/react-virtual-dom](https://www.codecademy.com/articles/react-virtual-dom)
* [https://reactjs.org/docs/faq-internals.html](https://reactjs.org/docs/faq-internals.html)

***Declarative Programming***  - way of programming where you describe what you want as a result as opposed to how you want it to get the result. 
* [https://codeburst.io/declarative-vs-imperative-programming-a8a7c93d9ad2](https://codeburst.io/declarative-vs-imperative-programming-a8a7c93d9ad2)
* [https://tylermcginnis.com/imperative-vs-declarative-programming/](https://tylermcginnis.com/imperative-vs-declarative-programming/)

***Controlled Components vs. Uncontrolled Components*** – controlled components values/inputs are controlled by the state of the component. In an uncontrolled component, the state is not updated. 
* [https://medium.com/@peter.yun.kim/controlled-and-uncontrolled-input-values-in-react-907119cc98d4](https://medium.com/@peter.yun.kim/controlled-and-uncontrolled-input-values-in-react-907119cc98d4)
* [https://reactjs.org/docs/uncontrolled-components.html](https://reactjs.org/docs/uncontrolled-components.html)
* [https://reactjs.org/docs/forms.html](https://reactjs.org/docs/forms.html)

***Class Component vs.Functional Component*** – Functional Components are literally JS functions that take in props and return a React Element.  Class Componets are ES6 classes that inherit from the React Component module. Classes can have state AND inherit React Lifecycle methods. 
* [https://reactjs.org/docs/components-and-props.html](https://reactjs.org/docs/components-and-props.html)
* [https://reactjs.org/docs/state-and-lifecycle.html](https://reactjs.org/docs/state-and-lifecycle.html)
* [https://alligator.io/react/class-components/](https://alligator.io/react/class-components/)

***Keys*** – special string attribute included when creating lists of elements – React uses them to determine which elements have changed, been added or removed. 
* [https://reactjs.org/docs/lists-and-keys.html](https://reactjs.org/docs/lists-and-keys.html)

***Higher Order Components*** - component that returns another component with additional props passed in; for code reuse; an example being `connect()` method in Redux

***React Lifecycle Methods*** – Available for class components that extend React.Component. Include `render()` which is required for each class component created. Other commonly uses are `ComponentDidMount()`, `ComponentWillUnmount()`, `ComponentWillUpdate()`, etc. 
* [https://engineering.musefind.com/react-lifecycle-methods-how-and-when-to-use-them-2111a1b692b1](https://engineering.musefind.com/react-lifecycle-methods-how-and-when-to-use-them-2111a1b692b1)
* [https://reactjs.org/docs/state-and-lifecycle.html](https://reactjs.org/docs/state-and-lifecycle.html)

***Refs in React*** – provides way to access DOM nodes or React elements created in the render method. They should not be overused. Typically used for managing focus, triggering animation, integrating with third art DOM libraries. 
* [https://reactjs.org/docs/refs-and-the-dom.html](https://reactjs.org/docs/refs-and-the-dom.html)

***JSX*** – syntax extension of JavaScript used by React. 
* [https://reactjs.org/docs/introducing-jsx.html](https://reactjs.org/docs/introducing-jsx.html)
* [https://reactjs.org/docs/jsx-in-depth.html](https://reactjs.org/docs/jsx-in-depth.html)
