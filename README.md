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
  name: 'Arnold',
  sayHello: function (message = 'Доброе утро') {
	if (typeof this.name === 'string'
		&& this.name.length > 0 && this.name != undefined || null) {
		return `${message}, ${this.name}`
	} else {
		return 'Имя пользователя не указано'
	}
  }
}
user.sayHello()
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
function range(first, last) {
  var arr = []
  if (first > last) {
    return arr
  }
  arr.push(first)
  return (arr.concat(range(++first, last))).toString()
}
range(1, 10)
```

***

### Задача №6

Напишите функцию, которая принимает массив из последовательности чисел и возвращает максимальное число.
* Реализовать с помощью рекурсии

```js
var numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

function maxNum(numbers) {
  if(numbers.length > 2) {
    numbers.splice(0, 1)
    return maxNum([numbers[0], maxNum(numbers)])
  } else {
    return numbers[0] >= numbers[1] ? numbers[0] : numbers[1]
  }
}
maxNum(numbers)
```
Через Math:

```js
function getMaxNum(numbers) {
  return Math.max.apply(null, numbers)
}
getMaxNum(numbers)
```

***

### Задача №7

Создать объект пользователя со следующими полями:
* firstName
* lastName
* birthday
Значения полей указать произвольное. Реализовать следующие геттеры и сеттеры:
* геттер fullName - возвращает конкатенированную строку, состоящую из firstName и lastName
* сеттер fullName - устанавливает значения в поля firstName и lastName
* геттер age - возвращает количество лет от даты указанной в birthday, до текущего дня.
* сеттер age - изменяет год в поле birthday, вычисляя это значение из текущего года и нового значения

```js
var user = {
  firstName: 'Max',
  lastName: 'Grinch',
  birthday: '01/01/1990',
  get fullName() {
    return `${this.firstName} ${this.lastName}`
  },
  set fullName(newFullName) {
    this.firstName = newFullName.substring(0, newFullName.indexOf(' '))
    this.lastName = newFullName.substring(newFullName.indexOf(' '))
  },
  get age() {
    return new Date(new Date() - new Date(this.birthday)).getFullYear() - 1970
  },
  set age(newBirthday) {
    var fullYear = new Date().getFullYear()
    this.birthday = this.birthday.substring(0, 7).concat(fullYear - newBirthday)
  }
}
```

***

### Задача №8

Создать объект товара со следующими полями:
* name
* id
* price
* discount
Значения полей указать произвольное. Реализовать следующие геттеры и сеттеры:
* геттер discountPrice - возвращает цену товара, уменьшенную на количество процентов указанных в поле discount
* сеттер discountPrice - устанавливает значение поля price, увеличивая новое значение на количество процентов указанных в поле discount

```js
var product = {
  name: 'Phone',
  id: 1,
  price: 8999,
  discount: 5,
  get discountPrice() {
    return this.price - this.price * (this.discount / 100)
  },
  set discountPrice(newPrice) {
    this.price = newPrice + newPrice * (this.discount / 100)
  }
}
```

# Homework #6

### Задача №1

Создайте объект с тремя методами и двумя свойствами:
* firstOperand - хранит значение первого операнда
* secondOperand - хранит значение второго операнда
* setValues() запрашивает два значения при помощи prompt, сохраняет их значение, приведенное к числу, в firstOperand и  secondOperand.
* sumValues() возвращает сумму введенных свойств.
* multiplyValues() возвращает произведение введенных свойств.
Сделать проверку в методах sumValues и multiplyValues на наличие чисел, если хотя бы одно число не указано, выводить в консоль сообщение ‘Числа не заданы’.

```js
var numbers = {
  firstOperand: null,
  secondOperand: null,
  setValues: function() {
    this.firstOperand = +prompt("First number")
    this.secondOperand = +prompt("Second number")
  },
  sumValue: function() {
    return !(isNaN(this.firstOperand && this.secondOperand) || !this.firstOperand || !this.secondOperand) ? (this.firstOperand + this.secondOperand) : 'Числа не заданы'
  },
  multiplyValues: function() {
    return !(isNaN(this.firstOperand && this.secondOperand) || !this.firstOperand || !this.secondOperand) ? (this.firstOperand * this.secondOperand) : 'Числа не заданы'
  },
}

