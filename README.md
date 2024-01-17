# JavaScript Basics
Коротка шпаргалка по минулих темах.

## Змінні та константи

```js
const firstName = 'John';
let age = 39;

console.log(firstName, age);

age = 40;
console.log(firstName, age);
```

## Коментарі

```js
// age - можна змінювати
let age = 39;

// firstName - не можна змінити
const firstName = 'John';

/* Це багаторядковий коментар
Це просто текст, що пояснює програму
Він не виконується комп'ютером */
```

## Операції з числами
```js
const addition = 10 + 5; // 15
const subtraction = 10 - 5; // 5
const multiplication = 10 * 5; // 50
const division = 10 / 5; // 2
const exponentiation = 10 ** 5; // 100000 - 10 у 5 степені
const remainder = 16 % 7; // 2 - остача від ділення 16 на 7

const x = 357;
const lastDigit = x % 10; // 7 - остання цифра
const lastTwoDigits = x % 100; // 57 - дві останні
```

## Зміна порядку дій за допомогою ()
```js
const result1 = 5 + 2 * 10; // 25
const result2 = (5 + 2) * 10; // 70
```
