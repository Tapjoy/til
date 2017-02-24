# toFixed with floor

`toFixed` is a pretty useful method. However, the numbers are always rounded and we can't control it.
In most cases this is not a problem, but it's not suitable for all situations.

```javascript
999.91.toFixed(1);  // '999.9'
999.99.toFixed(1);  // '1000.0'
```

This method doesn't accept options for rounding, so if we want to round it down, we need to do different way.
There are several ways, but I implemented it like this.

```javascript
// Assuming that lodash is imported
function trimByDecimal(value, decimal = 2) {
  if (value % 1 === 0) return value;
  const stringValue = _.toString(value);
  const indexOfDecimalPoint = stringValue.indexOf('.');
  return stringValue.slice(0, indexOfDecimalPoint + (decimal + 1));
}

trimByDecimal(999.91, 1);  // '999.9'
trimByDecimal(999.99, 1);  // '999.9'
```

Feb 24, 2017 by jeongwooklee
