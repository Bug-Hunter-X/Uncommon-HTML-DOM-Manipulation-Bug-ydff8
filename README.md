# Uncommon HTML DOM Manipulation Bug

This repository demonstrates a subtle bug related to DOM manipulation in HTML and JavaScript. The core problem lies in attempting to access and modify a DOM element before the browser has fully parsed and rendered the HTML.  This is especially relevant when dealing with scripts placed within the `<head>` section or early in the `<body>`.

## Bug Description
The JavaScript code attempts to hide the div element with the id "myDiv." However, because the script executes before the element exists in the DOM, the `getElementById` method returns `null`, causing a silent failure or a JavaScript error in some browsers.

## How to Reproduce
1. Clone this repository.
2. Open `bug.html` in a web browser. 
3. Observe that the text within the div is visible, demonstrating the issue.

## Solution
The solution involves ensuring that the script executes *after* the DOM is fully loaded. This can be achieved using the `DOMContentLoaded` event listener.