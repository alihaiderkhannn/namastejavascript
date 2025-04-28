# Notes episode 3, Namaste Javascript by Akshay Saini

Example 1

var x = 7;
function getName(){
    console.log("Namaste Javascript");
}
getName(); // this will give us "Namaste Javascript" printed out.
console.log(x); // this will give us 7 printed out.

Remember the execution context. We are creating a container which is the global execution context and defining two spaces (memory creation phase and code execution phase.)
In the first phase we are allocating memory for variable x which will be undefined in the first phase, and the function getName will be directly copied over. After allocating memory to variable and function, we are going to run the code in the code execution phase. There the variable x will get the value 7, and the function getName will be the same because it was copied over.
Therefore, the output there will be "Namaste Javascript" and 7.

Example 2

getName(); //function invokation.
console.log(x);

var x = 7;
function getName(){
    console.log("Namaste Javascript");
}

In this example we are demonstraing hoisting in Javascript. Declarations are hoisted to the top before the code is running. If we look at in the same way as earlier, we are creating a global execution context with two phases (memory creation and code execution phase). In the memory creation phase we are allocating undefined to x, and the function is copied directly over. In the code execution phase, we are seeing a function invokation in the first line and we are creating a function execution context which will print out "Namaste Javascript", and we will then delete this function execution context and move on. Next line is printing out the x variable which for now is undefined. So the output here will be "Namaste Javascript" and undefined. This means that functions are fully hoisted in javascript, but variable with var declarations are also hoisted but initialized with the value undefined.

Example 3

getName(); //Will print out "Namaste Javascirip" as expected now.
console.log(x); // this will give a complete error - Uncauht ReferenceError: x is not defined.

function getName(){
    console.log("Namaste Javascript");
}

So, in Javascript there is a huge difference between undefined and not defined.

Hoisting in Javascript is the concept where you can access variables and functions, even before it has been initialiazed or the code has been runned.

console.log(getName); //this will print out the whole function getName, even before the function has been initialized and runned through.

But when it comes to variables declared with var, it was printing out undefied.

getName(); // it will return getName is not a function, because when it is declared with var is will assume it like a variable. So getName will also be undefined here like a var variable.
console.log(x);
console.log(getName);

var x = 7;

var getName = () => {
    console.log("Namaste Javascript");
}