numbers.setValues()
console.log(numbers.sumValue())
console.log(numbers.multiplyValues())
```

***

### Задача №2

Написать функцию-конструктор calculatorMaker. При вызове как конструктор функция calculatorMaker в качестве аргументов должна принимать 2 числа (первый аргумент – начальное значение первого операнда, второй аргумент – начальное значение второго операнда, дефолтное значение которых равняется 0) и возвращать объект со следующими полями:
* firstOperand
* secondOperand
* history
и унаследованными методами:
* addition
* subtraction
* multiplication
* division
* showHistory
Поля firstOperand и secondOperand – переменные, в которых лежат значения, над которыми мы будем производить математические операции (могут быть только числом). Их начальное значение задается аргументами при вызове функции-конструктора.

Поле history – массив строк, в котором будут храниться все операции, произведенные этим экземпляром конструктора calculatorMaker в виде строк.
Пример массива history:

[‘5*8’, ‘5-8’, ‘5/8’]

Методы addition, subtraction, multiplication, division – сделать унаследованными и реализовать следующий функционал:
* Метод addition – производит сложение операндов
* Метод subtraction – производит вычитание операндов
* Метод multiplication – производит умножение операндов
* Метод division – производит деление операндов
* Все эти методы должны возвращать число (результат операции)
* Все эти методы должны добавлять сообщение о своём вызове в массив history
Метод showHistory – сделать унаследованным и реализовать следующую логику работы функции.
* Метод должен выводить в консоль сообщение ‘Список операций, выполненный этим экземпляром: ’ и далее выводит в консоль все сообщения из массива history, каждый элемент с новой строки.
* Если в массив history пуст, то выводить в консоль следующее сообщение: ‘Список операций – пуст’.

```js
function CalculatorMaker(firstOperand = 0, secondOperand = 0) {
  this.firstOperand = +firstOperand
  this.secondOperand = +secondOperand
  this.history = []
}

CalculatorMaker.prototype.addition = function() {
  this.history.push(`${this.firstOperand} + ${this.secondOperand}`)
  return this.firstOperand + this.secondOperand
}

CalculatorMaker.prototype.subtraction = function() {
  this.history.push(`${this.firstOperand} - ${this.secondOperand}`)
  return this.firstOperand - this.secondOperand
}

CalculatorMaker.prototype.multiplication = function() {
  this.history.push(`${this.firstOperand} * ${this.secondOperand}`)
  return this.firstOperand * this.secondOperand
}

CalculatorMaker.prototype.division  = function() {
  this.history.push(`${this.firstOperand} / ${this.secondOperand}`)
  return this.firstOperand / this.secondOperand
}

CalculatorMaker.prototype.showHistory = function() {
 !this.history.length ? console.log('Список операций – пуст') : console.log(`Список операций, выполненный этим экземпляром:\n${this.history.join('\n')}`)
}

var calc = new CalculatorMaker(6, 3)
console.log(calc.addition())
console.log(calc.subtraction())
console.log(calc.multiplication())
console.log(calc.division())
console.log(calc.history)
calc.showHistory()
```

# Homework #7

### Задача №1

С помощью конструктора создайте несколько объектов пользователей с полями name и age.
Пример объекта:
* {name: ‘Max’, age: 21}

Отдельно создайте функцию askQuestion, которая принимает в качестве аргументов две строки:
* Строка с приветствием
* Вопрос к пользователю

Функция должна возвращать конкатенированную строку, в которой в начале будет приветствие, после будет стоять имя пользователя, которому задается вопрос (использовать this), после чего будет идти вопрос который был задан пользователю. Вызвать этот метод с разными аргументами у нескольких пользователей, используя метод **apply()**.

```js
function User(name, age) {
  this.name = name
  this.age = age
}

