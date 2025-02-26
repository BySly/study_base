# Для чего нужны

Дженерики помогают писать универсальный код, а также иногда помогают отказаться от any. Главная задача - помочь писать код, который будет работать со значениями разных типов.
Преимущества:
- Можно безопасно хранить один объект, используя дженерики, не сохраняя другие типы
- Используя дженерики, можно избежать приведения типов любых переменных или функций во время вызова
- Более читабельный код


# Использование в функциях

Разработчики определяют тип заполнителя в угловых скобках, например `<T>`, используют этот тип заполнителя внутри функции для реализации дженерика.

Пример функции, которая возвращает первый аргумент массива `array` с использованием дженериков.
```ts
function firstElement<T>(arr: T[]): T {
	return arr[0]
}
```
Чтобы использовать функцию с различными типами массивов, при вызове функции передаётся определенный тип:
```ts
function firstElement<t>(array: T[]): T | undefined {
	return arr[0]
}

const numbers = [1, 2, 3]
const firstNumber = firstElement<number>(numbers)
console.log(firstNumber) // 1

const names = ['Daniel', 'Michael', 'Charlie']
const firstName = firstElement<string>(names)
console.log(firstName) // Daniel
```
В этом примере функция используется с двумя массивами разных типов, `number` массив чисел и `names` массив строк. Обходя определенный тип при вызове функции, функция может работать с соответствующим типом данных.


# Использование дженериков в классах и интерфейсах

Дженерики таже можно использовать в классах и интерфейсах. Например, класс представляющий стек, может быть написан с типом дженерик для поддержки любого типа.
```ts
class Stack<T> {
	pritvate data: T[] = []
	push(item: T) {
		this.data.push(item)
	}
	pop(): T | undefined {
		return this.data.pop()
	}
}

let numberStack = new Stack<number>()
numberStack.push(1)
numberStack.push(2)
console.log(numberStack.pop()) // 2
console.log(numberStack.pop()) // 1

let stringStack = new Stack<string>()
stringStack.push('a')
stringStack.push('b')
console.log(stringStack.pop()) // b
console.log(stringStack.pop()) // a
```

# Встроенный дженерик (универсальный тип) и интерфейсы

TypeScript предоставляет несколько встроенных универсальных типов и интерфейсов, таких как `Array`, `Promise` и `Map`, обычно используемых в JavaScript. Эти типы определяются с помощью дженерика (универсального типа) и могут использоваться с любым типом данных. Например, `Array` - это дженерик, представляющий упорядоченную коллекцию элементов. Его можно использовать с любым типом данных.
```ts
let numbers = [1, 2, 3];
let names = ['Daniel', 'Micheal', 'Charlie'];
```
Другим примером является `Promise`, представляющий значение, которое может быть еще недоступно, но будет доступно в какой-то момент в будущем. Тип также определяется с помощью дженерика, представляющего значение, которое будет доступно в будущем.
```ts
let promise: Promise<string> = new Promise((resolve, reject) => {
	setTimeout(() => {
		resolve("Hello, World!")
	}, 1000);});
promise.then((value: string) => console.log(value)); // 'Hello, World!'
```
Наконец, `Map` — это дженерик (универсальный тип), представляющий набор пар ключ-значение. Дженерики (универсальные типы) для ключей и значений могут быть разными.

```ts
let map = new Map<string, number>();
map.set("Daniel", 25);
map.set("Michael", 30);
console.log(map.get("Daniel")); // 25
```
Помимо использования этих встроенных дженериков (универсальных типов) и интерфейсов, вы также можете расширить их для добавления дополнительных функций. Например, вы можете создать собственный класс `Stack`, расширяющий встроенный тип `Array`, как показано в предыдущем примере. Это позволяет использовать преимущества встроенной функциональности типа `Array` при добавлении пользовательских функций.


# Заключение

Дженерики (Обобщения или Универсальные типы) в TypeScript предоставляют важную функцию для написания многократно используемого и гибкого кода. Они позволяют разработчикам абстрагироваться от типов, позволяя писать функции, классы и интерфейсы работающие с любым типом данных. Эта возможность TypeScript делает код более читабельным и удобным для сопровождения, а также уменьшает количество дублированного кода.