# You dont know JS Notes
Database MongoDB and CouchDB use javascript. Node.js is server side programming

64 bits in javascript
- When there are multiple operators with same precedence they are applied left to right
    X / % all same
- Infinity , -Infinity, NaN (Not a number)
- NaN == NaN is false

- Back tick can be used to embed values `${var1/2} is variable 1 divided by 2`
- typeof(x) gives the type of operator
- Precedence of logical operators is || < && < comparison
- Ternary operator (True)? case1 : case 2
    Runs case1 if true else case 2
- null and undefined are the value types. null == undefined gives true
- for precise comparison use === and !==
- || operator returns left when true otherwise right, && operator returns left if false
    This is called short circuit evaluation
- "use strict" should be written at global or function level to use strict mode

VARIABLES or BINDINGS
- can be declared using let, cost or var
- When variable does not hold any value it is undefined
- You cannot reassign to const values, it throws an error

Environment:- Collection of bindings that exist, some already exist like input.
- Number(), String(), Boolean() converts the value inside parenthesis to the required value

Inside a block the same variable is resolved, not global variable

- let has block scope and var has function scope

Conditional expressions
- All conditional expressions like if-else; for; do-while; while; switch-case exist
- "", null, undefined, 0,-0, Nan are false values in javascript
- === is strict equality that does not allow coercion
- == and != compares for the reference a value holds
- In comparison if both values are strings they are lexicographically compared
    if one of them is a number the both are converted to number
- When string is coerced to number it is NaN, and NaN is neither greater than nor less than any other value


## SCOPING
- Inside a block the same variable name is resolved to innermost variable, not global one
- All local scopes can see local scopes containing them and global scopes


## ARRAYS
- elements are stored as properties with index as the name of property
- values can be accessed using 
    - array.x
    - array[0]
    - array["0"]
- Array can store different types of data
- Array.length gives length of array
- push and pop at end
- unshift and shift at front
- Array loops like for each in java. (There also exists a forEach in javascript)
- Array.join(". ") returns string after joining an array of strings
- the values of an array can be passed using ...array to a rest parameter
- When passing an array we can access using variable name instead of index using
    [a,b,c,d]
- Array.forEach(l=>{console.log(l)}) is used to access each value and perform some function with it
- Array.map(x=> x*2)
    returns an array which maps the original array to twice its values
- Array.filter(condition) filters the array to a new array with taken if the condition is true
- Array.reduce(function) moves left to right through the array and then applies the function
    reduces the function array values to a particular value
- Array.some(function) :- returns true if any one of the array value returns true for function given
- Array.every(function) :- true if all function(value) are true
- for..of can be used to iterate directly over an array

### READ COMMON TO STRINGS AND ARRAYS AFTER STRING

```javascript
let entry = ["eat", "drink", "shit"];
for(let val of entry) {
    val;   //val will have the values of entry
}
entry.includes("eat")   // returns true because entry includes eat
entry.slice(1,2);  // outputs only "drink"
entry[1].includes("r"); // is true

var arr = [
    "hello world",
    42,
    true
]
//can be accessed using arr[0], arr[1], arr[2] and different type of variable will be accessed
```

## STRINGS
- Strings can be represented using ' ', " ", ` `
- String concatenation can be done using + operator
- "Z" is less than "a"
- String() converts to string
- .length gives length of the string
- String.toUpperCase() and toLowerCase() gives upper case and lowercase characters
- String.trim() removes the whitespaces at the start and end of the string
- String.padStart(3,"0") where 3 is the length to be padded by and "0" is the string to be added
- String.split(" ") returns an array of string splitted with " "
- Array.join(". ") joins an array of string
- String.repeat(3) returns a string repeated three times

### READ COMMON TO STRINGS AND ARRAYS AFTER STRING

```javascript
let strArray = ["Hey","How","are","you"];
strArray.join(" "); // is a string after joining the strings in str1
strArray[1].repeat(3);
```

### COMMON TO STRINGS AND ARRAYS
- .includes function is used to find if a array contains value
- .indexOf(value) finds the first index of a value. "ee" will give index of the substring as well
- .lastIndexOf(value) finds the last index
- .slice(start,end) gives the array from start to end-1 (inclusive and exclusive)
- arr1.concat(arr2) concatenates arr2 to array 1


