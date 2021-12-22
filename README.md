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
  const array = []
  let objPhone = Object.assign({}, phone)
  let arrKey = Object.entries(objPhone)
  for (let i = 0; i < arrKey.length; i++) {
    if(arrKey[i][1] !== null) {
      array.push(arrKey[i])
    }   
  }
  return Object.fromEntries(array)
}

itemForObjectPhone(phone)
```

*деструктурирующее присваивание*

```js
function itemForObjectPhone(phone) {
  const array = [];
  let phone = { ...objPhone }
  let arrKey = Object.entries(objPhone)
  for (let i = 0; i < arrKey.length; i++) {
    if(arrKey[i][1] !== null) {
      array.push(arrKey[i])
    }   
  }
  return Object.fromEntries(array)
}

itemForObjectPhone(phone)
```
