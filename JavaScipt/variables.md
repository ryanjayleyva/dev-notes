# Variables

Variables are _container_ for storing data.

## JavaScript variables can be declared in 3 ways.

- `let` - is a modern variable declaration.
- `const` - is like `let`, but the value of the variable can’t be changed.
- `var` - is an old-school variable declaration. Normally we don’t use it at all, but still exist.

## let

The statement below declares a varialble with the name "message" using `let`:

```JavaScript
let message;
```

We can put some data into it by using the assignment operator `=`.

```JavaScript
let message;

message = "Hello, React!"; // store the string "Hello, React!" in the variable named message
```

The string is now saved into the memory area associated with the variable. We can access it using the variable name:

```JavaScript
let message;
message = "Hello! React!";

alert(message); // shows the variable content
```

To be concise, we can combine the variable declaration and assignment into a single line:

```JavaScript
let message = "Hello, React!"; // define the variable and assign the value

alert(message); // Hello, React!
```

We can also declare multiple variables in one line:

```JavaScript
let user = "RJ", age = 34, message = "Hello, React!";
```

For the sake of better readability, please use a single line per variable.

The multiline variant is a bit longer, but easier to read:

```JavaScript
let user = "RJ";
let age = 34;
let message = "Hello, React!";
```

Some people also define multiple variables in this multiline style:

```JavaScript
let user = "RJ";
    age = 34;
    message = "Hello, React!"
```

…Or even in the “comma-first” style:

```JavaScript
let user = "RJ"
  , age = 30;
  , message = "Hello, React!";
```

**Technically, all these variants do the same thing. So, it’s a matter of personal taste and aesthetics.**

We can put any value in the variable.

We can also change it as many times as we want:

```JavaScript
let message;

message = "Hello, React!";

message = "Hello, World!"; // value changed

alert(message);
```

When the value is changed, the old data is removed from the variable:

We can also declare two variables and copy data from one into the other.

```JavaScript
let hello = "Hello, React!";

let message;

message = hello; // copy "Hello, React!" from the hello into message

// now two variables hold the same data
alert(hello);
alert(message);
```

**NOTE** Declaring twice trigger an error.

A variable should be declared only once.

A repeated declaration of the same variable is an error:

```JavaScript
let message = "Hello, React!";

// repeated 'let' leads to an error
let message = "Hello, React!"; // SyntaxError: 'message' has already been declared
```

So, we should declare a variable once and then refer to it without `let`.

```JavaScript
let message = "Hello, React!";

message = "Hello, World!";
```

## const

To declare a constant (unchanging) variable, use `const` instead of `let`:

```JavaScript
const myBirthday = "02.18.1990";
```

Variables declared using `const` are called “constants". They cannot be reassigned. An attempt to do so would cause an error:

```JavaScript
const myBirthday = "02.18.1990";

myBirthday = "02.04.1990"; // error, can't reassign the constant!
```

When a programmer is sure that a variable will never change, they can declare it with `const` to guarantee and communicate that fact to everyone.

### Uppercase Constants

There is a widespread practice to use constants as aliases for difficult-to-remember values that are known before execution.

Such constants are named using capital letters and underscores.

For instance, let’s make constants for colors in so-called “web” (hexadecimal) format:

```JavaScript
const COLOR_RED = "#F00";
const COLOR_GREEN = "#0F0";
const COLOR_BLUE = "#00F";
const COLOR_ORANGE = "#FF7F00";

// ...when we need to pick a color
let color = COLOR_ORANGE;
alert(color); // #FF7F00
```

Benefits:

- `COLOR_ORANGE` is much easier to remember than `"#FF7F00"`.
- It is much easier to mistype `"#FF7F00"` than `COLOR_ORANGE`.
- When reading the code, `COLOR_ORANGE` is much more meaningful than `#FF7F00`.

When should we use capitals for a constant and when should we name it normally? Let’s make that clear.

Being a “constant” just means that a variable’s value never changes. But some constants are known before execution (like a hexadecimal value for red) and some constants are calculated in run-time, during the execution, but do not change after their initial assignment.

For instance:

```JavaScript
const pageLoadTime = /* time taken by a webpage to load */;
```

The value of pageLoadTime is not known before the page load, so it’s named normally. But it’s still a constant because it doesn’t change after the assignment.

