### Understanding Callback hell

example:

```Javascript
function getData(dataId, getNextData) {
    //2s
    setTimeout(() => {
        console.log("data", dataId);
        if (getNextData) {
            getNextData();
        }
    }, 2000);
}

//callback hell
getData(1, () => {
    console.log("getting data2 ....");
    getData(2, () => {
        console.log("getting data3 ....");
        getData(3, () => {
            console.log("getting data4 ....");
            getData(4);
        });
    });
});
```

Certainly. Here's a brief explanation of the code:

1. `getData` function:

   - Takes a `dataId` and a callback function `getNextData`
   - Uses `setTimeout` to simulate a 2-second delay
   - Logs the `dataId` after the delay
   - Calls `getNextData` if provided

2. Main execution:
   - Calls `getData` for id 1
   - In its callback, calls `getData` for id 2
   - In id 2's callback, calls `getData` for id 3
   - In id 3's callback, calls `getData` for id 4

This creates a chain of nested callbacks, each waiting for the previous one to complete. The code fetches data sequentially: 1, then 2, then 3, then 4, with each step taking 2 seconds.

The nesting of these callbacks creates the "callback hell" structure, making the code harder to read and maintain as the chain of operations grows longer.

### Promises

To overcome the callback hell we use promises.

Promises have three states:

- Pending
- fulfilled(resolved)
- rejected

Syntax:

`let promise = new promise((resolve,reject)=>{...})`

- the arrow function here is a function with 2 handlers

- resolve and reject are callback functions provided by Js

Example:

```Javascript
let promise = new Promise((resolve, reject) => {
    console.log("this is promise");
    reject("this is an error");
})

```

Simple promise example

another Example with working api(not exactly api):

```javascript
function getData(dataId, getNextData) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("data", dataId);
      if (getNextData) {
        getNextData();
      }
      resolve("success");
    }, 5000);
  });
}
```

.then & .catch

`promise.then((res)=>{...})`

`promise.catch((err)=>{...})`

Example:

```Javascript
const getPromise = () => {
    return new Promise((resolve, reject) => {
        console.log("I am a promise");
        resolve("success");
    });
};

let promise = getPromise();
promise.then(() => {
    console.log("promise fulfilled");
});
```

It will log "I am a promise" immediately when getPromise is called, and then log "promise fulfilled" when the Promise resolves.

### Promise chaining

Example:

```Javascript
function asyncFunc1() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("data1");
      resolve("success");
    }, 4000);
  });
}

function asyncFunc2() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      console.log("data2");
      resolve("success");
    }, 4000);
  });
}

console.log("fetching data1....");
asyncFunc1().then((res) => {
  console.log("fetching data2....");
  asyncFunc2().then((res) => {
  });
});

```

Explanation:

- The main change is in the promise chain structure.
- After `asyncFunc1()` resolves, we return `asyncFunc2()` instead of nesting its `then`.
- We add another `then` to handle the resolution of `asyncFunc2`.

This creates a true promise chain where:

- `asyncFunc1` executes first
- When it completes, `asyncFunc2` is called
- When `asyncFunc2` completes, the final `then` is executed

This structure ensures that the promises execute sequentially, with each waiting for the previous one to complete before starting. It's more readable and easier to manage than nested promises.

Now promise chaining example to overcome callback hell in the above example:

```Javascript
function asyncFunc1() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            console.log("data1");
            resolve("success");
        }, 4000);
    });
    }
    function asyncFunc2() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            console.log("plata2");
            resolve("success");
        }, 4000);
    });
    }
//callback hell
// getData(1, () => {
//     console.log("getting data2 ....");
//     getData(2, () => {
//         console.log("getting data3 ....");
//         getData(3, () => {
//             console.log("getting data4 ....");
//             getData(4);
//         });
//     });
// });

console.log("fetching data1....");
    let p1 = asyncFunc1();
    p1.then((res) => {
        console.log("fetching data2....");
        let p2 = asyncFunc2();
        p2.then((res) => {});
    });
```

## Async Functions

An async function is a function that returns a Promise. It allows you to write asynchronous code using the await keyword inside it. This makes the asynchronous code look and behave more like synchronous code, which is easier to understand.

```Javascript
// Simulate an asynchronous operation using a Promise
function getData(dataId) {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            console.log("data", dataId);
            resolve("success");
        }, 2000);
    });
}

// Async-await
async function getAllData() {
    await getData(1);
    await getData(2);
    await getData(3);
}

getAllData();

```

instead of writing .then which was supposed to written when we used promise chaining await makes it wait.
