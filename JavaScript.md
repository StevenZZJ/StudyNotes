[TOC]

# JavaScript SE6

- Java has nothing to do with JavaScript

# Getting Started

## include JavaScript in HTML file

1. From page

```html
<script>
    'use strict'; //strict checking mode
	//...
</script>
```

2. From .js file

a file named abc.js

```html
<script src="abc.js"></script>
```

## Variables

> No need to declare type in JS `var score = 90`, `let` for loca

> `i=1` is a global variable !

> To print out variables in console/browser `console.log(score)`

```javascript
// 1.number type (JS does not distinguish integer and float)
123;
123.1;
1.123e3;
-99;
NaN; //Not a number
Infinity;

// 2.String


// 3.Boolean




```

## Operators

> `&&`, `||`, `!`
>
> `=`
>
> `==` Only check value
>
> `===` Check type and value
>
> - `NaN === NaN` is false
> - use isNaN() to check NaN
>
> Avoid compare floats
>
> ```javascript
> // A solution
> Math.abs(1/3-(1-2/3)) < 0.00000001;
> ```
>
> `null` and `undefined`

## Array

> Array in JS can have different types
>
> ```javascript
> var arr = [1,2,3,null,'hello'];
> 
> arr[5]; // Overflow will give `undifined`
> ```











