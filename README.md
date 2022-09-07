/////////// Let's start with basic functions:


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



/////////////// Strings

You can create a string in JavaScript by using the double quotes (") or single quotes (').

Here's an example:

"This is a string";
'This is another string!'
There is no difference between using a double quote or a single quote. They are exactly the same. Neither of these strings support interpolation (which means replacing a variable with its value inside of a string). String interpolation will be covered in a future lesson.

String property
The .length property is used to return the length of the string.

Here's an example of getting the length of "Nice!":

"Nice!".length;
 //5

Assuming you have a variable called text, here's how you'd get its length:


let text = "Hello World";
text.length; // 11
Basic String methods
Here are some common methods that you can call on strings:

.toLowerCase()
This will return a new string that has all of its characters in lower case:


"BLUE".toLowerCase(); // "blue";
Note that .length should not have () after it because it is a property (a value that has already been computed). Whereas .toLowerCase() is a method that requires the () because it's an action that you are performing.

.toUpperCase()
This will return a new string that has all of its characters in upper case:


"red".toUpperCase(); // "RED";
Visualize a variable (or expression)
When solving challenges feel free to use console.log() to visualize a variable or expression. It will show up in the console tab.

function sum(a, b) {
    console.log(a);
    console.log(a + b);
    return a + b;
}

// Sample usage
sum(1, 3);
With the code above, you will see 1 then 4 logged to the console because of the console.log(a) and console.log(a + b).

Note that console.log() is NOT a replacement for return. You still have to return after the console.log.

Recap
You can create strings with " or '
.length is a property that gives you the length of a string
.toUpperCase() is a function that converts the string to upper case
.toLowerCase() is a function that converts the string to lower case
parentheses () on function calls are required. .length is a property that is already pre-computed; therefore, it does not need parentheses.
console.log(...) is used for debugging and is NOT a replacement for return.