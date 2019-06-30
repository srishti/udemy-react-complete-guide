# React - The Complete Guide (Notes)

## Table Of Contents
[01 - Getting Started](#section-01)


## 01 - Getting Started <a id="section-01"></a>

### What is React?
> React is a JavaScript library for building user-interfaces. 

React is **JavaScript-driven**. The web applications created using React are written in JavaScript. Since JavaScript runs on the browser, it allows you to create super-fast web applications which do not require user to wait for the page reloads. The **user-interfaces** are the components that the user is able to see. Thus, *React is a library for creating highly reactive and super-fast JavaScript-driven web applications*.

---------------

### What are components?

Components are the building blocks of an application. Each component is a contained piece of code.

For an instance, a news application can be divided into 4 components - header, sidebar, headline and article content, as given in the image below:

![Example of Components in a webpage](/example-components-in-webpage.png)

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
