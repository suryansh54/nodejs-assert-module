# Node.js Assert Module
The assert module provides a way of testing expressions. If the expression evaluates to 0, or false, an assertion failure is being caused, and the program is terminated.

### Assert Methods
Method | Description 
--- | ---
assert() | Checks if a value is true. Same as assert.ok()
deepEqual() | Checks if two values are equal
deepStrictEqual() | Checks if two values are equal, using the strict equal operator (===)
equal() | Checks if two values are equal, using the equal operator (==)
fail()	 | Throws a specified error if the specified error evaluates to true
notDeepEqual()	 | Checks if two values are not equal
notDeepStrictEqual() | Checks if two values are not equal, using the strict not equal operator (!==)
notEqual() | Checks if two values are not equal, using the not equal operator (!=)
notStrictEqual() | Checks if two values are not equal, using the strict not equal operator (!==)
ok() | Checks if a value is true
strictEqual() | Checks if two values are equal, using the strict equal operator (===)

#### assert()

*Syntax*
`assert(expression, message);`

```javascript
var assert = require('assert');
assert(50 > 70);
```

#### assert.deepEqual()

*Syntax*
` assert.deepEqual(value1, value2, message);`

```javascript
var assert = require('assert');
var x = { a : { n: 0 } };
var y = { a : { n: 0 } };
var z = { a : { n: 1 } };
assert.deepEqual(x, y); //OK
assert.deepEqual(x, z); /*AssertionError: { a: { n: 0 } } deepEqual {a: { n: 1 } }*/
```

#### assert.deepStrictEqual()

*Syntax*
` assert.deepStrictEqual(value1, value2, message);`

```javascript
var assert = require('assert');
var x = { a : { n: 0 } };
var z = { a : { n: '0' } };
assert.deepStrictEqual(x, z, "My message goes here");
```

#### assert.equal()

*Syntax*
` assert.equal(value1, value2, message);`

```javascript
var assert = require('assert');
assert.equal(50, 50); //OK
assert.equal(50, "50"); //OK
assert.equal(50, 70); /*AssertionError: 50 == 70 */
```

#### notDeepEqual()
- The assert.notDeepEqual() method tests if two objects, and their child objects, are NOT equal, using the != operator.
- If the two objects are equal, an assertion failure is being caused, and the program is terminated.
- To compare the objects using the !== operator, use the assert.notDeepStrictEqual() method.

*Syntax*
` assert.notDeepEqual(value1, value2, message);`

```javascript
var assert = require('assert');
var x = { a : { n: 0 } };
var y = { a : { n: 0 } };
var z = { a : { n: 1 } };
assert.notDeepEqual(x, z); //OK
assert.notDeepEqual(x, y); /*AssertionError: { a: { n: 0 } } notDeepEqual {a: { n: 0 } }*/
```

#### assert.ok()
- The assert.ok() method tests if a given expression is true or not.
- If the expression evaluates to 0, or false, an assertion failure is being caused, and the program is terminated.

*Syntax*
`assert.ok(expression, message);`

```javascript
var assert = require('assert');
assert.ok(50 > 70);
```
