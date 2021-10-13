# Homework #1

### Задача №1

Перебрать элементы массива, произвести проверку на NaN. Если элемент является NaN, заменить его на null. По завершению цикла вывести в консоль сообщение ‘Проверка и изменение массива завершена’ и получившийся массив на следующей строке.

* Реализовать с помощью цикла for
* Реализовать с помощью цикла while

Пример массива для преобразований: **[16, true, 'MetraBit', NaN, {name: 'UserName', hobby: 'JS'}, 30, NaN, null, false, 'Vue']**

```js
var array = [16, true, 'MetraBit', NaN, { name: 'UserName', hobby: 'JS' }, 30, NaN, null, false, 'Vue']

for (var i = 0; i < array.length; i++) {
	if (array[i] !== array[i]) {
		array[i] = null
	}
}
console.log('Проверка и изменение массива завершена')
console.log(array)


// while
var arrayForWhile = [16, true, 'MetraBit', NaN, { name: 'UserName', hobby: 'JS' }, 30, NaN, null, false, 'Vue']
var n = arrayForWhile.length

while (n--) {
	if (arrayForWhile[n] !== arrayForWhile[n]) {
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
	arrayOfNumbers[i] = Number(arrayOfNumbers[i])
}

for (var x = 0; x < arrayOfNumbers.length; x++) {
	if (arrayOfNumbers[x] % 3 === 0) {
		counter++
	}
}

if (counter > 0) {
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
count > 0 ? console.log(`В данном массиве: ${count} чисел кратных 3`) : console.warn('В данном массиве нет чисел кратных 3')
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
var arrayOfTypes = [16, true, 'MetraBit', NaN, { name: 'UserName', hobby: 'JS' }, 30, NaN, null, false, 'Vue', ['test for Array']]

function arrayOftypesFunc(arrayOfTypes) {
	var countString = 0
	var countNumber = 0
	var countBoolean = 0
	var countNull = 0
	var countObject = 0
	var countArray = 0
	for (var i = 0; i < arrayOfTypes.length; i++) {
		if (typeof arrayOfTypes[i] === 'string') {
			countString++;
		} else if (typeof arrayOfTypes[i] === 'number') {
			countNumber++;
		} else if (typeof arrayOfTypes[i] === 'boolean') {
			countBoolean++;
		} else if (!arrayOfTypes[i]) {
			countNull++;
		} else if (arrayOfTypes[i] instanceof Array) {
			countArray++;
		} else {
			countObject++;
		}
	}
	console.log(`
	String: ${countString}
	Number: ${countNumber}
	Boolean: ${countBoolean}
	Null: ${countNull}
	Array: ${countArray}
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


# Homework #2

### Задача №1

Создать объект ‘user’ с полем ‘name’. Значение указать произвольное.

Добавить метод sayHello() в объект. Метод в качестве аргумента должен принимать единственное значение - строку приветствия. Сделать дефолтное значение этого формального параметра строкой: “Добрый день”.

Возвращать функция будет конкатенированную строку типа: ‘Приветствие’ и ‘name’. В функцию добавить проверки на:

* наличия поля ‘name’ в объекте (не undefined)
* поле ‘name’ является строкой
* поле ‘name’ не пустая строка

Если какое-либо условие не выполняется, то в этом случаи возвращать строку: ‘Имя пользователя не указано’. Для формирования результирующей строки использовать this.

``` js
var user = {
	name: 'Arnold'
}

user.sayHello = function (message = 'Доброе утро') {
	if (typeof this.name === 'string'
		&& this.name.length >= 1 && this.name != undefined || null) {
		return `${message}, ${this.name}`
	} else {
		console.log('Имя пользователя не указано')
	}
}
```

### Задача №2

Создать объект product, со следующими полями:

* name: ‘iPhone’,
* id: 7485,
* price: 1000

Написать метод этого объекта который в качестве аргумента принимает число (количество процентов, на которое нужно увеличить свойство ‘price’).

* Увеличить свойство ‘price’ на заданное количество процентов используя this.
* Вернуть новое значение свойства ‘price’.

``` js 
var product = {
	name: 'iPhone',
	id: 7485,
	price: 1000,
	getNumber: function (number = 45) {
		var pricePrecent = this.price / 100 * number
		return this.price = this.price + pricePrecent
	}
}
```

### Задача №3

Написать функцию ‘showStudentsFavoriteLessons’, которая в качестве аргументов будет принимать неограниченное количество имён студентов (строк). И выводит в консоль список любимых уроков для каждого студента.

Внутри функции ‘showStudentsFavoriteLessons’ создать массив ‘lessons’ и функцию ‘checkStudentFavoriteLessons’.

Массив ‘lessons’ будет состоять из строк (названий уроков).

Пример массива ‘lessons’:
* ['Математика', 'История', 'Спорт', 'Литература', 'Биология', 'География']

Функция ‘checkStudentFavoriteLessons’ в качестве аргумента будет принимать имя студента. В функции из массива ‘lessons’ нужно выбрать последние n элементов (где n – это случайное число) и поместить массив этих элементов в переменную ‘favoriteLessons’ Если в массиве есть хоть один элемент, то вернуть строку, в которой сначала будет имя студента, двоеточие и все элементы из массива ‘favoriteLessons’ через запятую. Если в массиве ‘favoriteLessons’ нет элементов, то вернуть строку с именем студента и сообщением ‘У этого студента нет любимых предметов’.

Один вызов функции должен выводить сообщения сразу для всех студентов.

Пример вызова функции: ```showStudentsFavoriteLessons('Артур', 'Женя', 'Костя', 'Маша', 'Денис')```

``` js
function showStudentsFavoriteLessons() {
	var lessons = ['Математика', 'История', 'Спорт', 'Литература', 'Биология', 'География']
	for (var i = 0; i < arguments.length; i++) {
		var result = checkStudentFavoriteLessons(arguments[i], lessons)
		console.log(result)
	}

	function checkStudentFavoriteLessons(userName, lessonsArray) {
		var favoriteLesson = []
		var nameLessonsLength = lessonsArray.length -1
		var elementsRandom = Math.floor(Math.random() * nameLessonsLength)
		for (var i = nameLessonsLength; i >= elementsRandom; i--) {
			favoriteLesson.push(lessonsArray[i])
		}
		return `${userName}: ${favoriteLesson.length > 0 ? favoriteLesson.join(', ' ) 
			: 'У этого студента нет любимых предметов'}`
	}

}
showStudentsFavoriteLessons('Артур', 'Женя', 'Костя', 'Маша', 'Денис')
```

