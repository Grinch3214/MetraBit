# Homework #1

### Задача №1

Перебрать элементы массива, произвести проверку на NaN. Если элемент является NaN, заменить его на null. По завершению цикла вывести в консоль сообщение ‘Проверка и изменение массива завершена’ и получившийся массив на следующей строке.

* Реализовать с помощью цикла for
* Реализовать с помощью цикла while

Пример массива для преобразований: **[16, true, 'MetraBit', NaN, {name: 'UserName', hobby: 'JS'}, 30, NaN, null, false, 'Vue']**

```js
var array = [16, true, 'MetraBit', NaN, { name: 'UserName', hobby: 'JS' }, 30, NaN, null, false, 'Vue']

for (var i = 0; i < array.length; i++) {
	if (array[i] !== array[i] && isNaN(array[i])) {
		array[i] = null
	}
}
console.log('Проверка и изменение массива завершена')
console.log(array)


// while
var arrayForWhile = [16, true, 'MetraBit', NaN, { name: 'UserName', hobby: 'JS' }, 30, NaN, null, false, 'Vue']
var n = arrayForWhile.length

while (n--) {
	if (arrayForWhile[n] !== arrayForWhile[n] && isNaN(arrayForWhile[n])) {
		arrayForWhile[n] = null
	}
}
console.log('Проверка и изменение массива завершена')
console.log(arrayForWhile)
```
***
### Задача №2

Перебрать массив, посчитать сколько в массиве чисел кратных трем и вывести в консоль сообщение ‘В данном массиве n чисел кратных 3’, если они есть. Если нет чисел кратных 3, вывести сообщение ‘В данном массиве нет чисел кратных 3’

n – количество чисел

Пример массива: 

**[45, '246', 73, '4', 15, 36, 17, 89, '49', 167, 123]**
* Использовать темплейтный литерал
* Реализовать с помощью цикла for
* Реализовать с помощью цикла while

``` js
var arrayOfNumbers = [45, '246', 73, '4', 15, 36, 17, 89, '49', 167, 123]
var counter = 0

for (var i = 0; i < arrayOfNumbers.length; i++) {
	arrayOfNumbers[i]
}

for (var x = 0; x < arrayOfNumbers.length; x++) {
	if (arrayOfNumbers[x] % 3 === 0) {
		counter++
	}
}

if (counter) {
	console.log(`В данном массиве: ${counter} чисел кратных 3`)
} else {
	console.warn('В данном массиве нет чисел кратных 3')
}

// while
var arrayOfNumbersForWhile = [45, '246', 73, '4', 15, 36, 17, 89, '49', 167, 123]

var arrNum = arrayOfNumbersForWhile.length
var count = 0

while (arrNum--) {
	if (arrayOfNumbersForWhile[arrNum] % 3 === 0) {
		count++
	}
}
console.log(count ? `В данном массиве: ${count} чисел кратных 3` : console.warn('В данном массиве нет чисел кратных 3'))
```
***

### Задача №3

Написать функцию, которая принимает в качестве входного параметра массив, в котором находятся элементы следующих типов: строка, число, логическое значение(булиан), null и объект. Посчитать количество элементов каждого типа и вывести в консоль в следующем формате:

* String: n
* Number: n
* Boolean: n
* Null: n
* Object: n
n – число элементов этого типа в массиве

Пример массива:

**[16, true, 'MetraBit', NaN, {name: 'UserName', hobby: 'JS'}, 30, NaN, null, false, 'Vue']**

``` js
var arrayOfTypes = [16, true, 'MetraBit', NaN, { name: 'UserName', hobby: 'JS' }, 30, NaN, null, false, 'Vue']

function arrayOftypesFunc(arrayOfTypes) {
	var countString = 0
	var countNumber = 0
	var countBoolean = 0
	var countNull = 0
	var countObject = 0
	for (var i = 0; i < arrayOfTypes.length; i++) {
		if (typeof arrayOfTypes[i] === 'string') {
			countString++;
		} else if (typeof arrayOfTypes[i] === 'number') {
			countNumber++;
		} else if (typeof arrayOfTypes[i] === 'boolean') {
			countBoolean++;
		} else if (!arrayOfTypes[i]) {
			countNull++;
        } else {
			countObject++;
		}
	}
	console.log(`
	String: ${countString}
	Number: ${countNumber}
	Boolean: ${countBoolean}
	Null: ${countNull}
	Object: ${countObject}
	`)
}
arrayOftypesFunc(arrayOfTypes)
```
***

### Задача №4

Написать функцию, которая принимает два аргумента. Первый аргумент - имя пользователя (строка). Второй аргумент – сообщение приветствия. Функция должна возвращать строку, объединяющую имя и сообщения приветствия.

Реализовать функцию используя ***function declaration***

Реализовать функцию используя ***function expression***

Использовать оператор **return**

``` js
// declaration
var userName = 'Pablo'
var userHi = 'Welcome'
function sayHi(userName, userHi) {
	return `${userName}, ${userHi}`
}

console.log(sayHi(userHi, userName))

//expression
var sayHello = function (userName, userHi) {
	return `${userName}, ${userHi}`
}

console.log(sayHi(userHi, userName))
```
