/////////// 1.Let's start with basic functions: //////////////////


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



/////////////// 2.Strings //////////////////////

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


///////////////////////////////    Template strings 
Last updated May 2021
You already know that you can create strings with double quotes or single quotes, but as you already know, these strings do not support interpolation.

Template strings, however, support interpolation and other nifty features.

Your first template string

`This is a template string`
The only difference is that template strings start and end with a backtick ` character.

The backtick is above the tab key on International keyboard layouts. For other keyboards, check out these threads for Windows/Linux & mac and look for your keyboard layout.

Multiline strings
Unlike single quote and double quote strings, template strings can span multiple lines. Here's an example:


let text = `This is a multiline
string that
just works!`
Whereas this would have not been possible with a normal string (single quotes or double quotes).

Interpolation
Template strings support interpolation! This means you could write a variable in your string, and get its value. The syntax is straightforward, you wrap your variable name with a dollar sign and curly braces. Let's take an example where we have a variable language with a value of JavaScript.


let language = "JavaScript";
`I am learning ${language}`; //"I am learning JavaScript";
Remember that string interpolation only works with backticks. If you ever try it and it doesn't work, double-check that you're using backticks rather than single or double-quotes.

Additional examples
How to write a multiline string
How to interpolate in JavaScript
Recap
A template string is a string created with the backtick character: `
Template strings can span multiple lines
Template strings support interpolation with the ${variableName} syntax


///////////////////////  Chapter recap 
Last updated August 2022
Congratulations on completing the Strings I chapter. We will dive deeper into strings in a future chapter, for now, make sure to review the key concepts from this chapter before we move on to the next one!

This is your first chapter recap! You can save it to your notes by clicking on the + icon on the top-right of the recap.

