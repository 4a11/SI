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


## Самостоятельная работа №7

### Задание 1
Найдите в интернете любую статью (объем статьи не менее 200 слов), скопируйте ее содержимое в файл и напишите программу, которая считает количество слов в текстовом файле и определит самое часто встречающееся слово. Результатом выполнения задачи будет: скриншот файла со статьей, листинг кода, и вывод в консоль, в котором будет указана вся необходимая информация.


```python
import string

with open('text.txt') as f:
    content = f.read().lower()

output = content.translate(str.maketrans('', '', string.punctuation))
words = output.split()
diff_words = []
diff_words_count = []

for i in words:
    if i.casefold() not in map(str.casefold, diff_words):
        diff_words.append(i)
        diff_words_count.append(words.count(i))



print(f"Кол-во слов в текстовом файле: {len(words)}")
print(f"Самое часто встречающиеся слово: {diff_words[diff_words_count.index(max(diff_words_count))]}")
print(f"Кол-во повторейний: {max(diff_words_count)}")
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_1.png)

### Задание 2
У вас появилась потребность в ведении книги расходов, посмотрев все существующие варианты вы пришли к выводу что вас ничего не устраивает и нужно все делать самому. Напишите программу для учета расходов. Программа должна позволять вводить информацию о расходах, сохранять ее в файл и выводить существующие данные в консоль. Ввод информации происходит через консоль. Результатом выполнения задачи будет: скриншот файла с учетом расходов, листинг кода, и вывод в консоль, с демонстрацией работоспособности программы


```python
data = ""
while data != "стоп":
    data = input("Сколько потратил? ('стоп' для прекращения ввода): ")
    with open('text.txt', 'a') as f:
        if data != "стоп" and data:
            f.writelines(data + '\n')

with open('text.txt', 'r+') as f:
    content = f.readlines()

num_list = list(map(lambda x: x.strip(), content))
_sum = 0

for i in num_list:
    _sum += int(i)

print(f"Сумма всех трат: {_sum}")
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_2.png)
![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_2_1.png)

### Задание 3
Имеется файл input.txt с текстом на латинице. Напишите программу, которая выводит следующую статистику по тексту: количество букв латинского алфавита; число слов; число строк.


```python
letters = 0

with open('input.txt') as f:
    text = f.readlines()

with open('input.txt') as f:
    words = f.read()

fxd_txt = list(map(lambda x: x.strip(), text)) # Убираю '\n' с конца каждой строки
fxd_words = list(map(lambda x: x.strip(), words)) # Убираю '\n' с конца каждой строки

for j in fxd_txt:
    letters += len(([i for i in j if 64<ord(i)<91 or 96<ord(i)<123])) # На самом деле не понимаю почему это работает

print(f"Кол-во символов латинского алфавита: {letters}")
print(f"Кол-во слов: {len(words.split())}")
print(f"Кол-во строк: {len(fxd_txt)}")

```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_3.png)


### Задание 4
Напишите программу, которая получает на вход предложение, выводит его в терминал, заменяя все запрещенные слова звездочками * (количество звездочек равно количеству букв в слове). Запрещенные слова, разделенные символом пробела, хранятся в текстовом файле input.txt. Все слова в этом файле записаны в нижнем регистре. Программа должна заменить запрещенные слова, где бы они ни встречались, даже в середине другого слова. Замена производится независимо от регистра: если файл input.txt содержит запрещенное слово exam, то слова exam, Exam, ExaM, EXAM и exAm должны быть заменены на ****.


```python
import re

with open('input.txt') as f:
    content = f.readlines()

fxd_txt = list(map(lambda x: x.strip(), content))


def just_replace(txt):
    for i in fxd_txt:
        txt = re.sub(i, len(i) * "*", txt, flags=re.IGNORECASE)

    return txt


txt = 'Hello, world! Python IS the programming language of thE future. My EMAIL is.... PYTHON is awesome!!!!'

print(just_replace(txt))
```
#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_4.png)
![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_4_1.png)

### Задание 5


```python

```

#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam6_5.png)
