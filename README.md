# What I Learned In Week 12 At Code Immersives

&nbsp;

## JavaScript Promises & Async/Await

Async functions. They allow you to write promise-based code as if it were synchronous, but without blocking the main thread. They make your asynchronous code less "clever" and more readable.

Async functions work like this:

    async function myFirstAsyncFunction() {
    try {
        const fulfilledValue = await promise;
    }
    catch (rejectedValue) {
        // …
     }
    }

If you use the async keyword before a function definition, you can then use await within the function. When you await a promise, the function is paused in a non-blocking way until the promise settles. If the promise fulfills, you get the value back. If the promise rejects, the rejected value is thrown.

### Example: Logging a fetch

Say we wanted to fetch a URL and log the response as text. Here's how it looks using promises:

    function logFetch(url) {
    return fetch(url)
        .then(response => response.text())
        .then(text => {
        console.log(text);
        }).catch(err => {
        console.error('fetch failed', err);
        });
    }

And here's the same thing using async functions:

    async function logFetch(url) {
    try {
        const response = await fetch(url);
        console.log(await response.text());
    }
    catch (err) {
        console.log('fetch failed', err);
    }
    }

It's the same number of lines, but all the callbacks are gone. This makes it way easier to read, especially for those less familiar with promises.

&nbsp;

## Promises vs. Callbacks

### Callbacks

This is the old-fashioned classical approach to asynchronous programming. You provide a function as an argument to another function that executes an asynchronous task. When the asynchronous task completes, the executing function calls your callback function.

The main disadvantage of this approach occurs when you have multiple chained asynchronous tasks, which requires you to define callback functions within callback functions within callback functions… This is called callback hell.

### Promises

Promises have been introduced in ES6 (2015) to allow for more readable asynchronous code than is possible with callbacks.

The main difference between callbacks and promises is that with callbacks you tell the executing function what to do when the asynchronous task completes, whereas with promises the executing function returns a special object to you (the promise) and then you tell the promise what to do when the asynchronous task completes.

In practice, this looks like this:

    const promise = asyncFunc();
    promise.then(result => {
        console.log(result);
    });

That is, instead of providing a function reference as an argument to asyncFunc (as you would with callbacks), asyncFunc immediately returns a promise to you, and then you provide the action to be taken when the asynchronous task completes to this promise (through its then method).
