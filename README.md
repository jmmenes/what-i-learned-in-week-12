# What I Learned In Week 12 At Code Immersives

&nbsp;

## Github Pages

https://pages.github.com/#user-site

https://pages.github.com/

GitHub Pages is a static site hosting service that takes HTML, CSS, and JavaScript files straight from a repository on GitHub, optionally runs the files

You can host your site on GitHub's github.io domain or your own custom domain.

&nbsp;

## HTML, CSS Review

Hypertext Markup Language (HTML) is the standard markup language for documents designed to be displayed in a web browser. It can be assisted by technologies such as Cascading Style Sheets (CSS) and scripting languages such as JavaScript.

Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language such as HTML. CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.

&nbsp;

## DOM Manipulation (Document Object Model)

The Document Object Model (DOM) is the data representation of the objects that comprise the structure and content of a document on the web.

The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

&nbsp;

## querySelector();

The querySelector() method returns the first element that matches one or more CSS selectors. If no match is found, it returns null.

Before querySelector() was introduced, developers widely used the getElementById() method which fetches an element with a specified id value.

Although getElementById() is still a useful method, but with the newer querySelector() and querySelectorAll() methods we are free to target elements based on any CSS selector, thus we have more flexibility.

&nbsp;

    document.querySelector();
    document.querySelectorAll();

    //The most used to access the DOM, because with it you can access class, id and tag. So each case would be:

    document.querySelector('#id');
    document.querySelector('.classname');
    document.querySelector('section');

The querySelector() method returns the first element that matches a specified CSS selector(s) in the document.

Note: The querySelector() method only returns the first element that matches the specified selectors. To return all the matches, use the querySelectorAll() method instead.

&nbsp;

## Event Listeners

An event listener is a procedure or function in a computer program that waits for an event to occur. Examples of an event are the user clicking or moving the mouse, pressing a key on the keyboard, disk I/O, network activity, or an internal timer or interrupt. The listener is programmed to react to an input or signal by calling the event's handler.

The term event listener is often specific to Java and JavaScript. In other languages, a subroutine that performs a similar function is referred to as an event handler.

The following JavaScript code would add an event listener to an HTML document:

    document.addEventListener('click', myfunction, false);

In this example, when HTML is rendered in a browser, the listener calls the function "myfunction" (defined elsewhere in the script) when the user clicks.

&nbsp;

## Absolute Positioning In CSS

This is a very powerful type of positioning that allows you to literally place any page element exactly where you want it. You use the positioning attributes top, left, bottom, and right to set the location. Remember that these values will be relative to the next parent element with relative (or absolute) positioning. If there is no such parent, it will default all the way back up to the <html> element itself meaning it will be placed relative to the page itself.

The trade-off (and most important thing to remember) about absolute positioning is that these elements are removed from the flow of elements on the page. An element with this type of positioning is not affected by other elements and it doesn’t affect other elements. This is a serious thing to consider every time you use absolute positioning. Its overuse or improper use can limit the flexibility of your site.

&nbsp;

## Nested Event Listeners

    const button1 = document.querySelector('#button-1');
    const button2 = document.querySelector('#button-2');
    const output = document.querySelector('.output');

    // Example of nested event listener (not reccomended)
    // The button2 eventListener will not be set until button1 is clicked

    button1.addEventListener('click', () => {

        output.style.backgroundColor = 'green';

        button2.addEventListener('click', () => {
            output.style.backgroundColor = 'red';
        });

    });

&nbsp;

## Event

What is an Event ?
JavaScript's interaction with HTML is handled through events that occur when the user or the browser manipulates a page.

When the page loads, it is called an event. When the user clicks a button, that click too is an event. Other examples include events like pressing any key, closing a window, resizing a window, etc.

Developers can use these events to execute JavaScript coded responses, which cause buttons to close windows, messages to be displayed to users, data to be validated, and virtually any other type of response imaginable.

Events are a part of the Document Object Model (DOM) Level 3 and every HTML element contains a set of events which can trigger JavaScript Code.

&nbsp;

Examples

- onclick Event Type
  This is the most frequently used event type which occurs when a user clicks the left button of his mouse.

- onsubmit Event Type
  onsubmit is an event that occurs when you try to submit a form.

&nbsp;

## Target Event Property

The target event property returns the element that triggered the event.

The target property gets the element on which the event originally occurred, opposed to the currentTarget property, which always refers to the element whose event listener triggered the event.

    event.target

&nbsp;

## Creating DOM Elements

The createElement() method creates an Element Node with the specified name.

    After the element is created, use the element.appendChild() or element.insertBefore() method to insert it to the document.

    // Retrieves and style the 'container' element
    const container = document.querySelector('#container');
    container.style.padding = '20px';
    container.style.backgroundColor = 'purple';

    // Creates a new element (not yet added to page)
    const title = document.createElement('h1');
    title.style.color = 'white';
    title.style.fontFamily = 'Arial, sans-serif';
    title.innerText = 'This is the best class ever!';

    // Adds an element to the page
    container.appendChild(title);

    // We can continue to modify title after its been added to the page
    title.style.color = 'green';

    // To remove an element from the page
    // title.remove();
