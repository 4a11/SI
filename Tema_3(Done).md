
# Тема 2. Базовые операции языка Python
Отчет по Теме #2 выполнил(а):
- Прокин Дмитрий Сергеевич
- ОЗИВТ-22-1-у

| Задание   | Лаб_раб | Сам_раб |
| --------- |-------- | ------- |
| Задание 1 | +       |  +      |
| Задание 2 | +       |  +      |
| Задание 3 | +       |  +      |
| Задание 4 | +       |  +      |
| Задание 5 | +       |  +      |
| Задание 6 | +       |         |
| Задание 7 | +       |         |
| Задание 8 | +       |         |
| Задание 9 | +       |         |
| Задание 10| +       |         |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
### Задание 1
Создайте две переменные, значение которых будете вводить через консоль. Также составьте условие, в котором созданные ранее переменные будут сравниваться, если условие выполняется, то выведете в консоль «Выполняется», если нет, то «Не выполняется»

```python
a = input("1)")
b = input("2)")

if (a == b):
    print("Условие выполняется")
else:
    print("Условие не выполняется")
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_1.png)

### Задание 2
Напишите программу, которая будет определять значения переменной меньше 0, больше 0 и меньше 10 или больше 10. Это нужно реализовать при помощи одной переменной, значение которой будет вводится через консоль, а также при помощи конструкций if, elif, else.

```python
a = int(input("Введите число:"))

if a < 0:
    print("число < 0")
elif 0 < a < 10:
    print("0 < число < 10")
else:
    print("число > 10")
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_2.png)

### Задание 3
Напишите программу, в которой будет проверяться есть ли переменная в указанном массиве используя логический оператор in. Самостоятельно посмотрите, как работает программа со значениями которых нет в массиве numbers.

```python
nums = [1, 2, 3, 6]
num = int(input('Введите чилсо: '))
if num in nums:
    print('Число есть в массиве')
else:
    print('Числа нет в массиве')
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_3_1.png)
![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_3_2.png)

### Задание 4
Напишите программу, которая будет определять находится ли переменная в указанном массиве и если да, то проверьте четная она или нет. Самостоятельно протестируйте данную программу с разными значениями переменной value

```python
nums = [1, 3, 4, 6, 8, 9, 15, 16, 73, 321, 322]
value = int(input("Введите значение переменной: "))
if value in nums:
    if value % 2 == 0:
        print("Переменная четная и есть в массиве nums")
    else:
         print("Переменная нечетная и есть в массиве nums")
else:
    print(f"переменной нет в массиве nums и она равна {value}")
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_4_1.png)
![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_4_2.png)

### Задание 5

```python
for i in range(10):
    if i == 0:
        i += 2
    if i == 1:
        continue
    if i == 2 or i == 3:
        print("i = 2 or 3")
    elif i in [4,5,6]:
        print("i = 4,5 or 6")
    else:
        break
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_5.png)

### Задание 6
Напишите программу, в которой при помощи цикла for определяется есть ли переменная value в строке string и посмотрите, как работает оператор else для циклов. Самостоятельно посмотрите, что выведет программа, если значение переменной value оказалось в строке string. 
Определять индекс буквы не обязательно, но если вы хотите, то это делается при помощи строки: `index = string.find(value)` Вы берете название переменной, в которой вы хотите что-то найти, затем применяете встроенный метод find() и в нем указываете то, что вам нужно найти. Данная строка вернет индекс искомого объекта.

```python
txt = 'Летели два крокодила, один зеленый, другой на север'
char = input('Введите символ: ')
for i in txt:
    if i == char:
        index = txt.find(char)
        print(f"Символ '{char}' есть в строке под {index} индексом")
        break
else:
    print(f"Символа '{char}' нет в строке")
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_6_1.png)
![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_6_2.png)


### Задание 7
Напишите программу, в которой вы наглядно посмотрите, как работает цикл for проходя в обратном порядке, то есть, к примеру не от 0 до 10, а от 10 до 0. В уже готовой программе показано вычитание из 100, а вам во время реализации программы будет необходимо придумать свой вариант применения обратного цикла.

```python
value = 10
for i in range(10, -1, -1):
    value -= i
    print(i, value)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_7.png)


### Задание 8
Напишите программу используя цикл while, внутри которого есть какие-либо проверки, но быть осторожным, поскольку циклы while при Михаил А. Панов неправильно написанных условиях могут становится бесконечными, как указано в примере далее.

```python
value = 0
while value < 100:
    if value == 0:
        value += 10
    elif value // 5 > 2:
        value += 5
    else:
        value -= 5
    print(value)

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_8.png)

