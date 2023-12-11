# Тема 5.
Отчет по Теме #5 выполнил(а):
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

## Лабораторная работа №5
### Задание 1
Друзья предложили вам поиграть в игру “найди отличия и убери повторения (версия для программистов)”. Суть игры состоит в том, что на вход программы поступает два множества, а ваша задача вывести все элементы первого, которых нет во втором. А вы как раз недавно прошли множества и знаете их возможности, поэтому это не составит для вас труда.

```python
set_1 = {'White', 'Black','Red','Pink'}
set_2 = { 'Red','Green','Blue','Red'}

print(set_1-set_2)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_1.png)

### Задание 2
Напишите две одинаковые программы, только одна будет использовать set(), а вторая frozenset() и попробуйте к исходному множеству добавить несколько элементов, например, через цикл.

```python
a = set ('abycgkvhjb')
print(a)
for i in range(1,6):
    a.add(i)
print(a)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_3_1.png)

```py
a = frozenset('abcdefg')
print(a)
for i in range(1,5):
    a.add(i)
print(a)
```

#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_3_2.png)

### Задание 3
На вход в программу поступает список (минимальной длиной 2 символа). Напишите программу, которая будет менять первый и последний элемент списка.P.S. В Python есть прикольное свойство, благодаря которому эту задачу можно решить более красиво, использовав всего 2 сточки кода, если интересно можете самостоятельно найти это решение.

```python
def replace(input_list):
    memory = input_list[0]
    input_list[0] = input_list[-1]
    input_list[-1] = memory

    return  input_list

print(replace([1, 2, 3, 4, 5]))
```                            
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_33.png)

### Задание 4
На вход в программу поступает список (минимальной длиной 10 символов). Напишите программу, которая выводит элементы с индексами от 2 до 6. В программе необходимо использовать “срез”

```python
a = [12, 34, 56, 33, 66, 88]
print(a[2:6])
```

#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_4.png)

### Задание 5
Иван задумался о поиске «бесполезного» числа, полученного из списка. Суть поиска в следующем: он берет произвольный список чисел, находит самое большое из них, а затем делит его на длину списка. Студент пока не придумал, где может пригодиться подобное значение, но ищет у вас помощи в реализации такой функции useless().

```python
def useless(lst):
    return max(lst) / len(lst)

print(useless([1, 2, 3, 4]))
print(useless([1, 2, 3, 4, 1, 2, 3, 4]))
print(useless([-123.5, 123135, 4525, 0]))
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_5.png)

### Задание 6
Ребята не могут определится каким супергероем они хотят стать. У них есть случайно составленный список супергероев, и вы должны определить кто из ребят будет каким супергероем. Необходимо использовать разделение списков

```python
superheroes = ['batman', 'flash', 'spider man']

dima, kolya, petya = superheroes

print('Дмитрий - ', dima)
print('Николай - ', kolya)
print('Петр - ', petya)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_6.png)

### Задание 7
Вовочка, насмотревшись передачи “Слабое звено” решил написать программу, которая также будет находить самое слабое звено (минимальный элемент) и удалять его, только делать он это хочет не с людьми, а со списком. Помогите Вовочке с реализацией программы. Подсказка: для этого вам необходимо отсортировать список и удалить значение при помощи pop().

```python
a = [4, 2, 3, 1]

a.sort()
print(a)
a.pop(2)
print(a)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_7.png)

### Задание 8
Михаил решил создать большой n-мерный список, для этого он случайным образом создал несколько списков, состоящих минимум из 3, а максимум из 10 элементов и поместил их в один большой список. Он также как и Иван не знает зачем ему это сейчас нужно, но надеется на то, что это пригодится ему в будущем.

```python
from random import randint

def list_maker():
    a = [randint(1, 100) * randint(3, 10)]
    return a

if __name__ == '__main__':
    result = []
    for i in range(randint(1, 5)):
        result.append(list_maker())

    print(result)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/task8.png)

### Задание 9
Вы работаете в ресторане и отвечает за статистику покупок, ваша задача сравнить между собой заказы покупателей, которые указаны в разном порядке. Реализуйте функцию superset(), которая принимает 2 множества. Результат работы функции: вывод в консоль одного из сообщений в зависимости от ситуации: 

