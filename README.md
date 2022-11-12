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

A higher order function is a function that takes at least one function as an input and/or returns a function as an output.


here above calculator can be called as an higher order function



Callbacks and higher-order functions simplify our code and keep it DRY.



asynchronous javascript:

hoisting in js
scope  chainin js
lexical scope in js
strict mode in js
this keyword
closure
what is asynchronous javascript
what is event loop


hoisting in js:

creation and execution phases

in js all the variables and functions declartions moved to the top  before they got executed



for e.g:
console.log(myname);
var myname;
myname="thapa";

output: undefined.


what is scope chain and lexical scoping in js?

scope chain is used to resolve the value of variable in js
scope chain in js is lexically defined 
at the top global scope which is window object
lexical scoping means inner function can get access to their parent functions variables but vice versa is not true

example:

let a = 'hello guys'; // global scope

function first() {
  let b = 'how are you?';
  function second() {
    let c = 'hi';
    console.log(a + b + c);
  }
  second();
  //console.log(a+b+c); // c is not defined here
}
first();

what is closures in js?

a closure in js gives access to an outer function's scope from an inner function.


example:

function outer(a){
  let b=5;
  function inner(){
    console.log(`sum is ${a+b}`)
  }
  return inner;
}

let closure=outer(3);
closure();


Use strict mode in js:


"use strict"


x="vinode"
console.log(x);

output:x is not defined;




x="vinode"
console.log(x);

output:vinode;



difference between synchronous and asynchronous js:

sync program:
function one() {
  console.log('func 1 is called');
}
function two() {
  console.log('func 2 is called');
  one();
  console.log('func 1 is called again');
}

two();



output:

func 2 is called
func 1 is called
func 1 is called again
func 1 is called


synchronous programming means only one task at a time that means after function 2 gets executed only function 1 gets executed it doesnt matter how much time it takes also after that only func 1 gets executed.
for e.g: 

1 work =10 min
2 work = 10 s

after first work only second work gets executed.


to overcome this asynchronous programming came into picture.

async program:


if it is async 1work=10 min and 2work=5s second work executed first and then tasks gets executed parallelly,no need to wait anywhere.


for e.g if we take facebook or instagram if we want to like or share something u need not wait till the video completes u can do it parallely this is the best example of asynchronous programming.

e.g


const func2 = () => {
  setTimeout(() => {
    console.log('func 2 is called');
  }, 2000);
};

const func1 = () => {
  console.log('func 1 is called');
  func2();
  console.log('func1 is called again');
};

func1();


now here first func 1 is called then it goes inside and then first console.log is printed and fun c2 is called but it is set for 2 sec now the task wont stop third console.log is printed and then func 2 is run.


this way tasks would continue.




Event loop in js:

there are three things in event loop:

1.execution stack

 a.global execution context- first every line in the code comes into this and any settimeout or api calls goes into next web api's otherwise gives output and vanishes
 
 2.web API 's - here the function or the code stays till the time interval is completed and then if completed it reaches message queue 
 
  a.setTimeOut()
  b.Dom
  c.ajax/api calls


3. message queue from here the process repeats again to the execution stack


this is called event loop which follows asynchronous programming in javascript.


















































































































