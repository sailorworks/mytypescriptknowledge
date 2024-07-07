# Event handling
solving this problem to understand this topic

construct a toggle button-dark mode and light mode

simply you have to get the element id using `document.getElementById()`

```javascript
let modeBtn = document.querySelector("#mode");
let currMode = "light"; // Initialize with light mode

modeBtn.addEventListener("click", () => {
    if (currMode === "light") {
        currMode = "dark";
        document.querySelector("body").style.backgroundColor = "black";
    } else {
        currMode = "light";
        document.querySelector("body").style.backgroundColor = "white";
    }
    console.log(currMode);
});
```

- First we have accessed the html tag that has id mode and given to the variable modeBtn.
- Then a new var is created currMode that has string light in it.
- addEventListener is a method that waits for that particular event to occur.
- we have to pass event and function to this method.
- here we have created a function that has if else loop.
- querySelector accesses body tag and applies respective background color.