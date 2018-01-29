# Execution Contexts and Lexical Environments

* **Syntax Parser** - A program that reads your code and determines what it does and if its grammar is valid.
* **Lexical Environment** - Where something sits physically in the code you write :
  * A lexical environment exists in programming languages in which **where** you write something is _important_.
* **Execution Context** - A wrapper to help manage the code that is running :
  * There are lots of lexical environments. Which one is currently running is managed via execution contexts. It can contain things beyond what you've written.
* **Name/Value Pair** - A name which maps to a unique value :
  * The name may be defined more than once, but only can have one value in any given **context**.
  * That value may be more name/value pairs.
* **Object** - A collection of name/value pairs :
  * The simplest definition when talking about **Javascript**.
* Global execution context creates 2 things :
  * Global object (in case of browsers it is also `window` object).
  * `this`
* In global environment - global object = `this`.

## Hoisting

```javascript
b(); // Called b!
console.log(a); // undefined

var a = "Hello World!";

function b() {
  console.log('Called b!');
}
```

### Behind the scenes

* Execution context is created in 2 phases :
  1. Creation Phase :
      * In creation  phase, JS engine sets up memory space for variables and functions.
      * All variables in JS, are initially set to `undefined`.
  2. Execution Phase :
      * Code executes. Function executes normally. But variables shows `undefined` (its initial vallue). Because execution of variable (`console.log(a);`) comes before its assignment to value.

## Undefined

```javascript
console.log(a); // Uncaught ReferenceError: a is not defined
```

**Means** - Variable has not been declared.

```javascript
var a;
console.log(a); // undefined
```

**Means** - Variable has been declared but has not been assigned any value yet.

* **Single threaded** - One command at a time.
* **Synchronous** - One at a time :
  * And in order...
  * Synchronous code means code executes one line at a time in the order it appears.