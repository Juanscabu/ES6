Sets
## Sets
A Set is a data structure that represents a collection of unique values, meaning that duplicate values are not allowed. The values within a Set can be of any data type, including primitive types and complex objects.

The basic methods that we can use on a Set are as follows:

new Set(iterable): Creates a new Set object. If an iterable argument is provided, such as an array, an iterable object, or a string, the elements of the iterable are added to the Set.
set.add(value): Adds a new element to the Set. If the element already exists, it is not added.
set.delete(value): Removes an element from the Set. Returns true if the element was successfully removed, and false if the element does not exist.
set.has(value): Returns true if the Set contains the specified value, and false otherwise.
set.clear(): Removes all elements from the Set.
set.size: Returns the number of elements in the Set.
set.values(): Returns an iterable object containing the values of the Set in the order in which they were inserted.
set.keys(): An alias for set.values(). Returns an iterable object containing the values of the Set in the order in which they were inserted.
set.entries(): Returns an iterable object containing pairs of values [value, value] for each element in the Set, in the order in which they were inserted.

## Removing duplicates from an array using Sets
One of the useful features of Sets is that, being a data structure that does not allow duplicate elements, we can use them to remove duplicates from an array in a very simple way.

To remove duplicates in an array using Sets, we can follow these steps:

Create a new Set object from the array containing duplicate elements.
Convert the Set object to an array using the Array.from() method or the spread operator ....
If we want to preserve the original order of the elements in the array, we can use the Map class and its set() and get() methods to remember the original position of each element in the array.
Here is an example of how we can remove duplicates from an array using Sets:

const arrayConDuplicados = [1, 2, 2, 3, 4, 4, 5];

const setSinDuplicados = new Set(arrayConDuplicados);

const arraySinDuplicados = Array.from(setSinDuplicados);

console.log(arraySinDuplicados); // Returns [1, 2, 3, 4, 5]
In this example, we create a new Set object from the arrayConDuplicados array, which contains duplicate elements. Then, we use Array.from() to convert the Set object to an array containing only the unique elements. The result is the arraySinDuplicados array, which contains [1, 2, 3, 4, 5].

If we wanted to preserve the original order of the elements in the array, we could do something like this:

const arrayConDuplicados = [1, 2, 2, 3, 4, 4, 5];
const mapPosicion = new Map();

const arraySinDuplicados = [];

for (const elemento of arrayConDuplicados) {
  if (!mapPosicion.has(elemento)) {
    mapPosicion.set(elemento, true);
    arraySinDuplicados.push(elemento);
  }
}

console.log(arraySinDuplicados); // Returns [1, 2, 3, 4, 5]
In this example, we create a Map object called mapPosicion to remember the original position of each element in the array. Then, we iterate over each element of the arrayConDuplicados array. If the element has not been seen before (i.e., it is not in mapPosicion), we add it to arraySinDuplicados and mark it as seen in mapPosicion. This way, we preserve the original order of the elements in arrayConDuplicados.

## WeakSets
WeakSets are a variant of Sets that allow for non-enumerable, weakly coupled object storage. That is, objects stored in a WeakSet are not counted in JavaScript's reference count, which means that an object stored in a WeakSet can be removed by JavaScript's garbage collector if there are no other references to it in the code.

The syntax for creating a WeakSet is as follows:

const myWeakSet = new WeakSet();
The way to use a WeakSet is similar to that of a Set. The main difference is that objects added to the WeakSet must be objects and not primitive values. Additionally, you cannot iterate over the elements of a WeakSet, as there is no forEach or values method.

Here are some basic methods that can be used with WeakSets:

add(object): Adds an object to the WeakSet.
delete(object): Removes an object from the WeakSet.
has(object): Returns true if the object is in the WeakSet, otherwise returns false.
WeakSets are useful when you want to store objects that should not affect JavaScript's reference count, such as DOM objects, objects used in caching, or temporary objects that are only needed for a short lifecycle. It is important to note that WeakSets cannot be used to safely store objects if they are still needed in other parts of the code, as JavaScript's garbage collector can remove them at any time.

## Maps
Maps are a data structure in which key-value pairs can be stored. Each element in a Map consists of a unique key and its corresponding associated value. Unlike an object, the key can be any type of data, including objects and functions.

The basic methods of Maps are as follows:

set(key, value): This method adds a new element to the Map. The first argument is the key, and the second argument is the value associated with that key.

const myMap = new Map();
myMap.set('key1', 'value1');
myMap.set('key2', 'value2');
get(key): This method returns the value associated with the specified key.
console.log(myMap.get('key1')); // 'value1'
has(key): This method returns true if the specified key exists in the Map, otherwise it returns false.

console.log(myMap.has('key1')); // true
console.log(myMap.has('key3')); // false
delete(key): This method removes the element with the specified key from the Map.
myMap.delete('key1');
console.log(myMap.has('key1')); // false
clear(): This method removes all elements from the Map.

myMap.clear();
console.log(myMap.size); // 0
size: This property returns the number of elements in the Map.

console.log(myMap.size); // 1
In addition, there are also other methods such as keys(), values(), and entries() that return iterators that you can use to iterate through and retrieve elements from the Map.

for (const [key, value] of myMap.entries()) {
  console.log(key, value);
}

## For...of for Iterable Collections
The for...of loop is used to iterate over iterable elements such as arrays, strings, maps, sets, and more. This loop is a simpler and more readable way to iterate over elements than the traditional for...in loop.

The basic syntax of the for...of loop is as follows:

for (const element of iterable) {
  // loop body
}
Where:

element: is a variable that represents the current element in each iteration of the loop.
iterable: is a variable that represents the iterable that will be iterated over.
Below are some examples of how to use the for...of loop on different types of iterables:

Arrays:
const arr = ['one', 'two', 'three'];

for (const element of arr) {
  console.log(element);
}
// output:
// 'one'
// 'two'
// 'three'
Strings:

const str = 'Hello';
for (const element of str) {
  console.log(element);
}

// output:
// 'H'
// 'e'
// 'l'
// 'l'
// 'o'
Maps:

const myMap = new Map([  ['key1', 'value1'],
  ['key2', 'value2'],
  ['key3', 'value3']
]);

for (const [key, value] of myMap) {
  console.log(key, value);
}
// output:
// 'key1' 'value1'
// 'key2' 'value2'
// 'key3' 'value3'
Sets:
const mySet = new Set(['one', 'two', 'three']);

for (const element of mySet) {
  console.log(element);
}

// output:
// 'one'
// 'two'
// 'three'
Keep in mind that the for...of loop only works with iterable objects. If you try to use it with a non-iterable object, like a plain object, it will throw an error.