## FUNCTIONS
- Bindings that store a function can be reassigned
- Function without return is undefined
- Function arguments can have default values using '=' operator
- A funcion can return a function
- Function = code + the environment in which it is created
- Functions have a side effect and return value
- Rest parameters are like VarArg in java
    ...numbers will take numbers in an array format
    an array can be passed using ...arrayOfNumbers
- When passing an array the variables can be accessed using names instead of index using

    [a,b,c,d]
- Higher order functions
    functions that take other functions as arguments
    functions that change other functions can be created
- Immediately invoked function expressions
```javascript
    (function IIFE(global){
        console.log("hello");
    })(window);
```
```javascript
// First method
const square = function(x){
    return x*x;
};
// Second method
function square1(x){
    return x*x;
}
// Third method, takes parameter x and returns x squared
const square3 = (x) => {
    return x*x;
};
//Short hand method of arrow function
const square4 = x => x*x;
```
### IMPORTANT FUNCTIONS

Math

    .PI .cos .sin .random .sine .min
    
    .floor .ceil .round 
    
    .abs





## OBJECTS
- string, number, boolean, undefined, null aren not objects
- values can be accessed using dot, example: day1.squirrel
- property without a valid binding name can be accessed using a bracket: ["touched tree"]
- "=" operatore creates new or replaces
- delete operator deletes a value
- "var" in object returns true or false if the object contains var
- Object.keys(object-name) returns the keys in object as an array of strings.
- Object.assign(ob1,ob2)    this assigns ob1 to ob2
- If a property name in brace is not followed by a value its value is taken as the binding of the same name
- an object value can be accesed using { }
let {d} = obj;
- JSON(Javascript object notation) is a method to serialize data and send it over network or for storing in a file

    - JSON.stringify(object) returns a string of the data

    - JSON.parse(string) returns an object from the string value of JSON
- Arrays and functions are a specialized versions of object type
- The this keyword points to the objects based on how they are called

- There are built in object sub-types String, Number, Boolean, Object, Function, Array, Date, RegExp, Error
- constructor form or literal form can be used in these subtypes
- If we want to add a property to an array and we specify its name as a number it will be seen as index
    
        array["3"] = "baz"; array[3] will be "baz"

DUPLICATING OBJECTS

- A shallow copy copies the primitives and creates a reference copy of the other properties
- var newObject = Object.assign({}, myObject); copies the myObject to {} and returns the target to newObject

Object property descriptor can be found using 

    
```javascript
Object.getOwnPropertyDescriptor( myObject, "a") // this will give the property description of "a"

Object.defineProperty(myObject, "a", {
    value: 2,
    writeable: true,
    configurable: true,     //cannot modify descriptor. If false only writeable can be converted from true to false(not false to true)
    enumerable: true        //prevent from using in for... in, or Object.keys(..)
});     //This can edit the properties of the object
```
IMMUTABLE

- properties or objects can be made immutable
- The array/ object/ funciton that it refers to is not immutable (can be edited)

1. writeable: false, configurable: false
1. prevent addition of properties, but allow existing to be changed
    Object.preventExtensions(myObject)
1. Object.seal(..) : calles preventExtensions(..) and also makes all properties as configurable:false
1. Object.freeze(..) : Object.seal(..) and also writeable:false
    deep freeze is calling freeze(..) also recursively on the object it references

[[GET]] and [[PUT]]
If an object does not contain a property, undefined is returned

get() and set()
- When we set a property to have a get() or set() its definition becomes an accessor descriptor(data descriptor)
- Even reassigning a property will not reassign, only the get() value will be returned
- When setting a property use alias variable this._a_ ; refer to this variable to get the values

Check if an object has property
- "a" in obj will return true or false, it also checks prototype
- obj.hasOwnProperty("a") only checks the object, not the prototype
- When an obect does not link to the object prototype
    Object.prototype.hasOwnProperty.call(myObject,"a");

- Object.keys(..) returns an array of enumerable properties
- Object.getOwnPropertyNames(..) returns an array of all properties, enumerable or not
    Above two only return the direct properties of the object
