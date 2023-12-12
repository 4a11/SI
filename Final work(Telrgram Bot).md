```py
import telebot
from docx.shared import Pt
from telebot import types  # для указание типов
from docx import Document


bot = telebot.TeleBot('token')

name_of_discipline = '',
name_of_cursework = ''
name_of_student = ''
name_of_group = ''
name_of_manager = ''
name_of_city = ''
year = ''


@bot.message_handler(commands=['start'])
def start(message):
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    btn1 = types.KeyboardButton("📋 Создать титульный лист")
    btn2 = types.KeyboardButton("❓ Задать вопрос")
    markup.add(btn1, btn2)
    bot.send_message(message.chat.id,
                     text="Привет, {0.first_name}! Я бот который может помочь тебе с созданием курсовой работы!😁".format(
                         message.from_user), reply_markup=markup)


@bot.message_handler(content_types=['text'])
def func(message):
    if (message.text == "👋 Поздороваться"):
        bot.send_message(message.chat.id, text="Привеет.. Спасибо что читаешь статью!)")
    elif (message.text == "❓ Задать вопрос"):
        markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
        btn1 = types.KeyboardButton("Как меня зовут?")
        btn2 = types.KeyboardButton("Что я могу?")
        back = types.KeyboardButton("Вернуться в главное меню")
        markup.add(btn1, btn2, back)
        bot.send_message(message.chat.id, text="Задай мне вопрос", reply_markup=markup)

    elif (message.text == "Как меня зовут?"):
        bot.send_message(message.chat.id, "Я великий и не повторимы, от которого зависят многие зачетки студентов,"
                                          "я тот о ком ты мечтал ночами, Я наиумнейший бот покуда мой создатель ")

    elif message.text == "Что я могу?":
        bot.send_message(message.chat.id, text="Поздороваться с читателями")

    elif (message.text == "Вернуться в главное меню"):
        markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
        btn1 = types.KeyboardButton("📋 Создать титульный лист курсача")
        btn2 = types.KeyboardButton("❓ Задать вопрос")
        markup.add(btn1, btn2)
        bot.send_message(message.chat.id, text="Вы вернулись в главное меню", reply_markup=markup)

    elif message.text == '📋 Создать титульный лист курсача':
        markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
        back = types.KeyboardButton("Вернуться в главное меню")
        markup.add(back)
        bot.send_message(message.chat.id, text="Хорошо, для начало введите название дисциплины", reply_markup=markup)
        bot.register_next_step_handler(message, create_title)

    else:
        bot.send_message(message.chat.id, text="Екарный бабай, такое я не умею..")


def create_title(message):
    global name_of_discipline
    name_of_discipline = message.text
    bot.send_message(message.chat.id, text=f"Хорошо, название курсовой работы?")
    bot.register_next_step_handler(message, create_header)


def create_header(message):
    global name_of_cursework
    name_of_cursework = message.text
    bot.send_message(message.chat.id, text=f"Хорошо, имя студента?")
    bot.register_next_step_handler(message, get_name_of_student)


def get_name_of_student(message):
    global name_of_student
    name_of_student = message.text
    bot.send_message(message.chat.id, text=f"Хорошо, имя группы?")
    bot.register_next_step_handler(message, get_name_of_group)


def get_name_of_group(message):
    global name_of_group
    name_of_group = message.text
    bot.send_message(message.chat.id, text=f"Имя организатора?")
    bot.register_next_step_handler(message, get_name_of_manager)


def get_name_of_manager(message):
    global name_of_manager
    name_of_manager = message.text
    bot.send_message(message.chat.id, text=f"Название города?")
    bot.register_next_step_handler(message, get_name_of_city)


def get_name_of_city(message):
    global name_of_city
    name_of_city = message.text
    bot.send_message(message.chat.id, text=f"Какой сейчас год?")
    bot.register_next_step_handler(message, get_year)


def get_year(message):
    global year
    year = message.text
    save_file(message)


def save_file(message):
    doc = Document(r'path')

    for paragraph in doc.paragraphs:
        paragraph.font = 'Times New Roman'
        paragraph.text = paragraph.text.replace("name_of_discipline", f"{name_of_discipline}")
        paragraph.text = paragraph.text.replace("name_of_cursework", f"{name_of_cursework}")
        paragraph.text = paragraph.text.replace("name_of_city", f"{name_of_city}")
        paragraph.text = paragraph.text.replace("year", f"{year}")

    for table in doc.tables:
        for row in table.rows:
            for cell in row.cells:
                for paragraph in cell.paragraphs:
                    paragraph.text = paragraph.text.replace("name_of_student", f"{name_of_student}")
                    paragraph.text = paragraph.text.replace("name_of_manager", f"{name_of_manager}")
                    paragraph.text = paragraph.text.replace("name_of_group", f"{name_of_group}")

    for paragraph in doc.paragraphs:
        for run in paragraph.runs:
            font = run.font
            font.name = 'Times New Roman'
            font.size = Pt(14)

    for table in doc.tables:
        for row in table.rows:
            for cell in row.cells:
                for paragraph in cell.paragraphs:
                    for run in paragraph.runs:
                        font = run.font
                        font.name = 'Times New Roman'
                        font.size = Pt(14)

    doc.save(f"changed_patter.docx")
    docc = open('changed_patter.docx', 'rb')
    bot.send_message(message.from_user.id, text=f"Файл сохранен")
    bot.send_document(message.from_user.id,docc)


bot.polling(none_stop=True)
```
