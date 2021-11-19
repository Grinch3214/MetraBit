# Homework #5

### Задача №1

Создайте IIFE, которое получает пароль в аргументе и возвращает внутреннюю функцию, которая в качестве аргумента принимает введенную строку и возвращает булево значение true, если введенная строка совпадает с паролем и faulse – если не совпадает. Для сохранения результата IIFE создайте переменную checkPassword.

```js
var password = 'qwerty'

var checkPassword = ((function(pass) {
    return function(passCheck) {
       return passCheck === pass
    }
})(password))
console.log(checkPassword(prompt('Введите пароль')))
```

***

### Задача №2

Создайте IIFE, которое получает число n (начальное значение) в качестве аргумента родительской функции и возвращает функцию, которая получает число, прибавляет его к n, которое находится в замыкании, и возвращает результат. Для сохранения результата IIFE создайте переменную addeter.

```js
var addeter = (function(n) {
  return function(t) {
    return t + n;
  };
})(+prompt('Первое число:'));
console.log(addeter(+prompt('Второе число:')))
```

***

### Задача №3

Создайте IIFE, которое вернёт функцию, у которой в замыкании будет переменная counter со значением 10. Сделайте так, чтобы каждый вызов возвращённой функции уменьшал это число на 1 и выводил на экран уменьшенное число. Добавьте функционал, чтобы отсчет доходил до 0, а затем каждый последующий вызов функции выводил на экран сообщение о том, что отсчет окончен.

```js
var result = (function(counter) {
  return function() {
    if(counter <= 0) {
        return 'Отсчёт окончен'
    } else {
      return --counter
    }
  }
})(10)
result()
```

***

### Задача №4

Напишите функцию, которая в качестве единственного аргумента принимает массив чисел и возвращает сумму чисел этого массива.
* Реализовать с помощью рекурсии

```js
var sum = (array) => (!array.length) ? 0 : array[0] + sum(array.slice(1))
sum([1, 5, 10])
```

***

### Задача №5

Напишите функцию, которая в качестве аргументов принимает два числа. Первое число – начало диапазона. Второе число – конец диапазона. Вернуть строку всех целых чисел из этого диапазона через запятую.
* Реализовать с помощью рекурсии

```js
function getRange(first, last) {
    if (first > last) {
        return 'Первое число должно быть меньше второго!'
    } else if(first === last) {
        return last
    } else {
        return ([first].concat(getRange(++first, last))).join(',')
    } 
}
getRange(1, 10)
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
