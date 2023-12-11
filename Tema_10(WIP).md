Отчет по Теме #10 выполнил(а):
- Прокин Дмитрий Сергеевич
- ОЗИВТ-22-1-у

| Задание   | Лаб_раб | Сам_раб |
| --------- |-------- | ------- |
| Задание 1 | +       | +       |
| Задание 2 | +       | +       |
| Задание 3 | +       | +       |
| Задание 4 | +       | +       |
| Задание 5 | +       | +       |
| Задание 6 | +       |         |
| Задание 7 | +       |         |
| Задание 8 | +       |         |
| Задание 9 | +       |         |
| Задание 10| +       |         |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №10
### Задание 1


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task1.png)

### Задание 2


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task2.png)

### Задание 3


```python

```                            
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task3.png)

### Задание 4


```python

```

#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task4.png)

### Задание 5


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task5.png)

### Задание 6


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task6.png)

### Задание 7


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task7.png)

### Задание 8


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task8.png)

### Задание 9


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task9.png)

### Задание 10


```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task10.png)


## Самостоятельная работа №10

### Задание 1
Вовочка решил заняться спортивным программированием на python, но для этого он должен знать за какое время выполняется его программа. Он решил, что для этого ему идеально подойдет декоратор для функции, который будет выяснять за какое время выполняется та или иная функция. Помогите Вовочке в его начинаниях и напишите такой декоратор. Подсказка: необходимо использовать модуль time Декоратор необходимо использовать для этой функции.

```python
import time

def time_of_func(func): # Устройство декоратора
    def wrapped(*args):
        start_time = time.perf_counter_ns()
        res = func(*args)
        print(time.perf_counter_ns() - start_time)
        return res
    return wrapped
@time_of_func # Декоратор
def fibonacci():

    fib1 = fib2 = 1
    temp = time.time()
    for i in range(2, 200):
        fib1, fib2 = fib2, fib1 + fib2
        print(fib1, end='\n')

if __name__ == '__main__':
    fibonacci()
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_1.png)

### Задание 2


```python
import os

def show_file(filename):
    try:
        if os.stat(filename).st_size > 0:
            print(f"{open(filename, encoding='utf-8').readlines()}")
        else:
            a = 1 / 0
    except:
        print("empty file")


show_file('input.txt')
show_file('rows_300.txt')
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_2.png)

### Задание 3



```python
try:
    data = int(input("Введите число: "))
    data = data + 2
    print(data)
except:
    print("Неподходящий тип данных. Ожидалось число")
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_3_1.png)
![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_3_2.png)


### Задание 4


```python
import time

def timer_func(func):
    # This function shows the execution time of
    # the function object passed
    def wrap_func(*args, **kwargs):
        t1 = time.time()
        result = func(*args, **kwargs)
        t2 = time.time()
        print(f'Function {func.__name__!r} executed in {(t2-t1):.4f}s')
        return result
    return wrap_func

@timer_func
def sum():
    sum = 1
    for i in range(0, 1000):
        sum += sum
        print(sum)

@timer_func
def sort_list(list):
    for i in range(len(list) - 1):
        for j in range(len(list) - i - 1):
            if list[j] > list[j + 1]:
                buff = list[j]
                list[j] = list[j + 1]
                list[j + 1] = buff
    print(list)


sum()
sort_list([1, 9, 5, 2, 7])
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_4.png)

### Задание 5



```python
class NoMoreDmitrii(Exception):
    def __init__(self, message, extra_info):
        super().__init__(message)
        self.extra_info = extra_info

class AnotherError(Exception):
    def __init__(self,  *args):
        if args:
            self.message = args[0]
        else:
            self.message = None

    def __str__(self):
        if self.message:
            return "AnotherError, {0} ".format(self.message)
        else:
            return "Выход из диапазона допустимых значений у списка!"


def divide_numbers(a, b):
    if b == 0:
        raise NoMoreDmitrii("Деление на ноль невозможно", {"a": a, "b": b})
    return a / b

def one_hundred_procent_working_code(list, index):
    try:
        if index != 0:
            print(list[index - 1])
        else:
            raise AnotherError
    except AnotherError as e:
        print(f"Сообщение об ощибке: {e}")


try:
    result = divide_numbers(10, 0)
except NoMoreDmitrii as e:
    print(f"Сообщение об ошибке: {e}")
    print(f"Дополнительная информация: {e.extra_info}")

    try:
        one_hundred_procent_working_code([1,2,3], 0)
    except AnotherError as e:
        print(f"Сообщение об ошибке: {e}")
```

#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam10_5.png)
