# Массив

- __.concat()__ - Метод применяется к массиву и создаёт из него новый. Все аргументы, переданные методу, будут добавлены в новый массив в том же порядке:
```javascript
const toDoList = ['Посадить дерево', 'Построить дом'];
const toDoListUpdated = toDoList.concat('Вырастить сына');

console.log(toDoListUpdated);

// ["Посадить дерево", "Построить дом", "Вырастить сына"]
```
Как аргумент можно передать и другой массив — его элементы будут скопированы и добавлены в новый массив:
```javascript
const moscowAttractions = ['Кремль', 'Третьяковская галерея'];
const spbAttractions = ['Эрмитаж', 'Мариинский театр'];
const volgogradAttractions = ['Мамаев Курган', 'Родина-мать'];

const russiaAttractions = moscowAttractions.concat(spbAttractions, volgogradAttractions);

// получим новый массив со значениями всех исходных массивов

console.log(russiaAttractions);

/*
  [
    "Кремль",
    "Третьяковская галерея",
    "Эрмитаж",
    "Мариинский театр",
    "Мамаев Курган",
    "Родина-мать"
  ]
*/
```
ссылки: [Яндекс Практикум](https://practicum.yandex.ru/learn/frontend-developer/courses/6099140a-985c-4b15-a7b9-a6a0e18c93eb/sprints/145379/topics/981c9561-2b1c-4be4-a2a3-2d661757f07f/lessons/b3a9fc16-a87b-463d-91ed-c23bd4425a8f/), [learn.javascript](https://learn.javascript.ru/array-methods), [MDN](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)

- __.join()__ - Метод создаёт строку из элементов массива, разделённых запятой:
```javascript
const bremenMusicians = ['Кот', 'Пёс', 'Трубадур', 'Осёл', 'Петух'];

console.log(bremenMusicians.join());

// "Кот,Пёс,Трубадур,Осёл,Петух"

console.log(`Представляем музыкантов: ${bremenMusicians.join(', ')}`);
// "Представляем музыкантов: Кот, Пёс, Трубадур, Осёл, Петух"

// при этом с исходным массивом ничего не произошло:
console.log(bremenMusicians);
// ["Кот", "Пёс", "Трубадур", "Осёл", "Петух"]
```
Если не передать join аргумент, элементы в строке будут перечислены через запятую. Но мы можем задать любой нужный разделитель:
```javascript
const bremenMusicians = ['Кот', 'Пёс', 'Трубадур', 'Осёл', 'Петух'];

console.log(bremenMusicians.join(' | '));

// "Кот | Пёс | Трубадур | Осёл | Петух"
```
ссылки: [Яндекс Практикум](https://practicum.yandex.ru/learn/frontend-developer/courses/6099140a-985c-4b15-a7b9-a6a0e18c93eb/sprints/145379/topics/981c9561-2b1c-4be4-a2a3-2d661757f07f/lessons/b3a9fc16-a87b-463d-91ed-c23bd4425a8f/), [learn.javascript](https://learn.javascript.ru/array-methods), [MDN](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Array/join)

- __.push()__ - Метод добавляет переданные ему аргументы в конец массива:
```javascript
const emeraldCityHeroes = ['Лев', 'Дровосек', 'Страшила'];
emeraldCityHeroes.push('Элли', 'Тотошка');

console.log(emeraldCityHeroes);

// ["Лев", "Дровосек", "Страшила", "Элли", "Тотошка"]
```

- __pop__ - Метод удаляет последний элемент массива. Он не принимает аргументы — только возвращает значение удалённого элемента. Если массив пуст, pop вернёт undefined:
```javascript
const insects = ['Бабочка', 'Мотылёк', 'Божья коровка', 'Комар'];

console.log(insects.pop()); // "Комар"
console.log(insects); // ["Бабочка", "Мотылёк", "Божья коровка"]
```

- __.shift()__ - Метод удаляет первый элемент массива. Исходный массив при этом изменится:
```javascript
const italyCities = ['Помпеи', 'Рим', 'Неаполь'];

const volcanoEruption = italyCities.shift();

// метод shift() возвращает удалённый элемент
console.log(volcanoEruption); // "Помпеи"

// массив остался без первого элемента
console.log(italyCities); // ["Рим", "Неаполь"]

// если массив изначально пустой, вернётся undefined:
const emptyArr = [];

console.log(emptyArr.shift()); // undefined
```

- __.unshift()__ - Метод добавляет элементы в начало массива. Их передают через запятую:
```javascript
const queue = ['Рабочие', 'Школьники', 'Студенты'];

queue.unshift('Пенсионеры', 'Инвалиды');

console.log(queue);

// ["Пенсионеры", "Инвалиды", "Рабочие", "Школьники", "Студенты"]
```
Метод unshift изменит исходный массив и напишет, сколько элементов в новом массиве:
```javascript
const queue = ["Пенсионеры", "Инвалиды", "Рабочие", "Школьники", "Студенты"];

console.log(queue.length); // 5
console.log(queue.unshift('Мне только спросить')); // 6
```

- __.slice()__ - Метод копирует часть массива и делает из неё новый массив. Он принимает на вход два аргумента:  
  * индекс элемента, с которого нужно начать копирование (включительно);  
  * индекс элемента, на котором нужно остановиться (не включительно).  
  
Исходный массив при этом не изменяется:
```javascript
const months = [
  'Январь',
  'Февраль',
  'Март',
  'Апрель',
  'Май',
  'Июнь',
  'Июль',
  'Август',
  'Сентябрь',
  'Октябрь',
  'Ноябрь',
  'Декабрь'
];

// начиная с индекса 2 ("Март") и до, но не включая индекс 5 ("Июнь")
const spring = months.slice(2, 5);

console.log(spring); // ["Март", "Апрель", "Май"]

console.log(months); /* ["Январь", "Февраль", "Март", "Апрель", "Май", "Июнь", "Июль", "Август", "Сентябрь", "Октябрь", "Ноябрь", "Декабрь"] */

// Как видите, исходный массив остался нетронутым
```
Можно передавать как аргумент и отрицательные числа. Тогда индекс будет считаться с конца массива:
```javascript
const months = [
  'Январь',
  'Февраль',
  'Март',
  'Апрель',
  'Май',
  'Июнь',
  'Июль',
  'Август',
  'Сентябрь',
  'Октябрь',
  'Ноябрь',
  'Декабрь'
];

// начиная с четвёртого элемента с конца и до первого с конца (не включительно)
const autumn = months.slice(-4, -1);
console.log(autumn); // ["Сентябрь", "Октябрь", "Ноябрь"]

// с третьего элемента с конца и до конца
const fourthQuarter = months.slice(-3);
console.log(fourthQuarter); // ["Октябрь", "Ноябрь", "Декабрь"]
```

- __.splice()__ - Метод splice выполняет два действия: удаляет элементы из массива и добавляет на их место новые.  
  * Первый аргумент метода — индекс элемента, с которого надо начать удалять.  
  * Второй — сколько элементов нужно удалить.  
  * Аргументы с третьего — элементы, которые мы хотим поставить на место удалённых. Их может быть сколько угодно или не быть вообще:
```javascript
const week = [
  'Понедельник',
  'Вторник',
  'Среда',
  'Четверг',
  'Пятница',
  'Суббота',
  'Воскресенье'
];

// начиная с индекса 0 удалим пять элементов и вставим на их место другие пять
const removedItems = week.splice(0, 5, 'Воскресенье', 'Суббота', 'Воскресенье', 'Суббота', 'Воскресенье');

console.log(removedItems); // ["Понедельник", "Вторник", "Среда", "Четверг", "Пятница"]

console.log(week); // ["Воскресенье", "Суббота", "Воскресенье", "Суббота", "Воскресенье", "Суббота", "Воскресенье"]
```
Этот код изменит исходный массив и вернёт новый из удалённых элементов. Новые значения добавлять необязательно — можно удалить существующие. И наоборот. Можно ничего не удалять — только добавить новые элементы.

- __Array.from()__ - Создаёт массив из «массивоподобного» объекта:
```javascript
const posts = content.querySelectorAll('.post');

const postsArray = Array.from(posts); // такой вызов вернёт полноценный массив
```
Объект считается массивоподобным, если: его элементы имеют числовые индексы, у него есть свойство length.

- __.forEach(function (){})__ - Метод нужен для обхода массива. В качестве аргумента forEach принимает функцию. Она будет вызвана на каждом элементе массива поочерёдно:
```javascript
const how = ['быстрее', 'выше', 'сильнее'];

how.forEach(function (item) {
    console.log(item + '.');
});

/*
  быстрее.
  выше.
  сильнее.
*/
```
Метод  forEach удобно использовать для работы с массивоподобными объектами. Например, с NodeList. Частая задача — пройтись по нескольким DOM элементам, вызвав для каждого из них функцию:
```javascript
const elements = document.querySelectorAll('.text');

elements.forEach((item) => {
   item.classList.add('text_is-active');
});
```
Метод forEach — более удобная для работы с массивом версия цикла for. Но с forEach нельзя использовать директивы continue и break.

- __.map(function (){})__ - Метод создаёт новый массив на основе существующего. В качестве аргумента map, как и forEach, принимает функцию. Эта функция должна вернуть значение, которое станет элементом нового массива.
```javascript
const firstArr = [0, 1, 2, 3, 4];

const secondArr = firstArr.map(function (item) { // Берём каждый элемент массива
  return item * item; // Возводим каждый элемент в квадрат
}); 

console.log(secondArr); // [0, 1, 4, 9, 16]
```
Результат работы функции — то, что указано после ключевого слова return. Если не прописать return, функция сработает, но вернёт undefined.  
Метод map нельзя применить к массивоподобным объектам.