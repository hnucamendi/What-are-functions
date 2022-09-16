# Functions. What are they?

Simply put a function in programming is like a container full of instructions. We can re-use this container and not have to worry about writing the instructions again and again. Since they are already in our function.

## Table of Contents

- [Vocabulary & Definitions](#Vocab)
- [Declaring a Function](#Delcaring-a-Function)
- [Invoking a Function](#Invoking-a-Function)
- [Anonymous Functions](#declaring-and-invoking-an-anonymous-function)
- [Using Variables in Functions](#using-arguments-and-parameters)

## Delcaring a Function

The Example given are very similar in other languages, but ill be digging deep into what functions look like in JavaScript. Not all languages have these types of functions.

Note about Functions in JavaScript: Functions can be assigned to variables, this is essential to understanding how to declare the [Arrow Function](#The-Arrow-Function) and the [Classic Non-Hoisted Function](#The-Classic-Non-Hoisted-Function)

### The Classic Hoisted Function

Check out how to call this type of Function [Here](#Invoking-Classic-Hoisted-Function)

```JavaScript
function helloWorld(){
  return "Hello World from a Hoisted Function"
}
```

### The Classic Non-Hoisted Function

Check out how to call this type of Function [Here](#Invoking-Classic-Non-Hoisted-Function)

```JavaScript
const helloWorld = function(){
  return "Hello World from a non-hoisted function"
}
```

### The Arrow Function

Check out how to call this type of Function [Here](#Invoking-Arrow-Function)

```JavaScript
const helloWorld = () => {
return "Hello World from an arrow function"
}
```

### [Why are there so many ways declare a function!](#why-are-there-so-many-ways-declare-a-function)

## Invoking a Function

A general key to invoking a function is that if a function is Hoisted, then it can be called before it is defined. Otherwise it must be called after the function definition [How to Define a Function](#delcaring-a-function). In this section ill show all the `valid` ways of invoking functions in JavaScript.

### Invoking Classic Hoisted Function

As you can see, hopefully this really describes what it means for a function to be Hoisted, the function declartion will always be read first, and because of this we can call the function before we declare it or after

```JavaScript
//Defining the function
function helloWorld(){
  return "Hello World from a Hoisted Function"
}

// Invoking the function after declaration
helloWorld() // returns "Hello World from a Hoisted Function"
```

```JavaScript
// Invoking the function before declaration
helloWorld() // returns "Hello World from a Hoisted Function"

//Defining the function
function helloWorld(){
  return "Hello World from a Hoisted Function"
}
```

### Invoking Classic Non-Hoisted Function

```JavaScript
//Defining the function
const helloWorld = function(){
return "Hello World from a Hoisted Function"
}

// Invoking the function after declaration
helloWorld() // returns "Hello World from a non-hoisted function"
```

### Invoking Arrow Function

```JavaScript
//Defining the function
const helloWorld = () => {
return "Hello World from an Arrow Function"
}

// Invoking the function after declaration
helloWorld() // returns "Hello World from an Arrow Function"
```

## Declaring and Invoking An Anonymous Function

Usually we dont create Anonymous Functions by themselves, so I will make a special section here to talk all about anonymous functions

```JavaScript
// Classic hoisted function with anonymous function
function add(a) {
  return function (b) {// This is the anonymous function => notice it has no variable name
    return a + b;
  };
}

//Invoking this function
console.log(add(1)(2)); //Returns 3
```

```JavaScript
// Classic Non-Hoisted with anonymous function
const add = function (a) {
  return function (b) { // This is the anonymous function => Notice its very similar to the example above
    return a + b;
  };
};

console.log(add(4)(3)); //Returns 7
```

```JavaScript
const add = (a) => {
  return (b) => { // This is the Anonymous function
    return a + b;
  };
};

console.log(add(3)(4)); //Returns 7

// The Cool thing about Arrow Functions is they are used to write Functions in shorthand like below

const add = (a) => (b) => a + b; // The `(b) =>` is the anonymous function
//This is called a one liner and its a very modern way of writing JS

console.log(add(3)(3)); // Returns 6
```

## Using Arguments and Parameters

```JavaScript
// Classic Hoisted Function with Parameters and Arguments
function sayHello(name) {
  return 'Hello ' + name;
}

console.log(sayHello('Osiel')); //Returns "Hello Osiel"
```

```JavaScript
// Classic Non-Hoisted Function with Parameters and Arguments
const sayHello = function(name) {
  return 'Hello ' + name;
}

console.log(sayHello('Harold')); //Returns "Hello Harold"
```

```JavaScript
// Arrow Function with Parameters and Arguments
const sayHello = (name) => {
  return 'Hello ' + name;
}

console.log(sayHello('Samny')); //Returns "Hello Samny"

// The shorthand would be like so:
const sayHello = (name) => 'Hello ' + name;
```

## Vocab

- Hoisted
  - Meaning to be tied up to something [Hoisted Definition](https://www.google.com/search?q=hoisted+definition&rlz=1C5GCEM_en&oq=hoist&aqs=chrome.0.69i59j69i57j46i433i512j0i131i433i512j46i175i199i512j46i131i199i433i465i512j0i512j0i131i433i512j0i512j46i175i199i512.1202j0j7&sourceid=chrome&ie=UTF-8). In Coding this translates to function that is tied to the top of the screen, so no matter what comes before it a `Hoisted function` will always be read first.
- Function
  - A way of grouping code so that we can later invoke or call this group of code and not have to re-write any code
- Anonymous
  - An anonymous function is a function without a variable name or identifier, They are fundamental for more advanced code. Here is an [example](#declaring-and-invoking-an-anonymous-function)
- Keywords / Reserved Words
  - Return Keyword
    - Used to return a value but not print it, it will be assigned to the variable that the function is held in
- Arguments
  - Arguments are passed in a function call (when invoking a function) to be used in the code the function executes. These variables are local to the specefic function
- Parameters
  - Parameters are used in a function definition to initialize local variables that are expected to be passed in later when calling(invoking) the function

## FAQ

### Why are there so many ways to declare a function!

Learning about all the ways to call(invoke) a function can be overwhelming, but you dont really need to remember all the possible ways to make / call functions, as long as you find a method that you like. The reason there are so many different options is because:

1. JavaScript is used for Frontend, Backend, Infrastructure, and almost anything else that a computer for system may need JavaScript is built to be shaped into any code base. So this means there are lot of ways to do the same thing, because of how JavaScript has evolved.
2. JavaScript is what we call an Unopinionated language, meaning JavaScript doesnt care how you get things done, as long as you get it done. There other languages like [Go](https://go.dev/) that are very opinionated meaning Go will not let you get away with writing code how you want; in a language like Go you need to follow strict guidlines and follow established practices.
