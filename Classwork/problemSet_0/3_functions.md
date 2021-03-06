# c1. Functions

Topics
* [I. Why functions?](#i-why-functions)
* [II. Passing Arguments](#ii-passing-arguments)
* [III. Returning Values](#iii-returning-values)

Exercises
* [Exercise 0. goGreenies()](#ex0)
* [Exercise 1. arguments and parameters](#ex1)
* [Exercise 2. madLib()](#ex2)
* [Exercise 2. multiply()](#ex3)

---

## I. Why functions?

A **function** is a block of code that performs a task or calculates a value. This block of code is referred to by a name (e.g. `background()`). Functions are important in computer science for:

1. making code easier to read and understand
2. preventing code repetition

**Abstraction** in computer science is the process of organizing complex code into discrete, simple units. Writing functions is one example of abstraction at play: by grouping lines of code under the heading of a function name, we reduce the complexity of our program and make it easier to understand.

As an example, the function **newmanColors()** is an easy way to designate that we'll apply Newman colors to shapes (as opposed to **jesuitColors()** which might apply blue colors). The Newman function sets the stroke to Newman green and the fill to white:

```javascript
function setup() {
    createCanvas(400, 400);
}

function draw() {
    newmanColors();
    ellipse(100, 100, 50, 50);
}

function newmanColors() {
    stroke(0, 255, 0);
    fill(255);
}


```

**OVERVIEW for declaring and calling functions**

* We declare functions by typing:

  1. `function` followed by the
  2. `myFunctionName` (such as newmanColors)
  3. `()` parentheses
  4. `{` open curly bracket
  5. the body of the function (`stroke(...` etc. in the example above)
  6. `}` close curly bracket to end the function declaration

* Once our function is *declared*, then we need to actually use it, or *call it*. Since the browser is only looking for code in the setup() and the draw(), we call the function in the draw():

```javascript
// ... some other code

function draw() {
    newmanColors();

    // ... some more code
}
```

---

<a name="ex0"></a>
<pre>
<b>Exercise 0:</b>
Write a function, <b>goGreenies()</b>, that prints to the console, "Go Greenies!" and draws a green
ellipse where the cursor is. Call this function in the draw().
</pre>

```javascript
function setup() {
    createCanvas(400, 400);
}

function draw() {
    // call your function here
}

// define your function here
```

---

## II. Passing Arguments

Passing data to functions is very important in programming. Let's say we want to write a function, **greeting()** that can alert us with "Hello, [name]" where we can pass in a value for name.

We can pass values to functions by
* passing values in parentheses when we call the function (`greeting("Jenna");`).
* put variable names in the parentheses when we declare the function (`function greeting(name) { ...`);

```javascript
function setup() {
    createCanvas(400, 400);
}

function draw() {
    greeting("Jenna");   
}

function greeting(name) {
  alert("Hello, " + name);
}
```

**NOTE**
* Function **parameters** are the items listed in the function definition (`name`).
* Function **arguments** are the real values passed to (and received by) the function (`"Jenna"`).

It's possible to pass multiple arguments to a function. We do this by separating the values with parentheses:

```javascript
function setup() {
  createCanvas(400, 400);
}

function draw() {
  greeting("Jenna", "deBoisblanc");   
}

function greeting(firstName, lastName) {
  alert("Hello, " + firstName + " " + lastName);
}
```

---

<a name="ex1"></a>
<pre>
<b>Exercise 1:</b>
In the example above, what are the arguments? The parameters?
</pre>

<a name="ex2"></a>
<pre>
<b>Exercise 2:</b>
Write a function <b>madLib()</b> that takes 4 strings as arguments (noun, adjective, verb, noun),
creates a story, and prints the story to the console.
</pre>

```javascript

function setup() {
    createCanvas(400, 400);
}

function draw() {
    madLib( /* noun, adjective, verb, noun*/ );
}

// define madLib() function here

```

---

## III. Returning Values

So far we've only looked at functions that execute code, but they do not *return* or resolve into values. Now we're going to look at functions that do a calculation and *return* a value. We can use the keyword *return* to specify that functions should store a value in memory after they are called. Returning values is useful if you'd like a function to perform a calculation and use that calculation in your code.


**Step 1.** Use *return* keyword when you have a value that you'd like the function to return.

```javascript
function add(val1, val2) {
    return val1 + val2;
}
```

**Step 2.** When we call add(), we can set a variable *sum* equal to the function add() because add() returns a value:

```javascript
function setup() {
    var sum = add(100, 20);   // we can set sum equal to add() b/c it returns a value
    console.log(sum);
}

function draw() { }

function add(val1, val2) {
    return val1 + val2;
}
```

As another example, let's write a function **getCircleArea()** that has a parameter (radius) and *returns* the area of the circle.

```javascript
function getCircleArea(r) {
    return r * r * Math.PI;
}
```

Now let's call the function and print the result to the console.

```javascript
function setup() {
  console.log(getCircleArea(3));
  console.log(getCircleArea(5));
}

function draw() { }

function getCircleArea(r) {
    return r * r * Math.PI;
}
```

---

<a name="ex3"></a>
<pre>
<b>Exercise 3:</b>
Write a function <b>multiply()</b> that has two parameters and <em>returns</em> their product.
Use the <b>multiply()</b> function inside of the text() function to display the product of two
values on the canvas.

</pre>

```javascript

function setup() {
    createCanvas(400, 400);
}

function draw() {
    var v1 = 5;
    var v2 = 3;
    text(v1 + " * " + v2 + " = ", 100, 80);
    text( /* code goes here */ , 150, 80);
}

// define multiply function here

```
