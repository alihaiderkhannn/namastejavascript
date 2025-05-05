#

An execution context is created when we run a Javascript program.

var n = 2; // initializing a variable with value 2.
function square (num) { // function square which takes num as a parameter creates a ans variable and multiplies whatever num will be passed in.
    var ans = num *num;
    return ans;
}
var square2 = square(n); // here square2 will be 4. because we are giving n as the argument inside the function and n was 2. (2*2)
var square4 = square(4); //this will be 16. because 4 is given as an argument.

When this program first will run, an global execution context will be created. (Everything that happens inside Javascript, happens inside an execution context.) There will be one global execution context in any program and it will be created at the beginning.
When this global execution context will be created, there will be two components. One for memory creation and the second for code execution phase.

In the first phase (memory creation phase) javascript are going through the whole program and it will allocate memory to variables and functions. We are going to allocate memory for the variable n, and in the first phase n will get the value undefined. But the function will be stored directly, like the whole function code will be copied over like this square { ... }. square2 and square4 will also get the value undefined.
So, the conclusion is that the variables will get value undefined and whole functions will be directly copied over in the first phase.

The second phase is the code execution phase. Javascript will now go through the whole program again line by line, but this time it will execute the whole code. It will first encounter the variable n and now it will give variable n the value 2. So variable n will be changed from undefined to value 2. Nothing happens in the next line because we have already copied the function over and assigned it the memory it needs.

var square2 = square(n); // here we are invoking a function. Function is being called / executed. And functions are like mini-programs in javascript, and therefore we will create another execution conext which is called function execution context.
Brand new function execution context is created ( with memory creation phase and code execution phase). We have only two variables in the function square which are num and ans. They will get the value undefined in the first phase.

In the code execution phase ( var square2 = square(n) ) n is the argument and initialized as 2, so the value 2 will be the argument inside the function. So num will now be initialized as 2.
Next line is var ans = num * num, and here we are going to multiply the value of num. We will get 4, and ans is getting the value 4 now.
The next line afterwards is return ans. return means that the functions is done with its work and it can now return the control to the GEC, and on line where the function was invoked. It will return the value of ans which is for to the variable square2. After the function program is runned, the FEC will be deleted.

var square4 = square(4); // this is basically the same as the explantion upside.

And when Javascript is done with running through all the code, the global execution context will also be deleted.

Call stack in javascript;
- GEC is always at the bottom.
- Whenever a function is invoked, there will be a FEC which will be putted on top of the GEC.
- And when the FEC is finished, it will be removed out., and the GEC will take over.
- 

