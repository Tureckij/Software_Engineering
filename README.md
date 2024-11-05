# ТЕМА 9. Концепции и принципы ООП
Отчет по Теме #9 выполнил:
- Орлов Данил Александрович
- ПИЭ-22-1

| Задание | Лаб_раб | Сам_раб |
| ------ |---------|---------|
| Задание 1 | +       | +       |
| Задание 2 | +       |         |
| Задание 3 | +       |         |
| Задание 4 | +       |         |
| Задание 5 | +       |         |

знак "+" - задание выполнено; знак "-" - задание не выполнено;

Работу проверили:
- к.э.н., доцент Панов М.А.

## Лабораторная работа №1
### Создайте класс “Car” с атрибутами производитель и модель. Создайте
### объект этого класса. Напишите комментарии для кода, объясняющие
### его работу. Результатом выполнения задания будет листинг кода с
### комментариями.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

my_car = Car('Ваз', '2114')
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/L1.png)

### Выводы

Создали класс “Car” с атрибутами производитель и модель.

## Лабораторная работа №2
### Дополните код из первого задания, добавив в него атрибуты и методы
### класса, заставьте машину “поехать”. Напишите комментарии для кода, объясняющие его работу. Результатом выполнения задания будет
### листинг кода с комментариями и получившийся вывод в консоль.

```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")


my_car = Car('Ваз', '2114')
my_car.drive()
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/L2.png)

### Выводы

добавили метод drive

## Лабораторная работа №3
### Создайте новый класс “ElectricCar” с методом “charge” и атрибутом
### емкость батареи. Реализуйте его наследование от класса, созданного в
### первом задании. Заставьте машину поехать, а потом заряжаться.
### Результатом выполнения задания будет листинг кода с комментариями
### и получившийся вывод в консоль.

```python

class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")


my_car = Car('Ваз', '2114')
my_car.drive()

class ElectricCarRip(Car):
    def __init__(self, make, model, battery_capacity):
        super().__init__(make, model)
        self.battery_capacity = battery_capacity

    def charge(self):
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kwh")


my_electric_car = ElectricCarRip('Zeekr', '1', 80)
my_electric_car.drive()
my_electric_car.charge()
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/L3.png)

### Выводы

Создали новый класс “ElectricCarRip” с методом “charge”
  
## Лабораторная работа №4
### Реализуйте инкапсуляцию для класса, созданного в первом задании.
### Создайте защищенный атрибут производителя и приватный атрибут
### модели. Вызовите защищенный атрибут и заставьте машину поехать.
### Напишите комментарии для кода, объясняющие его работу.
### Результатом выполнения задания будет листинг кода с комментариями
### и получившийся вывод в консоль.


```python

class Car:
    def __init__(self, make, model):
        self._make = make
        self.__model = model

    def drive(self):
        print(f"Driving the {self._make} {self.__model}")


my_car = Car("UAZ", "Bobik")
print(my_car._make)
#print(my_car.__model)
my_car.drive()
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/L4.png)

### Выводы

добавили инкапсуляцию

## Лабораторная работа №5
### Реализуйте полиморфизм создав основной (общий) класс “Shape”, а
### также еще два класса “Rectangle” и “Circle”. Внутри последних двух
### классов реализуйте методы для подсчета площади фигуры. После этого
### создайте массив с фигурами, поместите туда круг и прямоугольник, затем при помощи цикла выведите их площади. Напишите
### комментарии для кода, объясняющие его работу. Результатом
### выполнения задания будет листинг кода с комментариями и
### получившийся вывод в консоль.



```python
# Основной класс Shape с базовым методом area
class Shape:
    def area(self):
        # Метод заглушка, будет переопределен в дочерних классах
        pass

# Класс Rectangle, наследует от Shape
class Rectangle(Shape):
    def __init__(self, width, height):
        # Инициализация ширины и высоты для прямоугольника
        self.width = width
        self.height = height

    def area(self):
        # Метод для вычисления площади прямоугольника
        return self.width * self.height

# Класс Circle, наследует от Shape
class Circle(Shape):
    def __init__(self, radius):
        # Инициализация радиуса для круга
        self.radius = radius

    def area(self):
        # Метод для вычисления площади круга (приближенно)
        return 3.14 * self.radius * self.radius

# Создаем массив с фигурами, помещая туда круг и прямоугольник
shapes = [
    Rectangle(4, 5),  # Прямоугольник с шириной 4 и высотой 5
    Circle(3)         # Круг с радиусом 3
]

# Цикл для вывода площади каждой фигуры в массиве
for shape in shapes:

    print(f"Площадь фигуры: {shape.area()}")


```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/L5.png)

### Выводы

добавили два класса наследника, где переопределили метод area, таким образом применив полиморфизм

## Самостоятельная работа №1
### Самостоятельно создайте класс и его объект. Они должны
### отличаться, от тех, что указаны в теоретическом материале
### (методичке) и лабораторных заданиях. Результатом выполнения
### задания будет листинг кода и получившийся вывод консоли.

```python
class Animal:
    def __init__(self, hp):
        self.hp = hp

    def get_hp(self):
        return self.hp

my_animal = Animal(5)
print(my_animal.get_hp())
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/S1.png)

### Выводы

создание объекта с внутренним состоянием (hp) и метод для доступа к этому состоянию.
  
