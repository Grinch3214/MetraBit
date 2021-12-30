# Homework #15

### Задача №1

Создайте объект phone со следующими полями:
* Name
* Price
* Discount
* Quantity
* Weight

Значения укачать произвольные. Для нескольких полей задайте значение null.

Напишите функцию, которая в качестве единственного аргумента принимает объект. Для того, чтобы не изменить значения полученного в аргументах объекта, внутри функции, создайте переменную для копирования объекта и создайте копию полученного в аргументах объекта с использованием метода Object.assign()

При помощи метода Object.entries() создайте массив с элементами типа: [‘ключ’, ‘значение’]. Отфильтруйте данный массив так, чтобы в нём остались только элементы, у которых ‘значение’ нe равно null. Из отфильтрованного массива создайте объект, который будет состоять только из полей, значение которых не равно null. Функция должна возвращать получившийся объект.

Вызовите функцию с объектом phone для демонстрации правильной работы функции.
Реализуйте копирование полученного в аргументах объекта в переменную используя деструктурирующее присваивание.

```js
const phone = {
  name: 'Xiaomi M1',
  price: 3100,
  discount: '10%',
  quantity: null,
  weight: null
}

function itemForObjectPhone(phone) {
  let objPhone = Object.assign({}, phone)
  let arrKey = Object.entries(objPhone)
  let array = arrKey.filter(elem => elem[1] !== null)
  return Object.fromEntries(array)
}

itemForObjectPhone(phone)
```

*деструктурирующее присваивание*

```js
function itemForObjectPhone(phone) {
  let { ...objPhone } = phone
  let arrKey = Object.entries(objPhone)
  let array = arrKey.filter(elem => elem[1] !== null)
  return Object.fromEntries(array)
}

itemForObjectPhone(phone)
```

***

### Задача №2

Создайте ещё один объект, имя которого будет laptop. Объект должен содержать следующие поля:
* Name
* Price
* Discount
* Width
* Height
* Diagonal

Значения указать произвольные.

Напишите функцию, которая в качестве аргументов принимает два объекта. Функция должна найти не совпадающие имена полей двух объектов. Если имена полей первого объекта одинаковы с именами полей второго объекта, вывести true.  Если есть одно поле или более, которые встречается только в одном из двух объектов, вывести массив имен несовпадающих полей.
* Для нахождения массива ключей использовать Object.keys.

Вызовите функцию с объектами phone и laptop для демонстрации правильной работы функции.

```js
const phone = {
  name: 'Xiaomi M1',
  price: 3100,
  discount: '10%',
  quantity: null,
  weight: null
}

const laptop = {
  name: 'HP Pavilion G6',
  price: 4100,
  discount: '8%',
  width: 40,
  height: 33,
  diagonal: 15.6
}

function objectСomparison(prodA, prodB) {
  let prodAKeys = Object.keys(prodA)
  let prodBKeys = Object.keys(prodB)
  let comparison = []

  prodAKeys.forEach((currentValue) => {
    if(!(prodBKeys.includes(currentValue))) {
      comparison.push(currentValue)
    }
  })
  prodBKeys.forEach((currentValue) => {
    if(!(prodAKeys.includes(currentValue))) {
      comparison.push(currentValue)
    }
  })
  return comparison.length ? comparison : true
}

objectСomparison(laptop, phone)
```

***

### Задача №3


Напишите функцию, которая в качестве единственного аргумента принимает объект. При помощи метода Object.values() получите массив значений всех полей объекта.
Произведите проверку полученного массива, если получившийся массив пуст, то функция должна вернуть строку ‘Object is empty’. В ином случаи создайте переменные firstValue, secondValue и restValues и с использованием деструктирующего присваивания установите им следующие значения:
* firstValue – первый элемент массива
* secondValue – второй элемент массива
* restValues – оставшиеся элементы массива.

Присваивание реализовать одной строкой. Переменной restValues установить дефолтное значение, равное пустому массиву.
Из созданных переменных (firstValue, secondValue и restValues) создайте объект типа:

```
{
  firstValue: значение переменной firstValue,
  secondValue: значение переменной secondValue,
  restValues: значение переменной restValues
}
```


Функция должна возвращать созданный объект с 3-мя полями.
Вызовите функцию с объектами laptop для демонстрации правильной работы функции.

```js
const laptop = {
  name: 'HP Pavilion G6',
  price: 4100,
  discount: '8%',
  width: 40,
  height: 33,
  diagonal: 15.6
}

function getObject(product) {
  let array = Object.values(product)
  let [firstValue, secondValue = 'this value is empty', ...restValues] = array
  let updatedProduct = {
    firstValue: firstValue,
    secondValue: secondValue,
    restValues: restValues
  }

  return array.length ? updatedProduct : 'Object is empty'
}
getObject(laptop)
```

