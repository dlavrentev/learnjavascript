Let's start with basic functions:


function sum(x, y) {
    return x + y;
}
This piece of code defines a function called sum.
This means that you can now call sum(1, 3) which returns 4.
You can run it again with different values, such as sum(2, 5) and it will return the result of 2 + 5 which is 7.

Returning the result
In JavaScript, you have to return from inside functions. If you forget to write return, your function will return undefined.

The return keyword will also quit/exit the function.


function sum(x, y) {
    return x + y;
    console.log("Hello World"); // this will NEVER run
}
The return keyword will quit the function with the result (which is x + y), so the code afterward will never run!

