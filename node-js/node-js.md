# 📝 Node.js / JavaScript Interview Notes (Q1–Q10)

## 1. Difference between var, let, const

var → Can be redeclared, can be updated, function scoped, hoisted (value undefined)  
let → Cannot be redeclared, can be updated, block scoped, hoisted but not usable before declaration (TDZ)  
const → Cannot be redeclared, cannot be updated, block scoped, must assign value immediately

## 2. Temporal Dead Zone (TDZ)

TDZ is the time between variable creation and declaration where you cannot use the variable. Happens for let and const. Example: console.log(a); // ❌ Error, let a = 10;

## 3. Difference between Spread and Rest Operator

Spread (...) → expands values, used to copy/merge arrays/objects, e.g., let b = [...a]; Rest (...) → collects values, used in functions/destructuring, e.g., function sum(...nums) {}

## 4. Difference between Arrow and Normal Function

Arrow → short syntax, this is fixed (lexical), no arguments object, cannot be constructor, not hoisted. Normal → longer syntax, this depends on call, has arguments object, can be constructor, hoisted.

## 5. Difference between Shallow Copy and Deep Copy

Shallow copy → copies only top-level, nested objects still share reference. Deep copy → copies everything, nested objects independent, e.g., let b = {...a}; // shallow copy, let b = JSON.parse(JSON.stringify(a)); // deep copy

## 6. Promise in JavaScript & Why We Use It

Promise = object representing future value, handles async operations. States: pending, fulfilled, rejected. Why → avoid callback hell, clean async flow, easy error handling. Example: let p = new Promise((resolve, reject) => { resolve("Done"); }); p.then(msg => console.log(msg));

## 7. Closure

Closure = inner function remembers outer function variables even after outer function finishes. Example: function outer() { let count = 0; function inner() { console.log(count); } return inner; } const x = outer(); x(); // remembers count = 0

## 8. Which is better for API calls: Promise or async/await

Both work, but async/await is preferred → cleaner, easier to read, looks like normal code, error handling with try/catch. Example: async function getData() { try { const res = await fetch(url); const data = await res.json(); console.log(data); } catch(err) { console.log(err); } }

## 9. Generator in JavaScript

Generator = special function that can pause (yield) and resume (next). Example: function\* gen() { yield 1; yield 2; yield 3; } const g = gen(); console.log(g.next()); // {value:1, done:false} console.log(g.next()); // {value:2, done:false}

## 10. Difference between call, apply, and bind

call() → calls function immediately, arguments individually. apply() → calls function immediately, arguments as array. bind() → returns new function, call later, this fixed. Example: fn.call(obj, a, b); fn.apply(obj, [a, b]); const x = fn.bind(obj); x();