In other words, capital-named constants are only used as aliases for “hard-coded” values.

## var

`var`, which was the original way variables were declared in JavaScript. var is similar to let in that variables assigned this way can be reassigned, but it has other quirks that were cleared up when the language introduced let and const. By and large, it is not used anymore. However, you will likely come across code which uses var at some point, so it is useful to know that it exists.

**NOTE:** There are subtle differences between `let` and `var`.

In older scripts, you may also find another keyword: `var` instead of `let`:

```JavaScript
var message = "Hello, React!"
```

## Variable Naming

There are two limitations on variable names in JavaScript:

- The name must contain only letters, digits, or the symbols `$` and `_`.
- The first character must not be a digit.

Examples of valid names:

```JavaScript
let userName;
let test123;
```

When the name contains multiple words, `camelCase` is commonly used. That is: words go one after another, each word except first starting with a capital letter: `myVeryLongName`.

What’s interesting – the dollar sign `$` and the underscore `_` can also be used in names. They are regular symbols, just like letters, without any special meaning.

These names are valid:

```JavaScript
let $ = 1; // declared a variable with the name "$"
let _ = 2; // and now a variable with the name "_"

alert($ + _); // 3
```

Examples of incorrect variable names:

```JavaScript
let 1a; // cannot start with a digit

let my-name; // hyphens '-' aren't allowed in the name
```

### Case Matters

Variables named `apple` and `APPLE` are two different variables.

### Non-Latin letters are allowed, but not recommended

It is possible to use any language, including Cyrillic letters, Chinese logograms and so on, like this:

```JavaScript
let имя = '...';
let 我 = '...';
```

Technically, there is no error here. Such names are allowed, but there is an international convention to use English in variable names. Even if we’re writing a small script, it may have a long life ahead. People from other countries may need to read it sometime.

### Reserved Names

There is a list of [reserved words](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#keywords), which cannot be used as variable names because they are used by the language itself.

For example: `let`, `class`, `return`, and `function` are reserved.

The code below gives a syntax error:

```JavaScript
let let = 5; // can't name a variable "let", error!
let return = 5; // also can't name it "return", error!
```

### An assignment without use strict

Normally, we need to define a variable before using it. But in the old times, it was technically possible to create a variable by a mere assignment of the value without using `let`. This still works now if we don’t put `use strict` in our scripts to maintain compatibility with old scripts.

```JavaScript
// note: no "use strict" in this example

num = 5; // the variable "num" is created if it didn't exist

alert(num); // 5
```

This is a bad practice and would cause an error in strict mode:

```JavaScript
"use strict";

num = 5; // error: num is not defined
```

### Name Things Right

Talking about variables, there’s one more extremely important thing.

A variable name should have a clean, obvious meaning, describing the data that it stores.

Variable naming is one of the most important and complex skills in programming. A glance at variable names can reveal which code was written by a beginner versus an experienced developer.

In a real project, most of the time is spent modifying and extending an existing code base rather than writing something completely separate from scratch. When we return to some code after doing something else for a while, it’s much easier to find information that is well-labelled. Or, in other words, when the variables have good names.

Please spend time thinking about the right name for a variable before declaring it. Doing so will repay you handsomely.

Some good-to-follow rules are:

- Use human-readable names like `userName` or `shoppingCart`.
- Stay away from abbreviations or short names like `a`, `b`, and `c`, unless you know what you’re doing.
- Make names maximally descriptive and concise. Examples of bad names are `data` and `value`. Such names say nothing. It’s only okay to use them if the context of the code makes it exceptionally obvious which data or value the variable is referencing.
- Agree on terms within your team and in your mind. If a site visitor is called a “user” then we should name related variables `currentUser` or `newUser` instead of `currentVisitor` or `newManInTown`.

Sounds simple? Indeed it is, but creating descriptive and concise variable names in practice is not.

### Reuse or Create?

And the last note. There are some lazy programmers who, instead of declaring new variables, tend to reuse existing ones.

As a result, their variables are like boxes into which people throw different things without changing their stickers. What’s inside the box now? Who knows? We need to come closer and check.

Such programmers save a little bit on variable declaration but lose ten times more on debugging.

An extra variable is good, not evil.

Modern JavaScript minifiers and browsers optimize code well enough, so it won’t create performance issues. Using different variables for different values can even help the engine optimize your code.
