# fetch api

- The fetch api provides an interface for fetch (sending/receiving) objects.

- It uses request and response objects

- The fetch() method is used to fetch a resource(data).

Syntax:
`let promise = fetch(url,[options])`

simple api fetch:
Example:

```let url = "https://cat-fact.herokuapp.com/facts"

let panda = async () => {
    let response = await fetch(url)
    console.log(response)
}
```
