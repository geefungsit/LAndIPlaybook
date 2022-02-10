# Chapter 0 - Basics
We start counting at 0.

## Step 0 - IDE
Go to https://playcode.io/empty/

## Step 1 - Hello

```js
console.log("Hello world!")
```

## Step 2 - Defining a function
As you saw in the presentation/demo we can make this more generic
(concat instead of interpolation bc. more basic/easier to understand)

```js
function greet(addressee) {
  console.log("Hello " + addressee + "!")
}

greet("world")
```

## Step 3 - Parameters
Let's make it even more generic

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

greet("Hello", "world")
```

*Task:* Say "Hello", then say "Good morning"

## Step 4 - Constants
One principle of software engineering is DRY. Let's extract reused constants.

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

const ADDRESSEE = "world"

greet("Hello", ADDRESSEE)
greet("Good morning", ADDRESSEE)
```

*Task:* What is the advantage of doing so?

*Hint:* Replace with Person/Group you want to greet

## Step 5 - Conditionals
How do you make software do different things depending on circumstances?

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

const ADDRESSEE = "world"

const HOUR = 9

if(HOUR < 12) {
  greet("Good morning", ADDRESSEE)
} else {
  greet("Hello", ADDRESSEE)
}
```

*Task:* Say "Good evening" instead at after 18 o' Clock

## Step 6 - Built-in functions/libraries
Now we replace the hardcoded hour with the build-in functionality to get the current hour of the system clock.

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

const ADDRESSEE = "world"

const HOUR = new Date().getHours()

if(HOUR < 12) {
  greet("Good morning", ADDRESSEE)
} else if(HOUR >= 18) {
  greet("Good evening", ADDRESSEE)
} else {
  greet("Hello", ADDRESSEE)
}
```

## Step 7 - Lists
Automation relies on doing the same thing over and over.
Feel free to insert your team or your family as input (whatever is more important to you).

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

const ADDRESSEE = "world"

const HOUR = new Date().getHours()

if(HOUR < 12) {
  greet("Good morning", ADDRESSEE)
} else if(HOUR >= 18) {
  greet("Good evening", ADDRESSEE)
} else {
  greet("Hello", ADDRESSEE)
}

const PEOPLE = ["person1", "person2", "person3"]

PEOPLE.forEach(person => console.log(person))
```

*Task:* How to greet everyone according to the logic we established? Discuss

## Step 8 - Variables
Refactoring code to make it easier to add new functionality

```js
function greet(addressee) {
  const HOUR = new Date().getHours()

  let greeting = ""

  if(HOUR < 12) {
    greeting = "Good morning"
  } else if(HOUR >= 18) {
    greeting = "Good evening"
  } else {
    greeting = "Hello"
  }

  console.log(greeting + " " + addressee + "!")
}

const PEOPLE = ["person1", "person2", "person3"]

PEOPLE.forEach(person => greet(person))
```

## Step 9 - Objects
Data is often structured in some way to match real life relations

```js
function greet(addressee) {
  const HOUR = new Date().getHours()

  let greeting = ""

  if(HOUR < 12) {
    greeting = "Good morning"
  } else if(HOUR >= 18) {
    greeting = "Good evening"
  } else {
    greeting = "Hello"
  }

  console.log(greeting + " " + addressee + "!")
}

const PEOPLE = [
{
  name: "person1",
  beverage: "coffee"
},{
  name: "person2",
  beverage: "tea"
},{
  name: "person3",
  beverage: "orange juice"
},
]

PEOPLE.forEach(person => greet(person.name))
```

*Task:* Write and use a function that says "Here is your coffee/tea/…"

# Chapter 1 - Strech goals
## UI
As seen in the presention/demo we can use our functions in a HTML file

## Run locally
The js and HTML files are just plain text, there is nothing "magical" about them.
Copy the content to local files, rename them and open the HTML in the browser
