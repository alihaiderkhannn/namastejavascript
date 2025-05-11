# How function invokatin works behind the scenes

// introducing something in the global space here.

var x = 1;
a();
b();
console.log(x);

function a(){
    var x = 10;
    console.log(x);
}

function b(){
    var x = 100;
    console.log(x);
}

This will summarize execution context, hoisting, function invokation etc.
We are first creating a (global) execution context, because everything that happens inside javascript happens inside an execution context. An execution context will be created when a javascript program runs, and every js program has only one global exectution context on the top of the program.

Now in the GEC (global execution context) which is like a container/big box, we are creating two components. One for the memory creation phase and the second one for the code execution phase. In the first phase we are allocating memory for all the variables and functions in the program. var variables will get the value undefined and the functions will be directly copied over with their full body. So x will get the value undefined in the first phase, and a() and b() will be like a({...}) and b({...}).

After doing this we will go over to the code execution phase. x will now get the value 1. In the second line we are seeing a function invokation and therefore we will create a function execution context. So the GEC will stop on line 2, and we will move inside function a() and create the same execution context with two components. x will first be undefined and later it will get the value 10 and it will console.log this value. So the console will hold on to value 10. After this we will delete this FEC and go back to the GEC.

In the third line we are seeing another function invokation b() and do exactly the same. x is undefined first, then get the value 100 in the second phase, console log it, holds the value in the console and then delete this FEC.

In the third line it will console.log(x) and the only x we have in memory and in the global space is the x we defined in the global space which is 1.
So the answer here is,
10
100
1.