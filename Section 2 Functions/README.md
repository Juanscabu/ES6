## Optional Parameters
Optional parameters in JavaScript are a feature introduced in ES6 that allows declaring function parameters that do not need to be passed in every function call. This is useful when you want a function to have a default behavior if some of its arguments are not provided.

You can define a parameter as optional using the syntax of parameter = defaultValue. For example:

function greet(name, greeting = 'Hello') {
  console.log(`${greeting}, ${name}!`);
}

greet('John'); // Hello, John!
greet('Mary', 'Good morning'); // Good morning, Mary!
In this example, the parameter greeting is defined as optional with the default value of 'Hello'. If the function is called without providing the second argument, the default value is used.

## Rest Parameters
Rest parameters allow functions to accept a variable number of arguments as an array. This is achieved by using three consecutive dots ("...") before the last parameter of a function.

Let's see an example to better understand it:

function sum(...nums) {
  return nums.reduce((total, num) => total + num);
}

console.log(sum(1, 2, 3)); // output: 6
console.log(sum(4, 5, 6, 7)); // output: 22
In this example, the sum function accepts a variable number of arguments using the rest parameter ...nums. The arguments are converted into an array called nums inside the function. Then, the function uses the reduce method to sum the numbers in the array and returns the result.

The advantage of rest parameters is that they allow you to write functions that accept any number of arguments without having to specify each one of them in the function definition. This makes the code more flexible and easier to maintain. Additionally, rest parameters can also be used in combination with other parameters.

## Spread Operator and Passed-by-Reference Objects
The spread operator allows developers to expand an iterable (such as an array or an object) in places where multiple arguments or elements are expected. This is achieved by using three consecutive dots ("...") before the iterable.

Let's see some examples to better understand how the spread operator works:

// Example with arrays
const nums = [1, 2, 3];
const moreNums = [...nums, 4, 5, 6];
console.log(moreNums); // output: [1, 2, 3, 4, 5, 6]

// Example 2
const person1 = {name: "John", age: 27};
const person2 = {...person1};

// Example 3
const person1 = {name: "John", age: 27, vehicle: true, drives: true};
const person2 = {name: "Manuel", age: 25};

person2 = {...person2, ...person1};
In the first example, the spread operator is used to expand the nums array into the moreNums array. This means that the individual elements of the nums array are placed in the new moreNums array as comma-separated arguments. Then, the numbers 4, 5, and 6 are added to the end of the array.

In the second example, the spread operator is used to create a new object person2 that has all the properties of person1 but is not a reference to it (since in JavaScript, all objects are referenced) but rather
