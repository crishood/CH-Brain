# Python

Created: December 29, 2021 6:00 PM
Minded: Yes
Tag: #Platzi, #code, #datascience

## ¿Qué es Python?

Python is an easy to learn, powerful programming language. It has efficient high-level data structures and a simple but effective approach to object-oriented programming. Python’s elegant syntax and dynamic typing, together with its interpreted nature, make it an ideal language for scripting and rapid application development in many areas on most platforms.

## Empezando un script con Python

Muchos lenguajes de programación tienen una función especial que se ejecuta cuando el sistema empieza a correr un programa. Sin embargo Python no tiene esta función y lo que hace es empezar a correr el código desde la primera línea del archivo.

Crear una función principal es una buena práctica que nos ayuda a entender como funciona un programa.

```python
# Otras funciones que serán llamadas en orden desde la función main()
def main():
    pass

if __name__ == "__main__":
    main()
```

### Buenas prácticas con Python

Estas son buenas prácticas para hacer scripts:

1. Coloca la mayoría de código en clases o funciones.
2. Usa `__name__` para controlar la ejecución de tu código.
3. Crea una función llamada `main()` para contener el código que quieres ejecutar.
4. Llama las otras funciones del código desde `main()`.
5. Deja dos líneas de espacio entre función y función.

## Bucles

### While

Este es el “Bucle fundamental” porque está presente en casi todos los lenguajes de manera nativa.

El ciclo *while* tiene un límite constante. Para definir una constante en Python le asignamos un nombre en mayúsculas definidas.

```python
		LIMITE = 1000
    contador = 0
    potencia_2 = 2**contador
    while potencia_2 < LIMITE:
        print('2 elevado a ' + str(contador) + ' es igual a: ' + str(potencia_2))
        contador = contador + 1
        potencia_2 = 2**contador
```

### For

El bucle for recorre un rango que podemos definir mediante el tipo de dato `range()`

```python
for contador in range(1000):
        print(contador)
```

Por otro lado `range()` también recibe dos parámetros para funcionar como un intervalo. Algo así como te quiero de `range(0,3000)` 🥰

El bucle *for* es importante para recorrer una cadena de caracteres.

```python
#recorrer los caracteres
    nombre = input('Dame tu nombre bb: ')
    for letra in nombre:
        print(letra)
```

### Break & Continue

Comandos para romper bloques

```python
#break-continue
    for contador in range(100):
        if contador % 2 != 0:
            continue
        print(contador)
```

```python

    for i in range(100):
        if i == 83:
            break
```

### Módulos

Un módulo de Python es un paquete escrito por las personas que hicieron Python que añade funciones extra.

```python
import random
```

## Estructuras de datos

Son formas que nos brindan los lenguajes de programación para guardar varios datos dentro de una estructura.

### Listas

Las listas son vectores

```python
# Listas
lista_de_cosas = [1, 44, 'CrisHood', True]

# Agregar objetos a la lista
lista_de_cosas.append(32)

# Quitar objetos de la lista
lista_de_cosas.pop(3)

# Recorrer lista
for elemento in objetos:
	print(elemento)

# Slices
lista_de_cosas[::-1]
```

### Tuplas

Las listas son dinámicas, las tuplas no, estas son estáticas y ahorran memoria. Las tuplas son inmutables.

```python
mi_tupla = (1,2,3)
```

### Diccionarios

Los diccionarios son como objetos `json`

```python
# Declara un diccionario
mi_diccionario = {
        'llave1': 1,
        'llave2': 2,
        'llave3': 3,
    }
# Imprime el valor de un diccionario
print(mi_diccionario['llave1'])

# Recorre el diccionario con ciclos for
    for llaves in mi_diccionario.keys():
        print(llaves)

    for num in mi_diccionario.values():
        print(num)
    
    for llaves, num in mi_diccionario.items():
        print(llaves + ' ' + str(num))
```

## Notación de slices