- myObject.propertyIsEnumerable("a") checks whether the given property name exists(directly) and if its enumerable

NOTE: for..in is not ordered and may vary based on the javascript engine

ITERATOR OF ARRAY
```javascript
var it = myArray[Symbol.iterator](); 
    @@iterator property of myArray object is a function that returns the iterator object
it.next() // {value:1, done: false}
it.next() // {value:2, done: false}
it.next() // {value:3, done: false}
it.next() // {done:true}

let day1 = {
    squirrel : false,
    events: ["work", "sleep", "eat"]
};
day1.time = 24;     // creates a new property called time
delete day1.squirrel;
"squirrel" in day1;   // is a true value as it checks if day1 has squirrel

Object.keys(day1);  // returns the keys in the object as an array

var day2;
Object.assign(day1,day2);
let day3 = day1;
day2==day1 // returns false
day3==day1 // returns true

let journal = [];       // the properties of variable journal are taken with values of parameters
function addEntry(events, squirrel)
{
    journal.push({events, squirrel});
}

let {events} = day1; // now events binding stores the value that events in day1 holds
    // good way to access a variable in an object directly

// this keyword
function foo(){
    console.log(this.bar);
}

var bar = "global";
var obj1 = {
    bar:"obj1",
    foo:foo
};
var obj2 = {
    bar: "obj2"
};
// foo();      //prints undefined
// obj1.foo();  // prints "obj1"
// foo.call(obj2);  //prints "obj2"

// use of spread operator
const obb1 = {
    a:false,
    b:false,
    d:false,
}
const obb2 = {
    b:true,
    c:true,
    d:true
}
const obb3 = {...obb2,...obb1}; //obb1 overrites the obb2 properties in the left
// console.log(obb3);
```
## THE SECRET LIFE OF OBJECTS

Encapsulation

        hiding precise implementation through interfaces. 
        The program pieces are modelled using objects
        There are methods and properties that are a part of the interface, these are public
        Some are private and outside code cannot access it
Prototypes

        prototypes are like behaviour delegation where we link objects to delegate properties from one part to other
        In addition to properties object has a prototype, it is another object tht is fallback source of properties
        Object.prototype is entity behind most objects
        Object.getPrototypeOf({}) gives the prototype of the object
        Object.prototype has a toString() method that gives string representation of an object

        Functions derive from Function.prototype and Arrays from Array.prototype
Constructor function

        To make sure an object derives from the right prototype and also has the properties it needs
        



```javascript
function speak(line)
{
    console.log(`The ${this.type} rabbit says '${line}'`);
}
let whiteRabbit = {type:"White", speak};
// whiteRabbit.speak("I am white");  
// speak.call(whiteRabbit,"I am white");

Object.getPrototypeOf({}) == Object.prototype;  // returns true value

let protoRabbit = {
    speak(line){            //shorthand way of defining a function in the prototype
        console.log(`The ${this.type} rabbit says ${line}`);
    }
};
let killerRabbit = Object.create(protoRabbit);  //creates a killerRabbit with protoRabbit prototype
```
## SCOPE
- ReferenceError is a scope-resolution failure related while TypeError is when an illegal/ impossible
    action is performed. In TypeError scope resolution was successful
- The same identifier can be specified at multiple levels of nested scope, this is called shadowing
- In non strict mode if an identifier is not found until global scope, a new variable will be created
    in the global scope
- global variables can be accessed using window.varName
- Once object is found as "foo" the properties foo.bar.baz is accessed using property access rules
- eval(str) can be used to cheat lexical scoping to make it appear as if the str had been written at
    the time of authoring the code. It is used to execute dynamically generated code
- With is a method of property access without writing obj.a, obj.b etc 
- with turns an object and its properties to a scope with identifiers
- Function scope encourages the idea that all variables belong to the function, and can be used and 
    reused throughout the entirety of the function
- Principle of least privilege (only show whats minimally necessary)
- Function expression does not pollute the global scope with variable name, it becomes accessible only
    within the braces
- try catch statements with catch(err): err is only accessible in the catch block
- variables defined with let are not hoisted to the top of block, they dont observably exist until the declaration
- const are like let (block scoped) and their value remains constant

