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



/////////////////  Character access 
Last updated August 2022
You can access a specific character in a string by using the square brackets syntax [].

You have to provide the index of the character that you'd like to access, starting from 0.

Let's take an example where the variable language has the value: "JavaScript". Here's how you access the 1st character, the 2nd, and the 3rd:


const language = "JavaScript";

language[0]; //first character
language[1]; //second character
language[2]; //third character
If you'd like to debug your code and see the result of language[1] in the console, you have to console log it as follows:


console.log(language[1]);
Combining it with length
You can also combine the character access with the .length property. So using the same language variable, here's how you get the second to last character from it:


const language = "JavaScript";

language[ language.length - 2 ]; // "p" because it's the second to last character from "JavaScript"
Note that language[ language.length ] will be undefined because character access starts at 0.
So for a string of 9 characters, 8 is the position of the last character.

The .at(index) method
Since 2022, JavaScript now has a .at() method that reads the character at a certain index, which can also be negative.

Let's take a look at a few examples:

const language = "JavaScript";
language.at(0); // "J"
language.at(1); // "a"
language.at(-1); // "t"
language.at(-2); // "p"
The primary use case for the .at() method is negative indices, making it easier than relying on the .length property. However, you can use whichever approach you prefer.

When a negative index is specified, you start counting from the end. -1 is the last character, -2 is the one before it, etc.

You can continue using the square bracket syntax for all other use cases, knowing that language[-1] returns undefined. So, whenever you want to use a negative index, you should use the .at() method.

JSDoc
By now, you probably noticed that most of the challenges start with some comments that look like this:

/**
 * @param {string} name
 */
These comments are used to improve your coding experience. They let the code editor know what methods to suggest to you while you're typing. So you can ignore these comments. You will never have to change them or add them, and they don't affect the tests.

What is the "Sample usage"?
You may have also noticed that every challenge has some sample usage code at the end. For example, for the function getCharCount, we had:

// Sample usage - do not modify
console.log(getCharCount("Sam")); // 3
console.log(getCharCount("Alex 123")); // 8
console.log(getCharCount("Charley is here")); // 15
The goal of the sample usage is to show you the various ways we expect to call the function. Sometimes, we show you the expected output next to it in a comment.

Note that in the tests, we end up calling your function with more examples not visible in the sample code. The goal of this is to make sure that you've provided a correct answer that works in several scenarios, not just one or two scenarios.

Recap
Square brackets [index] are used to access a specific index from a string.
The index starts at 0. So the first character is index 0.
You can combine it with the length of a string to get another character in another position.
The .at() method allows you to read a character at an index (which can also be negative).



///////////////////// Substrings 

Last updated June 2021
A substring is a part or a portion of a string. For example, "rain" is a substring of the string "brain" because you can get "rain" by taking the last 4 characters.

When working with strings, you often need to get a few characters of a string rather than all of it. Thus we use the substring method.

Substring signature
A function signature gives you an explanation of the parameters that you need to pass for that method. Let's take a look at the signature of substring:

someString.substring(indexStart, indexEnd)
This means that when you call substring, you can give it 2 parameters, the first one for the indexStart and the second one for indexEnd.

indexStart: the position of the first character you'd like to include
indexEnd: the position of the first character you'd like to ignore
This means an indexEnd of 5, will only include up to character 4.

The combination of these 2 will give you a substring.

Let's take an example with a variable named language with a value JavaScript, and let's get the substring with indexStart of 1 and indexEnd of 4. This will return a string made up of all the characters from positions 1 to 3 because 4 is the first character that is ignored:

Substring example

The result of such substring is "ava".

Here's how you'd write it in JavaScript:


const language = "JavaScript";
language.substring(1, 4); //"ava"
Optional parameters
The indexEnd parameter is optional, which means you can pass the indexStart and it'll assume the indexEnd to be the same as the string length. Here's an example:


language.substring(4); //"Script"
It assumed that the indexEnd is the length of the string (10 in this example).

Legacy note
If you already know a bit of JavaScript, you might have used another method that performs a similar result. You can find the name of the function below, but we do not recommend that you use it because it's deprecated.

Do not use the .substr method as it's deprecated and works differently. Always use the .substring method.

Recap
A substring is a part or a portion of a string.
string.substring(indexStart, indexEnd) is used to return a portion of the string.
indexStart: the position of the first character you'd like to include.
indexEnd: the position of the first character you'd like to ignore.
the indexEnd argument is optional which means you can leave it out.



////////////////////  Plus operator 
Last updated January 2022
Good job on finishing your first real-world challenge. We will revisit this text ellipsis project several times in the following chapters so that we improve it.

In JavaScript, the plus operator (+) will behave differently based on the types of values you use it with.

You've already seen that 1 + 3 will return the number 4.

However, you could also use the + to concatenate 2 strings together, which means merging them together into 1 string.

Here's an example:


"Hello" + "World" //"HelloWorld"
will return one string: "HelloWorld". This would be useful if you'd like to concatenate 2 or more strings together. For example:


let prefix = "Mrs.";
let name = "Sam";
let string = prefix + " " + name; // "Mrs. Sam"
It's also possible to do the above with string interpolation, which is covered in the next lesson.

+= operator
Say you have the following code:


let name = "Sam";
name = name + " Blue";
console.log(name); // "Sam Blue"
You can rewrite the name = name + in a shorter way using the += operator:


let name = "Sam";
name += " Blue";
console.log(name); // "Sam Blue"