```python
a[start:stop]  # items start through stop-1
a[start:]      # items start through the rest of the array
a[:stop]       # items from the beginning through stop-1
a[:]           # a copy of the whole array
a[start:stop:step] # start through not past stop, by step
a[-1]    # last item in the array
a[-2:]   # last two items in the array
a[:-2]   # everything except the last two items
a[::-1]    # all items in the array, reversed
a[1::-1]   # the first two items, reversed
a[:-3:-1]  # the last two items, reversed
a[-3::-1]  # everything except the last two items, reversed
```

## Zen de Python

El Zen de Python se compone por los principios para escribir tu código de manera clara, sencilla y precisa. Estos son:

- **Bello es mejor que feo**:Pyhton es estéticamente superior a cualquier otro lenguaje de programación. Al momento de escribir código, es mejor que sea de manera limpia y estética.
- **Explícito es mejor que implícito**:Hacer más fácil que las otras personas entiendan el código.
- **Simple es mejor que complejo**: Es mejor tener una implementación simple, que ocupe pocas líneas de código y sea entendible, a que sea una larga y complicada.
- **Complejo es mejor que complicado**: Si tenemos que extendernos en la implementación y hacerla más compleja para que el código si se entienda, esto es mejor que hacerlo simple y mal.
- **Plano es mejor que anidado**: El *anidamiento* es cuando tenemos un bloque de código dentro de otro bloque de código (dependiendo de este). Esto se nota en Python por la identación, nos quedarían estos bloques muy corridos a la derecha. Es mejor evitar el anidamiento, y hacer las cosas de **manera plana**.
- **Espaciado es mejor que denso**: Por la identación de Python (sus sangrías), este principio se nos hace imposible de esquivar. El código inevitablemente es espaciado.
- **La legibilidad es importante**: Es importante que otros programadores puedan entender lo que estamos escribiendo. Esto hace más fáciles las cosas cuando trabajemos con otros en los proyectos.
- **Los casos especiales no son lo suficientemente especiales como para romper las reglas (sin embargo, la practicidad le gana a la pureza)**: Siempre que podamos respetar estas reglas que nos plantea Python, es mejor así. Sin embargo, si por el hecho de hacer un código muy puro o muy ‘Pythonista’, este pierde legibilidad, es mejor ser más prácticos y romper o saltearnos algunas de estas reglas para que el código sea más eficiente. Por lo tanto, llegado el momento debemos decidir si es mejor hacer las cosas de manera pura o práctica.
- **Los errores nunca deberían pasar silenciosamente (a menos que se silencien explícitamente)**: Manejar los errores es fundamental. Cada error nos dice algo y hay que prestarle atención. A menos que seas capaz de silenciar un error explícitamente, aunque para esto hay que tener criterio.
- **Frente a la ambiguedad, evitar la tentación de adivinar**:Nuestro código debería solamente tener una interpretación. Si en un contexto significa algo, y en otro otra cosa, es mejor que lo revisemos y busquemos una solución.
- **Debería haber una, y preferiblemente sola, una manera obvia de hacerlo. (A pesar de que esa manera no sea obvia a menos que seas holandés)**: Esto hace referencia al creador de Python ''Guido van Rossum", que de manera muy inteligente encontrar las soluciones precisas a los problemas, y deberíamos imitarlo.
- **Ahora es mejor que nunca**: Es mejor desarrollar nuestra solución cuánto antes, no dejarlo para mañana o para mas adelante.
- **A pesar de que nunca es muchas veces mejor que *ahora* mismo**: Si por hacer las cosas ya y tenemos poco tiempo, si es mejor dejarlo para después y no hacerlo apurado y mal.
- **Si la implementación es difícil de explicar, es una mala idea, y si es fácil de explicar, es una buena idea**: Si somos capaces de explicar nuestra implementación a otros desarrolladores paso a paso, es una buena idea. En cambio si no podemos hacerlo, significa que ni nosotros entendemos la implementación y deberíamos repensar nuestra forma de encarar la solución.
- **Los espacios de nombres son una gran idea, ¡Tengamos más de esos! (namespaces):** Es el nombre que se ha indicado luego de la palabra import, es decir la ruta (namespace) del módulo. (Lo veremos a profundidad más adelante).

