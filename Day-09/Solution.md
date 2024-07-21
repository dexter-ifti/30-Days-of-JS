### Day 9: DOM Manipulation

### Activity 1: Selecting and Manipulating Elements

#### Task 1: Select an HTML element by its ID and change its text content.
```html
<!-- HTML -->
<p id="myParagraph">Original text</p>

<!-- JavaScript -->
<script>
document.getElementById('myParagraph').textContent = 'New text';
</script>
```

#### Task 2: Select an HTML element by its class and change its background color.
```html
<!-- HTML -->
<div class="myDiv">Content</div>

<!-- JavaScript -->
<script>
document.querySelector('.myDiv').style.backgroundColor = 'lightblue';
</script>
```

### Activity 2: Creating and Appending Elements

#### Task 3: Create a new `div` element with some text content and append it to the body.
```html
<!-- JavaScript -->
<script>
let newDiv = document.createElement('div');
newDiv.textContent = 'This is a new div';
document.body.appendChild(newDiv);
</script>
```

#### Task 4: Create a new `li` element and add it to an existing `ul` list.
```html
<!-- HTML -->
<ul id="myList">
  <li>Item 1</li>
  <li>Item 2</li>
</ul>

<!-- JavaScript -->
<script>
let newListItem = document.createElement('li');
newListItem.textContent = 'Item 3';
document.getElementById('myList').appendChild(newListItem);
</script>
```

### Activity 3: Removing Elements

#### Task 5: Select an HTML element and remove it from the DOM.
```html
<!-- HTML -->
<div id="removeMe">Remove this element</div>

<!-- JavaScript -->
<script>
let elementToRemove = document.getElementById('removeMe');
elementToRemove.parentNode.removeChild(elementToRemove);
</script>
```

#### Task 6: Remove the last child of a specific HTML element.
```html
<!-- HTML -->
<ul id="myList">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<!-- JavaScript -->
<script>
let list = document.getElementById('myList');
list.removeChild(list.lastElementChild);
</script>
```

### Activity 4: Modifying Attributes and Classes

#### Task 7: Select an HTML element and change one of its attributes (e.g., `src` of an `img` tag).
```html
<!-- HTML -->
<img id="myImage" src="oldImage.jpg" alt="Old Image">

<!-- JavaScript -->
<script>
document.getElementById('myImage').src = 'newImage.jpg';
</script>
```

#### Task 8: Add and remove a CSS class to/from an HTML element.
```html
<!-- HTML -->
<div id="myDiv" class="oldClass">Content</div>

<!-- CSS -->
<style>
.newClass {
    color: red;
}
</style>

<!-- JavaScript -->
<script>
let myDiv = document.getElementById('myDiv');
myDiv.classList.remove('oldClass');
myDiv.classList.add('newClass');
</script>
```

### Activity 5: Event Handling

#### Task 9: Add a click event listener to a button that changes the text content of a paragraph.
```html
<!-- HTML -->
<button id="myButton">Click me</button>
<p id="myParagraph">Original text</p>

<!-- JavaScript -->
<script>
document.getElementById('myButton').addEventListener('click', function() {
    document.getElementById('myParagraph').textContent = 'Text changed!';
});
</script>
```

#### Task 10: Add a mouseover event listener to an element that changes its border color.
```html
<!-- HTML -->
<div id="hoverDiv">Hover over me</div>

<!-- CSS -->
<style>
#hoverDiv {
    width: 200px;
    height: 100px;
    border: 2px solid black;
}
</style>

<!-- JavaScript -->
<script>
document.getElementById('hoverDiv').addEventListener('mouseover', function() {
    this.style.borderColor = 'red';
});
</script>
```

### Feature Requests

1. **Text Content Manipulation Script**: Write a script that selects an HTML element by its ID and changes its text content.
```javascript
document.getElementById('elementID').textContent = 'New text content';
```

2. **Element Creation Script**: Create a script that demonstrates creating a new `div` element and appending it to the body.
```javascript
let newDiv = document.createElement('div');
newDiv.textContent = 'This is a new div element';
document.body.appendChild(newDiv);
```

3. **Element Removal Script**: Write a script that selects an HTML element and removes it from the DOM.
```javascript
let element = document.getElementById('elementID');
element.parentNode.removeChild(element);
```

4. **Attribute Modification Script**: Create a script that changes the attributes of an HTML element.
```javascript
document.getElementById('elementID').setAttribute('attributeName', 'newValue');
```

5. **Event Handling Script**: Write a script that adds event listeners to HTML elements to change their content or style based on user interactions.
```javascript
document.getElementById('buttonID').addEventListener('click', function() {
    document.getElementById('elementID').textContent = 'Content changed on click';
});
```

Thats it for today
