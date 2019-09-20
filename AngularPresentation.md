- [Chapter 1 - Introduction](#chapter1)
- [Chapter 2 - Architecture ](#chapter2)
- [Chapter 3 - Components](#chapter3)
- [Chapter 4 - Interpolation and Property Binding](#chapter4)
- [Chapter 5 - Class & Styles Binding](#chapter5)
- [Chapter 6 - Event Binding and references](#chapter6)
- [Chapter 7 - Two way Binding](#chapter7)

<!-- Noel's Section -->

## <a name="chapter1"/> Introduction
Angular is a JavaScript open-source front-end web application framework. It is primarily sustained by Google together with an extended community of people and companies, to approach many of the challenges faced when developing single page, cross platform, performant applications. It is fully extensible and works well with other libraries. 

Angular is a great tool that will:

 i)Enable you to create software quicker and with less effort
 ii)Result in a more maintainable software
 iii)Encourage good programming practices and design patterns like MVC
 iv)Allow you to collaborate easier with other people
 v)Allow you to become proficient in a reasonable time
 vi)Address problems that may arise in your software architecture such as Dependency Injection, DRY (Don’t Repeat Yourself), etc

## <a name="chapter2"/>Architecture

The basic building blocks of an Angular application are NgModules, which provide a compilation context for components. NgModules collect related code into functional sets; an Angular app is defined by a set of NgModules. An app always has at least a root module that enables bootstrapping, and typically has many more feature modules.

Components define views, which are sets of screen elements that Angular can choose among and modify according to your program logic and data.

Components use services, which provide specific functionality not directly related to views. Service providers can be injected into components as dependencies, making your code modular, reusable, and efficient.
  

https://angular.io/generated/images/guide/architecture/overview2.png

## <a name="chapter3"/>Components
Components are the most basic building block of an UI and Angular applications. A component controls one or more sections on the screen (what we call views). 

A component is self contained and represents a reusable piece of UI that is usually constituted by three important things:

i)A piece of html code that is known as the view
ii)A class that encapsulates all available data and interactions to that view through an API of properties and methods architectured by Angular. Here’s where we define the application logic (what it does to support the view)
And the aforementioned html element also known as selector.
Using the Angular @Component decorator we provide additional metadata that determines how the component should be processed, instantiated and used at runtime. For example we set the html template related to the view, then, we set the html selector that we are going to use for that component, we set stylesheets for that component.

        ```
            @Component({
            selector: 'my-app',
            templateUrl: './app.component.html',
            styleUrls: [ './app.component.css' ]
            })
            export class AppComponent  {
            name = 'Angular';
            }
            ```

## <a name="chapter4"/>Interpolation and Property Binding
What is Interpolation?

Angular interpolation is used for display a component property in the respective view template with double curly braces syntax. We can display all kind of properties data into view e.g. string, number, date, arrays, list or map.
    ```
        class AppComponent {

                propertyName: string;
                object: DomainObject;
            }
            
            {{ propertyName }}
            
            {{ object.propertyName }}
            ```

Angular automatically pulls the value of the propertyName and object.propertyName from the component and inserts those values into the browser. Angular updates the display when these properties change.




Data binding consist of one way data binding and two way data binding. Interpolation is used for one way data binding. Interpolation moves data in one direction from our components to HTML elements.



<!-- Justine's Section-->

## <a name="chapter5"/>Class & Styles Binding

In this part, we are going to learn how to bind classes and styles to an HTML element.
First, let us create a new class, as shown below

```javascript
@Component({
           selector: "my-tuts",
           template: `<h2>{{title}}</h2>`,
           styles: [`.myClass{
			    color:red;
			}']
	})
```

What does class binding do? It is going to assign a class to HTML elements, which is based on an expression, which evaluates as true or false. Let’s create a div tag, as shown below.

```html
<div [class.myClass]=" ">Apply Class Binding</div>
`,
```

Here, my class to apply is myClass, as shown above.
The class is going to be assigned to div tag, which is based on a variable of true or false.
Let us create a variable, (on the code editor).

That’s how class binding works. Similarly, we have style binding in order to apply inline styles to HTML elements.
Let’s create another property, as shown below.

```javascript
export class RathrolaComponent {
   public title = "Tutorials from Rathrola";
   public applyclass = true;
   public applyblue = true;
}
```

Now, let’s create another div tag, as shown below.

```html
<div [style.color]="applyblue?'blue':orange">Blue</div>
`,
```

If the two variables are false, we'll use the code given below.

```javascript
export class RathrolaComponent {
   public title = "Tutorials from Rathrola";
   public applyclass = false;
   public applyblue = false;
}
```

## <a name="chapter6"/>Event Binding and references

In this section, we are going to learn about event binding and references.
Now, we are only setting the values to DOM element properties, but there is no way to retrieve DOM element properties.

For Example
There might be a situation where the user will fill out a form or click a button, which results in the flow of data from the view to our component's class. This is where event binding comes into the picture by helping us to capture the data flow from the view to the component.
In order to understand event binding better, let’s first create a button, as shown below.

```javascript
@Component({
  selector: "my-tuts",
  template: `<h2>{{title}}</h2>
<button>Click me</button>`
})
```

Just like how we have square brackets for property binding, for event binding we use parentheses, (),as shown below

```html
<button (click)="onClick()">Click me</button>
```

In our class, let’s define the method, as shown below.

```javascript
onClick(){
console.log('ButtonClicked');
}
```

Save this and run it...

in Angular, it is very easy to reference HTML tags or the elements. Now, to reference an element, all we need to do is use the hash (#) symbol with any random variable, as shown below.

```html
<input type="text" #demoInput />`
```

In order to get the data which is flowing from an input tag, we can use a reference variable.

## For Example

Let’s say, we passed demoInput.value as one of the parameters for the onClick method.

```html
<button (click)="onClick(demoInput.value)">Click me</button>
```

Pass the value to the onClick value and log the value, as shown below.

```javascript
export class RathrolaComponent {
    public title = "Tutorials from Rathrola";
    onClick(value) {
        console.log(value);
    }
}
```

Save and run.

Key in some value, say, Hello world, and watch the console. It is going to log the input field, as shown below.

That is how event binding works; we have bound the button click event with a handler calledonClick. We are going to use the reference to input the elements. By passing its value, we can retrieve the value in our class.

Finally, to capture the event, we use \$event, as shown below.

```html
<button (click)="onClick($event)">Click me</button>
```

## <a name="chapter7"/>Two way Binding
Two-way data binding combines the square brackets of property binding with the parentheses of event binding in a single notation using the ngModel directive. Tip, to remember that the parentheses go inside the brackets, visualize a banana in a box. ```html [()]```

In this example, the name property value flows from the component to the input box as with property binding. This is why the input box contains 'World' when the page is displayed. See the application output below.

The user's changes also flow back to the component, updating the name property to the latest value, as with event binding. This is why the heading is updated as the user types a value.

import { Component } from '@angular/core';

```javascript
@Component({
  selector: 'app-hello-world',
  template: `
    <div>
      <label>Name:</label>
      <input type="text" [(ngModel)]="name">
      <h1 [hidden]="!name">Hello {{name}}!</h1>
    </div>`
})
export class HelloWorldComponent {
  name = 'World';
}

```