## Creando un ambiente virtual con VENV

Creación de ambiente Virtual:

`python3 -m venv nombre_venv`

- Usualmente el nombre del ambiente virtual es venv.

Activación del ambiente virtual:

- Windows:

`.\venv\Scripts\activate`

- Unix o MacOS:

`source venv/bin/activate`

Desactivar el ambiente virtual:

`deactivate`

Crear un alias en linux/mac:

`alias nombre-alias="comando"`

Crear un archivo de requerimientos

`pip **freeze** > requirements.txt`

## Alternativas a los ciclos: Comprehensions

### List Comprehensions

[ element for element in iterable if condition ]

¿Cómo leer el comprehension?

En mi lista yo voy a guardar:

Para cada elemento en el iterable, ese elemento, solo si se cumple la condición.

**element** → Cada uno de los elementos a poner en la nueva lista

**for element in iterable** → Ciclo a partir del cual se extraerán elementos en otra lista o cualquier iterable

**if condition** → Condición opcional para filtrar los elementos del ciclo

```python
squares = [i**2 for i in range(1,101) if i % 3 != 0]
```

![Untitled](Root/Cursos/Computer%20Science/Python/Untitled.png)

### **Dictionary comprehensions**

Es muy parecido a las list comprehensions:

```python
dictionay_naturals = {i: i**3 for i in range(1, 101) if i % 3 != 0}
```

**Estructura:**

`{key: value for element in iterable if condition}`

```python
my_dic = {i: math.sqrt(i) for i in range (1, 1001)}
```

## Lambdas

Son funciones anónimas en una sola línea de código.

```python
lambda argumentos: expresión
```

### **High order functions: filter, map y reduce**

Una función de orden superior es una función que recibe de parámetro otra función.

Filter: Filtra listas

Map: Convertir listas en una lista con otros elementos

Reduce: Transformar una lista en un sólo valor. Reduce se importa de functools.

```python
from functools import reduce
```

![Untitled](Root/Cursos/Computer%20Science/Python/Untitled%201.png)

## Manejo de errores

### Tipo de errores

![Untitled](Root/Cursos/Computer%20Science/Python/Untitled%202.png)

El traceback que es la traza del error se lee de abajo hacia arriba.

### Debugging

El debugging o depuración es una herramienta.

> *Importante: El debugging funciona bien cuando se selecciona bien la carpeta. Para hacer proyectos en WSL hay que usar la carpeta /home/sircrishood/ para los proyectos.*
> 

Breakpoint: Es un punto donde el programa se detiene. Se coloca usando el punto rojo de la columna izquierda del editor.

### Manejo de excepciones

- try except → Anidamos nuestro programa en dos bloques de código, el primero es el programa per se (el que se ejecuta normalmente, sin errores) y el segundo representa las instrucciones a seguir en caso de error. Su sintaxis es:
    
    ```python
    try:
    	<bloque1>
    except <error> as <alias>:
    	<bloque 2>
    
    ```
    
    - `<error>` es un parámetro opcional, permite capturar sólo el tipo de error indicado, si no se coloca captura todos los errores posibles (es buena práctica capturar cada tipo de error por separado)
    - `as <alias>` nos permite crear un alias al error, para trabajar con él.
- raise → Esta instrucción nos permite generar errores, es decir crear nuestros propios errores cuando detectemos que nuestro programa no actúa como debería con cierto tipo de datos. Su sintaxis es:
    
    ```python
    raise <NombreError>("<descripci[on del error>")
    ```
    
- finally → Es una bloque de código que se ejecuta exista un error o no (un tercer bloque después de try except), no es muy usual pero puede darse para cerrar archivos, conexiones a BBDD o liberar recursos.

## **Assert statements**

Al Sweigart en su libro “How to automate the boring stuff with Python” se las comparto:

