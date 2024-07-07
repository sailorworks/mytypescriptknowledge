# Document Object model

DOM is a tree structure of objects [you can find it here](https://www.freecodecamp.org/news/content/images/2024/01/9-dom-example.png)

html elements can be accessed by JS in the form of objects. These objects are present in document and document is present in window that by default present because of the browser.

console.log -> print

console.dir -> document -> methods/properties

try these in the console
`console.dir(document)`
`console.dir(document.body)`
Here you'll be able to access every element you've written in body using js.

- A really good example of dom is of dark and light mode - There are certain changes that needs to be done in css that can be only done using dom we make changes using javascript.

### Selecting with id

`document.getElementById('myId')`

This will return the element with the id you've written in the html file.

### Selecting with class

`document.getElementsByClassName('myClass')`

This will return an array of elements with the class you've written in the html file.

### Selecting with tag

`document.getElementsByTagName('tag')`

This will return an array of elements with the tag you've written in the html file.

### Query Selector

`document.querySelector('myId/myClass/tag')`

This will return the first element that matches the selector.

`document.querySelectorAll('myId/myClass/tag')`

This will return an array of elements that matches the selector.

### Properties

`element.tagName`

This property returns the tag name of the element in uppercase. It is useful for identifying the type of element node you are working with.

`element.innerText`

This property returns the text content of the element and all its children. It respects the styling of the text, such as hidden elements not being included in the returned value.

`element.innerHTML`

This property returns the HTML content of the element as a string. It allows you to get or set the HTML markup inside the element.

`element.textContent`

This property returns the textual content of the element and all its descendants. It includes text even from hidden elements, providing a way to access the full text content within the element.

### Getting and Setting Attributes

`element.getAttribute(attr)`

This method returns the value of the specified attribute on the element. If the attribute does not exist, it will return `null`.

Example:

```javascript
let value = element.getAttribute("href");
```

`element.setAttribute(attr, val)`

This method sets the value of the specified attribute on the element. If the attribute does not exist, it will create it.

Example:

```javascript
element.setAttribute("class", "newClass");
```

### Style

`element.style`

This property allows you to get or set the inline style of the element. It provides access to all the CSS properties as camelCase.

Example:

```javascript
element.style.color = "blue";
```

### Inserting Elements

`node.append(el)`

This method adds the specified element at the end of the node (inside).

Example:

```javascript
node.append(newElement);
```

`node.prepend(el)`

This method adds the specified element at the start of the node (inside).

Example:

```javascript
node.prepend(newElement);
```

`node.before(el)`

This method adds the specified element before the node (outside).

Example:

```javascript
node.before(newElement);
```

`node.after(el)`

This method adds the specified element after the node (outside).

Example:

```javascript
node.after(newElement);
```

### Deleting Elements

`node.remove()`

This method removes the node from the DOM.

Example:

```javascript
node.remove();
```