1 - «Супермножество не обнаружено»

2 – «Объект {X} является чистым супермножеством»

3 – «Множества равны»

```python
def superset(set_1, set_2):
    if set_1 > set_2:
        print(f'объект {set_1} является чистым супермножеством')
    elif set_1 == set_2:
        print('Множества равны')
    elif set_1 < set_2:
        print(f'объект {set_2} является чистым супермножеством')
    else:
        print('Супермножество не обнаружено')

if __name__ == '__main__':
    superset({1, 8, 3, 5}, {3, 5})
    superset({1, 8, 3, 5}, {5, 3, 8, 1})
    superset({3, 5}, {5, 3, 8, 1})
    superset({90, 100}, {3, 5})
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_9.png)

### Задание 10
Предположим, что вам нужно разобрать стопку бумаг, но нужно начать работу с нижней, “переверните стопку”. Вам дан произвольный список. Представьте его в обратном порядке. Программа должна занимать не более двух строк в редакторе кода.

```python
my_list = [2, 5, 8, 3]
print(my_list[::-1])
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab5_10.png)


## Самостоятельная работа №4

### Задание 1
Ресторан на предприятии ведет учет посещений за неделю при помощи кода работника. У них есть список со всеми посещениями за неделю. Ваша задача почитать:

• Сколько было выдано чеков

• Сколько разных людей посетило ресторан

• Какой работник посетил ресторан больше всех раз

Список выданных чеков за неделю:

[8734, 2345, 8201, 6621, 9999, 1234, 5678, 8201, 8888, 4321, 3365, 1478, 9865, 5555, 7777, 9998, 1111, 2222, 3333, 4444, 5556, 6666, 5410, 7778, 8889, 4445, 1439, 9604, 8201, 3365, 7502, 3016, 4928, 5837, 8201, 2643, 5017, 9682, 8530, 3250, 7193, 9051, 4506, 1987, 3365, 5410, 7168, 7777, 9865, 5678, 8201, 4445, 3016, 4506, 4506]

```python
list = [8734, 2345, 8201, 6621, 9999, 1234, 5678, 8201, 8888, 4321, 3365, 1478, 9865, 5555, 7777, 9998, 1111, 2222, 3333, 4444, 5556, 6666, 5410, 7778, 8889, 4445, 1439, 9604, 8201, 3365, 7502, 3016, 4928, 5837, 8201, 2643, 5017, 9682, 8530, 3250, 7193, 9051, 4506, 1987, 3365, 5410, 7168, 7777, 9865, 5678, 8201, 4445, 3016, 4506, 4506]
difference_peope = 0
memlist = []

for i in list:
    memlist.append(list.count(i))
    if list.count(i) == 1:
        difference_peope += 1

print("Всего посещений: ", len(list))
print("Всего разных посещений: ", difference_peope)
print("Какой работник больше всего посетил: ", list[memlist.index(max(memlist))])
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam5_1.png)

#### Вывод

Узнал больше про обработку данных из списков.

### Задание 2
На физкультуре студенты сдавали бег, у преподавателя физкультуры есть список всех результатов, ему нужно узнать

• Три лучшие результата

• Три худшие результата

• Все результаты начиная с 10

Ваша задача помочь ему в этом. Список результатов бега:

[10.2, 14.8, 19.3, 22.7, 12.5, 33.1, 38.9, 21.6, 26.4, 17.1, 30.2, 35.7, 16.9, 27.8, 24.5, 16.3, 18.7, 31.9, 12.9, 37.4] 

Результатом выполнения задачи будет: листинг кода, и вывод в консоль, в котором будет указана вся необходимая информация.

```python
my_list = [10.2, 14.8, 19.3, 22.7,
           12.5, 33.1, 38.9, 21.6,
           26.4, 17.1, 30.2, 35.7,
           16.9, 27.8, 24.5, 16.3,
           18.7, 31.9, 12.9, 37.4]

bList = list(set(my_list))
lowerTenList = []

bList.sort()

for i in bList:
    if i <= 10:
        bList.remove(i)

print(f"Три лучшие результата: {bList[0]}, {bList[1]}, {bList[2]}")
bList = bList[::-1]
print(f"Три лучшие результата: {bList[0]}, {bList[1]}, {bList[2]}")
print((f"Результаты больше 10: {bList}"))
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam5_2.png)

