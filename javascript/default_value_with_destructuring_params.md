# Default value with destructuring parameters

ES6 (ECMAScript 6) support very useful feature which name is `destructuring`.

## Destructuring

```javascript
const obj = { first: 'Jane', last: 'Doe' };
const {first: f, last: l} = obj;
// f = 'Jane'; l = 'Doe'
```

You can use this feature for function parameters, too.

```javascript
const obj = { first: 'Jane', last: 'Doe' };
const newFuction = ({ first, last }) => {
  console.log(first);
  console.log(last);
}

> newFunction(obj);
Jane
Doe
```

If you want to use multiple parameters with destructurable object, you can do like this.

```javascript
const newFunction = (a, b, opts) => {
  const { option1, option2 } = opts;
  console.log(option1);
  console.log(option2);
}

> newFunction('a', 'b', { option1: 1, option2: 2 })
1
2
```

Though if you should add default value for opts, don't do like this.

```javascript
const newFunction = (a, b, opts = { option1: 'op1', option2: 'op2' }) => {
}
```

In this case,
if you pass object`{ option1: 'test' }` for __opts__ parameter, __opts__ will be just `{ option1: 'test' }`.
Because you already passed `object` for __opts__, __opts__'s default value`{ option1: 'op1', option2: 'op2' }` will not be applied.

So, you should do like this.

```javascript
const newFunction = (a, b, { option1 = 'op1', option2 = 'op2' } = {}) => {
  console.log(option1);
  console.log(option2);
}
```

If last parameter is optional, don't forget `= {}` for default object.

```javascript
> newFunction(null, null);
op1
op2

> newFunction(null, null, { option1: 'test' });
test
op2

> newFunction(null, null, { option2: 'abc' });
op1
abc

> newFunction(null, null, { option1: 'a', option2: 'b' });
a
b
```

Mar 2, 2017 by kyuhohan
