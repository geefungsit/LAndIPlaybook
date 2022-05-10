# Chapter 0 - Basics
We start counting at 0.

## Step 0 - IDE
Go to https://jsbin.com/?js,console

## Step 1 - Hello
You can see your console on the right. We can output results from our computations there.

```js
console.log("Hello world!")
```

## Step 2 - Defining a function
As you saw in the presentation/demo we can make this more generic
For this we introduce a function: a reuseble pieces of code that accomplishes a specific task.

```js
function greet(addressee) {
  console.log("Hello " + addressee + "!")
}

greet("world")
```

## Step 3 - Additional parameters
Let's make it even more generic

We already saw a parameter in the last step. Parameters are inputs that functions operate on. Functions can have more than one parameter:

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

greet("Hello", "world")
```

*Task:* Say "Hello", then say "Good morning"

## Step 4 - Constants
One principle of software engineering is DRY (do not repeat yourself).
Let's extract reused constants: Pieces of data that do not change.

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

## Step 6 - Lists
Automation relies on doing the same thing over and over.
To do this we need to introduce lists (or rather arrays, don't worry about it).
Feel free to insert your team or your family (depending on what is more important to you).

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

const ADDRESSEE = "world"

const HOUR = 9

if(HOUR < 12) {
  greet("Good morning", ADDRESSEE)
} else if(HOUR >= 18) {
  greet("Good evening", ADDRESSEE)
} else {
  greet("Hello", ADDRESSEE)
}

const PEOPLE = ["person1", "person2", "person3"]

console.log(PEOPLE[0])
console.log(PEOPLE[1])
console.log(PEOPLE[2])
```

## Step 7 - Loop
In the real world there are lists with hundreds, thousands or much much more entries.
There has to be a better way to handle them. And there is! The for-loop:

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

const ADDRESSEE = "world"

const HOUR = 9

if(HOUR < 12) {
  greet("Good morning", ADDRESSEE)
} else if(HOUR >= 18) {
  greet("Good evening", ADDRESSEE)
} else {
  greet("Hello", ADDRESSEE)
}

const PEOPLE = ["person1", "person2", "person3"]

// read: "For each person of our list of people"
for (person of PEOPLE) {
  console.log("Hello", person)
}
```

*Task:* How to greet everyone according to the logic we established? Discuss

## Step 8 - Refactoring
You might have gotten to the following solution, which includes some repetition.

```js
function greet(greeting, addressee) {
  console.log(greeting + " " + addressee + "!")
}

const ADDRESSEE = "world"

const HOUR = 9

const PEOPLE = ["person1", "person2", "person3"]

if(HOUR < 12) {
  for (person of PEOPLE) {
    greet("Good morning", person)
  }
} else if(HOUR >= 18) {
  for (person of PEOPLE) {
    greet("Good morning", person)
  }
} else {
  for (person of PEOPLE) {
    greet("Hello", person)
  }
}
```

*Task:* Remember DRY? There are several ways to simplify our code. Discuss your ideas

## Step 9 - Variables
Refactoring code makes it easier to add new functionality.
This is one possible solution using variables: fields containing data that can change.

Note: We moved the time logic into the greet function because it "belongs there".
You may disagree. These are the things developers spend a lot of time discussing.

```js
function greet(addressee) {
  const HOUR = 9

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

for (person of PEOPLE) {
  greet(person)
}
```

*Task:* There is one constant here that should not be constant. Which one is it and what should we do about it?

## Step 10 - Built-in functions/libraries
Now we replace the hardcoded hour with the build-in function to get the current hour of the system clock.

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

for (person of PEOPLE) {
  greet(person)
}
```


## Step 11 - Objects
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

const person1 = {
  name: "Alice",
  beverage: "coffee"
}

const person2 = {
  name: "Bob",
  beverage: "tea"
}

const person3 = {
{
  name: "Eve",
  beverage: "orange juice"
}

console.log(person1.name)
console.log(person1.beverage)

const PEOPLE = [person1, person2, person3]
```

*Task 1:* Re-implement the previous functionality of greeting everyone

*Task 2:* Write and use a function that says "Here is your coffee/tea/…"


## Run locally
The js (and HTML files) are just plain text, there is nothing "magical" about them.
Copy the content to local files, rename them and open the HTML in the browser.

*Note:* Right now this won't do anything visible, because we are only logging in the console.
We'd need to tell the browser to display our results instead.
