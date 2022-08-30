# semantic-HTML

## The Importance of Semantics

 Some elements have a semantic meaning, but don’t really provide any context when announced by assistive technologies, such as the `<p>`element. Then there are elements that have a semantic meaning and are announced with some sort of context to help users perceive or operate them, like a `<button>`

 The `<div>`and `<span>` elements, most likely two of the more common elements you use, are semantically neutral.

 If you used `<div>`or `<span>`elements for any clickable areas, things most likely worked as intended for you. For example, perhaps you had something similar to the HTML below for your Rock, Paper, Scissors UI back in Foundations:

```html
<!-- These are buttons... right? -->
<div class='button-container'>
  <div class='rock'>Rock</div>
  <div class='paper'>Paper</div>
  <div class='scissors'>Scissors</div>
</div>
```

here’s no context to tell the user that they’re supposed to, or that they even can, interact with these elements.

This issue can be easily fixed by using semantic HTML:

```html
<!-- Okay, these are *definitely* buttons -->
<div class='button-container'>
  <button class='rock'>Rock</button>
  <button class='paper'>Paper</button>
  <button class='scissors'>Scissors</button>
</div>
```

Because the `<button>`element has a semantic meaning and provides context, a screen reader would announce the text content as well as the role of the element: “Rock, button”.

## Using Semantic HTML Correctly

* If you want to provide some sort of tabular data to a user, use a `<table>` element along with the elements related to it. This will allow a user to more easily navigate and understand the data being presented.

* When you use an input element, you should always create a relationship between it and a `<label>` element. A `<label>` provides context for what an input actually means to assistive technologies, announcing the label contents each time the input is announced. Not only that, but a proper `<label>` increases the clickable area of the input itself, which is useful for users who have trouble clicking on smaller items. There are two ways you can create this relationship:

```html
<!-- Useful when you need the input itself to have an ID -->
<label for='name'>Name</label>
<input type='text' id='name' />

<!-- Look, Ma, no ID! -->
<label>
  Name
  <input type='text' />
</label>
```

* Continuing with inputs, you should always use the `type` that makes the most sense for its intended use. `type="text"` makes more sense for a name or address field, while `type="email"` or `type="tel"` would of course make more sense for an e-mail or telephone field, respectively. For certain devices, using the correct `type` may show only the required or additional characters on the keyboard. A `type="tel"` input, for example, might make it much easier for users to fill out their phone number by providing larger, numerical-only keys on mobile or tablet devices.

* When you want to present a list of some sort to a user, you should use the appropriate list element (`<ol>`, `<ul>`, or `<dl>`) and their related list item elements. This will not only let the user know when they are entering or exiting a list, but also how many items are in the list.

## Headings and Landmarks

Headings are the `<h1>` through `<h6>` elements, and like the name implies, these elements act as headings to sections of a page. Landmarks, on the other hand, are HTML elements that act as regions of a page. There are seven native HTML elements that define these landmark regions:

* `<aside>`
* `<footer>`
* `<form>`
* `<header>`
* `<main>`
* `<nav>`
* `<section>`