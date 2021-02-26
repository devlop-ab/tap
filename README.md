<p align="center">
    <a href="https://www.npmjs.org/package/@devlop-ab/tap"><img src="https://img.shields.io/npm/v/@devlop-ab/tap.svg" alt="Latest Stable Version"></a>
    <a href="https://github.com/devlop-ab/tap/blob/main/LICENSE.md"><img src="https://img.shields.io/badge/license-MIT-green" alt="License"></a>
</p>

# tap

A JavaScript implementation of [Laravel's tap](https://laravel.com/docs/8.x/helpers#method-tap) helper.

# Installing

using npm

```bash
npm install @devlop-ab/tap
```

# Usage 

```js
import tap from '@devlop-ab/tap';

// or
const tap = require('@devlop-ab/tap');
```

`tap` accepts two arguments, a value and a callback.
The `callback` will get the `value` as the first argument, any return value of the callback will be ignored and the `original value` will be returned.

## Examples

```js

let someVariable = true;

let anotherValue = tap(someVariable, function () {
    console.log(someVariable); // true
});

console.log(anotherValue); // true
```

```js
let someVariable = true;

let anotherValue = tap(someVariable, function () {
    console.log(someVariable); // true
    
    // re-assignments have no effect
    someVariable = false;
    
    // return values are ignored
    return false;
});

console.log(anotherValue); // still true 
```
