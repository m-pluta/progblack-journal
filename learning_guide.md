# Introduction

[TypeScript](https://www.typescriptlang.org/), [SQLite](https://www.sqlite.org/index.html), and [TypeORM](https://typeorm.io/) are three powerful technologies that can help you build robust and scalable web applications with ease.

In this learning guide, we'll take a deep dive into these technologies, exploring their uses, benefits, and additional features. 
Whether you're a junior developer looking to expand your skill-set or a full-stack developer looking for new tools to add to your arsenal, this guide will provide you with the knowledge and resources you need adopt these tools.

# Motivation

You may be thinking, "Why should I learn TypeScript, SQLite, or TypeORM?".

Well, Typescript being a superset of Javascript, allows you to write web applications in a more robust and scalable way. Additionally, on the [Annual StackOverflow Developer Survey](https://survey.stackoverflow.co/2022/#most-loved-dreaded-and-wanted-language-love-dread), has consistently ranked in the top 5 most loved programming languages since 2017.

SQLite, similarly to Typescript has been ranked top 5 most popular since 2017 and top 3 since 2020. It is a powerful database management system, that is lightweight, easy to use and portable (self contained in a single file).

The only necessity remaining is a way to link these two technologies together. This is where TypeORM comes in. TypeORM is an Object Relational Mapper (ORM) that allows you to write SQL queries in TypeScript in a more intuitive way.

# Background

Before we get started, it's important to have a basic understanding of two pivotal technologies. Don't worry if these are unfamiliar to you, some reputable resources are provided below:

## JavaScript
- [Free codeacademy course](https://www.codecademy.com/learn/introduction-to-javascript)
- [W3schools tutorial guide](https://www.w3schools.com/js)
- [freeCodeCamp.org Follow-along Youtube course](https://www.youtube.com/watch?v=PkZNo7MFNFg)
[![](https://img.youtube.com/vi/PkZNo7MFNFg/maxresdefault.jpg)](https://www.youtube.com/watch?v=PkZNo7MFNFg)
## Databases
- [W3schools tutorial guide](https://www.w3schools.com/sql)
- [freeCodeCamp.org Follow-along Youtube course](https://www.youtube.com/watch?v=HXV3zeQKqGY)
[![](https://img.youtube.com/vi/HXV3zeQKqGY/maxresdefault.jpg)](https://www.youtube.com/watch?v=HXV3zeQKqGY)

# Typescript (550 words)

As mentioned before, Typescript is a superset of Javascript. This means that all Javascript code is valid Typescript code. However, since TypeScript adds additional features, not all Typescript code is valid Javascript code. This is why having a basic understanding of Javascript helps when learning Typescript.

The main additional feature of TypeScript is that it's statically typed which means that a variable's type is known before compile-time. This allows for more robust code, as the compiler can catch potential errors before they have a chance to occur.

There are many ways to get started with TypeScript.

A great way, from personal experience is to use the [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html), which has great guides for all levels of experience and provides plentiful examples.
If this is too fast paced, you may find:
- [Free codeacademy course](https://www.codecademy.com/learn/learn-typescript)
- [Typescript playground](https://www.typescriptlang.org/play)

useful, as they provide a more gradual introduction to TypeScript. If you prefer a learning experience with more human interaction, this [follow-along Youtube course](https://www.youtube.com/watch?v=30LWjhZzg5) might be right up your alley.

Undeniably, the best way to learn any language, is to use it, and in order to do so, you'll need to set up a development environment.

---

## Setting up a development environment

### **Using an online IDE**

A fast way to get started with writing Typescript is using an online IDE which allows you to write and execute code in your browser.
Some of the most popular online IDEs are:
- [W3schools](https://www.w3schools.com/typescript/typescript_editor.php)
- [Codepen](https://codepen.io/pen/)
- [Repl.it](https://repl.it/languages/typescript)

### **Using a local IDE**
There are many IDEs that support TypeScript, but my favourite is [VS Code](https://code.visualstudio.com/).

I strongly recommend setting up VS Code for Typescript according to this video: [Installation video](https://www.youtube.com/watch?v=4zdBk6wisxc) (Includes Node.js and Typescript compiler installation).

Most importantly, you should:
- Install the [VS Code TypeScript extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-next) following the enabling instructions.
- Have node.js installed.
- Have executed
    
        npm install -g typescript
    in your terminal to install the TypeScript compiler globally.

---

## TypeScript's features

TypeScript comes with several [built-in types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html). Some of which include:
- `boolean`
- `number`
- `string`
- `any`
- `void`
- `null`

**Note:** The `any` type allows you to assign any value to a variable. This is useful when you don't know the type of a variable at compile-time, however it is considered bad practice as it defeats the purpose of using TypeScript.

Example of defining variables:

![](./assets/learning-guide/0.svg)

You can also create your own types using the `type` keyword. For example, if you wanted to create a type for a person and use it, you could do so like this:

![](./assets/learning-guide/1.svg)

In this example, the `Person` type is defined as an object with two properties, `name` of type `string` and `age` of type `number`.

A fact that arises from this is that TypeScript treats types as sets of values that share something in common.

To show this using the previous example, an `aircraft` defined as follows:

![](./assets/learning-guide/2.svg)

is of type `Person` because it has the same properties as a `Person` object.

You can also define a type as a union of other types. For example, if you wanted to define a type that could be either a `string` or a `number`, you could do so like this:

![](./assets/learning-guide/3.svg)

These type annotations are also useful when defining functions. Going back to our previous example with people. If we wanted to define a function that takes a `Person` object and says Hello to them, we could do so like this:

![](./assets/learning-guide/4.svg)

Three other key features that TypeScript unlocked for us are:
- [Interfaces](https://www.typescriptlang.org/docs/handbook/2/objects.html)
- [Classes](https://www.typescriptlang.org/docs/handbook/2/classes.html)
- [Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)

These features are all very powerful, however they are beyond the scope of this guide and so will not be covered in detail.
Essentially:
- Interfaces are used to define the structure of an object without specifying the implementation.
- Classes are used to define the structure and implementation of an object.
- Generics are a way to create reusable code (e.g. classes and functions) that can work with different types, rather than being tied to a specific type.

Basic example using interfaces and classes:
![](./assets/learning-guide/5.svg)

Basic example which implements a stack data structure using generics:
![](./assets/learning-guide/6.svg)

Now that we have a basic understanding of TypeScript, we can begin to look at how to use it to connect to a database.



# TypeORM (350 words)
You may be wondering where the section for learning SQLite is. Conveniently, TypeORM has built in support for SQLite and so it will handle most of SQLite setup for us.


# Evaluation, Conclusion (130 words)





