## Object.is()
It is used to compare two values and determine whether they are equal or not.

The basic syntax of Object.is is as follows:

Object.is(value1, value2)
Object.is returns a boolean value (true or false) that indicates whether the two values are equal. Unlike the == and === operators, which perform a weak or strict equality comparison, Object.is performs a more precise and consistent comparison.

The following are some key features of Object.is:

Treats NaN as equal to NaN: Unlike the equality operators (== and ===), Object.is considers NaN to be equal to NaN. For example:
Object.is(NaN, NaN); // true
NaN === NaN; // false
NaN == NaN; // false

Treats -0 and 0 differently: Unlike the equality operators (== and ===), Object.is considers -0 and 0 to be different values. For example:
Object.is(-0, 0); // false
-0 === 0; // true
-0 == 0; // true

Compares objects strictly: Object.is compares objects strictly, meaning it only returns true if the two objects are identical (i.e., have the same memory reference). For example:
const obj1 = {};
const obj2 = {};
Object.is(obj1, obj2); // false
obj1 === obj2; // false
obj1 == obj2; // false

const obj3 = obj1;
Object.is(obj1, obj3); // true
obj1 === obj3; // true
obj1 == obj3; // true
In summary, Object.is is a method used to compare two values and determine whether they are equal or not. It is more precise and consistent than the equality operators (== and ===) and treats NaN and -0 and 0 specially. It also compares objects strictly, meaning it only returns true if the two objects are identical (have the same memory reference).

## Object.Assign()
Object.assign is a method used in JavaScript to copy the values of all enumerable properties from one or more source objects into a target object. In other words, Object.assign takes a target object and "mixes" it with one or more source objects, creating a final object that contains all the properties and values of the source objects.

The basic syntax of Object.assign is as follows:

Object.assign(target, source1, source2, ...)
Where target is the target object and source1, source2, etc. are the source objects to be mixed into the target object. Object.assign returns the target object.

## Object.GetPrototypeOf() and Object.SetPrototypeOf()
Object.getPrototypeOf() and Object.setPrototypeOf() are two methods in JavaScript that allow you to interact with an object's prototypes.

First, Object.getPrototypeOf() is used to get an object's prototype. Every object in JavaScript has a prototype, which is an object used as a template for the object in question. For example:

const myObject = {a: 1};
const myPrototype = Object.getPrototypeOf(myObject);
console.log(myPrototype); // Object {}

In this example, myObject has a prototype of Object {}, which is the default prototype in JavaScript.

On the other hand, Object.setPrototypeOf() is used to set the prototype of an object. For example:

const myObject = {a: 1};
const myPrototype = {b: 2};
Object.setPrototypeOf(myObject, myPrototype);
console.log(Object.getPrototypeOf(myObject)); // {b: 2}

In this example, we have set the prototype of myObject to {b: 2} instead of the default prototype. This means that myObject will now inherit the properties and methods defined in {b: 2}.

However, it's important to note that using Object.setPrototypeOf() is not recommended unless absolutely necessary. Changing an object's prototype can be very inefficient and can have unintended side effects. In general, it's better to avoid it and instead use prototype inheritance through class syntax or object copying with Object.assign().

## Object Destructuring
Object destructuring is a JavaScript feature that allows you to extract values from an object and assign them to variables more concisely. This can help make your code more readable and easier to understand.

The basic syntax for object destructuring is as follows:

const { property1, property2 } = object;
In this syntax, property1 and property2 are variable names used to extract values from the object. The object is passed as an argument and then destructuring extracts the values of the corresponding properties and assigns them to the variables.

For example, if we have an object person that contains the properties name and age, we can use object destructuring to extract these values and assign them to variables with the same names, as follows:

const person = { name: "John", age: 30 };
const { name, age } = person;

console.log(name); // "John"
console.log(age); // 30
You can also assign the extracted values to variables with different names:

const { name: myName, age: myAge } = person;

console.log(myName); // "John"
console.log(myAge); // 30
In addition, you can provide default values for variables in case the property does not exist in the object:

const { name, age, job = "Unknown" } = person;

console.log(name); // "John"
console.log(age); // 30
console.log(job); // "Unknown"
Object destructuring can also be used in function parameter assignment:

function showPerson({ name, age }) {
  console.log(`${name} is ${age} years old.`);
}

const person = { name: "John", age: 30 };
showPerson(person); // "John is 30 years old."
In summary, object destructuring is a useful and efficient way to extract values from an object in JavaScript.

## Array Destructuring
Array destructuring is another JavaScript feature that allows you to extract values from an array and assign them to variables more concisely.

The basic syntax for array destructuring is as follows:

const [ value1, value2 ] = array;
In this syntax, value1 and value2 are variable names used to extract the corresponding values from the array. The array is passed as an argument and then destructuring extracts the values of the corresponding elements and assigns them to the variables.

For example, if we have an array numbers that contains the values [1, 2, 3], we can use array destructuring to extract these values and assign them to variables, like this:

const numbers = [1, 2, 3];
const [firstNumber, secondNumber, thirdNumber] = numbers;

console.log(firstNumber); // 1
console.log(secondNumber); // 2
console.log(thirdNumber); // 3
You can also use array destructuring to extract only some values from the array and assign the remaining ones to an additional variable, using the ... operator:

const numbers = [1, 2, 3, 4, 5];
const [firstNumber, secondNumber, ...restOfNumbers] = numbers;

console.log(firstNumber); // 1
console.log(secondNumber); // 2
console.log(restOfNumbers); // [3, 4, 5]
Additionally, you can omit values from the array using consecutive commas:

const numbers = [1, 2, 3, 4, 5];
const [, , thirdNumber, fourthNumber] = numbers;

console.log(thirdNumber); // 3
console.log(fourthNumber); // 4
Array destructuring can also be used in assigning function parameters:

function addValues([value1, value2]) {
  return value1 + value2;
}

const numbers = [5, 7];
console.log(addValues(numbers)); // 12
In summary, array destructuring is a useful and efficient way to extract values from an array in JavaScript.