## Самостоятельная работа №2
### Самостоятельно создайте атрибуты и методы для ранее созданного
### класса. Они должны отличаться, от тех, что указаны в
### теоретическом материале (методичке) и лабораторных заданиях.
### Результатом выполнения задания будет листинг кода и
### получившийся вывод консоли.

```python
class Animal:
    def __init__(self, hp, voice):
        self.hp = hp
        self.voice = voice

    def get_hp(self):
        return self.hp

    def say(self):
        return self.voice

my_animal = Animal(5, "гав гав")
print(my_animal.get_hp())
print(my_animal.say())
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/S2.png)

### Выводы

создаем класс Animal с атрибутами здоровья (hp) и голоса (voice). Метод get_hp() возвращает здоровье, а say() — голос животного.
  
## Самостоятельная работа №3
### Самостоятельно реализуйте наследование, продолжая работать с
### ранее созданным классом. Оно должно отличаться, от того, что
### указано в теоретическом материале (методичке) и лабораторных
### заданиях. Результатом выполнения задания будет листинг кода и
### получившийся вывод консоли.


```python
class Animal:
    def __init__(self, hp):
        self.hp = hp
        self.voice = "я пес"

    def get_hp(self):
        return self.hp

    def say(self):
        return self.voice

class Dog(Animal):
    def __init__(self, hp):
        super().__init__(hp)
        self.voice = "не ем майонез"

my_animal = Animal(5)
my_dog= Dog(10)

print(my_animal.say())
print(my_dog.say())
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/S3.png)

### Выводы

Код создает класс Animal с голосом "я пес" и подкласс Dog, который переопределяет голос на "не ем майонез". При создании экземпляров Animal и Dog, их методы say() выводят разные значения.
  
## Самостоятельная работа №4
### Самостоятельно реализуйте инкапсуляцию, продолжая работать с
### ранее созданным классом. Она должна отличаться, от того, что
### указана в теоретическом материале (методичке) и лабораторных
### заданиях. Результатом выполнения задания будет листинг кода и
### получившийся вывод консоли.

```python
class Animal:
    def __init__(self, hp):
        self.__hp = hp  
        self.voice = "я животное"

    def get_hp(self):
        return self.__hp

    def set_hp(self, new_hp):
        if new_hp >= 0:  
            self.__hp = new_hp
        else:
            print("Значение здоровья не может быть отрицательным")

    def say(self):
        return self.voice

class Dog(Animal):
    def __init__(self, hp):
        super().__init__(hp)
        self.voice = "гав!"

my_animal = Animal(5)
my_dog = Dog(10)

print(my_animal.say())  
print(my_dog.say())      

print(my_animal.get_hp())  
my_animal.set_hp(8)       
print(my_animal.get_hp())  
my_animal.set_hp(-3)
```
### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/S4.png)

### Выводы

создаем класс Animal с закрытым атрибутом здоровья (__hp) и методом say(), возвращающим голос животного. Класс Dog наследует от Animal и изменяет голос на "гав!". Программа выводит голос каждого объекта и изменяет здоровье объекта Animal, проверяя на отрицательные значения.
  
## Самостоятельная работа №5
### Самостоятельно реализуйте полиморфизм. Он должен отличаться, от того, что указан в теоретическом материале (методичке) и
### лабораторных заданиях. Результатом выполнения задания будет
### листинг кода и получившийся вывод консоли.

```python
class Animal:
    def __init__(self, hp, sound="я животное"):
        self.__hp = hp
        self.sound = sound

    def get_hp(self):
        # Получение текущего значения здоровья
        return self.__hp

    def set_hp(self, new_hp):
        if new_hp >= 0:
            self.__hp = new_hp
        else:
            print("Значение здоровья не может быть отрицательным")

    def say(self):
        # Базовый метод возвращает звук животного
        return self.sound

class Dog(Animal):
    def __init__(self, hp, breed="Unknown"):
        # Инициализация с вызовом базового конструктора и добавлением породы
        super().__init__(hp, "гав!")
        self.breed = breed

    def fetch(self):
        # Метод, уникальный для класса Dog
        return f"{self.breed} весело приносит мяч!"


class Cat(Animal):
    def __init__(self, hp, color="Unknown"):
        # Инициализация с вызовом базового конструктора и добавлением цвета
        super().__init__(hp, "мяу!")
        self.color = color

    def climb(self):
        # Метод, уникальный для класса Cat
        return f"{self.color} кошка ловко забирается на дерево!"


animals = [Animal(5), Dog(10, "пес"), Cat(8, "Смурф")]

for animal in animals:
    print(animal.say())
    if isinstance(animal, Dog):
        print(animal.fetch())
    elif isinstance(animal, Cat):
        print(animal.climb())
 
```

### Результат.

![Меню](https://github.com/Tureckij/Software_Engineering/blob/Тема_8/8_module/S5.png)

### Выводы

Код определяет класс Animal с атрибутами здоровья и звука, и его подклассы Dog и Cat, каждый из которых добавляет уникальные атрибуты и методы: fetch() для собак и climb() для кошек. В цикле выводятся звуки всех животных, а для собак и кошек — их уникальные действия.

## Общие выводы по теме
Поработали с классами, их конструкторами, полиморфизмом и инкапсуляцией, а также наследованием.
