# Lección 3 — Soluciones

## Ejercicio 1: Implementa una clase con herencia múltiple

```python
class Base1:
    def method1(self):
        return "Base1 method"

class Base2:
    def method2(self):
        return "Base2 method"

class Derived(Base1, Base2):
    def combined_method(self):
        return f"{self.method1()} and {self.method2()}"

derived = Derived()
print(derived.combined_method())  # Output: Base1 method and Base2 method
```

## Ejercicio 2: Usa mypy para verificar tipos en un script

Escribe un script `example.py`:

```python
def add(x: int, y: int) -> int:
    return x + y
```

Ejecuta:

```
$ mypy example.py
```

Si no hay errores, significa que los tipos son correctos.

## Ejercicio 3: Crea un generador para números pares

```python
def even_numbers(max):
    num = 0
    while num <= max:
        yield num
        num += 2

for number in even_numbers(10):
    print(number)  # Output: 0, 2, 4, 6, 8, 10
```

## Ejercicio 4: Implementa un iterador personalizado

```python
class RangeIterator:
    def __init__(self, start, end):
        self.current = start
        self.end = end

    def __iter__(self):
        return self

    def __next__(self):
        if self.current > self.end:
            raise StopIteration
        else:
            self.current += 1
            return self.current - 1

for i in RangeIterator(1, 5):
    print(i)  # Output: 1, 2, 3, 4, 5
```

## Ejercicio 5: Refactoriza una función utilizando un decorador

```python
def my_decorator(func):
    def wrapper():
        print("Before function call")
        func()
        print("After function call")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
# Output:
# Before function call
# Hello!
# After function call
```