> *In plain English, an assert statement says, “I assert that this condition holds true, and if not, there is a bug somewhere in the program.” Unlike exceptions, your code should not handle assert statements with try and except; if an assert fails, your program should crash. By failing fast like this, you shorten the time between the original cause of the bug and when you first notice the bug. This will reduce the amount of code you will have to check before finding the code that’s causing the bug. Assertions are for programmer errors, not user errors. For errors that can be recovered from (such as a file not being found or the user enter-ing invalid data), raise an exception instead of detecting it with an assert statement.*
> 

Los assert statements son afirmaciones

```python
assert condicion, error
```

¿Cómo se lee?

Afirmo que esta condición es verdadera, si no, imprimo este mensaje de error.

## Archivos

Los archivos son de dos tipos:

1. Texto: Tienen bytes que representan letras y símbolos. `.txt .js .xml .csv .json`
2. Binarios: Tienen bytes que representan datos más complejos como imagen y sonido. `.mp3 .mov .png`

Por lo general vamos a editar archivos de texto.

Los archivos tienen tres modos de apertura:

1. R → Lectura
2. W → Escritura (Sobreescribiendo)
3. A → Escritura (Añadiendo al final)

Existen varias extensiones de archivos con los que podemos interactuar con python.

Para abrir un archivo seguimos las siguiente estructura:

```python
with open(<ruta>, <modo_apertura>)as <nombre>
```

`with` Es un manejador contextual, nos ayuda a controlar el flujo del archivo (sirve para que el archivo no se dañe cuando existe algún cierre inesperado)

`open(ruta , modo_apertura)`: es una función que necesita de dos parámetros

- `ruta`: es donde se encuentra nuestro archivo en nuestro equipo
- `modo_de_apertura`: como vamos a abrir el archivo, los modificadores son:
    - r → modo de lectura
    - w → modo de escritura (sobrescribe el archivo)
    - a → modo append (añade información al final del archivo)

`as <nombre>` nos ayuda a darle una abreviatura o un nombre a los datos que acabamos de leer

```python
with open('./archivos/numbers.txt', 'r', encoding='utf-8') as f:
```

# Módulos y Paquetes

Un módulo es cualquier archivo con extensión `.py` y un paquete es un conjunto de módulos. Estos sirven para crear código reutilizable.

En este caso `exploracion_espacial` es la carpeta del paquete.

![Untitled](Root/Cursos/Computer%20Science/Python/Untitled%203.png)

# Tipos de lenguajes

Compilados → Los que se comunican directamente con la máquina. Como C/C++

Interpretados → Como Python o Javascript que se comunican con un intérprete primero. 

Tipados → Como un lenguaje trata a los tipos de datos

- Estático
- Dinámico
- Débil
- Fuerte

![Untitled](Root/Cursos/Computer%20Science/Python/Untitled%204.png)

El tipado del lenguaje depende de cómo trata a los tipos de datos.

El tipado estático es el que levanta un error en el tiempo de compilación, ejemplo en JAVA:

```java
String str = "Hello" // Variable tipo String
str = 5 // ERROR: no se puede convertir un tipo de dato en otro de esta forma.

```

El tipado dinámico levantan el error en tiempo de ejecución, ejemplo en Python:

```python
str = "Hello" # Variable tipo String
str = 5 # La variable ahora es de tipo Entero, no hay error

## TIPADO FUERTE
x = 1
y = "2"
z = x + y # ERROR: no podemos hacer estas operaciones con tipos de datos distintos entre sí

```

El tipado débil es el que hace un cambio en un tipo de dato para poder operar con el, como lo hace JavaScript y PHP.

🐍 Python es un lenguaje de tipado 👾 Dinámico y 💪 Fuerte.

# **Tipado estático en Python**

Static Typing → Añadir sintaxis adicional

```python
# Variables
a: int = 5
b: str = 'Hola'
c: bool = True

def suma(a: int, b: int) -> int :
	return a + b

# Para trabajar con Diccionarios y Listas tipadas
from typing import Dict, List

positives: List [int] = [1,2,3,4,5]

users: Dict [str, int] = {
	"argentina": 1.
	"mexico": 34,
	"colombia": 45,
}

countries: List[Dict[str, str]] = [
	{
		"name" : "Argentina",
		"people" : "45000",
	},
	{
		"name" : "México",
		"people" : "9000000",
	},
	{
		"name" : "Colombia",
		"people" : "99999999999",
	}
]

# Para trabajar con tuplas tipadas
from typing import Tuple, Dict, List

# Podemos crear un tipado reutilizable
CoordinatesType = List[Dict[str, Tuple[int, int]]]

coordinates: CoordinatesType = [
	{
		"coord1": (1,2),
		"coord2": (3,5)
	},
	{
		"coord1": (0,1),
		"coord2": (2,5)
	}
]
```

