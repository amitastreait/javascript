# JavaScript Object Methods with Emojis 🚀

This document provides a comprehensive list of JavaScript object methods, along with detailed explanations and emoji-based examples for each.

## Table of Contents
1. [Object.assign()](#objectassign)
2. [Object.create()](#objectcreate)
3. [Object.defineProperty()](#objectdefineproperty)
4. [Object.defineProperties()](#objectdefineproperties)
5. [Object.entries()](#objectentries)
6. [Object.freeze()](#objectfreeze)
7. [Object.fromEntries()](#objectfromentries)
8. [Object.getOwnPropertyDescriptor()](#objectgetownpropertydescriptor)
9. [Object.getOwnPropertyDescriptors()](#objectgetownpropertydescriptors)
10. [Object.getOwnPropertyNames()](#objectgetownpropertynames)
11. [Object.getOwnPropertySymbols()](#objectgetownpropertysymbols)
12. [Object.getPrototypeOf()](#objectgetprototypeof)
13. [Object.is()](#objectis)
14. [Object.isExtensible()](#objectisextensible)
15. [Object.isFrozen()](#objectisfrozen)
16. [Object.isSealed()](#objectissealed)
17. [Object.keys()](#objectkeys)
18. [Object.preventExtensions()](#objectpreventextensions)
19. [Object.seal()](#objectseal)
20. [Object.setPrototypeOf()](#objectsetprototypeof)
21. [Object.values()](#objectvalues)

## Methods

### Object.assign()
Copies the values of all enumerable own properties from one or more source objects to a target object. It returns the modified target object.

```javascript
const target = { a: 1, b: 2 };
const source = { b: 3, c: 4 };
const returnedTarget = Object.assign(target, source);
console.log(target); // { a: 1, b: 3, c: 4 }
console.log(returnedTarget); // { a: 1, b: 3, c: 4 }

// Emoji example
const baseEmoji = { face: '😀' };
const features = { eyes: '👀', mouth: '👄' };
const customEmoji = Object.assign({}, baseEmoji, features);
console.log(customEmoji); // { face: '😀', eyes: '👀', mouth: '👄' }
```

### Object.create()
Creates a new object with the specified prototype object and properties.

```javascript
const person = {
  isHuman: false,
  printIntroduction: function() {
    console.log(`My name is \${this.name}. Am I human? \${this.isHuman}`);
  }
};

const me = Object.create(person);
me.name = 'Matthew';
me.isHuman = true;
me.printIntroduction();
// Output: My name is Matthew. Am I human? true

// Emoji example
const animalPrototype = {
  makeSound: function() {
    console.log(this.sound);
  }
};

const dog = Object.create(animalPrototype);
dog.sound = '🐶 Woof!';
dog.makeSound(); // Output: 🐶 Woof!
```

### Object.defineProperty()
Defines a new property directly on an object, or modifies an existing property on an object, and returns the object.

```javascript
const object1 = {};

Object.defineProperty(object1, 'property1', {
  value: 42,
  writable: false
});

object1.property1 = 77; // Throws an error in strict mode
console.log(object1.property1); // 42

// Emoji example
const emojiObj = {};

Object.defineProperty(emojiObj, 'mood', {
  value: '😊',
  writable: true,
  enumerable: true,
  configurable: true
});

console.log(emojiObj.mood); // 😊
emojiObj.mood = '😢';
console.log(emojiObj.mood); // 😢
```

### Object.defineProperties()
Defines new or modifies existing properties directly on an object, returning the object.

```javascript
const object1 = {};

Object.defineProperties(object1, {
  property1: {
    value: 42,
    writable: true
  },
  property2: {}
});

console.log(object1.property1); // 42

// Emoji example
const emojiPalette = {};

Object.defineProperties(emojiPalette, {
  happy: { value: '😊', writable: false },
  sad: { value: '😢', writable: false },
  angry: { value: '😠', writable: false }
});

console.log(emojiPalette.happy); // 😊
emojiPalette.happy = '😃'; // This won't change the value
console.log(emojiPalette.happy); // Still 😊
```

### Object.entries()
Returns an array of a given object's own enumerable string-keyed property [key, value] pairs.

```javascript
const object1 = {
  a: 'somestring',
  b: 42
};

for (const [key, value] of Object.entries(object1)) {
  console.log(`\${key}: \${value}`);
}
// Output:
// "a: somestring"
// "b: 42"

// Emoji example
const emojiMeanings = {
  '😊': 'happy',
  '😢': 'sad',
  '😠': 'angry'
};

console.log(Object.entries(emojiMeanings));
// Output: [['😊', 'happy'], ['😢', 'sad'], ['😠', 'angry']]
```

### Object.freeze()
Freezes an object. A frozen object can no longer be changed.

```javascript
const obj = {
  prop: 42
};

Object.freeze(obj);

obj.prop = 33; // Throws an error in strict mode
console.log(obj.prop); // 42

// Emoji example
const frozenEmoji = Object.freeze({ face: '🥶' });
frozenEmoji.face = '😎'; // This won't work
console.log(frozenEmoji.face); // Still 🥶
```

### Object.fromEntries()
Transforms a list of key-value pairs into an object.

```javascript
const entries = new Map([
  ['foo', 'bar'],
  ['baz', 42]
]);

const obj = Object.fromEntries(entries);
console.log(obj); // { foo: "bar", baz: 42 }

// Emoji example
const emojiArray = [['mood', '😊'], ['weather', '☀️'], ['food', '🍕']];
const emojiObject = Object.fromEntries(emojiArray);
console.log(emojiObject); // { mood: '😊', weather: '☀️', food: '🍕' }
```

### Object.getOwnPropertyDescriptor()
Returns an object describing the configuration of a specific property on a given object.

```javascript
const object1 = {
  property1: 42
};

const descriptor1 = Object.getOwnPropertyDescriptor(object1, 'property1');
console.log(descriptor1.configurable); // true
console.log(descriptor1.value); // 42

// Emoji example
const emojiObj = { mood: '😊' };
const moodDescriptor = Object.getOwnPropertyDescriptor(emojiObj, 'mood');
console.log(moodDescriptor);
// Output: { value: '😊', writable: true, enumerable: true, configurable: true }
```

### Object.getOwnPropertyDescriptors()
Returns all own property descriptors of a given object.

```javascript
const object1 = {
  property1: 42,
  property2: 'hello'
};

const descriptors1 = Object.getOwnPropertyDescriptors(object1);
console.log(descriptors1.property1.writable); // true
console.log(descriptors1.property2.value); // "hello"

// Emoji example
const emojiWeather = { sunny: '☀️', rainy: '🌧️' };
const weatherDescriptors = Object.getOwnPropertyDescriptors(emojiWeather);
console.log(weatherDescriptors);
// Output: { 
//   sunny: { value: '☀️', writable: true, enumerable: true, configurable: true },
//   rainy: { value: '🌧️', writable: true, enumerable: true, configurable: true }
// }
```

### Object.getOwnPropertyNames()
Returns an array of all properties (including non-enumerable properties except for those which use Symbol) found directly in a given object.

```javascript
const object1 = {
  a: 1,
  b: 2,
  c: 3
};

console.log(Object.getOwnPropertyNames(object1));
// Output: ["a", "b", "c"]

// Emoji example
const emojiFruit = { '🍎': 'apple', '🍌': 'banana' };
Object.defineProperty(emojiFruit, '🍊', { value: 'orange', enumerable: false });
console.log(Object.getOwnPropertyNames(emojiFruit));
// Output: ['🍎', '🍌', '🍊']
```

### Object.getOwnPropertySymbols()
Returns an array of all symbol properties found directly upon a given object.

```javascript
const obj = {};
const a = Symbol('a');
const b = Symbol.for('b');

obj[a] = 'localSymbol';
obj[b] = 'globalSymbol';

const objectSymbols = Object.getOwnPropertySymbols(obj);

console.log(objectSymbols.length); // 2
console.log(objectSymbols); // [Symbol(a), Symbol(b)]
console.log(objectSymbols[0]); // Symbol(a)

// Emoji example
const emojiObj = {};
const happySymbol = Symbol('😊');
const sadSymbol = Symbol('😢');

emojiObj[happySymbol] = 'happy';
emojiObj[sadSymbol] = 'sad';

console.log(Object.getOwnPropertySymbols(emojiObj));
// Output: [Symbol(😊), Symbol(😢)]
```

### Object.getPrototypeOf()
Returns the prototype (i.e. the value of the internal [[Prototype]] property) of the specified object.

```javascript
const prototype1 = {};
const object1 = Object.create(prototype1);

console.log(Object.getPrototypeOf(object1) === prototype1); // true

// Emoji example
const animalPrototype = { makeSound: function() { console.log(this.sound); } };
const dog = Object.create(animalPrototype);
dog.sound = '🐶 Woof!';

console.log(Object.getPrototypeOf(dog) === animalPrototype); // true
```

### Object.is()
Determines whether two values are the same value.

```javascript
console.log(Object.is('foo', 'foo'));  // true
console.log(Object.is(window, window));  // true
console.log(Object.is('foo', 'bar'));  // false
console.log(Object.is([], []));  // false

const foo = { a: 1 };
const bar = { a: 1 };
console.log(Object.is(foo, foo));  // true
console.log(Object.is(foo, bar));  // false

// Emoji example
console.log(Object.is('😊', '😊')); // true
console.log(Object.is('😊', '😃')); // false
```

### Object.isExtensible()
Determines if an object is extensible (whether it can have new properties added to it).

```javascript
const object1 = {};

console.log(Object.isExtensible(object1)); // true

Object.preventExtensions(object1);

console.log(Object.isExtensible(object1)); // false

// Emoji example
const emojiObj = { mood: '😊' };
console.log(Object.isExtensible(emojiObj)); // true
Object.preventExtensions(emojiObj);
console.log(Object.isExtensible(emojiObj)); // false
emojiObj.weather = '☀️'; // This won't work
console.log(emojiObj); // { mood: '😊' }
```

### Object.isFrozen()
Determines if an object is frozen.

```javascript
const object1 = {
  property1: 42
};

console.log(Object.isFrozen(object1)); // false

Object.freeze(object1);

console.log(Object.isFrozen(object1)); // true

// Emoji example
const emojiObj = { mood: '😊' };
console.log(Object.isFrozen(emojiObj)); // false
Object.freeze(emojiObj);
console.log(Object.isFrozen(emojiObj)); // true
emojiObj.mood = '😢'; // This won't work
console.log(emojiObj.mood); // Still 😊
```

### Object.isSealed()
Determines if an object is sealed.

```javascript
const object1 = {
  property1: 42
};

console.log(Object.isSealed(object1)); // false

Object.seal(object1);

console.log(Object.isSealed(object1)); // true

// Emoji example
const emojiObj = { mood: '😊' };
console.log(Object.isSealed(emojiObj)); // false
Object.seal(emojiObj);
console.log(Object.isSealed(emojiObj)); // true
emojiObj.weather = '☀️'; // This won't work
console.log(emojiObj); // { mood: '😊' }
```

### Object.keys()
Returns an array of a given object's own enumerable property names.

```javascript
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};

console.log(Object.keys(object1));
// Output: ["a", "b", "c"]

// Emoji example
const emojiObj = { '😊': 'happy', '😢': 'sad', '😠': 'angry' };
console.log(Object.keys(emojiObj));
// Output: ['😊', '😢', '😠']

```

### Object.preventExtensions()
Prevents new properties from ever being added to an object.

```javascript
const object1 = {};

Object.preventExtensions(object1);

try {
  Object.defineProperty(object1, 'property1', {
    value: 42
  });
} catch (e) {
  console.log(e);
  // Expected output: TypeError: Cannot define property property1, object is not extensible
}

// Emoji example
const emojiObj = { mood: '😊' };
Object.preventExtensions(emojiObj);
emojiObj.weather = '☀️'; // This won't work
console.log(emojiObj); // { mood: '😊' }
```

### Object.seal()
Seals an object, preventing new properties from being added to it and marking all existing properties as non-configurable.

```javascript
const object1 = {
  property1: 42
};

Object.seal(object1);
object1.property1 = 33;
console.log(object1.property1); // 33

delete object1.property1; // This won't work
console.log(object1.property1); // 33

// Emoji example
const emojiObj = { mood: '😊' };
Object.seal(emojiObj);
emojiObj.mood = '😢'; // This works
emojiObj.weather = '☀️'; // This won't work
delete emojiObj.mood; // This won't work
console.log(emojiObj); // { mood: '😢' }
```

### Object.setPrototypeOf()
Sets the prototype (i.e., the internal [[Prototype]] property) of a specified object to another object or null.

```javascript
const obj = {};
const parent = { foo: 'bar' };

console.log(obj.foo); // undefined

Object.setPrototypeOf(obj, parent);

console.log(obj.foo); // "bar"

// Emoji example
const emojiObj = { mood: '😊' };
const emojiProto = { 
  changeMood: function(newMood) { 
    this.mood = newMood; 
  } 
};

Object.setPrototypeOf(emojiObj, emojiProto);
emojiObj.changeMood('😢');
console.log(emojiObj.mood); // 😢
```

### Object.values()
Returns an array of a given object's own enumerable property values.

```javascript
const object1 = {
  a: 'somestring',
  b: 42,
  c: false
};

console.log(Object.values(object1));
// Output: ["somestring", 42, false]

// Emoji example
const emojiObj = { mood: '😊', weather: '☀️', food: '🍕' };
console.log(Object.values(emojiObj));
// Output: ['😊', '☀️', '🍕']
```

This document covers the most commonly used object methods in JavaScript. Each method is explained with a brief description, a standard example, and an emoji-based example to demonstrate its usage.
