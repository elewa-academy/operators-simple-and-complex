# Operators: Simple & Complex


__Simple__
```js
let a = 3 + 4;
// --- trace-blocked ---
let a = 3 + 4;
```

__Complex 1__
```js
let a = 1;
let b = a++;
// --- trace-blocked ---
let a = 1;
let b;
{ // a++
  b = a;
  a = a + 1;
};
```
__Complex 2__
```js
let a = 1;
let b = ++a;
// --- trace-blocked ---
let a = 1;
let b;
{ // ++a
  a = a + 1;
  b = a;
};
```


___
___
### <a href="http://elewa.education/blog" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/34921062-506450ae-f97d-11e7-875f-6feeb26ad72d.png" width="100" height="40"/></a>
