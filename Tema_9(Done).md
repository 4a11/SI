Отчет по Теме #9 выполнил(а):
- Прокин Дмитрий Сергеевич
- ОЗИВТ-22-1-у

| Задание   | Лаб_раб | Сам_раб |
| --------- |-------- | ------- |
| Задание 1 | +       | +       |
| Задание 2 | +       |         |
| Задание 3 | +       |         |
| Задание 4 | +       |         |
| Задание 5 | +       |         |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №9
### Задание 1


```python
class Ivan:
    __slots__ = ['name']

    def __init__(self, name):
        if name == 'Иван':
            self.name = f"Да, я {name}"
        else:
            self.name = f"Я не {name}, я Иван"

person1 = Ivan('Алексей')
person2 = Ivan('Иван')
print(person1.name)
print(person2.name)

person2.surname='Петров'
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab9_1.png)

### Задание 2


```python
class Iceream:
    def __init__(self, ingredient = None):
        if isinstance(ingredient, str):
            self.ingredient = ingredient
        else:
            self.ingredient = None


    def composition(self):
        if self.ingredient:
            print(f"Мороженное с {self.ingredient}")
        else:
            print('Обычное мороженное')

icecream = Iceream()
icecream.composition()
icecream = Iceream('Шоколадом')
icecream.composition()
icecream = Iceream(5)
icecream.composition()

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab9_2.png)

### Задание 3


```python
class MyClass:
    def __init__(self, value):
        self._value=value

    def set_value(self, value):
        self._value = value

    def get_value(self):
        return self._value

    def del_value(self):
        del self._value

    value = property(get_value, set_value, del_value, "Свойство value" )

obj = MyClass(42)
print(obj.get_value())
obj.set_value(45)
print(obj.get_value())
obj.set_value(100)
print(obj.get_value())
obj.del_value()
print(obj.get_value())
```                            
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task3.png)

### Задание 4


```python
class Mammal:
    className = 'Mammal'

class Dog (Mammal):
    species = 'canine'
    sounds = 'wow'

class Cat (Mammal):
    species = 'feline'
    sounds = 'neow'

dog = Dog()
print(f"Dog is { dog.className}, but they say {dog.sounds}")
cat =Cat()
print(f"Cat is { cat.className}, but they say {cat.sounds}")
```

#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab9_4.png)

### Задание 5


