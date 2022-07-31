- Обычная функция: 
	- `this = undefined (use strict)` 
	- `this = window (без ise strict)`
```js
function showThis(a, b) {
    console.log(this);
}
showThis (4, 5); // undefined
```
- В объекте  `this = obj`
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
- `this` в функции внутри объекта работает по аналогии с обычной функцией
```js
const obj = {
	a: 4,
	b: 5,
	sum: function (){
		function shout() {
	        console.log(this);
	    }
	    shout();
	}
};
obj.sum(); // undefined
```
- `this` в конструкторах и классах – это новый экземпляр объекта
```js
function User(name, id){
	this.name = name;
	this.id = id;
	this.hello = function(){
		console.log('hello' + this.name);
	};
} 
let ivan = new User('Ivan', 20); // this = ivan
```