#### Вывод

узнал как вывести n-ое кол-во больших или наименьших значений из листа.

### Задание 3
Преподаватель по математике придумал странную задачку. У вас есть три списка с элементами, каждый элемент которых – длина стороны треугольника, ваша задача найти площади двух треугольников, составленные из максимальных и минимальных элементов полученных списков. Результатом выполнения задачи будет: листинг кода, и вывод в консоль, в котором будут указаны два этих значения.

Три списка:

one = [12, 25, 3, 48, 71]

two = [5, 18, 40, 62, 98]

three = [4, 21, 37, 56, 84]

```python
import math

one = [12, 25, 3, 48, 71]
two = [5, 18, 40, 62, 98]
three = [4, 21, 37, 56, 84]


def area(a, b, c):
    p = (a + b + c) / 2
    S = math.sqrt(p*(p - a)*(p - b)*(p - c))
    return S


print(f"Площадь треугольника из 3 минимальных эелементов: {area(min(one), min(two), min(three))} сантиметров в квадрате")
print(f"Площадь треугольника из 3 максимальных эелементов: {area(max(one), max(two), max(three))} сантиметров в квадрате")

```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam5_3.png)

#### Вывод

Узнал про `min` и `max` больше.


### Задание 4
Никто не любит получать плохие оценки, поэтому Борис решил это исправить. Допустим, что все оценки студента за семестр хранятся в одном списке. Ваша задача удалить из этого списка все двойки, а все тройки заменить на четверки. Списки оценок (проверить работу программы на всех трех вариантах):


[2, 3, 4, 5, 3, 4, 5, 2, 2, 5, 3, 4, 3, 5, 4]


[4, 2, 3, 5, 3, 5, 4, 2, 2, 5, 4, 3, 5, 3, 4]


[5, 4, 3, 3, 4, 3, 3, 5, 5, 3, 3, 3, 3, 4, 4]


Результатом выполнения задачи будет: листинг кода, и вывод в консоль, в котором будут три обновленных массива.

```python
first = [2, 3, 4, 5, 3, 4, 5, 2, 2, 5, 3, 4, 3, 5, 4]
second = [4, 2, 3, 5, 3, 5, 4, 2, 2, 5, 4, 3, 5, 3, 4]
third = [5, 4, 3, 3, 4, 3, 3, 5, 5, 3, 3, 3, 3, 4, 4]


def fixBadGrades(lst):
    lst = [num for num in lst if num != 2]
    lst = [4 if num == 3 else num for num in lst]

    return lst


print(fixBadGrades(first))
print(fixBadGrades(second))
print(fixBadGrades(third))
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam5_4.png)

#### Вывод

Узнал о Списковый включениях

### Задание 5
Вам предоставлены списки натуральных чисел, из них необходимо сформировать множества. При этом следует соблюдать это правило: если какое-либо число повторяется, то преобразовать его в строку по следующему образцу: например, если число 4 повторяется 3 раза, то в множестве будет следующая запись: само число 4, строка «44», строка «444».

Множества для теста:
list_1 = [1, 1, 3, 3, 1]
list_2 = [5, 5, 5, 5, 5, 5, 5]
list_3 = [2, 2, 1, 2, 2, 5, 6, 7, 1, 3, 2, 2]

Результаты вывода (порядок может отличаться, поскольку мы работаем
с set()).


main.py
```python
list_1 = [1, 1, 3, 3, 1]
list_2 = [5, 5, 5, 5, 5, 5, 5]
list_3 = [2, 2, 1, 2, 2, 5, 6, 7, 3, 2, 2]


def countSame(_list):
    same_values = []
    same_values_count = []
    for i in _list:
        if i not in same_values:
            same_values.append(i)
            same_values_count.append(_list.count(i))

    for i in range(len(same_values_count)):
        for j in range(1, same_values_count[i] + 1):
            if same_values_count[i] != 1:
                same_values.append(str(same_values[i]) * j)

    return same_values


print(countSame(list_1))
print(countSame(list_2))
print(countSame(list_3))
```

#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam5_5.png)

#### Вывод

Вспомнил о двойных циклах.