You can create strings with " or '.
.length is a property that gives you the length of a string.
.toUpperCase() is a function that converts the string to upper case.
.toLowerCase() is a function that converts the string to lower case.
parentheses () on function calls are required. .length is a property that is already pre-computed; therefore, it does not need parentheses.
console.log(...) is used for debugging and is NOT a replacement for return.
Square brackets [index] are used to access a specific index from a string.
The index starts at 0. So the first character is index 0.
You can combine it with the length of a string to get another character in another position.
The .at() method allows you to read a character at an index (which can also be negative).
A substring is a part or a portion of a string.
string.substring(indexStart, indexEnd) is used to return a portion of the string.
indexStart: the position of the first character you'd like to include.
indexEnd: the position of the first character you'd like to ignore.
the indexEnd argument is optional which means you can leave it out.
The + operator is used to add 2 numbers
The + operator is used to concatenate 2 strings
A template string is a string created with the backtick character: `
Template strings can span multiple lines
Template strings support interpolation with the ${variableName} syntax


/////////////////////// 3.Numbers /////////////////////////////////
Last updated August 2022
1
2
-5
3.5
2000
2021
-23.51
All of these are examples of Numbers in JavaScript. It doesn't matter if it's negative or positive, or if it has decimals (values after the .) or not. We call them numbers.

Numeric separator (_)
You can represent larger numbers clearer, if you wish, with using the numeric separator (_). For example:

let nb = 1_000; // equivalent to 1000
It makes larger numbers easier to read. For example:

let nb = 1_000_000; // 1000000 (1 million)
The _ is taken out by JavaScript from the number. So, 10_00 is equivalent to 1000.

Converting from number to string
Though rarely used, you can convert a number to a string by calling the .toString() method.
Let's take an example where we have a variable called answer with a value 42;


let answer = 42;
answer.toString(); //"42"
MDN logoNumber.toString() on MDN


In the next lesson, we'll see how to do the opposite. Converting a string into a number.

Documentation on the Web
If you take a look at online documentation, you will often see String.prototype.toString(). Why is there a prototype? This is covered in-depth later in this course. For now, every time you see String.prototype.something(), it means there is a method something() that you can call on a String.

Mozilla Developer Network is the most authoritative website for JavaScript documentation. If you're getting started with JavaScript, however, you might find it a bit hard to grasp.

Therefore in this course, we are aiming to provide you with short and easy-to-consume explanations, so you don't feel overwhelmed when you are just beginning your learning journey.

When you are comfortable with what Learn JavaScript says about a topic and want to dig deeper and find out more, look for the MDN logo MDN logo and click the link that follows it to access much more in-depth information.

NaN
You may sometimes encounter NaN which stands for Not a Number. For example, if you try to multiply a number by a string (which you should not do):


// ❌
"abc" * 4; // NaN
NaN is often a sign that something is wrong with your code, most often you forgot to convert a string to a number. One of the most common cases is when an object property evaluates to undefined because of a typo and then it's used as if it was a valid number (more on that in later chapters as we learn about objects and object properties).

Recap
Convert from a number to string: value.toString()
NaN stands for Not a Number
NaN is often a sign of a bug.


//////////////////    Convert string to number 
Last updated March 2022
In some scenarios (explained below), you'd like to convert from a string to a number. For that, you'd have to use the Number.parseInt() method.

Here's an example:


let str = "42";
Number.parseInt(str, 10); //42
There's a lot going on here, so let's break it down step by step.

The function name is called Number.parseInt(). Yes, including the Number. bit. This is because there's a global object called Number which contains a method called parseInt().

This Number.parseInt() method expects 2 parameters:


Number.parseInt(string, radix);
The first parameter is the string that you'd like to convert into a number. The second argument is the radix that will be used in the conversion.

The radix is the base of the numerical system that you'd like to use. For most use cases the radix you'd like to use is 10 which represents the way we count numbers in our everyday lives. This system is called the decimal system (because we have 10 fingers, so we use the digits from 0 to 9).

Another example of radix is 2 which represents binary (a numerical system used by computers). If you'd like to dig deeper into this concept, check out this simplified Wikipedia page about Mathematical bases.

As a quick summary, the radix will most often be 10. If you're not sure what radix to choose, then it's most likely 10.

Can I skip the radix?
Even though the radix is an optional parameter, you should not skip it. That's because it does not always default to 10.
So make sure to always pass the radix as the 2nd parameter.

Number.parseInt(string, radix) does not always default to a radix of 10.

If you do try Number.parseInt() without a radix of 10, it will work. However, there are some edge cases (numbers starting with 0x) that would break. Thus, to be safe, it's always recommended to pass the radix.

Make sure to always specify the radix to avoid unpleasant surprises.

MDN logoNumber.parseInt() on MDN


Legacy notes
JavaScript is an evolving language that is over 25 years old. It keeps changing and evolving. Legacy notes will explain some confusing behavior or old functions that you may have encountered a while ago.

If you are learning JavaScript for the first time, then you don't need to spend a lot of time in those legacy notes.

Number.parseInt() and parseInt() are exactly the same thing. Prefer Number.parseInt() over parseInt().

A while ago, parseInt(string, radix) was the only way to convert numbers, however, a while later, this function has been cloned under the Number object and became Number.parseInt(string, radix) in an effort to group similar functions together under their relevant object.

They both work exactly the same. We do recommend that you stick with the modern approach which is Number.parseInt().

Use cases for converting to a number
There are several reasons why you'd like to convert a string to a number, but the most common one is when the number is entered by the user in a text box or the number is being read from the DOM (which is explained later on).

As you will see in the next challenge, these values will always be a string (even if the user writes a number). Thus, it is your job to convert it to a number.

If you forget to convert a string to a number, you will see that the intended addition is behaving like concatenation:

let a = 10;
let b = "20"; // we forgot to convert it to a number
a + b; // "1020" (concatenation instead of sum)
The Number.parseInt() method will try to convert the string it receives into a number. As you can see below, it most often works when the string starts with a number and ends with non-numeric values:


Number.parseInt("123abc", 10); // 123
Number.parseInt("5 meters", 10); // 5
Recap
Convert from string to number Number.parseInt(value, 10).
Number.parseInt() is the name of the function you're calling.
10 is the radix which you should specify.
Make sure to always specify the radix to avoid unpleasant surprises.


////////////// Operations 
Last updated January 2022
As you might expect, numbers can be multiplied and divided. We've already done an example of multiplication at the beginning of the course, using the * operator.
For division, you need to use the / operator.

Division remainder
You can also use the remainder operator % which returns the division remainder. Here's an example:


8 % 2; // Division remainder is 0
7 % 2; // Division remainder is 1 
Here's how the division remainder of 8 % 2 is calculated:

8 / 2 = 4
4 / 2 = 2
=> division remainder is 0 because 8 = 4 * 2 + 0

Where as for 7 % 2:

7 / 2 = 3 (rounded)
=> division remainder is 1 because 7 = 3 * 2 + 1

We'll use the division remainder in 2 chapters from now to check whether a number is even or odd.

MDN logoRemainder (%) on MDN


Number methods
While there are some other methods you could call on numbers, they are not very commonly used. What is commonly used, however, is the Math object which contains methods such as min(), max(), round(), etc.

Recap
The remainder operator (%) returns the division remainder between 2 numbers.


Chapter Recap
Convert from a number to string: value.toString()
NaN stands for Not a Number
NaN is often a sign of a bug.
Convert from string to number Number.parseInt(value, 10).
Number.parseInt() is the name of the function you're calling.
10 is the radix which you should specify.
Make sure to always specify the radix to avoid unpleasant surprises.
The remainder operator (%) returns the division remainder between 2 numbers.


/////////////////////// 4 Variables ///////////////////////////////
Last updated April 2022
Now that you've completed the first 3 chapters of this course, we recommend that you read the Features & FAQ page from the top-right menu.
This will familiarize you with all the features available in this app as well as the reasoning behind some of them. It also explains the importance of sleep when learning something new!

There are 2 ways to define a variable in JavaScript. Let's take a look at the difference between let and const.

let
The first time you define a variable, you have to prefix it with let = . Let's take an example:


let name = "Sam";
console.log(name);
This defines a variable called name with a value of "Sam". The next time you'd like to use that variable, you reference it by its name (you only use the let keyword for declaration).

Variables defined with let, can be re-assigned later on:


let language = "C++";
language = "JavaScript";
Another example with numbers:

let sum = 0;
sum += 1;
This is especially useful when you want to create a variable that needs to be incremented/decremented (such as a counter).

MDN logolet on MDN


const
Variables defined with const cannot be re-assigned. This means you can use the = sign only once when defining the variable. Here's an example:


const language = "C++"; // Cannot be re-assigned anymore
console.log(language); // "C++"

language = "Python" // ❌ Type error: this will break your script 
MDN logoconst on MDN


A note about const
An important note about const is that it does not create a Constant or an Immutable value. This will be thoroughly explained once we learn about arrays & objects. What you need to know, for now, is that you can only use the equal sign once, but you can still change elements inside an array or object.

let vs const
How do you decide if you're going to use let or const? The general rule is easy. Always go with const, until you realize that you need to be able to re-assign the variable later on, then switch it to let.
With time it becomes easier. For example, when you define a variable count (that you expect to increment), you will immediately realize that and use let.

The benefit of using const is that once a variable is an array, it will always be an array (but as you will see later on, the elements inside the array might change). This allows you to confidently use array methods on that variable because you know it will always be of type array.

Can I use 'var'?
When you're browsing the Internet for documentation, or Questions & Answers on StackOverflow, you will see a lot of code snippets using var instead of let & const.
Even though var still works, its usage is discouraged as it may be confusing in a lot of scenarios. So you can simply replace var with let (or const if the variable is not being reassigned).

Avoid using var when defining variables. Use let or const instead.

A thorough explanation of why you should avoid var is available towards the end of the course. We follow a unique approach in this course where we teach you modern JavaScript before uncovering the legacy and it has worked quite well for most of our students!

Recap
When you use a variable for the first time in JavaScript, you need to declare it with either let or const.
Use let for variables that you will need to re-assign later on (as in changing their value)
Use const for variables that you won't need to re-assign later on.
Variables declared with const are not constant. We will see why later in this course.
Variables declared with const cannot be re-assigned so you cannot have the = next to that variable name after declaring it.
If you see var, it's from the old version of JavaScript. You can convert it to let (sometimes const if the variable is not re-assigned).