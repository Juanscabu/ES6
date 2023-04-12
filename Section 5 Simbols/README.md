# Topics

## Symbols
A symbol in ES6 is a new primitive data type that is used to create unique and immutable identifiers. Symbols are created using the Symbol() function and can be used as keys in objects and object properties. We can also assign an optional description to the symbol, which makes it easier to identify when reading the code. Additionally, ES6 also includes some predefined symbols that can be used for certain tasks. Some examples of predefined symbols are:

Symbol.iterator: used to define a custom iterator for an object.

Symbol.toStringTag: used to define the string tag of an object.

Symbol.hasInstance: used to define a custom function to determine if an object is an instance of a certain class.

In summary, symbols in ES6 are a useful tool for creating unique and immutable identifiers, which can be used as keys in objects and object properties.

## Symbol.for() & Symbol.keyFor()
Symbol.for() is used to create global symbols that can be retrieved anywhere in the code. If Symbol.for() is used to create a symbol with a specific name, and then the same function is used to create another symbol with the same name, the same symbol will actually be returned in both cases.

Symbol.keyFor() is used to retrieve the name of a global symbol created with Symbol.for(). If a non-global symbol is passed, Symbol.keyFor() will return undefined.

## Object.getOwnPropertySymbols()
Object.getOwnPropertySymbols() is used to retrieve an array of all symbols that are own properties of an object. For example, if we have an object myObject that contains some symbol properties, we can retrieve an array of those properties using Object.getOwnPropertySymbols()
Also, it's important to note that Object.getOwnPropertySymbols() only retrieves symbol properties that are own properties of the object and not those inherited from its prototype chain. If we want to retrieve all symbol properties of an object, including the inherited ones, we can use the Reflect.ownKeys() method, which returns an array that includes all own and inherited properties of the object, including symbols.
