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

## Рядки

```js
const surname = 'Smith';
const name = 'John';

const firstCharacter = name[0]; // 'J' - перший символ

console.log(name.length); // 5 - кількість символів

const lastIndex = name.length - 1; // 4 - індекс останнього символа
const lastCharacter = name[lastIndex]; // 'n' - останній символ

const initials = name[0] + surname[0]; // 'JS' - конкатенація
const fullName = `Mr. ${name} ${surname}`; // 'Mr. John Smith' - інтерполяція
```

## Булев тип. Оператори порівняння.

```js
const a = 2;

console.log(
  a === 2, // true - `a` дорівнює 2
  a !== 2, // false - `a` не дорівнює 2
  a > 2, // false
  a < 2, // false
  a >= 2, // true
  a <= 2, // true
);
```

## Логічні оператори !, || та &&

```js
const age = 25;
let isChild = age < 18; // false
let isAdult = !isChild; // true - протилежне значення

let cash = 50;
let creditCard = 20;
let price = 40;

let hasEnoughCash = cash >= price;
let hasEnoughCredit = creditCard >= price;

let canPay = hasEnoughCash || hasEnoughCredit; // хоча б одна з умов
let canBuy = isAdult && canPay; // обидві умови
```

## Функції

```js
function calculateArea(length, width = 1.5) {
  // тут можуть бути інші команди

  return length * width;
}

let area1 = calculateArea(5, 7); // 35
let totalArea = 10 * calculateArea(3 * 4); // 10 * 12

// Якщо другий аргумент не передано
// то для `width` береться значення 1.5 встановлене за замовчуванням
let area2 = calculateArea(10); // 15 = 10 * 1.5
```

## Умовні оператори
```js
let age = 25;

if (age >= 18) {
  // виконується якщо умова вірна
  console.log('Adult');
}

if (age >= 18) {
  console.log('Hello!');
} else {
  // виконується якщо умова НЕ вірна
  console.log('Hi!');
}

// виконується лише перший блок умова якого вірна
// або блок `else`, якщо жодна з умов НЕ вірна
if (age >= 18) {
  console.log('Hello!');
} else if (age > 7) {
  console.log('Hi!');
} else if (age > 3) {
  console.log('Hi, kid!');
} else {
  console.log('Hi, toddler!');
}

let isPresent = true;

if (age >= 18 && isPresent) {
  // виконується якщо обидві умови вірні
  console.log('Hello!');
}
```

## Функція з умовними операторами

```js
function getGreeting(age) {
  // функція завершується, як тільки спрацює будь-який `return`
  // і не виконуватиме команди що стоять після
  if (age >= 18) {
    return 'Hello!';
  }

  if (age > 7) {
    return 'Hi!';
  }

  if (age > 3) {
    return 'Hi, kid!';
  }

  return 'Hi, toddler!';
}

let greeting = getGreeting(6);

console.log(greeting); // у консолі зʼявиться `Hi, kid!`
```

## Масиви

```js
let cities = ['Kyiv', 'London', 'Paris'];

console.log(cities.length); // 3
let firstCity = cities[0]; // Kyiv
let lastCity = cities[cities.length - 1]; // Paris

// заміняємо другий елемент масиву на інший
cities[1] = 'New York';
console.log(cities); // ['Kyiv', 'New York', 'Paris']

// Додаємо елементи в кінець масиву
cities.push('Amsterdam');
console.log(cities); // ['Kyiv', 'New York', 'Paris', 'Amsterdam']

cities.push('Roma', 'Tokyo');
console.log(cities); // ['Kyiv', 'New York', 'Paris', 'Amsterdam', 'Roma', 'Tokyo']
```

## Цикли

```js
// age - від 1 до 5
for (let age = 1; age <= 5; age += 1) { // age++
  console.log(`I am ${age}`);
}

// у зворотньому напрямку - від 3 до 1
for (let i = 3; i > 0; i--) {
  console.log(i);
}
```

## Функція з циклом

```js
function sumFromTo(min, max, step) {
  let sum = 0;

  // від `min` до `max` з кроком `step`
  for (let n = min; n <= max; n += step) {
    sum += n; 
  }

  return sum;
}

console.log(
  sumFromTo(1, 5, 2) // 9
);
```