```python
class Russian:
    @staticmethod
    def greeting():
        print("Привет")

class English:
    @staticmethod
    def greeting():
        print("Hello")

def greet(language):
    language.greeting()

ivan = Russian()
greet(ivan)
john = English()
greet (john)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab9_6.png)



## Самостоятельная работа №9

### Задание 1
Классовая структура:

Есть Помидор со следующими характеристиками:

    • Индекс
    • Стадия созревания (стадии: отсутствует, цветение, зеленый, красный)
Помидор может:

    • Расти (переходить на следующую стадию созревания)
    • Предоставлять информацию о своей зрелости
Есть Куст с помидорами, который:

    • Содержит список томатов, которые на нем растут
А также может:

    • Расти вместе с томатами
    • Предоставлять информацию о зрелости всех томатов
    • Предоставлять урожай
И также есть Садовник, который имеет:

    • Имя
    • Растение, за которым он ухаживает
Он может:

    • Ухаживать за растением
    • Собирать с него урожай
Задание:
Класс Tomato:

    1) Создайте класс Tomato
    
    2) Создайте статическое свойство states, которое будет содержать все стадии созревания помидора
    
    3) Создайте метод __init__(), внутри которого будут определены два динамических свойства: _index (передается параметром) и _state (принимает первое значение из словаря states). После написания этого блока кода в комментарии к нему укажите какими являются эти два свойства
    
    4) Создайте метод grow(), который будет переводить томат на следующую стадию созревания
    
    5) Создайте метод is_ripe(), который будет проверять, что томат созрел

    
Класс TomatoBush:

    1) Создайте класс TomatoBush
    
    2) Определите метод __init__(), который будет принимать в качестве параметра количество томатов и на его основе будет создавать список объектов класса Tomato. Данный список будет храниться внутри динамического свойства tomatoes
    
    3) Создайте метод grow_all(), который будет переводить все объекты из списка томатов на следующий этап созревания
    
    4) Создайте метод all_are_ripe(), который будет возвращать True, если все томаты из списка стали спелыми.
    
    5) Создайте метод give_away_all(), который будет чистить список томатов после сбора урожая
    
Класс Gardener:

    1) Создайте класс Gardener
    
    2) Создайте метод __init__(), внутри которого будут определены два динамических свойства: name (передается параметром, является публичным) и _plant (принимает объект класса TomatoBush). После написания этого блока кода в комментарии к нему укажите какими являются эти два свойства
    
    3) Создайте метод work(), который заставляет садовника работать, что позволяет растению становиться более зрелым
    
    4) Создайте метод harvest(), который проверяет, все ли плоды созрели. Если все, то садовник собирает урожай. Если нет, то метод печатает предупреждение
    
    5) Создайте статический метод knowledge_base(), который выведет в консоль справку по садоводству
    
Тесты:

    1) Вызовите справку по садоводству
    
    2) Создайте объекты классов TomatoBush и Gardener
    
    3) Используя объект класса Gardener, поухаживайте за кустом с помидорами
    
    4) Попробуйте собрать урожай, когда томаты еще не дозрели. Продолжайте ухаживать за ними
    
    5) Соберите урожай Результатом работы вашей программы будет листинг кода с подробными комментариями и скриншоты выполенния всех тестов.

```python
class Tomato:
    states = {'Отсутствует': 0, 'Цветение': 1, 'Зеленый': 2, 'Красный': 3}

    def __init__(self, index):
        self._index = index # Приватный аттрибут
        self._state = self.states['Отсутствует'] # Приватный аттрибут

    def grow(self):
        if self._state < 3:
            self._state += 1

    def is_ripe(self):
        return True if self._state == 3 else False


class TomatoBush:

    def __init__(self, num):
        self.tomatoes = [Tomato(index) for index in range(1, num + 1)]

    def grow_all(self):
        for tomato in self.tomatoes:
            tomato.grow()

    def all_are_ripe(self):
        return all([tomato.is_ripe() for tomato in self.tomatoes])

    def give_away_all(self):
        self.tomatoes = []


class Gardener:

    def __init__(self, name, plant):
        self.name = name # Публичный аттрибут
        self._plant = plant # Приватный аттрибут

    def work(self):
        self._plant.grow_all()

    def harvest(self):
        if self._plant.all_are_ripe():
            print('Урожай собран!')
            self._plant.give_away_all()
        else:
            print('Томаты еще не дозрели')

    @staticmethod
    def knowledge_base():
        print('Справка по садоводству:')
        print('1. Не забывайте регулярно поливать и подкармливать растения')
        print('2. Определите правильное расстояние между растениями, чтобы они не мешали друг другу в росте')
        print('3. Удалите поврежденные листья и плоды, чтобы предотвратить распространение болезней')


# Вызов справки по садоводству
Gardener.knowledge_base()

# Создание объектов классов TomatoBush и Gardener
bush = TomatoBush(5)
gardener = Gardener('John', bush)

# Уход за кустом с помидорами
gardener.work()
gardener.work()
gardener.work()

# Сбор урожая
gardener.harvest()

# Продолжение ухода за кустом, пока томаты не дозреют
gardener.work()
gardener.harvest()
gardener.work()
gardener.harvest()
gardener.work()
gardener.harvest()
# Сбор урожая после дозревания всех томатов
gardener.work()
gardener.harvest()
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam9.png)

#### Вывод

В данной задаче практически воспроизвелись все основы ООП.

