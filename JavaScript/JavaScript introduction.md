
Reference:  [An Introduction to JavaScript](https://javascript.info/intro)

It's time to learn JavaScript. But what is JavaScript?

## [What is JavaScript?](https://javascript.info/intro#what-is-javascript)

>#### Why is it called <ins>Java</ins>Script?**
>
>When JavaScript was created, it initially had another name: “LiveScript”. 
>
>But Java was very popular at that time, so it was decided that positioning a new language as a “younger brother” of Java would help.
>
>Now it has no relation to Java at all.

Today, JavaScript can execute not only in the browser, but also on the server, or actually on any device that has a special program called [the JavaScript engine](https://en.wikipedia.org/wiki/JavaScript_engine).

## [What can in-browser JavaScript do?](https://javascript.info/intro#what-can-in-browser-javascript-do)

Modern JavaScript is a “safe” programming language. It does not provide low-level access to memory or CPU, because it was initially created for browsers which do not require it.

In-browser JavaScript can do everything related to webpage manipulation, interaction with the user, and the webserver.

## [What CAN’T in-browser JavaScript do?](https://javascript.info/intro#what-can-t-in-browser-javascript-do)

JavaScript’s abilities in the browser are limited for the sake of a user’s safety. The aim is to prevent an evil webpage from accessing private information or harming the user’s data.

Examples of such restrictions include:
-   JavaScript on a webpage may not read/write arbitrary files on the hard disk, copy them or execute programs. It has no direct access to OS functions.
- Different tabs/windows generally do not know about each other. 
Read more about: [Same Origin Policy](https://javascript.info/cross-window-communication)
- JavaScript can easily communicate over the net to the server where the current page came from. But its ability to receive data from other sites/domains is crippled.

Such limits do not exist if JavaScript is used outside of the browser, for example on a server.

## [What makes JavaScript unique?](https://javascript.info/intro#what-makes-javascript-unique)

>-   Full integration with HTML/CSS.
>-   Simple things are done simply.
>-   Supported by all major browsers and enabled by default.

## [Languages “over” JavaScript](https://javascript.info/intro#languages-over-javascript)

-   [CoffeeScript](https://coffeescript.org/) is a “syntactic sugar” for JavaScript. It introduces shorter syntax, allowing us to write clearer and more precise code. Usually, Ruby devs like it.
-   [TypeScript](https://www.typescriptlang.org/) is concentrated on adding “strict data typing” to simplify the development and support of complex systems. It is developed by Microsoft.
-   [Flow](https://flow.org/) also adds data typing, but in a different way. Developed by Facebook.
-   [Dart](https://www.dartlang.org/) is a standalone language that has its own engine that runs in non-browser environments (like mobile apps), but also can be transpiled to JavaScript. Developed by Google.
-   [Brython](https://brython.info/) is a Python transpiler to JavaScript that enables the writing of applications in pure Python without JavaScript.
-   [Kotlin](https://kotlinlang.org/docs/reference/js-overview.html) is a modern, concise and safe programming language that can target the browser or Node.

## [Specification](https://javascript.info/manuals-specifications#specification)

[The ECMA-262 specification](https://www.ecma-international.org/publications/standards/Ecma-262.htm) contains the most in-depth, detailed and formalized information about JavaScript. It defines the language.

## [Manuals](https://javascript.info/manuals-specifications#manuals)

**[MDN (Mozilla) JavaScript Reference]( [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference))** is the main manual with examples and other information.


