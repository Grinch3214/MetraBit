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
var counter = 0
function ProductCreator() {
  this.instanceCounter = ++counter
  this.id = this.instanceCounter
  this.showProductCreatorInstanceCounter = function () {
    return counter
}
  }

var productA = new ProductCreator()
var productB = new ProductCreator()
var productC = new ProductCreator()
var productD = new ProductCreator()
var productE = new ProductCreator()

console.log(productA)
console.log(productB)
console.log(productC)
console.log(productD)
console.log(productE)
```
