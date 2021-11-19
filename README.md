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
