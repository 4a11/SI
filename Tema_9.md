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

## Лабораторная работа №7
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


## Самостоятельная работа №8

### Задание 1
Самостоятельно создайте класс и его объект. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли

```python
class Person:
    def say_hello():
        print(f"Привет")


Person.say_hello()
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_1.png)

### Задание 2
Самостоятельно создайте атрибуты и методы для ранее созданного класса. Они должны отличаться, от тех, что указаны в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def say_hello(self):
        print(f"{self.name} вас приветствует.")


dmitrii_object = Person("Дмитрий", "17")

dmitrii_object.say_hello()
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_2.png)

### Задание 3
Самостоятельно реализуйте наследование, продолжая работать с ранее созданным классом. Оно должно отличаться, от того, что указано в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Person(object):
    def __init__(self):
        self.name = "Dmitrii"

    def say_hello(self):
        print(f"{self.name} вас приветствует.")

class Student(Person):
    def __int__(self):
        Person.__init__()

    def write_off(self):
        return "someone write off " + self.name + " work."


student_object = Student()

print(student_object.write_off())

```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_3.png)


### Задание 4
Самостоятельно реализуйте инкапсуляцию, продолжая работать с ранее созданным классом. Она должна отличаться, от того, что указана в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.

```python
class Person:
    def __init__(self, name, age):
        self.__name = name
        self.__age = age

    def say_hello(self):
        print(f"{self.name} вас приветствует.")


dmitrii_object = Person("Дмитрий", "17")

dmitrii_object.say_hello()
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_4.png)

### Задание 5
Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и лабораторных заданиях. Результатом выполнения задания будет листинг кода и получившийся вывод консоли.


```python
class Cat:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def info(self):
        print(f"I am a cat. My name is {self.name}. I am {self.age} years old.")

    def make_sound(self):
        print("Meow")


class Dog:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def info(self):
        print(f"I am a dog. My name is {self.name}. I am {self.age} years old.")

    def make_sound(self):
        print("Bark")


cat1 = Cat("Kitty", 2.5)
dog1 = Dog("Fluffy", 4)

for animal in (cat1, dog1):
    animal.make_sound()
    animal.info()
    animal.make_sound()
```

#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam8_5.png)