```js
function factorial(N) {
  let result = 1; // починаємо з 1

  for (let n = 1; n <= N; n++) {
    result *= n; // помножуємо добуток попередніх чисел на поточне число n
  }

  return result; // повертаємо обчислений факторіал
}

const result = factorial(5);

console.log(result); // виведе 120
```

## Перебір рядків

```js
const title = 'String';

// прямий порядок
for (let i = 0; i < title.length; i++) {
  console.log(title[i]);
}

// зворотній
for (let i = title.length - 1; i >= 0; i--) {
  console.log(title[i]);
}

// без індексу
for (let char of title) {
  console.log(char);
}
```

### Обернення рядка

```js
let reversed = '';

for (let i = title.length - 1; i >= 0; i--) {
  reversed += title[i];
}

// for (let char of title) {
//   // додаємо символ перед тими, що були додані раніше
//   reversed = char + reversed;
// }

console.log(reversed); // 'gnirtS'
```

### Функція для заміни символів

```js
function replaceAll(input, char, replacement){
  let result = '';

  for (let ch of input) {
    if (ch === char){
      result += replacement;
    } else {
      result += ch;
    }
  }
 
  return result;
}

let title = 'Working with Strings';

console.log(
  replaceAll(title, ' ', '-')
); 
```

## Методи рядків

```js
let title = 'Working with Strings';

// Зміна регістру
console.log(
  title.toLowerCase(), // 'working with strings'
  title.toUpperCase() // 'WORKING WITH STRINGS'
  title, // 'Working with Strings'
);

function isLetter(ch) {
  return ch.toLowerCase() !== ch.toUpperCase();
}

// Заміна символів
console.log(
  title.replaceAll(' ', '-'), // 'working-with-strings'
  title.replaceAll('with', '**'), // 'working–**-strings'
);

// перевірка входження
console.log(
  title.includes(' '), // true
  title.includes('with'), // true
  title.includes('With'), // false
);

console.log(
  title.indexOf(' '), // 7
  title.indexOf('with'), // 8
  title.indexOf('Strings'), // 13
);
```

## Перебір масивів

```js
const prices = [10, 20, 30, 40, 50];
const totalPrice = getSum(prices);

console.log(totalPrice);

function getSum(values) {
  let sum = 0;

  for (let i = 0; i < values.length; i++) {
    sum += values[i];
  }

  // for (const value of values) {
  //   sum += value;
  // }

  return sum;
}

function getAverage(values) {
  if (values.length === 0) {
    return 0;
  }

  let sum = 0;

  for (const value of values) {
    sum += value;
  }

  return sum / values.length;
}

function getMin(values) {
  if (values.length === 0) {
    return 0;
  }

  let min = values[0];

  for (const value of values) {
    if (value < min) {
      min = value;
    } 
  }

  return min;
}
```

### Перетворення рядка у масив

```js
const text = 'one two three four five';

concole.log(text.split(' ')); // ['one', 'two', 'three', 'four', 'five']
concole.log(text.split(' а')); // ['one two three', 'our', 'ive']

const fruits = ['apple', 'banana', 'cherry', 'date'];
const joinedString = fruits.join(', '); // роздільник — кома та пробіл

console.log(joinedString); // у консоль виведеться рядок 'apple, banana, cherry, date'
```

### Фільтрування

```js
function getShortWords(words, maxLength) {
  let results = [];
  
  for (const word of words) {
    if (word.length <= maxLength) {
      results.push(word);
    }
  }
  
  return results;
}

const text = 'one two three four five';
const words = text.split(' ');

console.log(
  getShortWords(words, 4)
);
```

### Перетворення масива

```js
function getWordsLengths(words) {
  const result = [];
  
  for (const word of words) {
    result.push(word.length);
  }
  
  return result;
}

// отримаємо [3, 3, 5, 4, 4]
getWordsLengths(['one', 'two', 'three', 'four', 'five']);
```

### Пошук у масиві

```js
const words = ['apple', 'banana', 'cherry', 'date'];

console.log(words.includes('apple')); // true
console.log(words.includes('potato')); // false

console.log(words.indexOf('apple'));// 0
console.log(words.indexOf('cherry'));// 2
console.log(words.includes('potato')); // -1
```
