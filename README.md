# Bsbdbd

import math

# 5.1 Вычисление функции y(x)
print("Задание 5.1")
x = float(input("Введите значение x: "))
if x < -10:
    y = math.pi * x ** 2
elif -10 <= x < -5:
    y = x ** 4
elif -5 <= x < 10:
    y = math.e * abs(x)
else:
    y = 1 / math.sin(math.sqrt(x))
print(f"y(x) = {y:.3f}")

# 5.2 Найти число, которое находится между двумя другими
print("Задание 5.2")
a, b, c = map(int, input("Введите три числа: ").split())
middle = a if (b < a < c) or (c < a < b) else (b if (a < b < c) or (c < b < a) else c)
print(f"Число, которое находится между двумя другими: {middle}")

# 5.3 Количество дней в месяце с учетом високосного года
print("Задание 5.3")
year, month = map(int, input("Введите год и месяц (например, 2024 2): ").split())
days_in_month = (
    31 if month in {1, 3, 5, 7, 8, 10, 12}
    else 30 if month in {4, 6, 9, 11}
    else 29 if month == 2 and ((year % 4 == 0 and year % 100 != 0) or (year % 400 == 0))
    else 28
)
print(f"Количество дней в месяце: {days_in_month}")

# 5.4 Проверка, можно ли построить треугольник и его тип
print("Задание 5.4")
a, b, c = map(int, input("Введите длины трех сторон треугольника: ").split())
if a + b > c and a + c > b and b + c > a:
    triangle_type = "равносторонний" if a == b == c else "прямоугольный" if a ** 2 + b ** 2 == c ** 2 or b ** 2 + c ** 2 == a ** 2 or c ** 2 + a ** 2 == b ** 2 else "равнобедренный"
    print(f"Можно построить треугольник. Тип треугольника: {triangle_type}.")
else:
    print("Невозможно построить треугольник.")

# 5.5 Битовые операции
print("Задание 5.5")
x, y, operation = input("Введите два числа и операцию (например, 5 3 &): ").split()
x, y = int(x), int(y)
if operation == "&":
    result = x & y
elif operation == "|":
    result = x | y
elif operation == "^":
    result = x ^ y
elif operation == "<<":
    result = x << int(y)
elif operation == ">>":
    result = x >> int(y)
else:
    result = None
print(f"Результат операции: {bin(x)[2:]} {operation} {bin(y)[2:]} = {bin(result)[2:]}")
