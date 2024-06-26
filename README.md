﻿# typescript_workbook


### 1. Explain the data types available in TypeScript.

There are mainly two types of data types available in TypeScript:

Built-in data types: These data types already exist in typescript. They can be directly used to define the variables with different values.


String: It represents a text value like “GeeksforGeeks”, or “Computer Science”.
Number: It represents the numbered values i.e. 2, 28, 99, etc.
Boolean: It stores true or false values.
Null: An empty value deliberately assigned to a variable.
Undefined: Represents a variable that is declared but not initialized.
any: Represents any value of any data type and any number of values of different data types.
void: Used to represent that a particular function is not going to return any value of any data type.
User-defined data types: These are the data types that are defined by the user they may contain multiple values of multiple data types.

arrays: In typescript, arrays are used to store the multiple values of any kind of data type.
enums: A special class that specifies the constant variables.
classes: Used to store different data type values in the form of key-value pairs.
Interface: These represent the basic syntax and blueprint that an entity must adhere to.

### 2. Explain the behavior of arrays in TypeScript.

The arrays defined in typescript are different from JavaScript and they also behave differently from JavaScript arrays. In typescript, the arrays are defined by specifying the static data types and can only store the multiple values of a single kind of data type.

Example:

const typedArray1:number[] = [1, 23, 28, 56];
console.log(typedArray1);  // 1, 23, 28, 56

const typedArray2:number[] = [1, 23, 28, 56, "GeeksforGeeks"];
console.log(typedArray2); 
// Throws an error: Type 'string' is not assignable to type 'number'.

### 3. In how many ways we can declare variables in TypeScript?

In TypeScript, there are three ways in which we can declare variables:

Using the var keyword: It is the oldest way of declaring varibles.
var name: string = "GeeksforGeeks";
Using the let keyword: It was introduced in ES6 or ECMAScript 2015. It is a secure way of declaring variables than using var, as it has block scope.
let name: string = "GeeksforGeeks";
Using the const keyword: It was also introduceb in ES6. It is used to declare the constant variable whose values will not change throughout the code execution.
const name: string = "GeeksforGeeks"

### 4. How you can declare a explicit variables in Typescript?

In typeScript, you can declare static variables using the colons (:) followed by the data type of the explicit type. You can not assign a value of some other data type to a static variable. The values of the same data type can be assigned.

Syntax:
let variable_name: data-type = value;
Example:

let company_name: string = "GeeksforGeeks";
company_name = "Cricket";
console.log(company_name); // Prints Cricket

company_name = 28;
console.log(company_name); 
// Throws an error: Type '28' is not assignable to type 'string'.

### 5. How to declare a function with typed annotation in TypeScript?

In TypeScript, you can declare the functions by defining the type of parameters the take and the type of parameter it will return after the execution.

Example:

function annotedFunc(myName: string, age: number): string{
    return `My name is ${myName} and my age is ${age}.`;
}
console.log(annotedFunc("Emrit", 22));

// Prints: My name is Emrit and my age is 22.
console.log(annotedFunc("Neha", "18")); 

// Above statement throws an error: 
// Argument of type '"18"' is not assignable to parameter of type 'number'.

### 6. Describe the any type in TypeScript.

The any data type will allow you to assign the value of any data type to a variable. Sometimes, when the data is coming from other resouces like API call or user entered data. In that case, you may not aware of the type of the data so you can use the any data type to assign the value of any kind to a variable.

Example:

let studentData: string = `{
    "studentName": "Aakash",
    "studentID": 12345,
    "studentCourse": "B. Tech"
}`;
let student: any = JSON.parse(studentData);

console.log(student.studentName, student.studentID, student.studentCourse);
// Prints: Aakash 12345 B. Tech

### 7. What are the advantages of using TypeScript?

There are a lot of advantages of using TypeScript, some of them are listed below:

The TypeScript code can compile down to the JavaScript code that is runnable on every browser.
It allow us to declare strongly or statically typed variables.
It consist of advanced features like code completion, intelliSense etc.
It supports namespace concept with the help of modules.
TypeScript throw errors at the compilation time during development unlike of JavaScript that shows errors at the runtime.

### 8. List some disadvantages of using TypeScript.

There also exist some disadvantages of using TypeScript as listed below:

The concept of abstract classes is not supported by TypeScript.
Code Compilation is a time taking process in TypeScript.
A extra step of converting the TypeScript code into JavaScript code requires while running TypeScript.
A definition file needs to be added for using any external or third party library. All the external libraries not have the definition file.
The quality of all the definition files need to be correct.

### 9. Explain the void type in TypeScript.

It is just opposite of any type. The void type represents the unavailability of the data type for any variable. It is mainly used with the functions that returns nothing. The variables defined using the void keyword can only be assigned with the null and undefined values.

Example:

function favGame(): void{
    console.log("My Favourite game is Cricket.");
}
favGame(); 
// Prints: My Favourite game is Cricket.

### 10. What is type null and its use in TypeScript?

The null keyword is considered as a data type in TypeScript as well as in JavaScript. The null keyword basically indicates the unavailability of a value. It can be used to check whether a value is provided to a particular variable or not.

Example:

