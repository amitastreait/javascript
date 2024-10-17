# JavaScript Array Methods with Emojis 🚀

This document provides a comprehensive list of JavaScript array methods, along with explanations and emoji-based examples for each.

## Table of Contents
1. [push()](#push)
2. [pop()](#pop)
3. [unshift()](#unshift)
4. [shift()](#shift)
5. [concat()](#concat)
6. [slice()](#slice)
7. [splice()](#splice)
8. [forEach()](#foreach)
9. [map()](#map)
10. [filter()](#filter)
11. [reduce()](#reduce)
12. [find()](#find)
13. [findIndex()](#findindex)
14. [includes()](#includes)
15. [some()](#some)
16. [every()](#every)
17. [sort()](#sort)
18. [reverse()](#reverse)
19. [join()](#join)
20. [indexOf()](#indexof)
21. [lastIndexOf()](#lastindexof)
22. [fill()](#fill)
23. [flat()](#flat)
24. [flatMap()](#flatmap)

## Methods

### push()
Adds one or more elements to the end of an array and returns the new length of the array.

```javascript
let fruits = ['🍎', '🍌'];
let newLength = fruits.push('🍊');
console.log(fruits); // ['🍎', '🍌', '🍊']
console.log(newLength); // 3
```

### pop()
Removes the last element from an array and returns that element.

```javascript
let fruits = ['🍎', '🍌', '🍊'];
let lastFruit = fruits.pop();
console.log(lastFruit); // '🍊'
console.log(fruits); // ['🍎', '🍌']
```

### unshift()
Adds one or more elements to the beginning of an array and returns the new length of the array.

```javascript
let fruits = ['🍌', '🍊'];
let newLength = fruits.unshift('🍎');
console.log(fruits); // ['🍎', '🍌', '🍊']
console.log(newLength); // 3
```

### shift()
Removes the first element from an array and returns that element.

```javascript
let fruits = ['🍎', '🍌', '🍊'];
let firstFruit = fruits.shift();
console.log(firstFruit); // '🍎'
console.log(fruits); // ['🍌', '🍊']
```

### concat()
Merges two or more arrays and returns a new array.

```javascript
let fruits = ['🍎', '🍌'];
let moreFruits = ['🍊', '🍇'];
let allFruits = fruits.concat(moreFruits);
console.log(allFruits); // ['🍎', '🍌', '🍊', '🍇']
```

### slice()
Returns a shallow copy of a portion of an array into a new array object.

```javascript
let fruits = ['🍎', '🍌', '🍊', '🍇'];
let citrus = fruits.slice(2, 4);
console.log(citrus); // ['🍊', '🍇']
```

### splice()
Changes the contents of an array by removing or replacing existing elements and/or adding new elements in place.

```javascript
let fruits = ['🍎', '🍌', '🍊'];
let removed = fruits.splice(1, 1, '🥝', '🍇');
console.log(fruits); // ['🍎', '🥝', '🍇', '🍊']
console.log(removed); // ['🍌']
```

### forEach()
Executes a provided function once for each array element.

```javascript
let fruits = ['🍎', '🍌', '🍊'];
fruits.forEach((fruit, index) => {
  console.log(`\${index}: \${fruit}`);
});
// Output:
// 0: 🍎
// 1: 🍌
// 2: 🍊
```

### map()
Creates a new array with the results of calling a provided function on every element in the array.

```javascript
let numbers = [1, 2, 3, 4];
let emojis = numbers.map(num => '🍕'.repeat(num));
console.log(emojis); // ['🍕', '🍕🍕', '🍕🍕🍕', '🍕🍕🍕🍕']
```

### filter()
Creates a new array with all elements that pass the test implemented by the provided function.

```javascript
let animals = ['🐶', '🐱', '🐭', '🐰', '🐶', '🐱'];
let dogs = animals.filter(animal => animal === '🐶');
console.log(dogs); // ['🐶', '🐶']
```

### reduce()
Executes a reducer function on each element of the array, resulting in a single output value.

```javascript
let votes = ['👍', '👎', '👍', '👍', '👎', '👍'];
let tally = votes.reduce((acc, vote) => {
  acc[vote] = (acc[vote] || 0) + 1;
  return acc;
}, {});
console.log(tally); // { '👍': 4, '👎': 2 }
```

### find()
Returns the value of the first element in the array that satisfies the provided testing function.

```javascript
let animals = ['🐶', '🐱', '🐭', '🐰', '🦊'];
let firstSmallAnimal = animals.find(animal => ['🐭', '🐰'].includes(animal));
console.log(firstSmallAnimal); // '🐭'
```

### findIndex()
Returns the index of the first element in the array that satisfies the provided testing function.

```javascript
let fruits = ['🍎', '🍌', '🍊', '🍇'];
let index = fruits.findIndex(fruit => fruit === '🍊');
console.log(index); // 2
```

### includes()
Determines whether an array includes a certain value among its entries, returning true or false as appropriate.

```javascript
let fruits = ['🍎', '🍌', '🍊'];
console.log(fruits.includes('🍌')); // true
console.log(fruits.includes('🍇')); // false
```

### some()
Tests whether at least one element in the array passes the test implemented by the provided function.

```javascript
let fruits = ['🍎', '🍌', '🍊', '🍇', '🍉'];
let hasberry = fruits.some(fruit => fruit === '🍓');
console.log(hasberry); // false
```

### every()
Tests whether all elements in the array pass the test implemented by the provided function.

```javascript
let numbers = [2, 4, 6, 8];
let allEven = numbers.every(num => num % 2 === 0);
console.log(allEven); // true
```

### sort()
Sorts the elements of an array in place and returns the sorted array.

```javascript
let fruits = ['🍌', '🍎', '🍊', '🍇'];
fruits.sort();
console.log(fruits); // ['🍇', '🍈', '🍊', '🍌']

// For numbers, provide a compare function
let numbers = [4, 2, 5, 1, 3];
numbers.sort((a, b) => a - b);
console.log(numbers); // [1, 2, 3, 4, 5]
```

### reverse()
Reverses the order of the elements in an array in place and returns the reversed array.

```javascript
let fruits = ['🍎', '🍌', '🍊', '🍇', '🍉'];
fruits.reverse();
console.log(fruits); // ['🍉', '🍇', '🍊', '🍌', '🍎']
```

### join()
Joins all elements of an array into a string.

```javascript
let fruits = ['🍎', '🍌', '🍊'];
let fruitString = fruits.join(' and ');
console.log(fruitString); // "🍎 and 🍌 and 🍊"
```

### indexOf()
Returns the first index at which a given element can be found in the array, or -1 if it is not present.

```javascript
let fruits = ['🍎', '🍌', '🍊', '🍌'];
console.log(fruits.indexOf('🍌')); // 1
console.log(fruits.indexOf('🍇')); // -1
```

### lastIndexOf()
Returns the last index at which a given element can be found in the array, or -1 if it is not present.

```javascript
let fruits = ['🍎', '🍌', '🍊', '🍌'];
console.log(fruits.lastIndexOf('🍌')); // 3
```

### fill()
Fills all the elements of an array from a start index to an end index with a static value.

```javascript
let fruits = ['🍎', '🍌', '🍊', '🍇', '🍉'];
fruits.fill('🍓', 2, 4);
console.log(fruits); // ['🍎', '🍌', '🍓', '🍓', '🍉']
```

### flat()
Creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.

```javascript
let nestedEmojis = ['😀', ['😂', '🤣', ['😊', '😇']]];
let flatEmojis = nestedEmojis.flat(2);
console.log(flatEmojis); // ['😀', '😂', '🤣', '😊', '😇']
```

### flatMap()
First maps each element using a mapping function, then flattens the result into a new array.

```javascript
let greetings = ['Hello', 'Hi'];
let result = greetings.flatMap(greeting => [greeting, greeting + ' 👋']);
console.log(result); // ['Hello', 'Hello 👋', 'Hi', 'Hi 👋']
```

This document covers the most commonly used array methods in JavaScript. Each method is explained with a brief description and an emoji-based example to demonstrate its usage.
