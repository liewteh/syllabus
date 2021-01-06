---
id: code-style-guide
title: Code Style Guide
sidebar_label: Code Style Guide
---

## Why should I read this?

There are many different ways of writing code that achieve the same goal. However, programmers generally agree that there are some ways of writing code that are more understandable and *readable* than other ways.

To help write more understandable code, programmers follow a *style guide*. It provides guidelines for how to write code, how to structure it, common problems to avoid, etc.

## Using Prettier to format code automatically

Some of the guidelines are so common that there are automatic tools to do it for you! One of these tools is called Prettier. You should have installed this tool when you [set up your VS Code extensions](https://docs.codeyourfuture.io/course-processes/before-the-course/getting-setup#extensions).

Prettier is a tool that rearranges your code (called *formatting*). It follows a set of rules that programmers have agreed make your code easier to read and understand.

You might have a common problem when running Prettier. If you see something like this:

![Invalid code with red highlight](./assets/prettier-error.png)

Then you have written some code that is invalid and Prettier can't format it. A common is a missing bracket, so try looking for that first.

## Indent your code

You may have noticed that programmers tend to *indent* their code by starting a line of code with some space.

Here's an example in HTML:

```html
<div>
  <p>Hello world!</p>
</div>
```

And JavaScript:

```js
if (isVegetarian) {
  return "Macaroni and Cheese";
} else {
  return "Steak and Chips";
}
```

Indentation helps us to read our code by visually marking how the code is going to run. Programmers rely on this extra information to quickly read and understand code.

There are some guidelines about where to add indentation. For example, lines of code are indented when they are inside a function, an `if` statement or a `for` loop. Additionally, if any of those structures are inside another structure, then they are indented further.

The guidelines about where to add indentation can be complex, but the good news is that **Prettier adds indentation automatically** for us! However it is good to pay attention to where indentation is added, as you may find yourself writing code in an environment where Prettier is not installed.

## Don't leave lots of commented out code

When you are debugging a problem, you might comment out some sections of your code.

```js
// 🛑 Don't do this!
function addToShoppingList(item) {
  // console.log("Shopping list before", shoppingList);
  // console.log("Adding item", item);
  shoppingList.add(item);
  // console.log("Shopping list after", shoppingList);
}
```

In this example, there is some extra debugging information that is commented out.

Once you have solved the problem, you should remove large sections of commented out code. When you (or someone else) are reading your code, you want to know only the important pieces. Removing commented out code helps find the relevant code faster and easier.

### Saving old versions with Git

You might be worried about "losing" some experimental code that you want to "save" by commenting it out. However, this can cause confusion about which bits of code still work.

If you want to save some code, remember that you can commit it using Git. It will then be saved it forever. If decide to remove the code later you can delete it and make another commit.

## Don't leave unused variables

As you write code, you may make changes to the variables that you are using. You may rename some variables, make some new variables or change how the variables are used. This may leave some variables that are *unused*.

```js
function orderTaxi(pickUpTime) {
  let driverName = getDriverName();
  let customerName = getCustomerName(); // 🛑 Don't do this!

  return `${driverName} will pick you up at ${pickUpTime}`;
}
```

In this example, the `customerName` variable isn't used anywhere.

You should remove any variables that are unused. This is because if you (or someone else) is reading your code, it can be confusing if you see a variable and then find out later that it isn't used. It could make you think that there's a bug, because the variable must have been put there for a reason!

## Think of good names for your variables

Making our code understandable by others is critical to being a programmer. One of the main tools in our toolbox is good naming for our variables and function names.

There are no strict rules to follow when thinking of variable names, but there are some general guidelines. 

:::tip 
When thinking about whether a variable name is good, try to imagine that you are reading the code again in the future and you have forgotten exactly how it works.

Do the variable names help explain what the code is supposed to do?
:::

### Use `camelCase`

When writing JavaScript, programmers tend to use a convention called *`camelCase`*. This means starting your variable name with a lower case letter, and then every "word" after that starts with an upper case letter.

- `startingLocation`
- `timeToDestination`
- `trafficOnRoute`

This convention makes it easier to read variables that have multiple "words".

### Avoid short names

Very short variable names can be difficult to understand since the purpose of the variable can be unclear. They are also difficult remember, especially if there are many similarly named variables. Try to avoid short names or abbreviations.

Here are some examples of **bad** names that you should avoid:

- Single letters like `x` or `y`
- Abbreviations like `evt` instead of `event`

### Describe what the variable is/does

A good variable name quickly explains what it represents to anyone reading the code. Try to describe what the variable is or what it does within in code.

```js
// 🛑 Try to avoid this
let song = true;

// ✅ This is (probably) better
let isPlaying = true;
```

In this example, the variable name `song` doesn't tell us what it is used for. The `isPlaying` variable name is better since it tells us  whether a song is playing or not.

```js
// 🛑 Try to avoid this
function percentage() {
  // ...
}

// ✅ This is (probably) better
function getPercentage() {
  // ...
}
```

In this example, the function calculates a percentage and returns it. Therefore it is good to name it using the "get" verb to show that it returns something.

### Remember that you are communicating with another programmer

Don't forget that the person reading your code probably has some understanding of the *context*. If your function is named `getCustomer`, it's probably fine to name variables `name`, `age`, etc instead of `customerName`, `customerAge`. You don't need to explain *everything*.

**Naming variables is more of an art than a science**. Often you need some experience reading other people's code before you get really good at it.

:::tip
When reading other people's code, think about the variable names. If the names are not clear, make sure you understand the code first, then think about what names you would use instead.
:::