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
