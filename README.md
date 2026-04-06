# goit-js-hw-06

## Description

Homework for Topic 10: OOP — Classes. Practice using object methods with `this`, creating classes with private properties, and implementing class methods.

## Project Structure

```
goit-js-hw-06/
├── js/
│   ├── task-1.js
│   ├── task-2.js
│   └── task-3.js
├── .gitignore
├── .prettierrc.json
├── index.html
└── README.md
```

## How to Run

Open `index.html` in the browser and check the DevTools console for output.

## Tasks

### Task 1 — User Account

**File:** `task-1.js`

Before quitting, a developer broke the source code for managing user accounts in our food delivery service. Refactor the methods of the `customer` object by adding the missing `this` keyword when accessing object properties.

Use the starter code below and perform the refactoring. After the object declaration, method calls have been added. The console will display the results of their execution. Please do not change anything there.

```js
const customer = {
  username: "Mango",
  balance: 24000,
  discount: 0.1,
  orders: ["Burger", "Pizza", "Salad"],
  // Change code below this line
  getBalance() {
    return balance;
  },
  getDiscount() {
    return discount;
  },
  setDiscount(value) {
    discount = value;
  },
  getOrders() {
    return orders;
  },
  addOrder(cost, order) {
    balance -= cost - cost * discount;
    orders.push(order);
  },
  // Change code above this line
};

customer.setDiscount(0.15);
console.log(customer.getDiscount()); // 0.15
customer.addOrder(5000, "Steak");
console.log(customer.getBalance()); // 19750
console.log(customer.getOrders()); // ["Burger", "Pizza", "Salad", "Steak"]
```

Leave this code for mentor review.

**Mentor checklist:**

- Variable `customer` is declared
- The value of the `customer` variable is an object with properties and methods
- Calling `customer.getDiscount()` returns the current value of the `discount` property
- Calling `customer.setDiscount(0.15)` updates the value of the `discount` property
- Calling `customer.getBalance()` returns the current value of the `balance` property
- Calling `customer.getOrders()` returns the current value of the `orders` property
- Calling `customer.addOrder(5000, "Steak")` adds `"Steak"` to the `orders` array and updates the balance
- The `getBalance` method of the `customer` object uses `this`
- The `getDiscount` method of the `customer` object uses `this`
- The `setDiscount` method of the `customer` object uses `this`
- The `getOrders` method of the `customer` object uses `this`
- The `addOrder` method of the `customer` object uses `this`

---

### Task 2 — Storage

**File:** `task-2.js`

Create a class `Storage` that will create objects for managing a warehouse of goods. The class expects only one argument — an initial array of goods, which is stored in the created object as a private property `items`.

Declare the following class methods:

- `getItems()` — returns the array of current goods from the private property `items`.
- `addItem(newItem)` — accepts a new item `newItem` and adds it to the array of goods in the private property `items`.
- `removeItem(itemToRemove)` — accepts a string with the name of the item `itemToRemove` and removes it from the array of goods in the private property `items`.

Take the code below with instance initialization and method calls, and paste it after the class declaration to verify correct behavior. The console will display the results of their execution. Please do not change anything there.

```js
const storage = new Storage(["Nanitoids", "Prolonger", "Antigravitator"]);
console.log(storage.getItems()); // ["Nanitoids", "Prolonger", "Antigravitator"]
storage.addItem("Droid");
console.log(storage.getItems()); // ["Nanitoids", "Prolonger", "Antigravitator", "Droid"]
storage.removeItem("Prolonger");
console.log(storage.getItems()); // ["Nanitoids", "Antigravitator", "Droid"]
```

Leave this code for mentor review.

**Mentor checklist:**

- Class `Storage` is declared
- Method `getItems` is declared in the `Storage` class
- Method `addItem` is declared in the `Storage` class
- Method `removeItem` is declared in the `Storage` class
- The `items` property in the `Storage` class is declared as private
- The `getItems` method returns the value of the private `items` property of the calling instance
- The `addItem` method modifies the value of the private `items` property of the calling instance
- The `removeItem` method modifies the value of the private `items` property of the calling instance
- Calling `new Storage(["Nanitoids", "Prolonger", "Antigravitator"])` assigns an object to the `storage` variable
- The `storage` object does not have a public `items` property
- The first call to `storage.getItems()` right after initialization returns `["Nanitoids", "Prolonger", "Antigravitator"]`
- The second call to `storage.getItems()` after `storage.addItem("Droid")` returns `["Nanitoids", "Prolonger", "Antigravitator", "Droid"]`
- The third call to `storage.getItems()` after `storage.removeItem("Prolonger")` returns `["Nanitoids", "Antigravitator", "Droid"]`

---

### Task 3 — String Builder

**File:** `task-3.js`

Write a class `StringBuilder` that accepts one parameter `initialValue` — an arbitrary string, which is stored in a private property `value` of the created object.

Declare the following class methods:

- `getValue()` — returns the current value of the private property `value`.
- `padEnd(str)` — receives a parameter `str` (string) and appends it to the end of the private property `value` of the calling object.
- `padStart(str)` — receives a parameter `str` (string) and prepends it to the beginning of the private property `value` of the calling object.
- `padBoth(str)` — receives a parameter `str` (string) and adds it to both the beginning and the end of the private property `value` of the calling object.

Take the code below with instance initialization and method calls, and paste it after the class declaration to verify correct behavior. The console will display the results of their execution. Please do not change anything there.

```js
const builder = new StringBuilder(".");
console.log(builder.getValue()); // "."
builder.padStart("^");
console.log(builder.getValue()); // "^."
builder.padEnd("^");
console.log(builder.getValue()); // "^.^"
builder.padBoth("=");
console.log(builder.getValue()); // "=^.^="
```

Leave this code for mentor review.

**Mentor checklist:**

- Class `StringBuilder` is declared
- The `value` property in the `StringBuilder` class is declared as private
- Method `getValue` is declared in the `StringBuilder` class
- The `getValue` method returns the value of the private `value` property of the calling instance
- Method `padEnd` is declared in the `StringBuilder` class
- The `padEnd` method modifies the value of the private `value` property of the calling instance
- Method `padStart` is declared in the `StringBuilder` class
- The `padStart` method modifies the private `value` property of the calling instance
- Method `padBoth` is declared in the `StringBuilder` class
- The `padBoth` method modifies the value of the private `value` property of the calling instance
- Calling `new StringBuilder(".")` assigns an object to the `builder` variable
- The `builder` object does not have a public `value` property
- The first call to `builder.getValue()` right after initialization returns `"."`
- The second call to `builder.getValue()` after `builder.padStart("^")` returns `"^."`
- The third call to `builder.getValue()` after `builder.padEnd("^")` returns `"^.^"`
- The fourth call to `builder.getValue()` after `builder.padBoth("=")` returns `"=^.^="`

---

## Submission

- Link to the repository with source files
- Link to the live page on GitHub Pages
- Attached repository file in `.zip` format

## Requirements

- Code formatted with Prettier
- No errors or warnings in the browser console
- Project structure must match the specified schema exactly
