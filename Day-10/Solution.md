### Day 10: Event Handling


### Activity 1: Basic Event Handling

#### Task 1: Add a click event listener to a button that changes the text content of a paragraph.
```html
<!-- HTML -->
<button id="changeTextButton">Change Text</button>
<p id="textParagraph">Original text</p>

<!-- JavaScript -->
<script>
document.getElementById('changeTextButton').addEventListener('click', function() {
    document.getElementById('textParagraph').textContent = 'Text changed!';
});
</script>
```

#### Task 2: Add a double-click event listener to an image that toggles its visibility.
```html
<!-- HTML -->
<img id="toggleImage" src="image.jpg" alt="Image" style="display: block;">

<!-- JavaScript -->
<script>
document.getElementById('toggleImage').addEventListener('dblclick', function() {
    this.style.display = this.style.display === 'none' ? 'block' : 'none';
});
</script>
```

### Activity 2: Mouse Events

#### Task 3: Add a mouseover event listener to an element that changes its background color.
```html
<!-- HTML -->
<div id="mouseoverDiv">Mouse over me</div>

<!-- JavaScript -->
<script>
document.getElementById('mouseoverDiv').addEventListener('mouseover', function() {
    this.style.backgroundColor = 'yellow';
});
</script>
```

#### Task 4: Add a mouseout event listener to an element that resets its background color.
```html
<!-- HTML -->
<div id="mouseoutDiv" style="background-color: yellow;">Mouse out of me</div>

<!-- JavaScript -->
<script>
document.getElementById('mouseoutDiv').addEventListener('mouseout', function() {
    this.style.backgroundColor = '';
});
</script>
```

### Activity 3: Keyboard Events

#### Task 5: Add a keydown event listener to an input field that logs the key pressed to the console.
```html
<!-- HTML -->
<input id="keydownInput" type="text" placeholder="Type something">

<!-- JavaScript -->
<script>
document.getElementById('keydownInput').addEventListener('keydown', function(event) {
    console.log(`Key pressed: ${event.key}`);
});
</script>
```

#### Task 6: Add a keyup event listener to an input field that displays the current value in a paragraph.
```html
<!-- HTML -->
<input id="keyupInput" type="text" placeholder="Type something">
<p id="displayText"></p>

<!-- JavaScript -->
<script>
document.getElementById('keyupInput').addEventListener('keyup', function() {
    document.getElementById('displayText').textContent = this.value;
});
</script>
```

### Activity 4: Form Events

#### Task 7: Add a submit event listener to a form that prevents the default submission and logs the form data to the console.
```html
<!-- HTML -->
<form id="myForm">
  <input type="text" name="username" placeholder="Username">
  <input type="password" name="password" placeholder="Password">
  <button type="submit">Submit</button>
</form>

<!-- JavaScript -->
<script>
document.getElementById('myForm').addEventListener('submit', function(event) {
    event.preventDefault();
    let formData = new FormData(this);
    formData.forEach((value, key) => {
        console.log(`${key}: ${value}`);
    });
});
</script>
```

#### Task 8: Add a change event listener to a select dropdown that displays the selected value in a paragraph.
```html
<!-- HTML -->
<select id="mySelect">
  <option value="Option 1">Option 1</option>
  <option value="Option 2">Option 2</option>
  <option value="Option 3">Option 3</option>
</select>
<p id="selectedValue"></p>

<!-- JavaScript -->
<script>
document.getElementById('mySelect').addEventListener('change', function() {
    document.getElementById('selectedValue').textContent = `Selected: ${this.value}`;
});
</script>
```

### Activity 5: Event Delegation

#### Task 9: Add a click event listener to a list that logs the text content of the clicked list item using event delegation.
```html
<!-- HTML -->
<ul id="myList">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<!-- JavaScript -->
<script>
document.getElementById('myList').addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
        console.log(`Clicked item: ${event.target.textContent}`);
    }
});
</script>
```

#### Task 10: Add an event listener to a parent element that listens for events from dynamically added child elements.
```html
<!-- HTML -->
<div id="parentDiv">
  <button id="addButton">Add Item</button>
  <ul id="dynamicList"></ul>
</div>

<!-- JavaScript -->
<script>
document.getElementById('addButton').addEventListener('click', function() {
    let newItem = document.createElement('li');
    newItem.textContent = `Item ${document.getElementById('dynamicList').children.length + 1}`;
    document.getElementById('dynamicList').appendChild(newItem);
});

document.getElementById('parentDiv').addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
        console.log(`Clicked dynamic item: ${event.target.textContent}`);
    }
});
</script>
```

### Feature Requests

1. **Click Event Script**: Write a script that adds a click event listener to a button to change the text content of a paragraph.
```javascript
document.getElementById('buttonID').addEventListener('click', function() {
    document.getElementById('paragraphID').textContent = 'Text changed!';
});
```

2. **Mouse Events Script**: Create a script that handles mouseover and mouseout events to change the background color of an element.
```javascript
let element = document.getElementById('elementID');
element.addEventListener('mouseover', function() {
    this.style.backgroundColor = 'yellow';
});
element.addEventListener('mouseout', function() {
    this.style.backgroundColor = '';
});
```

3. **Keyboard Events Script**: Write a script that logs key presses and displays input field values using keydown and keyup event listeners.
```javascript
let input = document.getElementById('inputID');
input.addEventListener('keydown', function(event) {
    console.log(`Key pressed: ${event.key}`);
});
input.addEventListener('keyup', function() {
    document.getElementById('displayParagraphID').textContent = this.value;
});
```

4. **Form Events Script**: Create a script that handles form submission and change events on a select dropdown.
```javascript
let form = document.getElementById('formID');
form.addEventListener('submit', function(event) {
    event.preventDefault();
    let formData = new FormData(this);
    formData.forEach((value, key) => {
        console.log(`${key}: ${value}`);
    });
});

document.getElementById('selectID').addEventListener('change', function() {
    document.getElementById('displayParagraphID').textContent = `Selected: ${this.value}`;
});
```

5. **Event Delegation Script**: Write a script that demonstrates event delegation by handling events on dynamically added child elements.
```javascript
let parent = document.getElementById('parentID');
parent.addEventListener('click', function(event) {
    if (event.target.tagName === 'CHILD_TAG_NAME') {
        console.log(`Clicked item: ${event.target.textContent}`);
    }
});
```

Thats it for today