function getData(orgName: string | null, orgDesc: string | null): void {
    if (orgName === null || orgDesc === null) {
        console.log("Not enough values provided to print.");
    }
    else {
        console.log(`Organization Name: ${orgName}, 
        \nOrganization Description: ${orgDesc}`);
    }
}

getData(null, null);
getData("GeeksforGeeks",
    "A Computer Science Portal.");
Output:

Not enough values provided to print.
Organization Name: GeeksforGeeks,
Organization Description: A Computer Science Portal.

### 11. Describe the syntax for creating objects in TypeScript.

A object is basically a collection of key-value pairs, where each key needs to be unique. In TypeScript, the objects can be created by declaring the property name and the type it is going to store.

Example:

const myObj: { name: string, desc: string } = {
    name: "GeeksforGeeks",
    desc: "A Computer Science Portal"
};
console.log(myObj);
// Prints: { name: 'GeeksforGeeks', desc: 'A Computer Science Portal' }

### 12. Can we specify the optional properties to TypeScript Object, if Yes, explain How?

Yes, we can declare the TypeScript Objects by specifying the optional properties that may or may not be defined inside the object. We can declare these peoperties by using a ? symbol just after the property name while creeating the object.

Example:

const myObj: { name: string, desc: string, est?: number } = {
    name: "GeeksforGeeks",
    desc: "A Computer Science Portal",
};
console.log(myObj);
// Prints: { name: 'GeeksforGeeks', desc: 'A Computer Science Portal' }
myObj.est = 2008;
console.log(myObj);
// Prints: { name: 'GeeksforGeeks', desc: 'A Computer Science Portal' , est: 2008}

### 13. Explain the undefined type in TypeScript.

The concept undefined in TypeScript is similar to the concept of undefined in JavaScript. The undefined is used to indicate a variable which is declared but not assigned a value and it’s either hoisted or in temporal dead zone. The memory to these kind of variables is allocated in the memory allocation phase and a undefined value assigned to them untill a value is assigned by the developer or programmer.

### 14. What is never type and its uses in TypeScript?

A never type in typescript is indicate the values that may never be occured. It is mainly used with the function that return nothing and always thrown an exception or error. A never type is different from void type. Because, a function that returns nothing implicitly returns undefined and these functions are inferred using the void keyword. But a function that declared using the never keyword will never return a undefined it only returns never type. The never type can be used with following cases:

With an infinite loop.
In a function that throws exceptions or errors.
Example:

function neverFunc(): never{
    // Function Statements
}

### 15. Explain the working of enums in TypeScript?

An enum in typescript is used to create a collection of constants. It is basically a class that allow us to create multiple constants of numeric as well as string type. By default, the value of numeric constant starts from 0 and increases accordingly for every constant by a margin of 1. You can also change the initialisation value from 0 to any other value of your choice. It is declared using the enum keyword followed by the name of enum and constants.

Example:

enum demoEnum{
    milk = 1,
    curd,
    butter,
    cheese
}
let btr: demoEnum = demoEnum.butter;
console.log(btr)
// Prints: 3

### 16. Is TypeScript strictly statically typed language?

No, TypeScript is not a strictly statically typed language it is an optional statically typed language that means it is in our hands that a particular variable has to be statically typed or not. We can use the any type and allow a variable to accept the value of any kind of data type. We can also define a variabe with a particular data type that a variable can accept and throws error if a value of some other data type is assigned to it.

### 17. Is template literal supported by TypeScript?

Yes, template literal is supported by TypeScript. We can interpolate a string using the template literals syntax (“) in TypeScript. The values of different variables can be shown inside a string using ${variable_name} syntax while interpolating strig using template literals.

### 18. Differentiate between the .ts and .tsx file extensions given to the TyppeScript file.

The .ts file extension is used to create a file that contains the pure TypeScript code inside it. These files are mainly created to implement the classes, functions, reducers and other pure typescript code. These files does not contain any JSX code. On the other hand, the .tsx file extensions are used to create the files that contains the JSX code inside it. These files are mainly used to build a react component that returns the JSX code at the end.

### 19. Explain typeof operator in TypeScript and where to use it.

The typeof operator is used to check or get the type of a particular variable. It can also be used to set the similar explicit type to another variables.

Example:

const strVar: string = "GeeksforGeeks";
const numVar: number = 28;
console.log(typeof strVar, typeof numVar); //Prints: string number

const numVar2: typeof numVar = 25;
const strVar2: typeof strVar = "Cricket";
console.log(typeof strVar2, typeof numVar2); //Prints: string number

### 20. Explain the parameter destructuring in TypeScript.

The parameter destructuring is nothing more than the unpacking of the provided or passed object properties individually into the one or more parameters when the object is passed to an function. It can be done as shown below:

function getOrganisation({ org_name, org_desc }: { org_name: string, org_desc: string }) {
    console.log(`Organization Name: ${org_name}, \nOrganization Description: ${org_desc}`);
}
getOrganisation({ org_name: "GeeksforGeeks", org_desc: "A Computer Science Portal." });

// Prints:
// Organization Name: GeeksforGeeks,
// Organization Description: A Computer Science Portal.

### 21. What are interfaces in TypeScript?

