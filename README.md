# Operators: Simple & Complex

"Can this operation be broken down in a trace-block?"

---

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

---

### But it's not always so simple:

__Simple__
```js
let a = 3 + 4;
// --- trace-blocked ---
let a = 3 + 4;
```

__Complex__
```js
let a = 3 + "4";
// --- trace-blocked ---
let a;
{ // = 3 + "4";
  const step_1 = String(3);
  const step_2 = step_1 + "4";
  a = step_2;
};
```


___
___
### <a href="http://elewa.education/blog" target="_blank"><img src="https://user-images.githubusercontent.com/18554853/34921062-506450ae-f97d-11e7-875f-6feeb26ad72d.png" width="100" height="40"/></a>
