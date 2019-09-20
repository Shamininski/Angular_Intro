* [Chapter 1 - Introduction](#chapter1)
* [Chapter 2 - Architecture ](#chapter2)
* [Chapter 3 - Components](#chapter3)
* [Chapter 4 - Interpolation and Property Binding](#chapter4)
* [Chapter 5 - Class & Styles Binding](#chapter5)
* [Chapter 6 - Event Binding and references](#chapter6)
* [Chapter 7 - Two way Binding](#chapter7)



<!-- Noel's Section -->
## <a name="chapter1"/> Introduction





## <a name="chapter2"/>Architecture 




## <a name="chapter3"/>Components




## <a name="chapter4"/>Interpolation and Property Binding







<!-- Justine's Section-->
## <a name="chapter5"/>Class & Styles Binding

In this part, we are going to learn how to bind classes and styles to an HTML element.
First, let us create a new class, as shown below

@Component({ 
           selector: "my-tuts", 
           template: `<h2>{{title}}</h2>`, 
           styles: [`.myClass{ 
				        color:red; 
			    }'
            ] 
	})


What does class binding do? It is going to assign a class to HTML elements, which is based on an expression, which evaluates as true or false. Let’s create a div tag, as shown below.

<div [class.myClass]=" ">Apply Class Binding</div>`,


Here, my class to apply is myClass, as shown above.
The class is going to be assigned to div tag, which is based on a variable of true or false.
Let us create a variable, (on the code editor).


That’s how class binding works. Similarly, we have style binding in order to apply inline styles to HTML elements.
Let’s create another property, as shown below.

export class RathrolaComponent { 
   public title = "Tutorials from Rathrola"; 
   public applyclass = true; 
   public applyblue = true; 
}

Now, let’s create another div tag, as shown below.

<div [style.color]="applyblue?'blue':orange">Blue</div>`,


If the two variables are false, we'll use the code given below.

export class RathrolaComponent { 
   public title = "Tutorials from Rathrola"; 
   public applyclass = false; 
   public applyblue = false; 
}




## <a name="chapter6"/>Event Binding and references

In this article, we are going to learn about event binding and references.
Now, we are only setting the values to DOM element properties, but there is no way to retrieve DOM element properties.

For Example
There might be a situation where the user will fill out a form or click a button, which results in the flow of data from the view to our component's class. This is where event binding comes into the picture by helping us to capture the data flow from the view to the component.
In order to understand event binding better, let’s first create a button, as shown below.
 
@Component({ 
   selector: "my-tuts", 
   template: `<h2>{{title}}</h2> 
<button>Click me</button>` 
})

Just like how we have square brackets for property binding, for event binding we use parentheses, (),as shown below 

<button(click)="onClick()">Click me </button>

In our class, let’s define the method, as shown below.

onClick(){ 
console.log('ButtonClicked');
}


## <a name="chapter7"/>Save this and run it 



## <a name="chapter8"/>Two way Binding