function askQuestion(stringHello, stringQuestion) {
  return `${stringHello}, ${this.name}. ${stringQuestion}`
}

const userMax = new User('Макс', 21)
const userAlex = new User('Алекс', 24)
const userDasha = new User('Даша', 27)

console.log(askQuestion.apply(userMax, ['Приветики', 'И нафига ты это делаешь в 12 ночи?']))
console.log(askQuestion.apply(userAlex, ['Привет', 'Спать вообще не хочешь?']))
console.log(askQuestion.apply(userDasha, ['Привет', 'И ты туда же?)']))
```

***

### Задача №2

Создайте три объекта товаров.
Пример объектов:
* **{name: ‘Samsung Galaxy S20’, price: 800}**
* **{name: ‘Xiaomi 11’, price: 600}**
* **{name: ‘iPhone 12’, price: 1000}**

Напишите функцию getDiscountAmount, которая будет принимать единственным параметром число (процент скидки) и на основании свойства price (использовать this) будет возвращать сумму скидки для конкретного товара, предварительно убедившись что price отличен от нуля. При помощи метода bind создать функции расчета скидки для каждого объекта.

```js
const samsung = {
  name: 'Samsung Galaxy S20',
  price: 800
}

const xiaomi = {
  name: 'Xiaomi 11',
  price: 600
}

const iphone = {
  name: 'Iphone 12',
  price: 200
}

function getDiscountAmount(discount) {
  return this.price > 0 ? this.price / 100 * discount : 'Товар отсутствует'
}

const saleSamsung = getDiscountAmount.bind(samsung)
console.log('Скидка: ', saleSamsung(10))

const saleXiaomi = getDiscountAmount.bind(xiaomi)
console.log('Скидка: ', saleXiaomi(15))

const saleIphone = getDiscountAmount.bind(iphone)
console.log('Скидка: ', saleIphone(50))
```

***

### Задача №3

Создайте массив figures, который будет состоять из объектов двух видов фигур: прямоугольников и кругов (10 элементов).
Примеры объектов:
* Круг: {figureType: ‘circle’, radius: 5 }
* Прямоугольник: {figureType: ‘rectangle’, weight: 100, height: 50}

Написать функцию, которая будет проверять поле figureType, высчитывать площадь фигуры (реализовать с использованием this), для кругов округлить получившийся результат. Написать цикл для массива figures и выводить в консоль следующую строку:
‘Фигура №{номер фигуры} имеет площадь {результат вычислений}’
В цикле для каждого объекта вызвать ранее написанную функцию используя метод **call**

```js
const figures = [
    {
      figureType: 'circle', 
      radius: 5
    },
    {
      figureType: 'circle', 
      radius: 20
    },
    {
      figureType: 'circle', 
      radius: 25
    },
    {
      figureType: 'circle', 
      radius: 30
    },
    {
      figureType: 'circle', 
      radius: 40
    },
    {
      figureType: 'rectangle',
      weight: 100,
      height: 50
    },
    {
      figureType: 'rectangle',
      weight: 150,
      height: 100
    },
    {
      figureType: 'rectangle',
      weight: 250,
      height: 150
    },
    {
      figureType: 'rectangle',
      weight: 350,
      height: 200
    },
    {
      figureType: 'rectangle',
      weight: 450,
      height: 300
    },
]

function checkFigure() {
  return this.figureType === 'circle' ? Math.round(Math.pow(this.radius, 2) * Math.PI) : this.weight * this.height
}

