# I: What is Javascript

Javascript is a HIGH-LEVEL, PROTOTYPE-BASE OBJECT-ORIENTED, MULTI-PARADIGM, INTERPRETED OR JUEST-IN-TIME COMPLIED, DYNAMIC, SIGNLE-THRAEDED, GARBAGA-COLLECTED PROGRAMMING LANGUAGE with first-class functions and a non-blocking event loop concurrency model

## 1. HIGH-LEVEL

高级语言意味着 Javascript 不需要像 C/C++那般仔细地通过代码实现硬件/内存资源的管理，而是借助于语言本身的内部内存管理机制自动管理，带来的结果就是 JavaScript 运行时间永远不能比 C/C++快，也无法进行内存优化。

### 1.1 Garbage-collected

其中一个 JavaScirpt 内存管理工具成为垃圾回收，即 JavaScipt 会自动删除旧的和未使用的对象。
PS: JavaScript 中几乎所有的东西（数组，函数）都是对象（Object)，(字符串，数字不是)

### 1.2 Interpreted or Just-In-Time compiled

## 2. Multi-paradigm (多范式)

Paradiugm: An approach and mindset of structuring code, which will direct your coding style and technique
(范式是指代码格式)
JavaScirpt 多种代码范式，一般的范式分为：

1. Procedural Programming (程序化编程)
2. Object-oriented programming (OOP) （面向对象编程）
3. Functional programming （函数式编程，即基于函数的代码编程）

另外一种分类方式为：

1. Imperative (命令式)
2. Declarative （声明式）

## 2. PROTOTYPE-BASE Object-oriented

JavaScript 中几乎所有的东西（数组，函数）都是对象（Object)，(字符串，数字不是), 而对象的创建是通过原型继承（prototype-inheritance)实现的, 原型中包含了对象可调用的方法

<div align="center">
<img src="https://github.com/chaksw/Javascript-Beginner/blob/main/imgs/Prototype-base.png?raw=true" width=80%>
</div>

## 3. First-Class function

函数在 JavaScript 中被视为常规变量，也意味着它们可以被当作另一个函数函数的输入参数，也可以作为函数的返回值

<div align="center">
<img src=https://github.com/chaksw/Javascript-Beginner/blob/main/imgs/first-class-fcuntion.png?raw=true" width=80%>
</div>

## 4. Dynamic

在 JavaScript 的变量为动态变量 （弱类型语言），也就是说变量可以定义为任何变量类型，因此一个变量可以被赋值为整形，浮点型，字符串。而 JavaScript Engine 只有在代码执行阶段才会确认变量类型。
PS：typescript 为强类型语言，即需要在定义变量时声明变量类型

## 5. Single-threaded （单线程）& Non-blocking event loop concurrency model（非阻塞事件循环并发模型）

JavaScript 本身运行在一个单线程中，（一次只能执行一个指令（处理器执行代码）），所以我们需要一个处理多个任务同时出现的场景的手段，这就是 Non-blocking event loop concurrency model（非阻塞事件循环并发模型），简单来说就是将一些任务（如数据处理）放在后台执行，在这些任务执行完毕后。

# Principle

-   Values, using 'let'to define variable

```js
let firstName = "Jonas";
console.log(firstName);
```

-   Do not name a variable start with **high case**, unless is an Object
-   Do not name a `name` varialbe, is illeage in javascript

## Data primitive type

Javascript has dynamic typing: We do not have to manually define the data type of the value stored in a variable, Instead, data types are determined automatically.

1. Number. In javascript, all number is floating point numbers, which means they have always decimal, even
   if we don't see them or we don't define them

```js
let age = 23;
```

1. `String`: Sequence of characters, in javascript, double quote and single quote have the same function

```js
let lastName = "Jojo";
```

2. `Boolean`: Logical type that can only be true or false

```js
let fullAge = true;
```

3. `Undeined`: Value taken by a variable that is not yet defined (empty value)

```js
let children; undefined value
```

4. `Null`: Also means 'empty value' but not the same as undfined

```js
let parent = null;
```

5. `Symbol`(ES2015): Value that is unique and cannot be changed []

6. `BigInt` (ES 2020): Larger integers than the Number type can hold

## Other 2 ways to declare variable

1. use key word `const` to declare constant, any constant declared must have value assigned when we define them and could not be changed in anytime and anycase in the future.

```js
const age2 = 40;
```

2. se `var` to define variable, it seems like using `let`, but they have many differences simply saying is that, `let` is block scoop, and `var` is function scoop

```js
var job = "programmer";
```

## Operator

### Assignment operator

```js
let x = 10 + 5;
x += 10; // x = x + 10 = 25
x *= 4;
x++;
x--;
x--;
```

### Conmparison operators

```js
console.log(ageJonas > ageSarah); // >, <, >=, <=
```

### Strings and Template Literals

```js
const firstName = "Jonas";
const job = "teacher";
const birthYear = 1991;
const year = 2037;
const jonas = "I'm " + firstName + ", a " + (year - birthYear) + " years old " + job + "!";
console.log(jonas);
// A better way to do that - template literals (ES6 feature)
const jonasNew = `I'm ${firstName}, a ${year - birthYear} years old ${job}!`;
console.log(jonasNew);
```

### Type conversion `Number()`, `String()`

use `Number()` to convert string

```js
const inputYear = `1991`;
console.log(Number(inputYear) + 18); // to number
console.log(inputYear + 18);
```

When a string can not be logically converted to a number, `Number()` will return `NaN`, `NaN` is still a number, means invalid number

```js
console.log(Number(`Jonas`));
console.log(typeof NaN); //
```

use `String()` convert number to string

```js
console.log(String(23)); //
```

### Type coercion

-   minus(`-`) will cause type coercion to convert string to number

```js
console.log(`I am ${23} years old`);
console.log(`23` - `10` - 3);
```

-   plus(`+`) will also cause type coercion, but it's will convert number to string

```js
console.log(`23` + `10` + 3);
```

-   mutiplier(`*`) will cause type coercion to convert string to number

```js
console.log(`23` * `2`);
```

-   division(`/`) will cause type coercion to convert string to number

```js
console.log(`23` / `2`);
```

#### Exmaple

```js
let n = `1` + 1; // plus cause type coercion to convert number to string, so the result is '11';
n = n - 1; // minus will cause type coercion to convert string to number, so the result is 11 - 1 = 10
console.log(n);
console.log(2 + 3 + 4 + `5`); // 95
console.log(`10` - 2 - `3` - `4` + `5`); // 15
```

### Truthy and Falsy values

Five **falsy** value in javascript: `0`, `''`, `undefined`, `null`, `NaN`

```js
console.log(Boolean(0)); // number 0
console.log(Boolean("")); // null string
console.log(Boolean(undefined)); // value undefined
console.log(Boolean(null)); // null value
console.log(Boolean(NaN)); // invalid number
```

**NOTE:** Empty Object is also true

```js
console.log(Boolean({})); // return true
```

#### Example

```js
const money = 0;
if (money) {
    // money = 0 is a falsy value
    console.log("Don't spend it all ;)");
} else {
    console.log("You should get a job.");
}

let height;
if (height) {
    // undfined value is also falsy value
    console.log("YAY! Height is defined");
} else {
    console.log("Heigh is undefined");
}
```

### Equality Operator `===`, `==`

`===` equality operator is a strict equality operator, and it do not do the type coercio, which means it's will compare value and data type

```js
const age = 18;
if (age === 18) {
    console.log("You just became an adult :D");
}
```

`==` equality operator is loose strict equality operator, and it do the type coercion, which means i**t's will only compare the value after type conversion**

```js
if ("18" == 18) {
    console.log("it is not a strict equality operator");
}

if ("18" === 18) {
    console.log("it is not a strict equality operator");
} else {
    console.log("it is a strict equality operator");
}
```

### A MessageBox that accept content (string) from user

```js
const favourite = Number(prompt("What's your favourite number ?"));
console.log(favourite);
console.log(typeof favourite);
if (favourite === 23) {
    console.log("Cool! 23 is an amazing number!");
} else if (favourite === 7) {
    console.log("7 is also a cool number");
} else {
    console.log("Number is not 23 or 7");
}

if (favourite !== 23) {
    console.log("Why not 23?");
}
```

### Boolean Logic `&&`, `||`, `!`

```js
const hasDriveLicense = true;
const hasGoodVision = false;
console.log(hasDriveLicense && hasGoodVision);
console.log(hasDriveLicense || hasGoodVision);
console.log(!hasDriveLicense);
console.log(!hasDriveLicense && hasGoodVision);
console.log(!hasDriveLicense && !hasGoodVision);
console.log(!hasDriveLicense || !hasGoodVision);

const shouldDrive = hasDriveLicense && hasGoodVision;
if (shouldDrive) {
    console.log("Sarah is able to drive!");
} else {
    console.log("Someone else should drive...");
}

const isTired = true;
console.log(hasDriveLicense || hasGoodVision || isTired);

const shouldDrive = hasDriveLicense && hasGoodVision;
if (shouldDrive && !isTired) {
    console.log("Sarah is able to drive!");
} else {
    console.log("Someone else should drive...");
}

let age = 16;
if (!(age >= 20)) {
    console.log();
} else if (age >= 20 && age <= 30) {
    console.log();
} else if (age >= 20 || age <= 30) {
    console.log();
} else if (!(age >= 20) && age <= 30) {
}
```

### `use strict`

During development, we need to use the uptodate Google Chrome to ensure our code could be used in the latest javascript standard. <br>
After developpment, to ensure our development could be used in any versioin of browser we use Babel to transpile and polyfill code (converting back to ES5 to ensure browser compatibility for all users)<br>
Some word (variable name) is reserved, in strict mode, defining them will cause `syntaxError` but without declaration of 'use strict', this kind of error will not show

### Function

In using function declaration, function could be called before its'definition, but we could not called the function expresiion before defining it.

#### function declaration

```js
function logger() {
    console.log("My name is Jonas");
}

// calling/running/invoking function
logger();

function fruitProcessor(apples, oranges) {
    console.log(apples, oranges);
    const juice = `Juice with ${apples} apples🍎 and ${oranges} oranges🍊`;
    return juice;
}

const appleJuice = fruitProcessor(5, 0);
console.log(appleJuice);

const appleOrangeJuice = fruitProcessor(2, 4);
console.log(appleOrangeJuice);

function calcAge1(birthYear) {
    // const age = 2037 - birthYear;
    // return age;
    return 2037 - birthYear;
}

const age1 = calcAge1(1991);
console.log(age1);
```

#### Function expression (Anonymity function)

Anonymity function, also called function expression

```js
const calcAge2 = function (birthYear) {
    return 2037 - birthYear;
};

const age2 = calcAge2(1991);
console.log(age1, age2);
```

#### Arrow function

Arrow function, it's a function expression, the return value is implicit in this function, `birthYear` is input parameter, and the return value is implicit (2037 - birthYear)

-   Arrow function with parameter

```js
const calcAge3 = (birthYear) => 2037 - birthYear;
const age3 = calcAge3(2000);
console.log(age3);

Arrow function with parameter
const yearUntilRetirement = (birthYear) => {
    const age = 2037 - birthYear;
    const retirement = 65 - age;
    return retirement;
};

console.log(yearUntilRetirement(1991));
```

-   Arrow function with multiple parameter

```js
const yearUntilRetirement = (birthYear, firstName) => {
    const age = 2037 - birthYear;
    const retirement = 65 - age;
    return `${firstName} retires in ${retirement} years`;
};

console.log(yearUntilRetirement(1991, "Jonas"));
console.log(yearUntilRetirement(1980, "Bob")); */
```

#### Functions calling other functions

```js
function cutFruitPieces(fruit) {
    return fruit * 4;
}

function fruitProcessor(apples, oranges) {
    const applePieces = cutFruitPieces(apples);
    const orangePieces = cutFruitPieces(oranges);
    const juice = `Juice with ${applePieces} apples🍎 and ${orangePieces} oranges🍊`;
    return juice;
}

console.log(fruitProcessor(2, 3)); */
```

### Array

1. Way1 to create array

```js
let friends = ["Michael", "Steven", "Peter"];
console.log(friends);
console.log(friends.length);
console.log(friends[friends.length - 1]);
friends[2] = "Jay";
console.log(friends);
```

It's can be reassigned anytime in any form

```js
friends[5] = "Mike";
console.log(friends[3]);
console.log(friends[4]);
console.log(friends);
friends = ["Bob", "Alice"];
console.log(friends); //
```

2. Way2 to create array
   An array can contain any data type

```js
const years = new Array(1991, 1984, 2008, 2020);
console.log(years);
console.log(years[1]);

const firstName = "Jonas";
// an array can contain any data type
const jonas = [firstName, "Schmedtmann", 2037 - 1991, "teacher", friends];
console.log(jonas);
```

#### Basic Array Operations (Methods)

1. Add elements `push`

```js
// Add elements
const newLength = friends.push("Ray"); // push(), return the new length value of array
console.log(friends, newLength);
// unshift(), insert an element at the first position of array, and also return the new length value
const newLen = friends.unshift("John");
console.log(friends, newLen);
```

2. Remove elements `pop`, `shift`

-   Use `pop` to remove the **last** element of array and return the removed element
-   Use `shift` to emove the **first** element of array, and return the removed element

```js
// Remove elements
const popped = friends.pop(); // remove the last element of array and return the removed element
console.log(friends, popped);
const shifted = friends.shift(); // remove the first element of array, and return the removed element
console.log(friends, shifted);
```

3. Return index of element `indexof`

```js
// return index of element
console.log(friends.indexOf("Michael"));
```

1. `includes`

Verify if the element is in the array and return the boolean

```js
// Includes, verify if the element is in the array and return the boolean
friends.push(23);
console.log(friends.includes("Steven"));
console.log(friends.includes("Ray"));
console.log(friends.includes("23")); // doesn't word, includes method is in strict mode
console.log(friends.includes(23));

if (friends.includes("Steven")) {
    console.log("You have a friend called Steven");
}
```

### Object

Object is a **key-value** pair

```js
const jonas = {
    firstName: "Jonas",
    lastName: "Schmedtmann",
    age: 2037 - 1991,
    job: "Teacher",
    friends: ["Micheal", "Peter", "Steven"],
};
```

-   Get data from Object

```js
// get data from Object
console.log(jonas);
console.log(typeof jonas);
console.log(jonas.lastName);
console.log(jonas["lastName"]);

const nameKey = "Name";
console.log(jonas["first" + nameKey]);
console.log(jonas["last" + nameKey]); */

const interestedIn = prompt(
    "What do you want to know about Jonas ? Choose between firstName, lastName, age, job, and friends"
);
// if interestedIn is not the key value existed in object Jonas,
// jonas[interestedIn] wil return falsy value undefined
console.log(jonas[interestedIn]);
if (jonas[interestedIn]) {
    // undefined is falsy value
    console.log(jonas[interestedIn]);
} else {
    console.log(
        "Wrong request! Choose between firstName, lastName, age, job, and friends"
    );
}
```

-   Object operations

```js
// Object operations
jonas.location = "Portugal";
jonas["twitter"] = "@jonasschmedtman";
console.log(jonas);
```

### Object methodes

```js
const jonas = {
    firstName: "Jonas",
    lastName: "Schmedtmann",
    birthYear: 1991,
    job: "Teacher",
    friends: ["Micheal", "Peter", "Steven"],
    hasDriversLicense: false,
    // To define a function inside an Object, we need function expression rather than function declaration
    // calcAge: function (birthYear) {
    //     return 2037 - birthYear;
    // },
    // this point to the Object itself
    // calcAge: function () {
    //     // console.log(this);
    //     return 2037 - this.birthYear;
    // },
    // this point to the Object itself
    calcAge: function () {
        // console.log(this);
        this.age = 2037 - this.birthYear;
        return this.age;
    },

    getSummary: function () {
        console.log(
            `${this.firstName} is a ${this.calcAge()}-years old ${this.job}, and he has ${
                this.hasDriversLicense ? "a" : "no"
            } driver's license`
        );
    },
};

console.log(jonas.calcAge());
console.log(jonas.age);
console.log(jonas.age);
jonas.getSummary();
// console.log(jonas["calcAge"]());
```

### Loop iteration

```js
// console.log("lifting weights, repetition 1 🏋️‍♀️");
// console.log("lifting weights, repetition 2 🏋️‍♀️");
// console.log("lifting weights, repetition 3 🏋️‍♀️");
// console.log("lifting weights, repetition 4 🏋️‍♀️");
// console.log("lifting weights, repetition 5 🏋️‍♀️");
// console.log("lifting weights, repetition 6 🏋️‍♀️");
// console.log("lifting weights, repetition 7 🏋️‍♀️");
// console.log("lifting weights, repetition 8 🏋️‍♀️");
// console.log("lifting weights, repetition 9 🏋️‍♀️");
// console.log("lifting weights, repetition 10 🏋️‍♀️");
for (let rep = 1; rep <= 10; rep++) {
    console.log(`lifting weights, repetition ${rep} 🏋️‍♀️`);
}
```

#### Example

```js
const jonas = ["Jonas", "Schmedtmann", 1991, "Teacher", ["Micheal", "Peter", "Steven"], false];

const types = [];
for (let i = 0; i < jonas.length; i++) {
    // Read from jonas array
    // console.log(jonas[i], typeof jonas[i]);
    // Filling types array
    // types.push(typeof jonas[i]);
    types[i] = typeof jonas[i];
    console.log(types[i]);
}
console.log(types);

const years = [1991, 2007, 1969, 2020];
const ages = [];
for (let i = 0; i < years.length; i++) {
    ages.push(2037 - years[i]);
}
console.log(ages);
```

### `continue` and `break`

```js
console.log("--- ONLY STRING ---");
for (let i = 0; i < jonas.length; i++) {
    // Read from jonas array
    if (typeof jonas[i] !== "string") continue;
    if (typeof jonas[i] === "number") break;
    console.log(jonas[i], typeof jonas[i]);
}

console.log("--- BREAK WITH NUMBER ---");
for (let i = 0; i < jonas.length; i++) {
    // Read from jonas array
    if (typeof jonas[i] === "number") break;
    console.log(jonas[i], typeof jonas[i]);
}
```

### Loop backward and loop in loop

```js
const jonas = ["Jonas", "Schmedtmann", 1991, "Teacher", ["Micheal", "Peter", "Steven"], false];

for (let i = jonas.length - 1; i >= 0; i--) {
    console.log(jonas[i], typeof jonas[i]);
    if (typeof jonas[i] === "object") {
        for (let j = 0; j < jonas[i].length; j++) {
            console.log(jonas[i][j]);
        }
    }
}

for (let exercise = 1; exercise < 4; exercise++) {
    console.log(`------- Starting Exercise ${exercise} -------`);
    for (let rep = 1; rep < 6; rep++) {
        console.log(`Exercise ${exercise}: Lifting weight repetition ${rep} 🏋️‍♀️`);
    }
}
```

### `while` Loop

```js
let rep = 1;
while (rep < 10) {
    console.log(`Lifting weight repetition ${rep} 🏋️‍♀️`);
    rep++;
}

let dice = 0;
while (dice !== 6) {
    dice = Math.trunc(Math.random() * 6) + 1;
    console.log(`You rolled a ${dice}`);
    if (dice === 6) {
        console.log(`You rolled a ${dice}, loop is about to end`);
    }
}
```