### Modulo `mypy`

El modulo mypy se complementa con el modulo typing ya que permitirá mostrar los errores de tipado debil en Python.

### Ventajas

Código más legible y que veamos los errores más profundos de entrada.

# Scope

El scope es el alcance que tienen las variables. Depende de donde declares o inicialices una variable para saber si tienes acceso. **Regla de oro:**

> una variable solo esta disponible dentro de la region donde fue creada
> 

### Local Scope

Es la región que corresponde el ámbito de una función, donde podremos tener una o mas variables, las variables van a ser accesibles únicamente en esta region y no serán visibles para otras regiones

### Global Scope

Al escribir una o mas variables en esta region, estas podrán ser accesibles desde cualquier parte del código.

![https://static.platzi.com/media/user_upload/Untitled-5d8878b2-048d-4017-a0de-a582e3f494d5.jpg](https://static.platzi.com/media/user_upload/Untitled-5d8878b2-048d-4017-a0de-a582e3f494d5.jpg)

# Nested functions & closures

**Nested functions →** Funciones anidadas → Una función dentro de otra función

Reglas para encontrar un closure

1. Debemos tener una nested function
2. La nested function debe referenciar un valor de un scope superior
3. La función que envuelve la nested debe retornarla también

Usamos closures cuando tenemos una clase que tiene solo un método y cuando trabajamos con decoradores.

```python
def make_multiplier(x):

    def multiplier(n):
        return x * n

    return multiplier

times10 = make_multiplier(10)
times4 = make_multiplier(4)

print(times10(1)) # 10
print(times10(3)) # 30
print(times4(5)) # 16
print(times10(times4(2))) # 80
```

# Decoradores

Un decorador es un closure especial.

Un decorador es una función que recibe como parámetro otra función, le añade cosas, la decora, la enriquece y devuelve otra función diferente.

## Azúcar sintáctica → Sugar Syntax

Esta azúcar la vemos en el código embellecido y estético.

```python
def mayusculas(func):
    def envoltura(texto):
        return func(texto).upper()
    return envoltura

# Usar el @ para llamar a la función decoradora es un truco de sugar syntax
@mayusculas
def mensaje(nombre):
    return f'{nombre}, recibiste un mensaje'

print(mensaje('Xiomara'))
```

***args y **kwargs**

```python
from datetime import datetime

def execution_time(func):
    def wrapper(*args, **kwargs):
        initial_time = datetime.now()
        func(*args, **kwargs)
        final_time = datetime.now()
        time_elapsed = final_time - initial_time
        print('Pasaron' + str(time_elapsed.total_seconds()) + ' segundos')
    return wrapper

@execution_time
def random_func():
    for _ in range(1, 1000000):
        pass

@execution_time
def suma (a: int, b: int) -> int:
    return a + b

suma(5, 5)
random_func()
```

# Iteradores

Una estructura de datos para guardar datos infinitos.

Los iterables son los objetos que podemos recorrer en un ciclo for como una cadena de caracteres o una lista.

Todos los iterables se convierten en iterador para poder ser recorridos por los ciclos for del lenguaje.

Para crear iteradores hay que hacer una clase con un constructor y dos métodos.

```python
import time

class FiboIter():
    def __init__(self, max_number:int):
        self.max_number = max_number
    
    def __iter__(self):
        self.n1 = 0
        self.n2 = 1
        self.counter = 0
        return self

    def __next__(self):
        if self.counter == 0:
            self.counter += 1
            return self.n1
        elif self.counter == 1:
            self.counter += 1
            return self.n2
        else:
            self.aux = self.n1 + self.n2
            if self.aux > self.max_number:
                raise StopIteration
            self.n1, self.n2 = self.n2, self.aux
            self.counter += 1
            return self.aux

if __name__ == '__main__':
    fibonacci = FiboIter(144)
    for element in fibonacci:
        print (element)
        time.sleep(0.5)
```

## Ventajas de usar iteradores

Nos permite guardar una cantidad de datos enorme con buen rendimiento porque los iteradores son una función matemática. Los iteradores son el equivalente al svg en diseño.

```python
self.n1 = self.n2
self.n2 = self.aux
self.n1, self.n2 = self.n2, self.aux # Esta línea reemplaza las dos anteriores.
# El primer elemento antes del igual tendrá el valor del primer elemento después del igual.
```

# Generadores

Los generadores son sugar syntax para los iterators. 

Las ventajas de usar generadores es que son más fáciles de escribir que los iterators y que tienen los mismos beneficios. 

```python
def fibo_gen():
    n1 = 0
    n2 = 1
    counter = 0
    while True:
        if counter == 0:
            counter += 1
            yield n1
        elif counter == 1:
            counter += 1
            yield n2
        else:
            aux = n1 + n2
            n1, n2 = n2, aux
            counter += 1
            yield aux

if __name__ == '__main__':
    fibonacci = fibo_gen()
    for element in fibonacci:
        print(element)
        time.sleep(0.5)
```

# Sets

Son colecciones de datos únicos e inmutables. En español se llaman conjuntos.

```python
# set de enteros
my_set = {1, 3, 5}
print(my_set)

# set de diferentes tipos de datos
my_set = {1.0, "Hi", (1, 4, 7)}
print(my_set)
```

```python
#ejemplo de operaciones sobre sets 
my_set = {1, 2, 3} 
print(my_set) #Output {1, 2, 3} 

#añadiendo un elemento al set 
my_set.add(4) 
print(my_set) #Output {1, 2, 3, 4}

#añadiendo varios elementos al set, python ignorará elementos repetidos 
my_set.update([1, 5, 6]) 
print(my_set) #Output {1, 2, 3, 4, 5, 6}

# eliminado elementos del set 
my_set.discard(1) 
print(my_set) #Output {2, 3, 4, 5, 6}

# borrando un elemento aleatorio 
my_set.pop()
print(my_set) #Output el set menos un elemento aleatorio 

#limpiar el set 
my_set.clear()
print(my_set) # Output set()
```

## Operaciones de conjuntos de los sets

```python
# Union
my_set1 = {3,4,'t'}
my_set2 = {5,6,'f'}

my_set3 = my_set1 | my_set2 # {3,4,'t',5,6,'f'}

# Intersección
my_set1 = {3,4,'t'}
my_set2 = {5,4,'f'}

my_set3 = my_set1 & my_set2 # {4}

# Diferencia
my_set1 = {3,4,'t'}
my_set2 = {5,4,'f'}

my_set3 = my_set1 - my_set2 # {3, 't'}

# Diferencia simétrica
my_set1 = {3,4,'t'}
my_set2 = {5,4,'f'}

my_set3 = my_set1 ^ my_set2 # {3,'t',5,'f'}
```

En caso de que quieran hacer operaciones con sets y hacerlo de forma más explícita pueden usar los métodos:

```python
set1.union(set2)
```

```python
set1.symmetric_difference(set2)
```

```python
set1.difference(set2)
```

```python
set1.intersection(set2)
```

# Fechas

```python
import datetime

my_time = datetime.datetime.now() # Ahora

my_day = datetime.datetime.today() # El día de hoy

print(f'Year: {my_day.year}')
```

## Tabla de formato

![Untitled](Root/Cursos/Computer%20Science/Python/Untitled%205.png)

```python
from datetime import datetime

my_datetime = datetime.now()
print(my_datetime)

my_str = mydatetime.strftime('%d/%m/%Y')
print(f'Formato LATAM: {my_str}')
```

## Time zones

Sabemos que en cada país la hora es diferente.

Instalar pytz