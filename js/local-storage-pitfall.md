```js
// TLDR:
// If storing anything other than string...
// Always stringify and parse it

// bad
localStorage.setItem("flag", false);
// will be interpret as truthy later on (because it become a string?)
localStorage.getItem("flag");

// good
localStorage.setItem("flag", JSON.stringify(false));
JSON.parse(localStorage.getItem("flag"));
```
