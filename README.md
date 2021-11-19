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
