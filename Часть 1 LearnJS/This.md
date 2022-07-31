- Обычная функция: 
	- `this = undefined (use strict)` 
	- `this = window (без ise strict)`
```js
function showThis(a, b) {
    console.log(this);
    
    function sum() {
        console.log(this);
        return a + b;
    }
}
showThis (4, 5); // undefined
```
- Объект: 
	- `this = obj`
```js
const obj = {
	a: 4,
	b: 5,
	sum: function (){
		console.log(this);
	}
};
obj.sum(); // {a: 4, b: 5, sum: [Functiom: sum]}
```