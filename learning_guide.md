# Introduction

[TypeScript](https://www.typescriptlang.org/), [SQLite](https://www.sqlite.org/index.html), and [TypeORM](https://typeorm.io/) are three powerful technologies that can help you build robust and scalable web applications with ease.

This learning guide will take a deep dive into these technologies, exploring their uses, benefits, and additional features. 
Whether you're a junior developer looking to expand your skill-set or a full-stack developer looking for new tools to add to your arsenal, this guide will provide you with the knowledge and resources you need adopt these tools.

# Motivation

You may be thinking, "Why should I learn TypeScript, SQLite, or TypeORM?".

Well, Typescript is a superset of Javascript, and allows you to write web applications in a robust way. Additionally, on the [Annual StackOverflow Developer Survey](https://survey.stackoverflow.co/2022/#most-loved-dreaded-and-wanted-language-love-dread), it has ranked in the top 5 most loved programming languages since 2017.

SQLite is a powerful database management system, that is lightweight, easy to use and portable (contained in one file). Similarly to Typescript, it has ranked top 5 most popular since 2017 and top 3 since 2020.

What remains, is a need to link these. This is where TypeORM comes in. TypeORM is an ORM (Object-Relational Mapper) that allows you to interact with a database in a more intuitive way.

# Background

It's important to have a basic understanding of two pivotal technologies. If these are unfamiliar to you, some reputable resources are provided below:

## JavaScript
- [Free codeacademy course](https://www.codecademy.com/learn/introduction-to-javascript)
- [W3schools tutorial guide](https://www.w3schools.com/js)
- [freeCodeCamp.org Follow-along Youtube course](https://www.youtube.com/watch?v=PkZNo7MFNFg)
[![](https://img.youtube.com/vi/PkZNo7MFNFg/maxresdefault.jpg)](https://www.youtube.com/watch?v=PkZNo7MFNFg)
## Databases
- [W3schools tutorial guide](https://www.w3schools.com/sql)
- [freeCodeCamp.org Follow-along Youtube course](https://www.youtube.com/watch?v=HXV3zeQKqGY)
[![](https://img.youtube.com/vi/HXV3zeQKqGY/maxresdefault.jpg)](https://www.youtube.com/watch?v=HXV3zeQKqGY)

# Typescript

Typescript is a superset of Javascript. This means that all Javascript code is valid Typescript code. However, since TypeScript adds additional features, not all Typescript code is valid Javascript code. This is why a basic understanding of Javascript helps in learning Typescript.

The main additional feature of TypeScript is that it's statically typed which means you can define the type of any variable. This allows the compiler to catch potential errors before they have a chance to occur.

A great way to get started with TypeScript from personal experience is to use the [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html), which has guides for all levels of experience and provides plentiful examples.
If this is too fast paced, you may find:
- [Free codeacademy course](https://www.codecademy.com/learn/learn-typescript)
- [Typescript playground](https://www.typescriptlang.org/play)

useful, as they provide a more gradual introduction. If you prefer a learning experience with more human interaction, this [follow-along Youtube course](https://www.youtube.com/watch?v=30LWjhZzg5) might be right up your alley.

Undeniably, the best way to learn any language, is to use it. To do so, you'll need a development environment.

---

## Development environment setup

### **Online IDE**

A fast way to get started is using an online IDE which allows you to write and execute code in your browser.
Some popular online IDEs are:
- [W3schools](https://www.w3schools.com/typescript/typescript_editor.php)
- [Codepen](https://codepen.io/pen/)
- [Repl.it](https://repl.it/languages/typescript)

### **Local IDE**
There are many IDEs that support TypeScript, but my favourite is [VS Code](https://code.visualstudio.com/).

I recommend setting up VS Code for Typescript using this video: [Installation video](https://www.youtube.com/watch?v=4zdBk6wisxc) (Includes Node.js and Typescript compiler installation).

Before continuing, you should:
- Install the [VS-Code TypeScript extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-next), and enabled it.
- Have node.js installed.
- Have executed
    
        npm install -g typescript
    in your terminal to install the TypeScript compiler globally.

A tool that will prove to be handy with TypeScript is `ts-node`.
This npm package allows you to execute Typescript code without having to compile it. 

To install it, run:

    npm install -g ts-node

Anytime you want to execute a Typescript file, you can do:

    ts-node <filename>

---

## TypeScript's features

TypeScript comes with several [built-in types](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html). Some of which include:
- `boolean`
- `number`
- `string`
- `any`
- `void`

**Note:** The `any` type allows you to assign **any** value to a variable. This is useful when you don't know the type of a variable at compile-time, however it is considered bad practice as it defeats the purpose of using TypeScript.

Example defining variables:

![](./assets/learning-guide/0.svg)

You can create your own types using the `type` keyword. 

For example:

![](./assets/learning-guide/1.svg)

In this example, the `Person` type is defined as an object with two properties, `name` of type `string` and `age` of type `number`.

An observation from this is that TypeScript treats types as sets of values that share something in common.

To show this using the previous example:

![](./assets/learning-guide/2.svg)

The `aircraft` is of type `Person` because it has the same properties as a `Person` object.

You can also define a type as a [union type](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#union-types). 

For example:

![](./assets/learning-guide/3.svg)

These type annotations are also useful when defining functions. With out previous example, if we wanted to define a function that takes a `Person` object and says Hello to them, we could do so like this:

![](./assets/learning-guide/4.svg)

Three additional key features that TypeScript unlocked for us are:
- [Interfaces](https://www.typescriptlang.org/docs/handbook/2/objects.html) used to define the structure of an object without specifying the implementation.
- [Classes](https://www.typescriptlang.org/docs/handbook/2/classes.html) used to define the structure and implementation of an object.
- [Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html) used to create reusable code (e.g. classes and functions) that can work with different types, rather than being tied to a single type.

These features are all very powerful, however they are beyond the scope of this guide and so will not be covered in detail.

Basic example using interfaces and classes:
![](./assets/learning-guide/5.svg)

Basic example which implements a stack data structure using generics:
![](./assets/learning-guide/6.svg)

Now that we have a basic understanding of TypeScript, we can begin to look at how to use it to connect to a database.

# TypeORM
You may be wondering where the SQLite section is. Conveniently, TypeORM has built in support for SQLite so it will handle the SQLite setup for us.

To get started, the most thoroudh way is to use the [TypeORM documentation](https://typeorm.io/). Additionally, there is a TypeScript example project provided by TypeORM  [here](https://github.com/typeorm/typescript-example).

I will outline the main steps required to get started with TypeORM and SQLite.

1. Setup a blank TypeScript project, following the steps outlined in the [Local IDE](#local-ide) section.

2. Install TypeORM, reflect-metadata, and the SQLite driver

        npm i typeorm reflect-metadata sqlite3 --save

3. Install development dependencies

        npm i --save-dev @types/node ts-node

4. Setup your directory like this:
![](./assets/learning-guide/7.svg)
`index.ts`, `data-source.ts`, `user.entity.ts` are empty files.

5. In your `tsconfig.json`, ensure the following settings are set:
![](./assets/learning-guide/8.svg)

In our bare-bones TypeORM project, we can now create a database. This exemplar database will store user information. Each user has an auto-generated `id`, `username`, `password`, and `create_time` (the time the user was created).

While basic, this database is enough to demonstrate the core functionality of TypeORM.

In `user.entity.ts`, define the `User` entity like this:

![](./assets/learning-guide/9.svg)

The best practice is to have all entity files end in `.entity.ts` for organisation purposes.

**Note** the use of [decorators](https://orkhan.gitbook.io/typeorm/docs/decorator-reference) (text prefixed by `@`) to define the table and column names. This is a feature of TypeORM for defining the structure of a database.

Now we can create a database connection in `data-source.ts`:
![](./assets/learning-guide/10.svg)

This is a good place to import `reflect-metadata` as it is guaranteed to be imported before any database operations are performed.

There may be other ways handle asynchronous database initialisation, but personally I define a function `ensureInitialisedDB`. This function is called in `index.ts` before any requests are made.

Finally, we can create a simple script to create a user, and fetch all users, in `index.ts`:

![](./assets/learning-guide/11.svg)

**Note** that the `await` keyword is used to wait for asynchronous database operations to complete.

A useful feature of TypeORM is that once we have created the user, we can access the auto-generated `id` of the `user`.

To run the script, either transpile it using

        tsc

or if you have installed `ts-node`, use:

    ts-node src/index.ts

# Most common TypeORM issue
![](./assets/learning-guide/error1.svg)

or

![](./assets/learning-guide/error2.svg)

There are three main causes of these issues:
- The database did not finish initialising before the first request was made. Remember it is an asynchronous process.
- You have not imported the `reflect-metadata` package in the global place of your app, e.g. `index.ts`.
- Entity paths are referecing the wrong file type. Try using:

        entities: [__dirname + '/../**/*.entity.{js,ts}']

    in your `data-source.ts` file.

# Conclusion

All three of the technologies we have looked at are powerful, and have a lot of potential. Additionally they are easy to learn given the amount of documentation available and resources provided in this guide.

TypeScript is a language that is very quickly evolving, which is great, however it can be difficult to keep up with the changes. This is an issue often encountered on StackOverflow, where the accepted answer is often outdated, even though it was written recently.

SQLite & TypeORM are both amazing tools, however they should not be your first choice when working on large scale applications. They are ideal for prototyping only. 

## Alternatives

There is no direct alternative to TypeScript, its a versatile language and it solves a specific JavaScript issue - type safety.

Possible SQLite [alternatives](https://survey.stackoverflow.co/2022/#section-most-loved-dreaded-and-wanted-databases):
- PostgreSQL
- MongoDB
- MySQL

TypeORM alternatives:
- Sequelize
- Mongoose
- LoopBack
- Prisma
- MikroORM

Thank you for reading this guide. I hope you have found it useful.






