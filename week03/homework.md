### convertStringToNumber 函数

```javascript
const convertStringToNumber = (string, radix = 10) => {
    if (radix > 10) {
        return;
    }
    let flag = /e|E/.test(string);
    if (!flag) {
        let chars = string.split('');
        let number = 0;
        let i = 0;
        while (i < chars.length && chars[i] != '.') {
            number = number * radix;
            number += chars[i].codePointAt(0) - '0'.codePointAt(0);
            i++;
        }
        if (chars[i] === '.') {
            i++;
        }
        let fraction = 1;
        while (i < chars.length) {
            fraction /= radix;
            number += (chars[i].codePointAt(0) - '0'.codePointAt(0)) * fraction;
            i++;
        }
        return number;
    } else {
        let logNumber = Number(string.match(/\d+$/)[0]);
        let number = string.match(/^[\d\.]+/)[0].replace(/\./, '');
        if (/e-|E-/.test(string)) {
            return Number(number.padEnd(logNumber + 1, 0));
        } else {
            return Number(number.padStart(logNumber + number.length, 0).replace(/^0/, '0.'));
        }
    }
}
```
------
### convertNumberToString 函数

```javascript
const convertNumberToString = (number, type) => {
    if (arguments.length < 2) {
        type = 10;
    }
    var integer = Math.floor(number);
    var fractionPos = ('' + number).indexOf('.');
    var fractionLength = ('' + number).length - fractionPos - 1;
    var fraction = (number - integer).toFixed(fractionLength);
    var str = '';
    while (integer > 0) {
        str = integer % type + str;
        integer = Math.floor(integer / type);
    }
    if (fractionPos > -1) {
        str += '.';
        while (fractionLength > 0) {
            fraction *= type;
            str += Math.floor(fraction % type);
            fractionLength--;
        }
    }
    return str;
}
```
------

### JavaScript 对象

- Function Exotic Object
    - [[call]]
    - [[Construct]]
- Array Exotic Object
    - [[DefineOwnProperty]]
- String Exotic Object
    - [[GetOwnProperty]]
    - [[DefineOwnProperty]]
    - [[OwnPropertyKeys]]
- Arguments Exotic Objects
    - [[GetOwnProperty]] 
    - [[DefineOwnProperty]]
    - [[Get]] 
    - [[Set]] 
    - [[Delete]]
- Module Namespace Exotic Objects
    - [[Module]]
    - [[Exports]]
- Integer-Indexed Exotic Objects
    - [[GetOwnProperty]] 
    - [[HasProperty]]
    - [[DefineOwnProperty]] 
    - [[Get]] 
    - [[Set]]
    - [[OwnPropertyKeys]]