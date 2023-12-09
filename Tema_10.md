Отчет по Теме #7 выполнил(а):
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

```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_2.png)

### Задание 3


```python

```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_3.png)


### Задание 4


```python

```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_4.png)

### Задание 5



```python

```

#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_5.png)
