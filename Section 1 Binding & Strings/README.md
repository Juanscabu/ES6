# Topics

## Var vs Let
The main difference between **var** and **let** is the variable's scope. Variables declared with **var** have function scope, which means they are accessible within the function in which they are declared, while variables declared with **let** have block scope. Additionally, variables declared with **var** are hoisted to the top of the function, which means they can be used before being declared, while this is not the case with variables declared with **let**. In summary, it is recommended to use **let** instead of **var** to have greater control over your variables scope and avoid issues like hoisting, although **var** is still useful in certain cases.

## Const
**const** is used to declare constants, whose value cannot be modified after being declared. Constants are useful in situations where it is important that the value of a variable does not change, such as in the case of a mathematical constant or a string used in multiple places in the code. The scope of a constant is limited to the block in which it is declared, just like with variables declared with **let**.

## String Functions
**startsWith**: This method is used to check whether a string starts with the specified substring. It returns **true** if the string starts with the substring and **false** otherwise.

**endsWith**: This method is used to check whether a string ends with the specified substring. It returns **true** if the string ends with the substring and **false** otherwise.

**includes**: This method is used to check whether a string contains the specified substring. It returns **true** if the string contains the substring and **false** otherwise.

**repeat()** is a method available in the prototype of the String class that is used to repeat a string of characters multiple times.

## Literal Templates
Template literals are a way to define text strings in JavaScript that allows for a more readable and functional syntax for string concatenation and value interpolation.

Instead of using single or double quotes to define a text string, backticks (`) are used. Within a text string defined with backticks, variables and expressions can be included within placeholders using the syntax ${expression}.

For example, instead of concatenating variables and strings using the + operator, a template literal can be used to achieve the same result in a more readable and functional way

## Template Tags
Template tags allow modifying the behavior of string literals. Essentially, they are functions that are invoked with a string literal as an argument, and can manipulate and process that text string in some way before it is evaluated and rendered.
The syntax for using a template tag is to add the name of the function in front of the string literal using backticks