A interface in TypeScript is used to define a syntax that must be followed by the entity of that interface. An Interface defines the properties, methods and the events and considered as the members of the interface. The interfaces only contain the declarations of the members. The initialisation or the assignment will be done by the class that is deriving the interface. Interfaces are defined using the interface keyword.

Example:

interface interface_name{
    // Define the members like methods properties and events etc.
}

### 22. In what situation you should use a class and a interface?

We can use the classes and interfaces to define our own custom data types. There are different use cases and situations where we can use the interfaces and classes.

An interface can be used in a situation where the shape, structure and the contact will be defined for indicating how a object or class will look like without their implementation. It can also be used to enforce some properties and methods to a class and object.

On the other hand, a class can be used where we need to enclose the data to hide it from outer code and prevent the direct acces of this data. It can be used to implement the Object Oriented Programmin concepts.

### 23. What are the differences between the classes and the interfaces in TypeScript?

A class is defined using the class keyword. The classes can contain the methods, properties and variables. Methods of a class are defined when the class is implemented. A class instance will allow us to access the properties and methods defined inside the class.

Interfaces are defined using the interface keyword. It contains only the declarations of the properties and methods which are implemented by the derived class.

### 24. How you can compile a TypeScript file?

The TypeScript code is not executed directly. It requires to convert the TypeScript code into JavaScript. You can use tsc <file_name> command to execute the TypeScript code and convert it into JavaScript.

tsc script.ts

### 25. How to combine multiple TypeScript files and convert them into single JavaScript file?

There is a command named –outfile that is follwed by the JavaScript filename and the multiple TypeScript files. If the JavaScript file name is not provided then all the TypeScript files are combined in the first TypeScript file specified in the format.

tsc --outfile combined.js script1.ts script2.ts script3.ts

### 26. How to compile a TypeScript file at real time while updating the file?

The command –watch can be used to compile a typescript file which is continuosly updating. This file can be compiled at the real time.

tsc --watch realTime.ts

### 27. Is it possible to call the constructor function of the base class using the child class?

Yes, the base class constructor can be called using the super() method inside the constructor function of the child class with the required parmeters if the base class constructor function takes parameters.

### 28. How to declare a class in TypeScript?

The syntax for declaring the classes in TypeScript is almost same as in JavaScript. In TypeScript, you can also use the typed declarations for the variables and methods of the class.

Example:

 class Cricketer{
    name: string;
    runs: number;

    constructor(name: string, runs: number){
        this.name = name;
        this.runs = runs;
    }

    thisMatchRund(): number{
        this.runs += 139;
        return this.runs;
    }
}

### 29. How to declare a arrow function in TypeScript?

In TypeScript, we can declare the arrow functions in the same format as we declare in vanilla JavaScript. TypeScript allow us to use the typed declaration with by specifying the type of parameters and the type of return value as well.

Example:

const typedArrowFunc = (org_name: string, desc: string): string => {
    let company: string = `Organization: ${org_name}, Description: ${desc}`;
    return company;
}
console.log(typedArrowFunc("GeeksforGeeks", "A Computer Science Portal"));
// Prints: Organization: GeeksforGeeks, Description: A Computer Science Portal

### 30. How to define a function which accepts the optional parameters?

You can define a function with optinal parameters by using a ? symbol in the declaration of the function for the parameter which you want to make the optional as shown below:

Example:

function cricketer(c_name: string, runs?: number): void{
    if(!runs){
        console.log(`Cricketer Name: ${c_name}, Runs Scored: Not Available`);
    }
    else{
        console.log(`Cricketer Name: ${c_name}, Runs Scored: ${runs}`);
    }
}
cricketer("Virat Kohli", 26000);
cricketer("Yuzvender Chahal");
// Prints: 
// Cricketer Name: Virat Kohli, Runs Scored: 26000
// Cricketer Name: Yuzvender Chahal, Runs Scored: Not Available

### 31. How the inheritance can be used in TypeScript?

Inheritance is one of the main four pillars of Object Oriented Programming. It allows a class to inherit or acquire the properties and methods of other class and implement them with the instance created using the inherited class. The inheritance can be implemented using the extends keyword after the child class name followed by the parent class name.

class Child extends Parent{
    // Properties of child class
}

### 32. What are modules in TypeScript?

Modules are used to create a collection of multiple data types that may include the classes, functions, interfaces and variables. The modules have their own scope. The members defined inside modules can not be accessed directly by the other code. Modules are imported using the import statement and defined using the export keyword to export it.

Example:

module multiply{
    export function product(a: number, b: number): number{
        return a*b
    }
}

### 33. In how many ways you can classify Modules?

There are two types of Modules available in TypeScript:

Internal Modules: These modules are used to specify the collection of classes, interfaces, functions and variables that can be exported to other modules as a single unit.
External Modules: These are the separate TypeScript files that include more code and consist of at least one export or import statement in it.

### 34. What is the use of tsconfig.json file in TypeScript?

This file helps to compile the project by providing the compiler options. It also makes the working directory as the root directory of the project.

### 35. What are Decorators in TypeScript?

In TypeScript, decorator is a syntax that can be used to define the function, classes, properties etc. to modify their behaviour and add some metadata to them. These are basically the higher order function that takes target element as argument and returns the modified version of it with the help of some function.

