- [Chapter 1 - Introduction](#chapter1)
- [Chapter 2 - Architecture ](#chapter2)
- [Chapter 3 - Components](#chapter3)
- [Chapter 4 - Interpolation and Property Binding](#chapter4)
- [Chapter 5 - Class & Styles Binding](#chapter5)
- [Chapter 6 - Event Binding and references](#chapter6)
- [Chapter 7 - Two way Binding](#chapter7)

<!-- Noel's Section -->

## <a name="chapter1"/> Introduction

## <a name="chapter2"/>Architecture

## <a name="chapter3"/>Components

## <a name="chapter4"/>Interpolation and Property Binding

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
Two-way data binding combines the square brackets of property binding with the parentheses of event binding in a single notation using the ngModel directive. Tip, to remember that the parentheses go inside the brackets, visualize a banana in a box. [()]

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