```javascript
var obj = {
    a:1,
    b:2,
    c:3
}
with(obj) {
    a = 3;
    b = 4;
    c = 5;
}
//Function expression
(function foo(){
    var a = 3;
    // console.log(a);      //outputs 3
})();

// let has block scoping
var foo = 2;
if (foo) {
	let bar = foo * 2;
	// console.log( bar1 );
}
```

HOISTING
- The declarations are done first during compilation
- The assignment is done "in place" during execution
- Functions are hoisted first, and then variables. Also function entirely gets hoisted.
- Subsequent function declarations override previous ones


CLOSURES
- closure is when a function is able to remember and access its lexical scope even when the 
    function is outside its lexical scope
- let has a block scope and can be used in for loops that creates a separate copy each time the loop is executed
 
MODULE PATTERN
1. there must be an enclosing function that must be called once (each time creates a new module instance)
1. the enclosing function must return back at least one inner function
    We can modify the publicAPI functions using other functions

```javascript
function fn1(){
    var a = 2;
    function bar(){
        console.log(a);
    }
    return bar;
}
var baz = fn1();
// baz();      //the inner scope of fn1() is still in use and does not go away

let array1 = [];
for (let i=1;i<=5;i++)
{
    setTimeout(function timer(){
        array1.push(i);
    },i*1000);
}
// setTimeout(function print(){console.log(array1)},6000); // prints [1,2,3,4,5,6]

//Module pattern example

function CoolModule() {
	var something = "cool";
	var another = [1, 2, 3];
	function doSomething() {
		console.log( something );
	}
	function doAnother() {
		console.log( another.join( " ! " ) );
	}
	return {
		doSomething: doSomething,
		doAnother: doAnother
	};
}

var foo = CoolModule();

// foo.doSomething(); // cool
// foo.doAnother(); // 1 ! 2 ! 3

var MyModules = (function Manager() {
	var modules = {};

	function define(name, deps, impl) {
		for (var i=0; i<deps.length; i++) {
			deps[i] = modules[deps[i]];
		}
		modules[name] = impl.apply( impl, deps );
	}

	function get(name) {
		return modules[name];
	}

	return {
		define: define,
		get: get
	};
})();
```
## "this" and object prototypes
- "this" allows a function to be reused in multiple contexts
- this is not an author time binding, it is runtime binding. It is contextual based on condition of invoking
- the "execution context" stores details about where and how a function was called, and what parameters were passed
- this is neither a reference to the function, nor to the functions lexical scope
- this binding does not have anything to do with where it is declared, but on how it is called

RULES

- DEFAULT BINDING

        (default rule when no other rules apply): standalone function invocation will refer to the default binding
        In strict mode the global object is not eligible for default binding. strict mode state of call site is irrelevant
- IMPLICIT BINDING

        does the call site have a context object (owning or containing object)
        only the top/last level of object property reference chain matters to the call-site
        Implicitly can be lost when the variable simply points to the function and is not called in the objects context
- EXPLICIT BINDING

        can be implemented using the function.call(object) function. 
        This call() funciton is available from the prototype of the functions
        hard binding can be achieved using 
            var bar = bind(func,obj)
- new BINDING
        
        New binding > Explicit binding > Implicit binding > default binding
        Note: new and .call, .apply cannot be used together
            when we use var baz = new bar(3), the value 3 will be applied to baz's property, not hard bound bar's object

        If we pass null or undefined to the call/ bind function the default binding will be taken into consideration



```javascript
//Last level of object property reference matters
function foo1()
{
    console.log(this.a);
}
var obj2 = {
    a: 42,
    foo1:foo1
}
var obj1 = {
    a: 2,
    obj2 :obj2
}
// obj1.obj2.foo1();    // output is 42

// Hard binding using a separate function that uses call (further calling will not change the context)
function foo2() {
	console.log( this.a );
}
var obj3 = {
	a: 2
};

var bar = function() {
	foo2.call( obj3 );
};

bar(); // 2
setTimeout( bar, 100 ); // 2

// `bar` hard binds `foo`'s `this` to `obj`
// so that it cannot be overriden

// bar.call( window ); // 2
```