### Задание 9
Напишите программу с использованием вложенных циклов и одной проверкой внутри них. Самое главное, не забудьте, что нельзя использовать одинаковые имена итерируемых переменных, когда вы используете вложенные циклы.
```python

```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_9.png)

### Задание 10
Напишите программу с использованием flag, которое будет определять есть ли нечетное число в массиве. В данной задаче flag выступает в роли индикатора встречи нечетного числа в исходном массиве, четных чисел.


```python
ever_array = [2, 4, 6, 8, 9]
flag = False
for value in ever_array:
    if value % 2 == 1:
        flag = True

if flag is True:
    print("В массиве есть нечетное число")
else:
    print("В массиве все четные числа")
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/lab3_10.png)



---



## Самостоятельная работа №3

### Задание 1
Напишите программу, которая преобразует 1 в 31. Для выполнения поставленной задачи необходимо обязательно и только один раз использовать:
1) Цикл for,
2) *= 5,
3) += 1.
Никаких других действий или циклов использовать нельзя
   
```python
num = 1

for i in range(2):
    num *= 5
    num += 1

print(num)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/sam3_1.png)


### Задание 2
Напишите программу, которая фразу «Hello World» выводит в обратном порядке, и каждая буква находится в одной строке консоли. При этом необходимо обязательно использовать любой цикл, а также программа должна занимать не более 3 строк в редакторе кода.

```python
txt = 'Hello World'
for i in reversed(txt):
    print(i)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/sam3_2.png)

### Задание 3
Напишите программу, на вход которой поступает значение из консоли, оно должно быть числовым и в диапазоне от 0 до 10 включительно (это необходимо учесть в программе). Если вводимое число не подходит по требованиям, то необходимо вывести оповещение об этом в консоль и остановить программу. Код должен вычислять в каком диапазоне находится полученное число. Нужно учитывать три диапазона:
• от 0 до 3 включительно
• от 3 до 6
• от 6 до 10 включительно
Результатом работы программы будет выведенный в консоль диапазон. Программа должна занимать не более 10 строчек в редакторе кода.

```python
a = int(input('1)'))
if a >= 0 and a < 3:
    print('от 0 до 3')
elif a >= 3 and a < 6:
    print('от 3 до 6')
elif a >= 6 and a < 10:
    print('от 6 до 10')
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/sam3_3_1.png)

### Задание 4
Манипулирование строками. Напишите программу на Python, которая принимает предложение (на английском) в качестве входных данных от пользователя. Выполните следующие операции и отобразите результаты:

• Выведите длину предложения.

• Переведите предложение в нижний регистр.

• Подсчитайте количество гласных (a, e, i, o, u) в предложении.

• Замените все слова "ugly" на "beauty".

• Проверьте, начинается ли предложение с "The" и заканчивается ли на "end". Проверьте работу программы минимум на 3 предложениях, чтобы охватить проверку всех поставленных условий.

```python
import re

txt = input('Введите текст: ')
chars = ['a', 'e', 'i', 'o', 'u']
charsCount = 0

for i in txt:
    if i in chars:
        charsCount += 1

print(f'Всего символов: {len(txt)}')
print(f'Тескт в нижнем регистре: {txt.lower()}')
print(f'charsCount)
print(re.sub('ugly', 'beauty', txt))
print(txt.startswith('The') and txt.endswith('end'))
```
#### Результат.
 
![Меню](https://github.com/4a11/SI/blob/main/pic/sam3_4.png)


### Задание 5
Составьте программу, результатом которой будет данный вывод в консоль:


![Меню](https://github.com/4a11/SI/blob/main/pic/sam3_num1.png)


Программу нужно составить из данных фрагментов кода:


![Меню](https://github.com/4a11/SI/blob/main/pic/sam3_num2.png)


```python
counter = 0
string = 'hello'
memory = ' world'
values = [0, 2, 4, 6, 8, 10]

while counter != 10:
    if counter in values:
        print(string + memory)
        print(string)

    counter += 1

string = string + ' world'
memory = string

print(memory)
```
#### Результат.

![Меню](https://github.com/4a11/SI/blob/main/pic/sam3_5.png)

