# Homework #9

### Задача №1

Напишите функцию, которая единственным аргументом будет принимать массив чисел. Функция должна возвращать сумму квадратных корней для всех четных чисел массива. Для реализации функционала функции используйте методы filter(), map() или reduce().

```js
function getNumbers(array) {
  return array.filter(element => !(element % 2))
    .reduce((accumulator, element) => accumulator + Math.sqrt(element), 0)
}

getNumbers([9, 27, 39, 49, 64, 81])
```

***

### Задача №2

Напишите функцию, которая единственным аргументом будет принимать массив чисел. Функция должна возвращать число элементов, которое нужно сложить чтобы в сумме получилось больше 20-ти. Если сумма всех чисел массива меньше 20, вывести сообщение об этом в консоль. Для реализации функционала функции используйте метод reduce().

```js
function numbers(array) {
  let number = 0
  const sum = array.reduce(function(accumulator, value) {
    if (accumulator <= 20) {
      number++
      accumulator = accumulator + value
    }
    return accumulator
  }, 0)
  return sum > 20 ? `Сумма ${number} элементов больше 20` : `Сумма ${number} элементов меньше 20`
}
numbers([1, 4, 13])
```

***

### Задача №3

Напишите функцию, которая единственным аргументом будет принимать массив строк. Функция должна возвращать массив со строками, длина которых больше 5-ти символов. Для реализации функционала функции 
* используйте метод filter()
* используйте метод reduce().

```js
const words = ['one', 'two', 'four', 'seven', 'eleven', 'twelve']

// filter
function getElements(array) {
  return array.filter(element => element.length > 5)
}
getElements(words)

// reduce

function reduceWords(array) {
  let words = array.reduce((accum, item) => {
    if (item.length > 5) {
      accum.push(item)
    }
    return accum
  }, [])
  return words
}
reduceWords(words)
```
***

### Задача №4

Напишите функцию, которая единственным аргументом будет принимать массив чисел, одним элементом которого должен быть 0. Функция должна возвращать сумму первых N элементов до первого нуля. Если в массиве нет элементов 0, то возвращать строку ‘Переданный массив не содержит нулей’. Для реализации функционала функции используйте метод forEach() или reduce().

```js
const nums = [1, 2, 4, 56, 0, 21, 22]

function checkZerro(numbers) {
  const zerro = numbers.find(item => item === 0 )
  if (zerro !== 0) {
      return'Массив не содержит нулей'
  }
  const zeroIndex = numbers.indexOf(0)
  const sum = numbers.slice(0, zeroIndex).reduce((accum, value) => accum + value)
  return sum
}
checkZerro(nums)

//forEach

function checkZerro(numbers) {
  const zerro = numbers.find(item => item === 0 )
  if (zerro !== 0) {
      return'Массив не содержит нулей'
  }
  let sum = 0
  numbers.slice(0, numbers.indexOf(0)).forEach(item => sum += item)
  return sum
}
checkZerro(nums)
```
