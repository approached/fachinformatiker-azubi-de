---
title: Python for programmers
---

# Python for programmers

Dieses Tutorial dient Entwickler die bereits eine Programmiersprache beherrschen.

## Environment

Home: https://www.python.org/
IDE: https://www.jetbrains.com/pycharm/
MacOS: `brew install python@3.9`


## Basis
```python
# Variable
name = 'Andreas' # string can be declared with single or double quotes
age = 20
tax = 0.19

# Casting
i = int(6)    # i will be 6
s = str(5)    # s will be '5'
f = float(9)  # f will be 9.0

# Output
print('My Name is ' + name + ' and i\'m ' + str(age) + ' years old.')
print('The current tax is now: ' + str(int(tax*100)) + '%')

# GetType
print(type(3)) # <class 'int'>
print(type(6.7)) # <class 'float'>
print(type(1j)) # <class 'complex'>
```

## Data Types
* Text Type:	str
* Numeric Types:	int, float, complex
* Sequence Types:	list, tuple, range
* Mapping Type:	dict
* Set Types:	set, frozenset
* Boolean Type:	bool
* Binary Types:	bytes, bytearray, memoryview
* None Type:	NoneType

## If/Else

* Equals: `a == b`
* Not Equals: `a != b`
* Less than: `a < b`
* Less than or equal to: `a <= b`
* Greater than: `a > b`
* Greater than or equal to: `a >= b`

Normal:
```python
a = 10
b = 22
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```

Kurz:
```python
print("A") if 10 > 20 else print("B")
```

## Loops
For:
```python
for x in ['', 'Hans', 'im', 'Glück']:
    print(x)

for x in range(0, 4):
    print(x)

for x in range(4):
    print(x)
```

While:
```python
i = 1
while i < 3:
  print(i)
  i += 1
```

## Input
```python
name = input('Bitte gib den Namen ein: ')
print('Mein Name ist: ' + name)
```

## Random
```python
import random

print(random.randrange(1, 10))
print(random.choice(['Otto', 'Julia']))
```

## Array
Python hat keine eingebaute Unterstützung für Arrays, aber stattdessen können **Python-List** verwendet werden.

List:
```python
list = ["avocado", "banana", "cherry", "pear"]
print(list)
print(type(list))
print(len(list))

mixList = ["foo", 123, False, 4.23]
mixList.append('muh')
print(mixList)
print(type(mixList))
print(len(mixList))
```

Tuple:
Ein Tupel ist eine Sammlung, die geordnet und unveränderlich ist.
Tupel werden mit runden Klammern geschrieben.
```python
list = ("avocado", "banana", "cherry", "pear")
print(list)
print(type(list))
print(len(list))
```

Set:
Ein Set ist eine Sammlung, die ungeordnet, unveränderbar* und unindiziert ist.
Mengen können nicht zwei Elemente mit demselben Wert enthalten.
```python
list = {"avocado", "banana", "cherry", "pear", "avocado"}
print(list)
print(type(list))
print(len(list))
```

Dictionary:
Wird verwendet um Datenwerte in Schlüssel:Wert-Paaren zu speichern.
```python
person = {
  "name": "Julia",
  "is_programmer": False,
  "age": 1964
}
print(person)
print(type(person))
print(len(person))
```

## Funktion
```python
def helloMyFrind(name, isProgrammer = True):
  print("Hello " + name)
  if isProgrammer:
      print('Nice that your also a programmer')

helloMyFrind("Jonas")
```

## Lambda
Bei einer Lambda-Funktion handelt es sich um eine kleine anonyme Funktion. Der Vorteil von Lambda-Funktionen liegt in der Möglichkeit, in anderen Funktionen wiederverwendet zu werden.
```python
import datetime

today = datetime.date.today()
todayYear = today.year

# example 1
getBirthdayYear = lambda age: todayYear - age
print(getBirthdayYear(30))

# example 2
def getBirthday(age):
  return lambda fromYear: fromYear - age
getBirthdayCalculation = getBirthday(30)
print(getBirthdayCalculation(2000))
```

Reference: https://www.youtube.com/watch?v=uFeHt9LtJXM


## Klassen / Object
```python
class Car:
    def __init__(self, brand):
        self.brand = brand
        self.horse_power = 100

    def more_speed(self):
        self.horse_power = 120

    def __str__(self):
        return f"{self.brand}({self.horse_power})"

audi = Car("Audi")
print(audi.brand)
print(audi.horse_power)
audi.more_speed()
print(audi.horse_power)
print(audi)

# delete
del audi
try:
    audi
except NameError:
    print("object is deleted")
else:
    print("object exists")
```


## Notes

* https://www.w3schools.com/python
* [Python Autoclick](/python-autoclick)
* [Python Charts](/python-charts)
