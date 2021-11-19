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
        var numberCenter = arrayNumber.length / 2

        var arrMerge = arrayNumber.slice()
        arrMerge.splice(numberCenter, 0, arrayString)
        arrMerge = arrMerge.flat()
        var test = arrMerge.slice(0, arrMerge.length / 2)
//         console.log(test)
        return test
    } else { 
        console.log('Массивы имеют разную длину') 
    } 
} 
var num = [73, 4, 11, 234, 58, 134] 
var str = ['js', 'css', 'jq', 'html', 'vue', 'bootstrap'] 
giveMeArray(num, str)
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
var phrase = 'The quick brown fox jumps over the lazy dog.'

function cutString(phrase, str) {
  var phraseWord = phrase.indexOf(str)
  var lengthStr = str.length
  return phrase.substr(0, phraseWord) + phrase.substr(phraseWord + lengthStr + 1)
}

cutString(phrase, 'lazy')


var phrase = 'The quick brown fox jumps over the lazy dog.'

function cutString(phrase, str) {
  var phraseWord = phrase.indexOf(str)
  var lengthStr = str.length
  return phrase.substring(0, phraseWord) + phrase.substring(phraseWord + lengthStr + 1)
}

cutString(phrase, 'lazy')


var phrase = 'The quick brown fox jumps over the lazy dog.';

function cutString(phrase, str) {
  var phraseWord = phrase.indexOf(str)
  var lengthStr = str.length
  return phrase.slice(0, phraseWord) + phrase.slice(phraseWord + lengthStr + 1)
}

cutString(phrase, 'lazy')
```
