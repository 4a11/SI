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
Составьте текстовый файл и положите его в одну директорию с программой на Python. Текстовый файл должен состоять минимум из двух строк.

#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_1.png)

### Задание 2
Напишите программу, которая выведет только первую строку из вашего файла, при этом используйте конструкцию open()/close().

```python
f = open('input.txt', 'r')
print(f.readline())
f.close()
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_2.png)

### Задание 3
Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию open()/close().

```python
f = open('input.txt', 'r')
print(f.readlines())
f.close()
```                            
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_3.png)

### Задание 4
Напишите программу, которая выведет все строки из вашего файла в массиве, при этом используйте конструкцию with open().

```python
with open('input.txt') as f:
    print(f.readlines())
```

#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_4.png)

### Задание 5
Напишите программу, которая выведет каждую строку из вашего файла отдельно, при этом используйте конструкцию with open().

```python
with open('input.txt') as f:
    for line in f:
        print(line)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_5.png)

### Задание 6
Напишите программу, которая будет добавлять новую строку в ваш файл, а потом выведет полученный файл в консоль. Вывод можно осуществлять любым способом. Обязательно проверьте сам файл, чтобы изменения в нем тоже отображались

```python
with open('input.txt', 'a+') as f:
    f.write('\nIm additional line')

with open('input.txt', 'r') as f:
    result = f.readlines()
    print(result)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_6.png)

### Задание 7
Напишите программу, которая перепишет всю информацию, которая была у вас в файле до этого, например напишет любые данные из произвольно вами составленного списка. Также не забудьте проверить что измененная вами информация сохранилась в файле.

```python
lines = ['one', 'two', 'three']
with open('input.txt', 'w') as f:
    for line in lines:
        f.write('\nCycle run ' + line)
    print('Done!')
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_7.png)

### Задание 8
Выберите любую папку на своем компьютере, имеющую вложенные директории. Выведите на печать в терминал ее содержимое, как и всех подкаталогов при помощи функции print_docs(directory).

```python
import os

def print_docs(directory):
    all_files = os.walk(directory)
    for catalog in all_files:
        print(f'Папка {catalog[0]} содержит:')
    print(f'Директории: {", ".join([folder for folder in catalog[1]])}')
    print(f'Файлы: {", ".join([file for file in catalog[2]])}')
    print('-'*40)

print_docs(r'D:\nanoCad')
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_8.png)

### Задание 9
Документ «input.txt» содержит следующий текст:

Приветствие

Спасибо 

Извините

Пожалуйста

До свидания

Ты готов?

Как дела?

С днем рождения!

Удача!

Я тебя люблю. 

Требуется реализовать функцию, которая выводит слово, имеющее максимальную длину (или список слов, если таковых несколько). Проверьте работоспособность программы на своем наборе данных

```python
def longest_words(file):
    with open(file , encoding='utf-8') as f:
        words = f.read().split()
        max_length = len(max(words, key=len))
        for word in words:
            if len(word) == max_length:
                sought_words = word

        if len(sought_words) == 1:
            return sought_words[0]
        return sought_words

print(longest_words('input.txt'))
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_9.png)

### Задание 10
Требуется создать csv-файл «rows_300.csv» со следующими столбцами:

• № - номер по порядку (от 1 до 300);

• Секунда – текущая секунда на вашем ПК;

• Микросекунда – текущая миллисекунда на часах.

Для наглядности на каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунды.

```python
import csv
import datetime
import time

with open('rows_300.csv', 'w', encoding='utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№', 'Секунда', 'Микросекунда'])
    for line in range(1, 301):
        writer.writerow([line, datetime.datetime.now().second, datetime.datetime.now().microsecond])
        time.sleep(0.01)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab7_10.png)


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

#### Вывод

Понял как работать с текстовыми файлами

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

#### Вывод

Узнал про цикл ввода и "стоп рычаг"

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

#### Вывод

сделал по сути статистический анализ текста


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

#### Вывод

Узнал о прекраснейшой библеотеке `re`.

### Задание 5
Требуется создать csv-файл «rows_300.csv» со следующими столбцами:
– № - номер по порядку (от 1 до 300);
– Секунда – текущая секунда на вашем ПК;
–  Микросекунда – текущая миллисекунда на часах.
На каждой итерации цикла искусственно приостанавливайте скрипт на 0,01 секунды.

```python
import csv
import datetime
import time
 
with open('rows_300.csv', 'w', encoding='utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['№', 'Секунда ', 'Микросекунда'])
    for line in range(1, 301):
        writer.writerow([line, datetime.datetime.now().second, datetime.datetime.now().microsecond])
        time.sleep(0.01)
```

#### Результат

![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_5.png)
![Меню](https://github.com/4a11/SI/blob/main/pic/sam7_5_1.png)

#### Вывод

Придумал велик... 
