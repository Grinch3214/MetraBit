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

***

### Задача №5

Написать четыре функции, каждая из которых будут в качестве аргумента принимать массив studentsMarks и возвращать указанные ниже значения:
* Массив с именами студентов, записанными заглавными буквами. Для реализации функционала функции используйте метод map().
* Массив с именами студентов, набравших более 50 баллов и имеющих id больше 120. Для реализации функционала функции используйте метод filter()
* Общую сумму баллов студентов. Для реализации функционала функции используйте метод reduce().
* Массив с именами студентов, у которых баллы больше 50, после начисления поощрения в 15 баллов. Для реализации функционала функции используйте метод reduce().

Пример массива:
```js
const studentsMarks  = [
  {name: 'John', id: 123, mark : 98 },
  {name: 'Baba', id: 101, mark : 23 },
  {name: 'yaga', id: 200, mark : 45 },
  {name: 'Wick', id: 115, mark : 75 }
]
```
---
```js
function nameStudents(studentsMarks) {
  return studentsMarks.map(item => item.name.toUpperCase())
}
nameStudents(studentsMarks)


function bestStudents(studentsMarks) {
  const students = studentsMarks.filter(item => {
    if(item.mark > 50 && item.id > 120) {
      return item.name
    }
  })

  const name = students.reduce((accum, item) => {
    accum.push(item.name)
    return accum
  }, [])
  return name
}
bestStudents(studentsMarks)


function sumMarks(studentsMarks) {
  return studentsMarks.reduce((accum, item) => accum += item.mark, 0)
}
sumMarks(studentsMarks)


function bonusForStudents(studentsMarks) {
  let students = studentsMarks.reduce((accum, item) => {
    if((item.mark + 15) > 50) {
      accum.push(item.name)
    }
    return accum
  }, [])
  return students
}

bonusForStudents(studentsMarks)
```

***

### Задача №6

Напишите функцию, которая единственным аргументом будет принимать массив чисел. Функция должна возвращать массив его сумм каждого элемента и всех стоящих перед ним чисел. Для реализации функционала функции используйте метод .forEach().

```js
const numbers = [ 8, 4, 9, 7 ]

function sumEachElenet(array) {
  let num = 0
  const numbersNew = []
  array.forEach(element => numbersNew.push(num += element))
  return numbersNew
}
sumEachElenet(numbers)
```

***

### Задача №7

Напишите функцию, которая принимает массив в качестве единственного аргумента и возвращает полученный массив без повторяющихся значений. 
Для реализации функционала функции используйте методы .filter() и .indexOf().

```js
const array = [10, 11, 12, 11, 13, 'html', 'css', 'js', 'css', 'js', 'vue']

function deleteDublicate(arr) {
  return arr.filter((currValue, index) => {
      return arr.indexOf(currValue) === index
    })
}
deleteDublicate(array)
```

***

### Задача №8

Напишите функцию, которая принимает массив с вложенными массивами и возвращает одномерный (плоский) массив.

```js
const testArray = [1, 2, [4, [11, 10]], 6, [7, 0], 9]

function flatArray(arr) {
  return arr.flat(Infinity)
}
flatArray(testArray)
```

***

### Задача №9

Напишите функцию, которая в качестве аргументов принимает массив элементов и число. Функция должна возвращать массив с массивами из  элементов переданного массива. Длина внутренних массивов должна быть равной числу, переданному в качестве аргумента. Если длина исходного массива не кратна переданному числу, то оставшиеся элементы также поместить в массив.

```js
const arr = ['html', 'css', 'js', 'vue', 'react', 'angular']

function splitArray(array, number) {
  const splArray = []
  array.forEach((value, index) => {
    if (index % number === 0) {
      splArray.push([value])
    } else {
      splArray[splArray.length - 1].push(value)
    }
  })
  return splArray
}
splitArray(arr, 4)
```

***

### Задача №10

Напишите функцию, которая в качестве единственного аргумента принимает массив объектов с информацией о работниках.
Пример массива:
```js
[
  {
    name: 'Sasha',
    age: 45,
    salary: 1900,
  },
  {
    name: 'Max',
    age: 21,
    salary: 1500,
  },
  {
    name: 'Nikita',
    age: 29,
    salary: 800,
  },
  {
    name: 'Sergey',
    age: 32,    
    salary: 2300,
  }
]
```
Функция должна отсортировать данный массив по возрастанию зарплаты и вернуть получившийся массив. 
Для реализации функционала функции используйте метод .sort().

