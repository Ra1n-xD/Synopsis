- Обычная функция: 
	- `this = undefined (use strict)` 
	- `this = window (без ise strict)`
```js
function showThis(a, b) {
    console.log(this);
}
showThis(); // undefined
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
- `this` в функции внутри объекта (тоже самое, что и при обычной функии)
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
- Callback не имеет `this` и идет вверх 
```js
const obj = {
	num: 5,
	sayNumber: function(){
		const say = () =>{
			console.log(this);
		}
		say();
	}
};
obj.sayNumber(); //this = obj
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
- Ручная привязка `this: call, apply, bind`
```js
function sayName(surname) {
    console.log(this);
    console.log(this.name + surname);
}
const user = {
    name: 'Ed'
};

sayName.call(user, 'Lox');
//{ name: 'Ed' }
//EdLox
sayName.apply(user, ['Lox']);
//{ name: 'Ed' }
//EdLox
```
```js
function count(num) {
    return this * num;
}
const double = count.bind(2); // this = 2

console.log(double(3)); // 6
console.log(double(5)); // 10
```
- При использовании НЕ стрелочной функции в обработчике `this = элементу`. У callback `this = undefined (use strict)` или `this = window (без ise strict)`
```js
const btn = document.querySelector('button');

btn.addEventListener('click', function(){
    console.log(this); // <button></button>
});
```