for(let i = 0; i < figures.length; i++) {
  console.log(`Фигура №${i} имеет площадь ${(checkFigure.call(figures[i])).toFixed()}`)
} 
```

***

### Задача №4

Создайте конструктор ProductCreator. Добавьте ему свойство instanceCounter и метод showProductCreatorInstanceCounter. 
Метод showProductCreatorInstanceCounter должен наследоваться всеми потомками конструктора ProductCreator и возвращать число созданных потомков этим конструктором. 
При создании нового экземпляра конструктором ProductCreator счётчик instanceCounter должен увеличиваться на 1 и это значение должно быть записано в поле id создаваемого объекта.


```js
function ProductCreator() {
  ProductCreator.prototype.instanceCounter = 0
  ProductCreator.prototype.showProductCreatorInstanceCounter = function() {
    ProductCreator.prototype.instanceCounter++
    if (this instanceof ProductCreator) {
      this.id = ProductCreator.prototype.instanceCounter
      return `ID экземпляра: ${this.id}`
    }
  }
}
```

# Homework #8

### Задача №1

Напишите функцию, которая последовательно выводит в консоль числа от 1 до 20, с интервалом между числами 1000мс. 
То есть, весь вывод должен занимать 2000мс, в течение которых каждые 1000мс в консоли появляется очередное число.
* Реализовать с помощью setInterval
* Реализовать с помощью setTimeout вместо setInterval

**setTimeout**
```js
(function() {
  let i = 1

  setTimeout(function run() {
    console.log(i)
    if (i < 20 ) {
      setTimeout(run, 1000)
      i++
    }
  }, 1000)
})()
```

**setInterval**

```js
(function interval() {
  let i = 1

  setInterval(function run() {
    if(i <= 20) console.log(i)
    i++
  }, 1000)
})()
```

***

### Задача №2

Сделать светофор, который "зажигает" красный, желтый, зеленый свет попеременно.
Написать функцию, которая в качестве аргументов принимает четыре числа.
* Первое число - сколько секунд будет ‘гореть’ красный.
* Второе число - сколько секунд будет ‘гореть’ желтый.
* Третье число - сколько секунд будет ‘гореть’ зеленый.
* Четвёртое число - на сколько будет включен светофор. 

Функция должна выводить в консоль сообщение ‘Светофор включен’ и запускать таймер для выключения светофора через заданное в качестве четвёртого параметра количество секунд таймер. После выключения светофора, вывести в консоль сообщение ‘Светофор выключен’. В течении времени работы светофора в консоль должны выводится строки ‘зелёный’, ‘жёлтый’, ‘красный’ по очереди с интервалами между цветами переданными в качестве параметров функции для каждого из цветов. (т.е. если зелёному был задан интервал 3 сек., то жёлтый должен ‘загореться’, через 3 сек. после зелёного)

```js
function lights(green, yellow, red, time) {
  console.log('Светофор включен')

  setTimeout(function greenLight() {
    console.log('Зеленый')
    document.querySelector('body').style.background = 'green'
  }, green * 1000)

  setTimeout(function yellowLight() {
    console.log('Жёлтый')
    document.querySelector('body').style.background = 'yellow'
  }, yellow * 1000)

  setTimeout(function redLight() {
    console.log('Красный')
    document.querySelector('body').style.background = 'red'
  }, red * 1000)

  setTimeout(function lights() {
    console.log('Светофор выключен')
    document.querySelector('body').style.background = '#fff'
  }, time * 1000)
}

lights(1, 3, 5, 7)
```

***

### Задача №3

Напишите функцию, которая через prompt, предлагает пользователю сделать ставку (ввести сумму денег, типа ставка на спорт), после ввода числа в prompt, выведите в консоль сообщение ‘Ваша ставка принята’. Сгенерируйте случайное число в диапазоне от -5 до 5. Через 3 секунды выведите сообщение в консоль информацию о том, что он “выиграл” или “проиграл” с такой логикой: если случайное число отрицательное или равно 0 - то он "не угадал" со своей ставкой, выведите в консоль сообщение ‘Вы проиграли. Ваши деньги сгорели.’ Если число положительное, то выведите в консоль сообщение ‘Вы выиграли. Ваш выигрыш составляет { сумма выигрыша }’. Для расчёта суммы выигрыша нужно умножить сумму ставки на случайно сгенерированное число в диапазоне от -5 до 5.

```js

```