### 36. What are the different ways for controlling the visibility of member data?

TypeScript provide us with the three ways to control the visibility of members like methods and properties in classes.

Private: The private members can be accessed only inside the class. They can not be accessed by the outer code.
Public: It is the default visibilty of the members. These members can be access from any where in the code by defining the class instance.
Protected: These members can only be accessed by the classes that are inherited using the members class. No other code that does not inherit the class can access these members.

### 37. How to debug a TypeScript file?

A TypeScript file can be debugged using the –sourcemap command that is followed by the file name. It will create a new file with the fileName.ts.map name.

tsc --sourcemap script.ts

### 38. How to convert a .ts file into TypeScript Definition file?

You can change a .ts file into the definition file with the help of TypeScript compiler by using the –declaration command followed by the name od the .ts file. The definition file will make the TypeScript file reuseable.

tsc --declaration script.ts

### 39. Is it possible to create the static classes in TypeScript?

No, TypeScript does not supports the static classes. Because, in typescript does not require the static classes as you can simply create any function or data as a object without creating a containing class.

### 40. Describe anonymous functions and their uses in TypeScript?

The anonymous functions are the functions that are declared without a name. These functions are mainly used to pass to another function as a call back function like while attaching an event and calling the setTimeout() method etc.

Example:

myBtn.addEventListener('click', function () {
    // Add click functionality
});

### 41. Explain the union types in TypeScript?

The union types in TypeScript represents that the value of a variable can be one of the specified types. The union type uses a straight vertical bar(|) to show the options for the variable types.

Example:

let unionVar: number | boolean = true;
console.log(unionVar); // true

unionVar = 56;
console.log(unionVar); // 56

### 42. Explain type alias in TypeScript?

A type alias in TypeScript is used to give a new and the meaning fule name for a combined or new type. The type alias will not create a new type instead it create new names for the type it refers to.

type combinedType = number | boolean

### 43. Is it possible to create the immutable Object properties in TypeScript?

Yes, you can use the readonly property before the properties names while defining the objects. It makes the properties of object to be initialized at the time of declaring the object. If you try to update the value of any immutable property it will not allow you to do it as it is a readonly property.

### 44. What is “in” operator and why it is used in TypeScript?

The in opertaor is used to check whether a property is present in the testing object or not. It will return true, if it finds the property in the object. Otherwise, it will return false.

### 45. Expalin conditional typing in TypeScript?

In TypeScript, we can use the ternary operator(condition? true:false) to assign the dynamic types to an property. It will assign a type dynamically based on the condition defined in the ternary operator.

### 46. Explain noImplicitAny in TypeScript.

The noImplicitAny is a compiler option that we can add to the tsconfig.json file and make the TypeScript compiler to throw an error if a function or method for a particular type is invoked on a parameter of any type. Generally, TypeScript expect a explicit type to be associated with the parameters, but somethimes we don’t need to specify the explicit type. In that case, TypeScript assigns a explicit type as any type to that parameter and allows to perform operations. But we can force the compiler to throw an error if a explicit type is not defined for a parameter.

### 47. Explain type inference in TypeScript.

The type inference refers to the automatically assigning the explicit types to the variable which does not declared using the expicit type. Generally, it is done at the time when the variables are declared and initialized at the same time with a value of some data type.

### 48. Which principles of Object Oriented Programming are supported by TypeScript?
TypeScript supports all the four principles of Object Oriented Programming as:

Abstraction
Encapsulation
Inheritance
Polymorphism

### 49. In how many ways you can use the for loop in TypeScript?
There are mainly three ways in which you can use the for loop in TypeScript as listed below:

Using the simple for loop: It is the simple for loop used to iterate through any number of variables by defining and using a variable.
for(let i=0; i<n; i++){ // code statement}
Using the for-of loop: It can be used to iterate through the array elements without defining the iterator variable.
for(let item of myArr){ // code statement}
Using the forEach() method: It is a method that takes a callback function and operate the functionality to each item of the array.
myArr.forEach(() => { // code statement})

### 50. Explain Mixins in TypeScript

The mixins are used to create the classes from the reuseable components. They can be built using the different partial classes. In simple language, we can say that instead of a class extends another class, a function can take a class and then return the class as a result. The function that takes the class and returns a class is known as mixin.

https://www.geeksforgeeks.org/typescript-interview-questions/





Beginner Level TypeScript Interview Questions


### 1. What is TypeScript?
WhatisTypescript

TypeScript is a superset of JavaScript. It is an object-oriented and tightly typed programming language. TypeScript code is transformed to JavaScript, which may be used in any environment that supports JavaScript, including browsers, Node.js, and your own applications.
Anders Hejlsberg of MICROSOFT created TypeScript. TypeScript was created in response to the limitations of JavaScript for constructing large-scale applications within Microsoft and among its external customers. There was a demand for bespoke tooling to make developing JavaScript components easier due to the complexity of working with complicated JavaScript code.
TypeScript is a variant of JavaScript with a few more features. TypeScript extends JavaScript with extra syntax to provide a more robust interface with your editor. TypeScript is a scripting language that is compatible with JavaScript and relies on type inference to deliver advanced functionality without the need for additional code.


### 2. Explain Arrays in TypeScript
A collection of values of the same data type is called an array. It's a kind that's been defined by the user. To store values of the same kind, you use arrays. Arrays are collections of values that are ordered and indexed. The indexing begins at zero, with the first element having index 0, the second having index 1, and so on.

Syntax: 

var array_name[:datatype];        //declaration 

array_name = [val1,val2,valn..]   //initialization

Example:

let values: number[] = [];

values[0] = 10;

values[1] = 20;

values[2] = 30;

### 3. List the Applications of TypeScript
Both client-side and server-side JavaScript applications can be built with TypeScript.
TypeScript is used to create both client-side and server-side JavaScript applications.
Because TypeScript adds more functionality and provides errors directly in the code, it can be used instead of JavaScript.
TypeScript is a programming language that is used to create large-scale enterprise systems.

### 4. List the Advantages of TypeScript
Problems are highlighted throughout development and at compilation time.
Typescript can be run in any browser or JavaScript engine.
A namespace notion is created by declaring a module.
IntelliSense is a TypeScript feature that provides active hints as you type.
Strongly typed or static typing is supported. The advantage of TypeScript is that it is strictly typed or allows for static typing. Because of static typing, it may confirm type correctness at compilation time.

### 5. List the disadvantages of TypeScript
It takes a long time to compile TypeScript code.
Abstract classes are not supported in TypeScript.
Converting TypeScript to JavaScript requires an additional compilation step.
Its type scheme is extremely complicated.

### 6. Explain the features of Arrays in TypeScript
An array declaration allocates memory blocks in a sequential order.
Arrays are immutable. This means that once an array is created, it cannot be resized.
An array element is represented by each memory block.
The subscript/index of an array element is a unique number that identifies the element.
Arrays, like variables, should be declared before being used. Declare an array with the var keyword.
The term "array initialization" refers to the process of filling an array with elements.
The values of array elements can be updated or modified, but they cannot be erased.

### 7. How to declare a variable in TypeScript?
Let and const are the two methods to declare variables.
Alphabets and numeric digits can both be used in variable names.
Except for the underscore (_) and the dollar ($) sign, they cannot contain spaces or special characters.
A digit can’t be the first character in a variable name.
let var a=10;

 or

function f() {

  var message = "Hello, world!";

  return message;

}

### 8. Name the access modifiers supported in TypeScript.
 The access modifiers supported by TypeScript are:

Protected- All child classes and members have access to them, but the instance does not.
Private- Only members have access
Public- Members, child classes, and instances of the class have access to the public modifier.

### 9. Explain Loops in Typescript
A loop statement allows to repeat the execution of a statement or a series of statements. To handle looping requirements, TypeScript provides a variety of loops.

For Loop
The for loop is a definite loop implementation. A definite loop is defined as a loop with a fixed number of iterations.

While Loop
When the condition supplied evaluates to true, the while loop executes the instructions.

Do..While Loop
The do...while loop is identical to the while loop, except that the condition isn't evaluated the first time the loop runs.

### 10. What is the use of the tsconfig.json file?
TS_Int_Qs_tsconfig.json

The tsconfig.json file is a JSON format file where you may specify several options to inform the compiler how to compile a project. The presence of this file in the directory implies that it is the TypeScript project root.

### 11. How to convert a string to a number in TypeScript?
TS_Int_Qs_stringtono..

You can convert a string to a number by using parseInt(), parseFloat() and Number(‘’) Method.

### 12. What is meant by contextual typing?
When one side of the equation has type but the other does not, the TypeScript compiler determines the form. You can skip typing on the right side because TypeScript will figure it out for you. This reduces the amount of time spent typing code.

### 13. What is JSX?
TS_Int_Qs_JSX.

It's a syntax that's similar to XML and can be embedded. It must be converted into TypeScript that is valid. The JSX file with the.tsx extension is used.

JSX has an XML-like syntax that can be embedded. It is intended to be turned into legitimate JavaScript, though the semantics of that transformation will vary depending on the implementation. TypeScript allows you to embed JSX, type verify it, and compile it to JavaScript immediately.

### 14. Define static typing
Static typing refers to a compiler that has recognisable variables, arguments, and object members at compile time. This aids in the early detection of faults. 

### 15. What are import and export keywords in TypeScript?
Import keyword is used to export declaration. Example: export * from module
Any variable, function, or type alias can be exported with the export keyword

### 16. Can TypeScript be used for the backend?
By combining TypeScript with Node.js, backend applications can benefit from the added security that the language provides.

### 17. How will you check if a variable is null or undefined in TypeScript?
if(value) return true if value is not null, undefined, empty, false, 0 or NaN.

### 18. What are getters/setters?
TS_Int_Qs_Getters%26Setters

Getters and setters prevent access to an object's members.They allow you to have more precise control over how a member interacts with each object. A getter method starts with keyword ‘get’ and setter method starts with keyword ‘set’

### 19. How can a class constant be implemented in TypeScript?
Class properties cannot be declared with the const keyword. The keyword 'const' cannot be used in a class member.

### 20. What is the Declare Keyword in TypeScript?
Since JavaScript lacks a TypeScript declaration, the declare keyword is used to include it in a TypeScript file without causing a compilation issue. Ambient methods and declarations use the term to define a variable that already exists.

### 21. What is an Interface with reference to TypeScript?
The interface specifies the syntax that classes must use. All of the members of an interface are implemented by a class that implements it. It's possible to refer to it, but not to use it. A type-checking interface is used by the TypeScript compiler.

### 22. Describe ‘as’ syntax in TypeScript.
In TypeScript, the 'as' syntax is used for Type assertion. It was created because the original syntax was incompatible with JSX. Only as-style assertions can be used with JSX and TypeScript.

Example:

let stdid: any=007

let stdid= id as number;

### 23. Define Lambda function.
For defining function expressions, TypeScript provides a shortcut syntax. A lambda function is an unnamed anonymous function. 

Example:

let sum=(a: num, b: num): num=>{ return a+b;}

console.log(sum(5,10)); //returns 15

Here, ?=>? is a lambda operator.

### 24. How to create objects in Typescript?
Objects are collections of keys and values that resemble a dictionary. The keys must be one-of-a-kind. They resemble arrays and are sometimes referred to as associative arrays. An array, on the other hand, employs numbers to index the values, whereas an object lets you use any type as the key.

An Object type in TypeScript refers to any value with properties. It can be defined simply by specifying the properties and the kinds of those properties. As an example,

let pt: { x: number; y: number } = {

  x: 10,

  y: 20

};

### 25. Explain Different Data Types in Typescript?
Data Type

Keyword

Description

Number

Number

Both Integer and Floating-Point numbers are represented by it.

Boolean

Boolean

True and false values are represented.

String

String

It's used to denote a string of characters.

Void

Void

Usually applied to function return types.

Null

Null

It's used when an object isn't worth anything.

Undefined

Undefined

Indicates the value assigned to an uninitialized variable.

Any

Any

Any type of value can be assigned to a variable if it is declared with any data-type.

### 26. What is meant by Type Inference?
When you don't specify an explicit type for a variable, TypeScript can infer it. Type inference is the term for this. This is normally done during the declaration, when the variables or parameters are initialized.

TypeScript recognises that the variable koo is a string, even if you don't mention string as a type.

let koo = "Hello world";

console.log(typeof koo);  // "string"

### 27. Explain Tuples in Typescript With Example
Tuples are a collection of values that are diverse. It allows for the storage of many fields of various sorts. Tuples can also be used as function parameters.

There are instances when it is necessary to save a collection of values of various types. Arrays will not suffice in this situation. TypeScript provides a data type called tuple that aids in this endeavor.

Syntax:

var tuple_name = [value c,value b,value c,…value n]

For Example:

var yourtuple = [12,"Hi"];




Intermediate Level TypeScript Interview Questions
After seeing the beginner level TypeScript Interview questions, look at the Intermediate level TypeScript Interview Questions.

### 28. What is Anonymous Function in TypeScript?
Anonymous functions are those that have no identifier (function name) attached to them. At runtime, these functions are dynamically declared. Anonymous functions, like normal functions, can accept inputs and return outputs. After its initial creation, an anonymous function is normally inaccessible. An anonymous function can be assigned to variables. 

Syntax: 

var res = function( [arguments] ) { ... }

Example:

var msg = function() { 

   return "hello world";  

} 

console.log(msg())

### 29. How to Install Typescript?
TypeScript is a JavaScript programming language for use in applications. TypeScript extends JavaScript with optional types that support tools for large-scale JavaScript applications in any browser, on any host, and on any operating system. TypeScript compiles to legible JavaScript that adheres to industry standards. 

You can install TypeScript globally with npm, which means you can run the tsc command from anywhere in your terminal.

For the latest stable version:

npm install -g typescript

### 30. What are Decorators?
TS_Int_Qs_decorators.

The Decorator is a type of declaration that is used to decorate a class declaration, method, accessor, property, or argument. Decorators take the form @expression, where expression must evaluate to a function that will be called with information about the decorated declaration when it is called at runtime.

Example: 

function color(value: string) {

 // this is the decorator factory, it sets up

 // the returned decorator function

 return function (target) {

   // this is the decorator

   // do something with 'target' and 'value'...

 };

}

### 31. What are Mixins?
Combining simpler partial classes is a popular approach of constructing classes from reusable components. For languages like Scala, you may be familiar with the concept of mixins or characteristics.

To extend a base class, the design relies on generics and class inheritance. The finest mixin support in TypeScript is provided through the class expression pattern.

We have a class where mixins are applied on top of it.

class Sprite {

 name = "";

 x = 0;

 y = 0;

 constructor(name: string) {

   this.name = name;

 }

}

### 32. Explain Classes in TypeScript.
In terms of OOPs, a class is a template for producing objects. Object-oriented programming elements like as classes, interfaces, polymorphism, and data binding are all supported by TypeScript. The term "object" refers to a physical entity. Classes were not supported in JavaScript ES5 or earlier. This is a feature that Typescript inherits from ES6.

A class is a collection of items with similar characteristics. Fields, methods, constructors, Blocks, Nested classes, and interfaces are all included in the class.

Syntax to declare a class:

class class_Name{    

    field;    

    method;    

} 

### 33. What is Namespace and how to declare it?
The namespace is used to group functionalities logically. To enable a single or a group of linked functionalities, a namespace can include interfaces, classes, functions, and variables.

The namespace keyword, followed by the namespace name, can be used to construct a namespace. Curly brackets can be used to define all interfaces, classes, and other objects.

Syntax: 

namespace <name>

{   

}

### 34. What are Rest Parameters in Typescript?
You can use rest parameters when the number of parameters that a function will get is unknown or varies.
The rest parameter can take zero or more parameters. The compiler will generate an array of arguments containing the name of the rest parameter.
let Greet = (greeting: string, ...names: string[]) => {

  return greeting + " " + names.join(", ") + "!";

}

Greet("Hi!", "John", "Sam"); // returns "Hi John, Sam"

Greet("Hi!");// returns "Hi !

### 35. What are Objects in TypeScript?
An object is a type of instance that consists of a collection of key-value pairs. Scalar values, functions, and even arrays of other objects can be used as values.

Syntax:

var object_name = { 

   key1: “value”, //scalar value 

   key2: “value”,  

   key3: function() {

      //functions 

   }, 

   key4:[“contentA”, “contentB”] //collection  

};

### 36. Explain Type Aliases 
Type aliases give a type a new name. Type aliases are similar to interfaces in that they can be used to name primitives, unions, tuples, and any other kinds that you'd have to define by hand otherwise.

Aliasing doesn't truly create a new type; instead, it gives that type a new name. Aliasing a primitive isn't very useful, however it can be used for documentation purposes.

Type aliases, like interfaces, can be general; all you have to do is add type parameters and utilise them on the right side of the alias declaration.

type Container<T> = { value: T }; 

### 37. Explain Modules in TypeScript
A module is created with the intention of organizing TypeScript code. Modules are classified as follows:

Internal Modules: Internal Modules were previously used to logically group classes, interfaces, and functions into a single unit that could then be exported into a different module. In the most recent version of TypeScript, this logical grouping is referred to as namespace.

External Modules: External modules allow you to describe and load dependencies between many external js files in TypeScript.

### 38. What are Mapped Types ?
Taking an existing type and making each of its properties optional is a typical undertaking.

Because this happens frequently enough in JavaScript, TypeScript has a feature called mapped types that allows you to define new types based on existing ones. The new type turns each property in the old type in the same way into a mapped type. You can, for example, make all properties optional or of the readonly type. 

It's important to note that this syntax refers to a type rather than a member. You can use an intersection type to add more members:

Now, take a look at the simple mapped type and its parts:

type Keys = "option1" | "option2";

type Flags = { [K in Keys]: boolean };

The syntax is similar to that of index signatures with a for.. in the middle. There are three sections in total:

The type variable K is assigned to each property one by one.

The literal union of strings The names of the properties to iterate over are stored in keys.

The property's type as a result.

### 39. What are Conditional Types in TypeScript ?
Based on a condition given as a type relationship test, a conditional type chooses one of two alternative types:

T extends U ? X : Y

When T can be assigned to U, the type is X, and when it can't, the type is Y.

Because the condition depends on one or more type variables, a conditional type T extends U? X: Y and is either resolved to X or Y or delayed. Whether to resolve to X or Y, or to defer, when T or U contains type variables is determined by whether the type system has enough information to conclude that T is always assignable to U.

### 40. What are Distributive Conditional Types?
Distributive conditional types are conditional types in which the checked type is a bare type parameter. During instantiation, distributive conditional types are automatically distributed over union types.

For example, an instantiation of T extends U ? X : Y with the type argument A | B | C for T is resolved as (A extends U ? X : Y) | (B extends U ? X : Y) | (C extends U ? X : Y).

### 41. Explain how TypeScript files can be supported from Node Modules
TypeScript includes a series of declaration files to guarantee that TypeScript and JavaScript support works well right out of the box (.d.ts files). The various APIs in the JavaScript language, as well as the standard browser DOM APIs, are represented in these declaration files. While there are some fair defaults based on your target, you can configure the lib setting in the tsconfig.json to specify which declaration files your program uses.

TypeScript has a feature similar to @types/ support that allows you to override a specific built-in lib. TypeScript will check for a scoped @typescript/lib-* package in node modules when selecting which lib files to include. After that, you can use your package manager to install a specific package to take over for a particular library.

### 42. Explain the Components of Typescript

Internally, the TypeScript language is separated into three layers. Each of these layers is further subdivided into components. These layers are as follows:

Language
The TypeScript Compiler 
Language Services for TypeScript
Language: It is written in TypeScript and includes TypeScript language components. It includes syntax, keywords, and type annotations.

TypeScript Compiler (TSC): The TypeScript compiler (TSC) converts TypeScript programmes into JavaScript code. It also converts your TypeScript code to JavaScript code, parsing and type-checking it.

The TypeScript Language Services:  Provides information that allows editors and other tools to deliver greater assistance capabilities like automated refactoring and IntelliSense. It adds a layer of abstraction to the core-compiler pipeline. It allows you to do things like code formatting and outlining, colorization, statement completion, signature help, and so on.

### 43. What are Object-Oriented Principles supported by TypeScript?
TS_Int_Qs_oops

The object-oriented principles supported by TypeScript are Encapsulation, Inheritance, Polymorphism and Abstraction 

Encapsulation is a major component of Object Oriented Programming, and it is a method of structuring code so that each block of code has its own set of access points for external code.

TypeScript makes creating an object model and inheritance chain a breeze. To construct classes, simply use the standard class keyword. The extended keyword causes the stated base class to be inherited by the child class.

Polymorphism occurs when many classes inherit from the same parent and override the same functionality. Each of those kid classes is now responsible for implementing a property or method, but they may do so in their own unique way.

Abstraction is a method of modelling objects in a system that separates the responsibilities of the class or type from the code that inherits it.

### 44. Explain the Drawbacks of using Declaration Files with Typescript
There are two drawbacks to using these declaration files with TypeScript:

Since you upgrade TypeScript, you must also deal with changes to TypeScript's built-in declaration files, which can be difficult when the DOM APIs change so regularly.

Customizing these files to meet your needs and the demands of your project's dependencies is difficult (e.g. if your dependencies declare that they use the DOM APIs, you might also be forced into using the DOM APIs).

Advanced Level TypeScript Interview Questions
So those were all Intermediate level TypeScript Interview Questions, now look at the Advanced level TypeScript Interview Questions

### 45. How to compile Typescript with Visual Studio Code?
Visual Studio Code includes TypeScript language support but does not include the TypeScript compiler.
You need to install the TypeScript compiler either globally or in your workspace to transpile TypeScript source code to JavaScript
The easiest way to install TypeScript is through npm, the Node.js Package Manager.       If you have npm installed, you can install TypeScript globally (-g) on your computer by:
npm install -g typescript

You can test your install by checking the version or help.
tsc --version

### 46.  What are the Recent Advancements in TypeScript?
TypeScript 4.2 has been released, and it includes more flexible type annotations, tougher checks, additional configuration choices, and a few breaking changes.
Rest arguments can now be placed anywhere in a triple type. In type error messages, type aliases are no longer enlarged, resulting in a better developer experience.
TypeScript 4.2 brings the language one step closer to its aim of accurately typing JavaScript at any size, anywhere JavaScript is used.

### 47. Explain the Awaited Type and Promise Improvements
The Awaited type is a new utility type introduced in TypeScript 4.5. This type is intended to represent activities such as await in async functions and the.then() method on Promises - notably, the way they recursively unwrap Promises.

// A = string

type A = Awaited<Promise<string>>;

// B = number

type B = Awaited<Promise<Promise<number>>>;

// C = boolean | number

type C = Awaited<boolean | Promise<number>>;

Existing APIs, such as JavaScript built-ins like Promise.all, Promise.race, and others, can benefit from the Awaited type. In fact, some of Promise.all's inference concerns provided a foundation for Awaited.

Promise.all combines certain traits with Awaited to produce far superior inference results.

### 48. Explain how TypeScript files can be supported from Node Modules
TypeScript includes a series of declaration files to guarantee that TypeScript and JavaScript support works well right out of the box (.d.ts files). The various APIs in the JavaScript language, as well as the standard browser DOM APIs, are represented in these declaration files. While there are some fair defaults based on your target, you can configure the lib setting in the tsconfig.json to specify which declaration files your program uses.

TypeScript has a feature similar to @types/ support that allows you to override a specific built-in lib. TypeScript will check for a scoped @typescript/lib-* package in node modules when selecting which lib files to include. After that, you can use your package manager to install a specific package to take over for a particular library.

### 49. What is Type Assertion? Explain its types 
You can find yourself in a scenario where you know a type for an entity that is more specific than its present type.

A type assertion is similar to a type cast in other languages, but it does not do any additional data verification or restructuring. It has no effect on runtime and is only used by the compiler. TypeScript expects that you, the programmer, have completed any necessary specific checks.

There are two types of type assertions.

One is the as-syntax:

let someValue: unknown = "this is a string";

let strLength: number = (someValue as string).length;

The other version is the “angle-bracket” syntax:

let someValue: unknown = "this is a string";

let strLength: number = (<string>someValue).length;

Both samples are identical. selecting one over the other is basically a matter of preference; however, only as-style assertions are allowed when combining TypeScript with JSX. 

### 50. What is Recursive Type Aliases?
The ability to "recursively" reference type aliases has always been limited. The reason for this is because each type alias must be capable of substituting itself for whatever it aliases. Because this isn't always possible, the compiler rejects some recursive aliases.

Interfaces can be recursive, but their expressiveness is limited, and type aliases cannot. That involves combining the two: creating a type alias and extracting the type's recursive portions into interfaces. It's effective.

type ValueOrArray<T> = T | ArrayOfValueOrArray<T>;

interface ArrayOfValueOrArray<T> extends Array<ValueOrArray<T>> {}

https://www.simplilearn.com/tutorials/typescript-tutorial/typescript-interview-questions



https://www.turing.com/interview-questions/typescript

https://medium.com/@microclip.lakeesha/basics-of-typescript-a-practical-guide-78addaacc5a
