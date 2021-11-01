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
***

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
***

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

# Homework #3

### Задача №1

Написать функцию, которая в качестве формальных параметров принимает неограниченное количество аргументов. В функции произвести проверку является ли переданный аргумент массивом. Из аргументов, которые являются массивами, сделать один общий массив. Добавить строку ‘Start’ в начало массива, строку ‘The End’ в конец массива. Вернуть результирующий массив в обратной последовательности (Первый элемент – последний, а последний - первый).

Пример аргументов:
* null, 123, ‘JS’, [‘Nastya’, ‘Dima’, ‘Max’, ‘Masha’], undefined, {}, true, [‘Sasha’, ‘Denis’, ‘Marina’]

``` js
function checkArray() {
    var arr = []
    for (var i = 0; i < arguments.length; i++) {
        if (arguments[i] instanceof Array) {
            arr = arr.concat(arguments[i])
        }
    }
    arr.unshift('Start')
    arr.push('The End')
    arr.reverse()
    return arr
}
checkArray(null, 123, 'JS', ['Nastia', 'Dima', 'Max', 'Masha'], undefined, {}, true, ['Sasha', 'Denis', 'Marina'])
```
***

### Задача №2

Написать функцию, которая в качестве аргументов принимает два массива, первый – массив чисел, второй – массив строк. Производит проверку равна ли длинная первого массива, длине второго массива. Если результат отрицательный, то вернуть строку “Массивы имеют разную длину”. Если результат положительный, то отсортировать массив чисел по возрастанию и с помощью метода **splice** добавить все элементы массива со строками в середину массива с числами (чтобы в результате получился одномерный массив).

Пример массивов:
* [73, 4, 11, 234, 58, 134]
* ['js', 'css', 'jq’, ‘html’, ‘vue’, ‘bootstrap’]

``` js
function giveMeArray(arrayNumber, arrayString) { 
    if (arrayNumber.length === arrayString.length) { 
        arrayNumber.sort(function(a, b) { 
            return a - b 
        }) 
        var indexCenter = Math.floor(arrayNumber.length / 2) 
        for (let i = 0; i < arrayString.length; i++) { 
           arrayNumber.splice(indexCenter++, 0, arrayString[i]) 
        } 
        
         
    } else { 
        console.log('Массивы имеют разную длину') 
    } 
    return arrayNumber; 
} 
var num = [73, 4, 11, 234, 58, 134] 
var str = ['js', 'css', 'jq', 'html', 'vue', 'bootstrap'] 
giveMeArray(num, str) 
console.log(num)
```
***

### Задача №3

Написать функцию, которая принимает в качестве аргумента строку произвольной длины и число (n) – до какого символа обрезать строку.

Реализуйте сравнение длины строки и переданного вторым аргументом числа. Если длина строки превышает n, то вернуть строку, состоящую из первых n символов строки и добавить троеточия в конце. Если меньше, вернуть начальную строку, в которой, заменены все пробелы на “-” и первая и последняя буквы являются заглавными.

``` js
function giveMeStringBro(str, num) {
  if (str.length > num) {
    var sliceStr = str.slice(0, num)
    var result = sliceStr.concat('...')
    return result
  } else if (str.length < num) {
    var newStr = str.replace(/ /g, '-')
    return newStr
  }
}
giveMeStringBro('Hello my dear friend', 11)
```
***

### Задача №4

Напишите функцию, которая принимает первым аргументом фразу, а вторым аргументом – слово (часть заданной фразы). Вырежьте из фразы заданное слово и верните строку которая осталась.

``` js
var phrase = 'The quick brown fox jumps over the lazy dog.';

function cutString(phrase, str) {
  var phraseWord = phrase.indexOf(str)
  var lengthStr = str.length
  return phrase.substr(0, phraseWord) + phrase.substr(phraseWord + lengthStr + 1)
}

cutString(phrase, 'lazy')
```

# Homework #4

### Задача №1

Напишите функцию, которая возвращает количество своих вызовов
* Переменная счётчика должна быть внутри функции
* Реализовать с помощью замыкания

```js 
function counter() {
  var count = 0

  return function() {
    return count++
  }
}

var countPlus = counter()

countPlus()
```
***

### Задача №2

Напишите функцию, которая будет создавать случайное число в диапазоне от 1 до 50 при каждом вызове.
Для сохранения числа, создайте результирующий массив. Этот массив, должен быть доступен только для функции, которая создаёт случайные числа. Добавляйте в него только уникальные числа и возвращайте результирующий массив, если созданное функцией число было уникальным и попало в массив. Если созданное функцией число уже есть в массиве, то возвращайте строку "Это число уже есть в массиве!".
* Реализовать с помощью замыкания

```js
function random() {
  var array = []
  return function() {
    var number = Math.floor(Math.random() * 50)
    if (!array.includes(number)) {
      array.push(number)
    } else {
      console.log('Это число уже есть в массиве!')
    }
    return array
  }
}
var pushArr = random()

pushArr()
```

# Homework #5

### Задача №1

Создайте IIFE, которое получает пароль в аргументе и возвращает внутреннюю функцию, которая в качестве аргумента принимает введенную строку и возвращает булево значение true, если введенная строка совпадает с паролем и faulse – если не совпадает. Для сохранения результата IIFE создайте переменную checkPassword.

```js
var checkPassword = (function(password = 'qwerty') {
  return function(string) {
    return string === password ? true : false
  }
})()
checkPassword('qwerty')
```

***

### Задача №2

Создайте IIFE, которое получает число n (начальное значение) в качестве аргумента родительской функции и возвращает функцию, которая получает число, прибавляет его к n, которое находится в замыкании, и возвращает результат. Для сохранения результата IIFE создайте переменную addeter.

```js
var addeter = (function(n) {
  var n = 2
  return function(t) {
    return t + n;
  };
})();
addeter(6) // 8
```

***

### Задача №3

Создайте IIFE, которое вернёт функцию, у которой в замыкании будет переменная counter со значением 10. Сделайте так, чтобы каждый вызов возвращённой функции уменьшал это число на 1 и выводил на экран уменьшенное число. Добавьте функционал, чтобы отсчет доходил до 0, а затем каждый последующий вызов функции выводил на экран сообщение о том, что отсчет окончен.

```js
var result = (function() {
  var counter = 10
  return function() {
    if(counter <= 0) {
        return 'Отсчёт окончен'
    } else {
      return --counter
    }
  }
})()
result()
```

***

### Задача №4

Напишите функцию, которая в качестве единственного аргумента принимает массив чисел и возвращает сумму чисел этого массива.
* Реализовать с помощью рекурсии

```js
var sum = (array) => (array.length === 0) ? 0 : array[0] + sum(array.slice(1))
sum([1, 5, 10])
```

***

### Задача №5

Напишите функцию, которая в качестве аргументов принимает два числа. Первое число – начало диапазона. Второе число – конец диапазона. Вернуть строку всех целых чисел из этого диапазона через запятую.
* Реализовать с помощью рекурсии

```js

```

