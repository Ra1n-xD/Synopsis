- Обычная функция: this = undefines (use strict) или this = window (без ise strict)
```js
function showThis(a, b) {
    console.log(this);
    
    function sum() {
        console.log(this);
        return a + b;
    }
}
showThis (4, 5);
```