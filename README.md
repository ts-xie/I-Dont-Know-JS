# I-Dont-Know-JS

> Different than [You-Dont-Know-JS](https://github.com/getify/You-Dont-Know-JS), I-Dont-Know-JS list all the _abnormal_ but usefull JS expressions that I've learned so far.

### [Function.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/length)

We can use it to test against pass-in functions.

```
let f = () => {};
f.length === 0;

let g = (d, x) => {};
g.length === 2;

// usage
function foo(f) {
  if(f.length < 2) doSomething();
  bar();
}
```

### `&&` and `||`

Logical operators can be used for logically eliminate if/else statements.

```
f() && g();

// is equivalent to
let f = f();
f ? g() : f;
```

```
f() || g();

// is equivalent to
let f = f();
f ? f : g();
```

### [`_` and `$`](https://stackoverflow.com/questions/205853/why-would-a-javascript-variable-start-with-a-dollar-sign)

They are permitted anywhere in an identifier. Conventionally use `_` for private property, and use `$` for DOM reference.

```
this._id = 1;

$el = document.querySelector('p');

function list(_){
  return Array.prototype.slice.call(_)
}
```

### [`self` === `this`](https://stackoverflow.com/questions/16875767/difference-between-this-and-self-in-javascript)

In browser, `self` evaluate to `Window`. `this` is evaluated based on the context.

```
function a() {
  this.name = 'mengo';
  console.log(this);
  console.log(self);
}

new a;

// { name: 'mengo' }
// Window{}
```

### [parentheses is optional](https://stackoverflow.com/questions/35949554/invoking-a-function-without-parentheses)

```
function car(){
  setup()
}

let c = new car;
```

### [!!value](https://stackoverflow.com/questions/784929/what-is-the-not-not-operator-in-javascript)
Convert `value` to Boolean type.
```
!!null         // false
!!NaN          // false
!!undefined    // false
!!''           // false
!!{}           // true
!![]           // true
!!function(){} // true
```

### [!function(){}()](https://stackoverflow.com/questions/3755606/what-does-the-exclamation-mark-do-before-the-function)
Functionally same as self invocation function.
```
!function(){}(); // returns true
// same as
(function(){})(); // returns undefined
```
