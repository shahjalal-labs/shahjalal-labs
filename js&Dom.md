## ✅ JavaScript (Core) Interview Questions

### 1. What is the difference between `==` and `===` in JavaScript?

```js
0 == "0"; // true  → value comparison (loose equality)
0 === "0"; // false → value + type comparison (strict equality)
```

---

### 2. Explain closures in JavaScript.

```js
function outer() {
  let count = 0;
  return function inner() {
    count++;
    return count;
  };
}

const counter = outer();
console.log(counter()); // 1
console.log(counter()); // 2
```

> Closure allows inner function to access variables of outer function, even after it has returned.

---

### 3. Difference between `var`, `let`, and `const`

```js
var x = 1; // function-scoped, hoisted
let y = 2; // block-scoped, not hoisted
const z = 3; // block-scoped, cannot be reassigned
```

---

### 4. What is event delegation?

```html
<ul id="list">
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

```js
document.getElementById("list").addEventListener("click", function (e) {
  if (e.target.tagName === "LI") {
    console.log("Clicked:", e.target.textContent);
  }
});
```

> Instead of adding listeners to every `<li>`, we use one listener on the parent `<ul>`.

---

### 5. How to create and insert a DOM element dynamically?

```js
const div = document.createElement("div");
div.textContent = "Hello!";
div.className = "greeting";
document.body.appendChild(div);
```

---

### 6. How does `this` behave in JavaScript?

```js
const person = {
  name: "John",
  greet() {
    console.log("Hi,", this.name);
  },
};
person.greet(); // "Hi, John"

const greetFunc = person.greet;
greetFunc(); // "Hi, undefined" (in non-strict mode, `this` is window/global)
```

---

### 7. Explain bubbling and capturing in DOM events.

```js
element.addEventListener("click", handler, true); // capturing phase
element.addEventListener("click", handler, false); // bubbling phase (default)
```

---

### 8. How to debounce a function in JavaScript?

```js
function debounce(fn, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => fn.apply(this, args), delay);
  };
}

window.addEventListener(
  "resize",
  debounce(() => {
    console.log("Resize event!");
  }, 300),
);
```

---

### 9. How do you clone an object in JavaScript?

```js
const obj = { a: 1, b: 2 };
const clone = { ...obj }; // shallow copy
const deepClone = JSON.parse(JSON.stringify(obj)); // deep copy (limited)
```

---

### 10. How to select elements and modify DOM content?

```js
const title = document.querySelector("h1");
title.textContent = "Updated Title";
title.style.color = "blue";
```

---

live site: edu-verse.surge.sh
github client:
github server:
