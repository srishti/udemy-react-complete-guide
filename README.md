# React - The Complete Guide (Notes)

## Table Of Contents
[01 - Getting Started](#01---getting-started)  
[02 - Refreshing Next Generation JavaScript (Optional)](#02---refreshing-next-generation-javascript-optional)


## 01 - Getting Started

### What is React?
> React is a JavaScript library for building user-interfaces. 

React is **JavaScript-driven**. The web applications created using React are written in JavaScript. Since JavaScript runs on the browser, it allows you to create super-fast web applications which do not require user to wait for the page reloads. The **user-interfaces** are the components that the user is able to see. Thus, *React is a library for creating highly reactive and super-fast JavaScript-driven web applications*.

---------------

### What are components?

Components are the building blocks of an application. Each component is a contained piece of code.

For an instance, a news application can be divided into 4 components - header, sidebar, headline and article content, as given in the image below:

![Example of Components in a webpage](/images/example-components-in-webpage.png)

#### Advantages of component-driven approach:
- **Managability:**
Component-driven approach makes the code more managable. If you have a header component in your application and in future, if you decide to change something in the header, you don't have to find the code for the header in the entire application. You just need to go to the header component to make the changes.

- **Reusability:**
React components can be thought of as custom HTML components. Suppose that you are designing a social media application in which you show a webpage where the friends list is shown. In this friends list, you show user details of all the friends. In such a case, you do not need to create components for different friends. You can just create a generic component to show a friend and this generic component can be reused to show all other friends.
Now, definitely you can achieve the same goal using plain HTML, CSS and JavaScript but then you will have to repeat your code over and over again. With components, you don't have to rewrite your code. You can write the code just once and reuse it as many times as you need.

**Example:**
`Person` Component - [Demo on Codepen](https://codepen.io/anon/pen/KjQqvJ)

---------------

### Why use React?

1. React solves the problem that you encounter with normal JavaScript when the UI state becomes difficult to manage in complex applications. With Vanilla JavaScript, you need to manually target elements using `querySelector`. With JQuery too, traversing the DOM is quite easy but you still need to use methods to target elements when manipulating them. React makes an application highly dynamic in the sense that the elements can be inserted or removed from the DOM dynamically.

2. With React, you get the chance to focus on the business logic rather than focusing on how things are working behind-the-scenes.

3. React has a huge ecosystem of other libraries and is well supported by an active community of high-performing developers.

---------------

### SPA vs. MPA

| Single Page Applications | Multi-Page Applications |
| :------------- |:------------- |
| There's only one HTML page loaded when the user visits the application for the first time. Thereafter, all the content is loaded dynamically by React. | Multiple HTML pages are rendered where each page has content for a given URL. |
| Each component and the overall application is managed by React. | It may be possible that only some components and not the entire application is managed by React. |
| Typically has a single `ReactDOM.render()` method. | Can have multiple `ReactDOM.render()` methods depending upon the number of React components to be plugged in the application at different places. |

---------------


## 02 - Refreshing Next Generation JavaScript (Optional)

### let vs. const

Article on Medium written by me - ['let' me be a 'const'(ant), not a 'var'(iable)!](https://medium.com/free-code-camp/let-me-be-a-const-ant-not-a-var-iable-1be52d153462)

---------------

### Arrow Functions

ES6 introduced array functions, which are the alternative to normal functions.

ES5 normal function syntax:
```js
function fun() {
    // some code here
}
```

ES6 arrow function syntax:
```js
const fun = () => {
    // some code here
}
```

**Key Difference in syntax:** You use an equality operator = before the parameter(s) and a fat arrow => after the parameter(s) of the function.

ES6 arrow functions solve the problem with the `this` keyword that occurs with the ES5 normal function syntax. When you use the `this` keyword inside an arrow function, it will not change its context surprisingly.

**Case A: Single parameter**

If a function consists of a single parameter, you can skip the parenthesis around the parameter.

Consider the code snippet given below:
```js
const print = (name) => {
    console.log(name);
}

print('Srishti');
```

In the code snippet given above, a single parameter `name` exists. So, you can skip the parenthesis around it and rewrite the arrow function in the following syntax:

```js
const print = name => {
    console.log(name);
}

print('Srishti');
```

Remember that skipping the parenthesis is allowed only when there's just ONE parameter and does not work when there's no parameter or when there're more than one parameters.


**Case B: Single return statement in entire function body**

If a function consists of a single return statement in the entire body code, you can skip writing the `return` keyword and curly braces surrounding the function body. Also, you can write everything on the same line instead of spanning the definition to multiple lines.

Consider the following code snippet:
```js
const multiply = num => {
    return num * 2;
}

multiply(5);
```

In the code snippet given above, there exists a single `return` statement in the entire body of the function. So, you can skip the `return` statement, the curly braces and bring everything on the same line. The new code snippet will look like the one given below:

```js
const multiply = name => num * 2;

multiply(5);
```

---------------

### Modules: Exports & Imports

In JavaScript, you can write modular code. The code can be split into multiple files where each file is called a *module*. Now, how do you reuse code written in a module? That's simple. You simply export the code written in one module and then import it in another module where the exported code is required to be used. 

There are two types of *imports* and *exports*:
#### 1. Default Exports & Imports
The `default` keyword is used to export a default code construct from a module. It is important to note that there can be only one default export in a module.

*Assume that there are two files named `person.js` and `app.js` at the same path in a folder.*

**Exporting from a module:**
*person.js*

```js
const person = {
    name: "Srishti"
}
export default person;
```

**Importing in a module:**
*app.js*

```js
import person from './person.js'; // importing person object from person module
```

When exporting the `person` object, the `default` keyword is used. So, this is a default export. When importing the exported code inside another module, you need to specify the path of the module after the `from` keyword. When using a default export, you can use either use the same name that you used while exporting or you can use a different name.

Let's see an example of a different name used when importing a default export.

**Importing in a module with different name:**
*app.js*

```js
import prsn from './person.js'; // different name (prsn) from the one used when exporting (person)
```

While exporting the object from `person` module, `person` name was used but while importing the object in the `app` module, `prsn` name is used, which is different from the name used when exporting.

#### 2. Named Exports & Imports
When you want to export multiple code constructs from a module, you should use named exports. It is important to note that unlike default export, there can be any number of named exports in a module.

*Assume that there are two files named `utility.js` and `app.js` at the same path in a folder.*

**Exporting from a module:**
*utility.js*

```js
export const clean = () => {
    // some code here
}

export const baseData = 10;
```

**Importing in a module:**
*app.js*

```js
import { clean } from './utility.js'; // importing clean function from utility module
import { baseData } from './utility.js'; // importing baseData constant from utility module

```

Remember that when using named imports, you MUST use the same name, which was used when exporting from a module. The name given to a code construct works as its identification and hence the name - *named* exports and imports.

**Importing in a module using alias:**

There's a workaround to using the same name used while exporting something using named export. You can use an alias when working with named imports. For this, you first need to import the named export using the same name with which it was exported and then give it a different name. This new name can be used throughout the module in which you are importing the code. Let's understand this taking the code in the previous example.

*app.js*

```js
import { clean as cls } from './utility.js'; // importing clean function from utility module with alias
import { baseData as bd } from './utility.js'; // importing baseData constant from utility module with alias
```

In the code snippet given above, you import the code using the same name which you used while exporting. Then, you need to write the keyword `as` which tells that the name which follows this keyword will be an alias. At the end, you specify the alias. So, the syntax for using alias in named export is:

```js
{ nameUsedWhenExporting as alias }
```

**Importing everything at once:**

You can import everything at once using the asterisk symbol `*` and then assign it to an object defined using an alias.

Let's take the previous example to see how this can be done.

```js
import * as util from './utility.js';
```

In the code snippet given above, everything (all named exports) will be imported from the `utility` module and will be assigned to an object named `util`. Thus, everything that was exported from the utility module, can now be accessed as the properties of the `util` object. You can use `util.clean()` and `util.baseData` to access the function and the constant exported from the `utility` module.

#### Summary

Remember that you can also mix the one default export with any number of named exports in a file.

![Summary of Default & Named Exports/Imports](/images/import-export.png)

---------------

### Classes, Properties & Methods

A class is a blueprint of an object. A class is created using the `class` keyword. A class can have both *properties* as well as *methods*. 

**Syntax:**
```js
class Person {
    // properties & methods
}
```

A `constructor` is a special method defined inside a class which is invoked when the class is instantiated (an object of a class is created).

**Example:**
```js
class Person {
    constructor() {
        this.name = "Srishti"; // property
    }
    printPersonDetails () { // method
        console.log('Name: ' + this.name);
    }
}
```

Here, the class `Person` is defined with the `class` keyword. The class has a property called `name` which is initialized with the value `'Srishti'` inside the `constructor` method. The method named `printPersonDetails` prints the value of the `name` property.

A class is instantiated (object of a class is created) using the `new` operator. 

```js
const p = new Person();
console.log(p.name);
console.log(p.printPersonDetails());
```

*Output:*
```js
"Srishti"
"Name: Srishti"
```

In the code snippet given above, the class `Person` is instantiated and this instance is held inside the constant named `p`.

#### Inheritance

A class can inherit properties and methods of another class. To inherit a class, the `extends` keyword is used. The class, from which the properties & methods are inherited, is called the *base/parent* class and the class, which inherits the properties or methods of the base/parent class, is called its *derived/child* class.

```js
class Employee extends Person {
    // class definition
}
```

In the code snippet given above, the class `Employee` inherits the class `Person` using the `extends` keyword. 

Let's now add some properties and methods to the `Employee` class.

```js
class Employee extends Person {
    constructor() {
        super();
        this.empID = 101; // property of Employee class
    }

    printEmployeeDetails () { // method of Employee class
        console.log('Employee Code: ' + this.empID);
    }
}
```

In the code snippet given above, the `Employee` class is the *derived* class and the `Person` class is the *base* class. Note that there is a method `super()` invoked inside the `constructor` method of the `Employee` class. The invocation of the `super()` method must be done before using the `this` keyword in the `constructor` or returning from the `constructor` of the derived class. The `super()` method is used to invoke the `constructor` method of the *base* class.

If you fail to invoke the `super()` method, you will get a `ReferenceError` stating *'Must call super constructor in derived class before accessing 'this' or returning from derived class'*.

Now, when you instantiate the `Employee` class, it inherits the property `name` and method `printPersonDetails` of the `Person` (base) class and has an additional property `empID` and method `printEmployeeDetails` of its own, as validated in the code snippet given below.

```js
const e = new Employee();
// properties & methods of base class
console.log(e.name);
console.log(e.printPersonDetails());
// own properties & methods
console.log(e.empID);
console.log(e.printEmployeeDetails());
```

Output:
```js
"Srishti"
"Name: Srishti"
101
"Employee Code: 101"

```

#### ES7: Defining Properties & Methods in Classes

**Properties:**
Till now, you have seen the following ES6 syntax for defining a property in a class:

```js
class Person {
    constructor() {
        this.name = "Srishti";
    }
}
```

With ES7 syntax, you can directly assign a property inside your class without defining it inside the `constructor` method. This saves you from writing the `constructor` method in your class. Thus, the above code snippet can be written as:

```js
class Person {
    name = "Srishti";
}
```

**Methods:**
Till now, you have seen the following ES6 syntax for defining a method in a class:

```js
class Person {
    // assume that the name property is already defined in the class
    printPersonDetails() { // method
        console.log('Name: ' + this.name);
    }
}
```

With ES7 syntax, you can declare a method in a class as a property. These methods are anonymous methods assigned to a property in the class. Thus, the above code snippet can be written as:

```js
class Person {
    // assume that the name property is already defined in the class
    printPersonDetails = () => { // method defined as property
        console.log('Name: ' + this.name);
    }
}
```

Earlier you saw the following code snippet written in the ES6 syntax:
```js
class Person {
    constructor() {
        this.name = "Srishti"; // property
    }

    printPersonDetails () { // method
        console.log('Name: ' + this.name);
    }
}
```

If you apply the above ES7 syntax rules, the above code snippet can be rewritten as follows:
```js
class Person {
    name = "Srishti"; // property

    printPersonDetails = () => { // method defined as property
        console.log('Name: ' + this.name);
    }
}
```

#### Summary:

![Properties & Methods in Class](/images/properties-and-methods-in-class.png)

---------------

### Spread Operator & Rest Parameter

The syntax of the spread operator and the rest parameter is denoted by three dots `...`. Whether the syntax is the spread operator or the rest parameter, it depends on where the syntax is used. 

#### Spread Operator
The spread operator is used to split up elements of an array or properties of an object.

**Arrays:**
If you have an array and you wish to insert some elements at the beginning/end of the array, you can use the spread operator as shown in the code snippet given below:

```js
let squaresList = [4, 9, 16];
let newSqauresList = [1, ...squaresList, 25];

console.log(newSqauresList); 
```

*Output:*
```js
[1, 4, 9, 16, 25]
```

**Objects:**
If you have an object and you wish to insert some properties in the object, you can use the spread operator as shown in the code snippet given below:

```js
let orderDetails = {
    id: 101,
    amount: 1000
}
let newOrderDetails = { ...orderDetails, discount: 100 };

console.log(newOrderDetails);
```

*Output:*
```js
{
    id: 101,
    amount: 1000,
    discount: 100
}
```

Spread operator lets you achieve this because the array elements or the object properties are pulled out before being transferred to the new array or object.

#### Rest Parameter
The rest parameter is used to merge a list of function arguments in an array. Consider the following code snippet:

```js
function calculateSum(...args) {
    let sum = 0;
    args.forEach((a) => sum += a);
    return sum;
}

console.log(calculateSum(1, 2, 3));
console.log(calculateSum(1, 2, 3, 4));
```

*Output:*
```js
6
10
```

In the code snippet given above, all the arguments sent to the function `calculateSum` are catched inside a parameter named `args`. Since the parameter is preceded with the `...` operator, it becomes an array holding all the arguments passed to the function.

---------------

### Destructuring

Destructuring allows you to extract specific array elements or object properties and store them inside variables.

It may sound similar to the spread operator but it is not. Spread operator is used to copy all the elements inside an array or properties inside an object whereas destructuring is used to target individual element in an array or property in an object.

#### Array Destructuring

```js
const [a, b] = ["Hello", "Srishti"];
console.log(a); // Output => "Hello"
console.log(b); // Output => "Srishti"
```

In the code snippet given above, the elements of the array are destructured. The first element of the array is stored inside the constant `a` and the second element of the array is stored inside the constant `b`.

In array destructuring, the order of the elements defines which element is destructured. Consider the following code snippet:

```js
const [num1, num2] = [1, 2, 3];
console.log(num1, num2); // Output => 1 2
```

In the code snippet given above, the first two elements of the array are only extracted. 

Now, if you want to extract the third element of the array in place of the second element, you should use the syntax given below:

```js
const [num1, , num3] = [1, 2, 3];
console.log(num1, num3); // Output => 1 3
```

Notice that you are following the order of the elements in the array as evident from the code snippet given above. In order to extract the third element of the array, you can leave the place for the second element empty but you cannot just entirely skip the second element.

#### Object Destructuring

```js
const {name, gender} = {
    name: "Srishti",
    gender: "female"
}

console.log(name); // Output => "Srishti"
console.log(gender); // Output => "female"
```

In the code snippet given above, the properties of the object are destructured. The first property is pulled out and stored in the constant named `name` and the second property is pulled out and stored in the constant named `gender`.

In object destructuring, the name of the property defines which property is to be pulled out. Remember that you need to use the same name as that of the property to be extracted from the object.

Now, suppose you want to extract only the name and not the gender from the object, so you can use the following syntax:

```js
const {name} = {
    name: "Srishti",
    gender: "female"
}

console.log(name); // Output => "Srishti"
console.log(gender); // Output => ReferenceError: gender is not defined
```
In the code snippet given above, the variable `gender` is *not defined* because the property with the name `gender` is not pulled out from the object and there is no constant with the name `gender`.

Destructuring is very useful when working with function arguments. Consider the following code snippet:

```js
const printName = (personObj) => {
    console.log(personObj.name);
}
printName({name: "Srishti", gender: "female"}); // Output => "Srishti
```

Inside the function in the code snippet given above, even though you just need to print the name yet you are actually passing a complete object named `personObj` to the function. Although this is no big problem but it makes you write the code `personObj.name` inside the function. This can be avoided by using the concept of destructuring:

```js
const printName = ({name}) => {
    console.log(name);
}
printName({name: "Srishti", gender: "female"}); // Output => "Srishti"
```

Though he output of the code snippet given above is same as that of the earlier code snippet, the advantage you get with destructuring is that you are saved from writing some code. Also, you can focus on targeting only those elements of an array or the properties of an object which are actually required.

---------------

### Reference & Primitive Types

#### Primitive Types

The primitive datatypes - Number, String, Boolean, null, undefined, Symbol in JavaScript are called the primitive types. 

```js
const num = 1;
const numCopy = num; 
console.log(numCopy); // Output => 1
```

In the code snippet given above, the constant `num` is of primitive type. So, when you assign this constant `num` to another constant `numCopy`, a copy of the value in the contained inside `num` is created and is stored in the constant `numCopy`. Thus, the output of `numCopy` is value `1`.

Thus, remember that in primitive types, if you copy a constant/variable into another constant/variable, a copy of the value will be stored.

#### Reference Types

Objects and arrays are called reference types in JavaScript. This is because when they are copied to other constants/variables, a copy is not created. Rather, their reference is copied. Consider the following code snippet:

```js
const person = {
    name: "Srishti",
    gender: "female"
}

const personCopy = person;

console.log(personCopy);
```

*Output:*
```js
{
    name: "Srishti",
    gender: "female"
}
```

In the code snippet given above, the constant `person` is an object and thus, a reference type. The object contained inside this constant is stored in some place in the memory. The constant `person` stores the location of the object in memory. Now, when this `person` is assigned to another constant named `personCopy`, the `personCopy` constant stores the same memory location as contained inside the constant `person`. Thus, the constant object `person` is not actually copied. Rather, `personCopy` points to the same object as pointed by `person` in memory. So, if you make any change in the `person` object, the same change will be reflected in the `personCopy` object too and vice-versa. This can be validated by the following code snippet:

```js
const person = {
    name: "Srishti",
    gender: "female"
}

const personCopy = person;
personCopy.name = "Cheeti";

console.log(person);
```

*Output:*
```js
{
    name: "Cheeti",
    gender: "female"
}
```

In the code snippet given above, the constant `person` is first copied to the constant `personCopy`. Then, the name property inside the `personCopy` constant is changed. Now, when you print the `person` constant, you find that the `person` object is also changed.

The same rule is applicable on arrays too. You assign an array to a variable. Then you copy this array inside another variable. Now, if you manipulate the elements of the array using one of the variables, the same change will be reflected in the other variable too.

This is an important point to remember because you may copy an object/array to another variable and accidently manipulate it, thus bringing unexpected results. You should copy an object/array in an immutable manner in the sense that you should actually make a copy of the object/array rather than copying a reference. In order to achieve this, you can use the spread operator `...`. The spread operator will pull out all the properties of an object and these properties can then be assigned to another object. Thus, the spread operator lets you create a shallow copy of an array/object. Consider the following code snippet for a better understanding:

```js
const person = {
    name: "Srishti",
    gender: "female"
}

const personCopy = {...person};
personCopy.name = "Cheeti";

console.log(person);
```

*Output:*
```js
{
    name: "Srishti",
    gender: "female"
}
```

In the code snippet given above, the `personCopy` object is manipulated but the `person` object is not changed. This is because the `personCopy` constant contains an actual copy of the `person` object and not the reference to the `person` object since you have used the spread operator for copying the `person` object.

---------------

### Array Methods

There were some array methods introduced in *ES5* version. Amongst them, three methods, which are popularly used on arrays, are `map()`, `filter()`, and `reduce()`.

#### `map()` Method
The `map()` method is used when each element in an array needs to be transformed. In other words, when you need to perform a function on each element of the array, you should use the `map()` method. Consider the following code snippet:

```js
const num = [1, 2, 3];

const doubleNum = num.map(n => n*2);
console.log(doubleNum);
```

*Output:*
```js
[2, 4, 6]
```

Remember that this is not the next generation JavaScript but the normal JavaScript syntax.

---------------