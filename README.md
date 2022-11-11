# advanced-javascript topics

Event propagation(event bubbling and event capturing)

Higher Order Function

Call back function

Function currying

Call back hell

Ajax call using XMLHttprequest


Bonus Section JSON

Fetch API

Promises

Async-Await

Error handling in Js


event propagation :

event bubbling and event capturing

event propagation mainly classified into 3 phases:

they are:

1.capture phase-going from window to event target phase
2.target phase-it is the target phase
3.bubble phase-it is again event target parent back to the window.

event bubbling:

while event bubbling event is first captured and then handled by the innermost elements and then propagated to the outer elements.


event capturing:

while event capturing the event is first captured by the outermost elements and then propagated to the innermost elements this is also called trickling 

example:


function first(event) {
  console.log(1);
}
function second() {
  console.log(2);
}
function third() {
  console.log(3);
}
var button = document.getElementById("button");
var container = document.getElementById("container");
button.addEventListener("click", first);
button.addEventListener("click", second);
container.addEventListener("click", third);


function first(event) {
  event.stopPropagation();
  console.log(1);
}

function first(event) {
  event.stopPropagation();
  console.log(1);
}




Call back function:

a function which gets passed as an argument to another function is called callback function.


const add = (a, b) => {
  return a + b;
};

const subs = (a, b) => {
  return Math.abs(a - b);
};

const mult = (a, b) => {
  return a * b;
};

//now we are using call back i.e..,

const calculator = (num1, num2, operator) => {
  return operator(num1, num2);
};

console.log(calculator(5, 2, add));



Higher order function:

a function which takes another function as an argument returns another out  is called higher order function.
we call any function that does that is a higher order function


here above calculator can be called as an higher order function
































































