# Differences between lodash's _.assign and _.assignIn

### _.assign

`_.assign` mutates object and is loosely based on `Object.assign`.

```javascript
function Foo() {
  this.a = 1;
}
 
function Bar() {
  this.c = 3;
}
 
Foo.prototype.b = 2;
Bar.prototype.d = 4;
 
_.assign({ 'a': 0 }, new Foo, new Bar);
// => { 'a': 1, 'c': 3 }
```

### _.assignIn
```javascript
function Foo() {
  this.a = 1;
}
 
function Bar() {
  this.c = 3;
}
 
Foo.prototype.b = 2;
Bar.prototype.d = 4;
 
_.assignIn({ 'a': 0 }, new Foo, new Bar);
// => { 'a': 1, 'b': 2, 'c': 3, 'd': 4 }
```

### Note
This naming convention also apply to other methods, such as `_.keys` and `_.keysIn`.

---

Aug 22 2019, by @jeongwooklee
