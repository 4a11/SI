![image](https://github.com/4a11/SI/assets/82211506/af536957-cbe8-46a6-85e3-10817c6b17e3)Отчет по Теме #11 выполнил(а):
- Прокин Дмитрий Сергеевич
- ОЗИВТ-22-1-у

| Задание   | Лаб_раб | Сам_раб |
| --------- |-------- | ------- |
| Задание 1 | +       | +       |
| Задание 2 | +       | +       |
| Задание 3 | +       | +       |
| Задание 4 | +       | +       |
| Задание 5 | +       | +       |


знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №11
### Задание 1
Простой итератор, но у него нет гибкой настройки, например его
нельзя развернуть. Он работает просто как next(), но нет prev()

```python
numbers = [ 0, 1, 2, 3, 4, 5]
for item in numbers:
    print(item)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab11_1.png)

### Задание 2
Класс итератор с гибкой настройкой и удобными применением

```python
class CountDown:
    def __init__(self, start):
        self.count = start + 1

    def __iter__(self):
        return self

    def __next__(self):
        self.count -= 1
        if self.count < 0:
            raise StopIteration
        return self.count

if __name__ == '__main__':
    counter = CountDown(5)
    for i in counter:
        print(i)

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab11_2.png)

### Задание 3
Генератор списка

```python
a = [i** 2 for i in range (1,5)]

print('a -' , a)
for i in a:
    print(i)

print('iter(a) -', iter(a))
for i in a:
    print(i)
```                            
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab11_3.png)

### Задание 4
Выражения генераторы

```python
b = (i ** 2 for i in range(1,5))
print(b)
print('first')
for i in b:
    print(i)
print('second')

for i in b:
    print(i)
```

#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab11_4.png)

### Задание 5
Такой же счетчик, как и в первом задании, только это генератор и
использует yield

```python
ef countdown(count):
    while count >=0:
        yield count
        count-=1

if __name__ == '__main__':
    counter = countdown(5)
    for i in counter:
        print(i)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab11_5.png)


## Самостоятельная работа №11

### Задание 1
Вас никак не могут оставить числа Фибоначчи, очень уж они вас
заинтересовали. Изучив новые возможности Python вы решили
реализовать программу, которая считает числа Фибоначчи при
помощи итераторов. Расчет начинается с чисел 1 и 1. Создайте
функцию fib(n), генерирующую n чисел Фибоначчи с
минимальными затратами ресурсов. Для реализации этой функции
потребуется обратиться к инструкции yield (Она не сохраняет в
оперативной памяти огромную последовательность, а дает
возможность “доставать” промежуточные результаты по одному).
Результатом решения задачи будет листинг кода и вывод в консоль с
числом Фибоначчи от 200.

```python
def fib(num):
    a, b = 1, 1
    for i in range(num):
        yield a
        a, b, = b, a + b

fib_seq = fib(7)
for i in fib_seq:
    print(i)
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_1.png)

#### Вывод

функция `fib` создает список чисел фибаначи

### Задание 2
К коду предыдущей задачи добавьте запоминание каждого числа
Фибоначчи в файл “fib.txt”, при этом каждое число должно
находиться на отдельной строчке. Результатом выполнения задачи
будет листинг кода и скриншот получившегося файла


```python
def fib(num):
    fib_list = [0, 1]
    for i in range(2, num):
        fib_list.append(fib_list[i-1] + fib_list[i-2])
    return fib_list

a = int(input("Введите кол-во: "))

fib_nums = fib(a)

with open('fib.txt', 'w') as f:
    for i in fib_nums:
        f.write(str(i) + "\n")
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_2.png)

#### Вывод

функция `fib` создает список чисел фибаначи, а после мы из записываем в файл `fib.txt`

