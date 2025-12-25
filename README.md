# a-two-dimensional-array-of-fifteen-rows-and-two-columns
Дано двовимірний масив з п'ятнадцяти рядків і двох стовпців. Знайти номера двох сусідніх рядків, сума елементів в яких мінімальна. Відсортувати кожен рядок масиву за зростанням (функція).
# Функція знаходить номери двох сусідніх рядків з мінімальною сумою елементів
    def find_min_sum_rows(matrix):
    min_sum = matrix[0][0] + matrix[0][1] + matrix[1][0] + matrix[1][1]
    index = 0

    # Перевірка всіх пар сусідніх рядків
    for i in range(1, 14):
        s = matrix[i][0] + matrix[i][1] + matrix[i+1][0] + matrix[i+1][1]
        if s < min_sum:
            min_sum = s
            index = i

    # Повертаємо номери рядків (нумерація з 1)
    return index + 1, index + 2


# Функція сортує кожен рядок масиву за зростанням
    def sort_rows(matrix):
       for row in matrix:
        row.sort()



# Введення двовимірного масиву 15×2
    matrix = []

    print("Введення масиву 15x2")

    for i in range(15):
    row = []
    for j in range(2):
        value = float(input(f"Введіть елемент [{i+1}][{j+1}]: "))
        row.append(value)
    matrix.append(row)

    r1, r2 = find_min_sum_rows(matrix)
    print("Рядки з мінімальною сумою:", r1, r2)

# Сортування рядків та виведення результату
    sort_rows(matrix)

    print("Відсортований масив:")
    for row in matrix:
      print(row)

    input("Натисніть Enter для завершення...")
