# **Week 1** \~ 30/01 - 05/02

This week was not a very productive week but that was as expected. The assignment just got released on Wednesday, and so the main part of this week was spent thinking about what project to do.

From the beginning I had a feeling that I would want to work collaboratively with people from the course rather than online on an open source project. I had found a group of people to work with quite fast due to working with them on another coursework so that worked out well.

We all shared a similar interest which was we wanted to learn *TypeScript* and so it didnt take long for us to start brainstorming ideas.

We came up with a short list of ideas:
- VS-Code Extension
- VR Application
- P2P Messenger using Typescript
- Something using image recognition
- Split into two groups, one group creating a virus and another creating a detector

After coming up with this vague list, we decided it would be best to break off for the weekend to have some to reflect and potentially come up with better ideas in the following week.

We organised to meet up tomorrow (Monday 6th) after our ADS lecture in the morning.

# **Week 2** \~ 06/02 - 12/02

Following the weekend break, we all came to the conclusion that we were definitely going to be doing something to do with TypeScript and came up with a few more TypeScript related ideas which were:
- Mock banking system + database
- TypeScript or New Framework

From this list we chose the 2 projects which were most promising and they were:
- P2P Messenger using Typescript
- Mock banking system + database

We decided that the Mock banking system was the more promising project as it would allow us to learn and use a larger variety of technology.

Now that the project was decided, we established a relatively clear plan of action:
- Week 3
    - Learn TypeScript and certain technologies using typescript e.g. npm, VS-Code 
- Week 4:
    - Create front end
    - Learn basics of SQL
- Week 5:
    - Make an entity relationship diagram (ERD) for database
    - Start making backend
    - Learn specific functions of SQL related to our needed functionality
- Week 6
    - Complete backend and login system
- Week 20:
    - Polish front end
    - Fix bugs

... and set some goals for our project:
1. Learn TypeScript
2. Learn SQL
3. Write legible code with comments that any coder could understand
4. Create a functional website linked to a database
5. Create a login system for the website

Now that we had a plan and goals, we decided to create an organisation on GitHub and we named it [LMC-Enjoyers](https://github.com/LMC-Enjoyers). 

We finished off our meeting and agreed that next week's focus should be on learning TypeScript.

# **Week 3** \~ 13/02 - 19/02

I started the week by starting to learn TypeScript.
My first google search was 'learn typescript' and it led me to a free [codeacademy](https://www.codecademy.com/learn/learn-typescript) course which very quickly introduced me to the language.
Things I learnt:
- Basic syntax of TypeScript
- How to transpile TS to JavaScript
- Benefits of type-safety which was a familiar concept to me due to being proficient with Java.
- Uses of the .tsconfig file
- Parameter annotations
- Return types
- How to write documentation for TS functions

Overall this course was quite nice, but it felt like the learning was too slow so didnt end up finishing it. It felt much like a playground for learning TS in a fun way.

I decided to switch up the pace by going to the official [TypeScript documentation](1https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes-oop.html) which had a dedicated guide for people learning TS with a background in a statically typed language like Java.

This was actually a really interesting read, and it highlighted two main things:
- TypeScript treats types as sets of values that share something in common
- The type system is fully erased at runtime.

e.g. If you had two interfaces and two log functions:
```TypeScript
interface Car {
    speed: number;
    wheels: number;
}

interface Bird {
    name: string:
    wings: number;
}

function logCar(c: Car) {
  console.log("speed = " + c.speed + ", wheels = " + c.wheels);
}
 
function logBird(b: Bird) {
  console.log("name = " + b.name + ", wings = " + b.wings);
}
```
and a custom object `obj`
```TypeScript
const obj = {
    name: 'Boeing 737-700',
    speed: 828,
    wheels: 3,
    wings: 2
};
```
then these two function calls will surprisingly work
```TypeScript
logCar(obj);
logBird(obj);
```
because `obj` has properties from both interfaces so it can be treated as those interfaces.

> The relationships between types are determined by the properties they contain, not whether they were declared with some particular relationship.

Additionally, if you had a class called `Car`
```TypeScript
class Car {
    wheels: number;
    speed: number;
    drive() {
    }
}
```
then the result of calling
```TypeScript
typeof (new Car())
```
will be `"object"` and not `Car` or `"Car"`

During the week, me and my team also updated our timeline to include what our current progress was and it was in line with our plan

# **Week 4** \~ 20/02 - 26/02

This week we created a git repo in our organisation and assigned each person their roles.

We also met up on Wednesday for a short meeting and made a few key points:
- Just learning Typescript is not enough
- Decided to use a new framework - React
- Switch from using a SQL server to SQLite which is more appropriate for a small project like ours and is more portable which allows for independent development.

We created the group's repository in our organisation on Github and spent some time tweaking everyone's permissions so that changes would be made by create pull requests.

We also collaborated together on a discord call and created a mockup of our UI/UX design for the website.
![Mockup of UI/UX design](./assets/mockup.png)

Next week, our plan is to start working on actually implementing this mockup using React and Typescript into a working prototype. This plan may be a bit ambitious though due to other coursework potentially affecting the workflow.

# **Week 5** \~ 27/02 - 02/03

This week was busy just as expected, and not much was really done towards the project.
I was mainly consumed by my CT coursework trying to optimise my SAT solver for the SAT race (which fortunately was very successful).

Over the weekend a few people in my group started to work on the front-end implementation of the website, which turned out okay. The website matched 
the mockup really well, but it was really unresponsive and didn't accomodate for different viewports at all. As a group we decided to postpone front-end for some time and to focus on other components of the app.

In the next week I will focus on improving my knowledge in TypeScript and developing a way for our app to interact with a back-end SQLite database.

