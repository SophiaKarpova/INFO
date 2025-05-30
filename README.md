import time

# Переносим функции из test.py сюда
def chek_question(question):
    last_letter = question.find('#')
    cut_question = question[0:last_letter]
    right_answer = question[last_letter + 1]
    answer = input(cut_question)
    return 1 if answer == right_answer else 0

def marks(point):
    if point < 2:
        return 'Ты не прошел'
    elif point >= 3:
        return 'Молодец, вы приняты!'
    else:
        return 'Почти, но нужно больше правильных ответов'

# Основной код
name = input('Введите имя: ')

question1 = "Вопрос 1...#1"
question2 = "Вопрос 2...#2"
question3 = "Вопрос 3...#3"
question4 = "Вопрос 4...#4"

start = time.time()
point = chek_question(question1)
point += chek_question(question2)
point += chek_question(question3)
point += chek_question(question4)
time_taken = round(time.time() - start, 2)

print(f"{name}, ваш результат: {point}/4")
print(f"Время: {time_taken} сек")
print(marks(point))
