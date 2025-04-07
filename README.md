# Introduction to JavaScript and DOM Manipulation

## Objectives

Write basic JavaScript functions.
Manipulate the DOM dynamically.
Respond to user interactions.

## Instructions

- Create a script.js file and link it to a HTML.
- Structure the document using DOCTYPE, html, head, and body.

>[!NOTE]
>  - Write JavaScript that:
>  - Changes text content dynamically.
>  - Modifies CSS styles via JavaScript.
>  - Adds or removes an element when a button is clicked.


# Tasks
- Create a well-structured HTML5 document.
- Use at least 5 different HTML elements.
- Ensure semantic correctness.

Happy Coding! 💻✨


Step 1: Create an HTML5 Document

First, let's structure our HTML5 document with semantic correctness and link to our script.js file.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Web Page</title>
    <link rel="stylesheet" href="styles.css"> <!-- Optional: for styling elements, create styles.css if needed -->
    <script src="script.js"></script>
</head>
<body>
    <header>
        <h1>Interactive Web Page</h1>
    </header>
    <nav>
        <button id="addElementBtn">Add Element</button>
    </nav>
    <main>
        <div id="content">
            <p id="dynamicText">Welcome to our interactive webpage!</p>
            <span class="hide-on-click">Click me to change my style!</span>
            <section>This is a section.</section>
            <article>This is an article.</article>
        </div>
    </main>
    <footer>
        <p>Footer Content</p>
    </footer>
</body>
</html>
Step 2: Create script.js

Next, let's write the JavaScript that accomplishes the tasks specified. This script will change text content dynamically, modify CSS styles, and add/remove elements based on user interaction.

// script.js
document.addEventListener('DOMContentLoaded', function() {
    // Change text content dynamically
    const dynamicText = document.getElementById('dynamicText');
    dynamicText.innerText = 'Hello, User!';

    // Modify CSS styles via JavaScript
    const clickMe = document.getElementsByClassName('hide-on-click')[0];
    clickMe.addEventListener('click', function() {
        this.style.backgroundColor = this.classList.toggle('highlight');
        this.style.color = this.classList.contains('highlight') ? 'white' : 'black';
    });

    // Add or remove an element when a button is clicked
    const addElementBtn = document.getElementById('addElementBtn');
    addElementBtn.addEventListener('click', function() {
        const newElement = document.createElement('p');
        newElement.textContent = 'New Content Added!';
        document.getElementById('content').appendChild(newElement);

        // Optionally, remove the last paragraph when clicked again
        if (document.getElementById('content').lastChild) {
            document.getElementById('content').lastChild.remove();
        }
    });
});
