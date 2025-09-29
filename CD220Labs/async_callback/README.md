# async_callback Lab (Node.js + Callbacks)

This is the “async_callback” lab from the **CD220Labs / Cloud applications with Node.js & React** repository.  
This lab demonstrates asynchronous control flow using callbacks in Node.js.

> **Note**: This README assumes you are using **Node.js v20**.

---

## Table of Contents

- [Prerequisites](#prerequisites)  
- [Setup & Installation](#setup--installation)  
- [Running the Lab / Example](#running-the-lab--example)  
- [Project Structure](#project-structure)  
- [Key Concepts](#key-concepts)  
- [Usage Examples](#usage-examples)  
- [Troubleshooting / Tips](#troubleshooting--tips)  
---

## Prerequisites

- Node.js v20 (or a compatible LTS version)  
- npm (comes bundled with Node.js)  
- Basic familiarity with JavaScript, Node.js, and callbacks  

---

## Setup & Installation

1. Clone the repository (or navigate to this directory if already cloned):

    ```bash
    git clone https://github.com/ShaorongChen/lkpho-Cloud-applications-with-Node.js-and-React.git
    cd lkpho-Cloud-applications-with-Node.js-and-React/CD220Labs/async_callback
    ```

2. Install dependencies:

    ```bash
    npm install
    ```
    (If there is no `package.json`, you might not need this step; check the code.)

---

## Running the Lab / Example

To run the example(s) in this lab:

```bash
node index.js
# or
node app.js
```
---

## Key Concepts

In this lab you will see or practice:

* Asynchronous programming with **callbacks**
* Handling errors in callback functions (error-first callback style)
* Organizing nested callbacks (the “callback hell” problem)
* Simple control flow using callbacks (series, parallel, sequential execution)
* Converting callback-based code to more manageable patterns (if applicable)

---

## Usage Examples

Here are some example snippets / usage patterns you might find:

```js
// callback_example.js

function doSomething(arg, callback) {
  setTimeout(() => {
    if (!arg) {
      return callback(new Error("Missing argument"));
    }
    callback(null, `Result is ${arg}`);
  }, 500);
}

// Usage:
doSomething("hello", (err, result) => {
  if (err) {
    console.error("Error:", err.message);
  } else {
    console.log("Success:", result);
  }
});
```

You might also chain callbacks:

```js
doSomething("first", (err, res1) => {
  if (err) return console.error(err);
  doSomething("second", (err, res2) => {
    if (err) return console.error(err);
    console.log("Both done:", res1, res2);
  });
});
```

Make sure to test edge / error cases.

---

## Troubleshooting / Tips

* If you see syntax errors, double-check Node version (`node -v`)
* Watch out for missing `return` statements in callback error paths (to prevent “double callback”)
* To avoid deeply nested callbacks, consider refactoring into named functions or using libraries (or migrating later to promises/async-await)
* Use `console.log` or `debugger` to trace callback flow