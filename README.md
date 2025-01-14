# Модуль 6
"Наследование классов"

## Дополнительное практическое задание

Цель: Закрепить полученные знания и навыки, решив задачу повышенной сложности, связанную с наследованием классов.

### Задание "Они все так похожи"

2D, 3D или даже 4D? Мы не будем углубляться в столь сложные измерения, но поэкспериментируем с двумерными и трехмерными фигурами.

Вы когда-нибудь задумывались о том, как устроены графические библиотеки для языков программирования? Конечно, они выполняют сложные расчеты с использованием видеокарты, но что лежит в основе их удобства?

Из названия задачи становится ясно, что все геометрические фигуры обладают схожими свойствами, такими как длина сторон, цвет и другие.

Давайте создадим простые классы для некоторых из этих фигур, используя наследование. В будущем, изучая сторонние библиотеки, вы сможете найти похожие классы, уже написанные другими программистами.

### Общее техническое задание

Необходимо реализовать четыре класса: Figure (родительский), Circle, Triangle и Cube. Объекты этих классов должны обладать методами для изменения размеров, цвета и других свойств.

Многие атрибуты и методы должны быть инкапсулированы, и для них должны быть написаны интерфейсы взаимодействия (методы) — геттеры и сеттеры.

### Подробное техническое задание

#### Атрибуты класса Figure

Класс Figure должен обладать следующим атрибутом: **sides_count** = 0.

Каждый объект класса Figure должен иметь следующие атрибуты:

* **Инкапсулированные атрибуты**: **__sides** — список сторон (целые числа) и **__color** — список цветов в формате RGB.
* **Публичные атрибуты**: **filled** — закрашенность (логическое значение).

И методы:

* **get_color** — возвращает список RGB цветов.
* **__is_valid_color** — служебный метод, принимающий параметры r, g, b. Проверяет корректность переданных значений перед установкой нового цвета. Корректный цвет: все значения r, g и b — целые числа в диапазоне от 0 до 255 (включительно).
* **set_color** — принимает параметры r, g и b в виде чисел и изменяет атрибут **__color** на соответствующие значения, предварительно проверив их корректность. Если введены некорректные данные, цвет остается прежним.
* **__is_valid_sides** — служебный метод, принимающий неограниченное количество сторон. Возвращает True, если все стороны — целые положительные числа и количество новых сторон совпадает с текущим. False — во всех остальных случаях.
* **get_sides** — возвращает значение атрибута **__sides**.
* **__len__** — возвращает периметр фигуры.
* **set_sides(self, *new_sides)** — принимает новые стороны, если их количество равно **sides_count**, то изменяет, в противном случае — не изменяет.

#### Атрибуты класса Circle

Класс Circle должен обладать следующими атрибутами: **sides_count** = 1.

Каждый объект класса Circle должен иметь следующие атрибуты и методы:

- Все атрибуты и методы класса Figure.
- Атрибут **__radius** — рассчитывается исходя из длины окружности (одной единственной стороны).
- Метод **get_square** — возвращает площадь круга (можно рассчитать как через длину, так и через радиус).

#### Атрибуты класса Triangle

Класс Triangle должен обладать следующими атрибутами и методами: **sides_count** = 3.

Каждый объект класса Triangle должен иметь следующие атрибуты и методы:

- Все атрибуты и методы класса Figure
- Метод **get_square** — возвращает площадь треугольника. (можно рассчитать по формуле Герона)

#### Атрибуты класса Cube

Класс Cube должен обладать следующими атрибутами: **sides_count** = 12.

Каждый объект класса Cube должен иметь следующие атрибуты и методы:

- Все атрибуты и методы класса Figure
- Переопределить **__sides**, создав список из 12 одинаковых сторон (передаётся 1 сторона)
- Метод **get_volume** — возвращает объём куба.

ВАЖНО!

При создании объектов проверяйте количество переданных сторон. Если сторон не ровно **sides_count**, создайте массив с единичными сторонами в том количестве, которое требует фигура.

Примеры:

* **Circle((200, 200, 100), 10, 15, 6)** — поскольку у круга всего одна сторона, то его стороны будут — [1].
* **Triangle((200, 200, 100), 10, 6)** — поскольку сторон у треугольника 3, то его стороны будут — [1, 1, 1].
* **Cube((200, 200, 100), 9)** — поскольку сторон (рёбер) у куба 12, то его стороны будут — [9, 9, 9,..., 9] (12).

Вы можете вводить дополнительные атрибуты и методы, но не переусердствуйте!
