# Progrmación orientada a objetos

Created: January 2, 2022 8:45 AM
Minded: Yes
Professors: #AnnCode
Tag: #Platzi, #code

**Objetos**

Los Objetos son aquellos que tienen propiedades y comportamientos, también serán sustantivos (Pueden ser Físicos o Conceptuales).

Las **Propiedades** también pueden llamarse **atributos** y estos también serán sustantivos. Algunos atributos o propiedades son nombre, tamaño, forma, estado, etc. Son todas las características del objeto.

Los **Comportamientos** serán todas las operaciones que el objeto puede hacer, suelen ser verbos o sustantivos y verbo.

**Clase**

Una **Clase** se el modelo por el cual nuestros objetos se van a construir y nos van a permitir generar más objetos.

Analizamos Objetos para crear **Clases**. Las **Clases** son los modelos sobres los cuales construiremos nuestros objetos.

**Abstracción** es cuando separamos los datos de un objeto para generar un molde.

**Modularidad**

La **modularidad** va muy relacionada con las clases y es un principio de la Programación Orientado a Objetos y va de la mano con el Diseño Modular que significa dividir un sistema en partes pequeñas y estas serán nuestros módulos pudiendo funcionar de manera independiente.

La **modularidad** de nuestro código nos va a permitir

- Reutilizar
- Evitar colapsos
- Hacer nuestro código más mantenible
- Legibilidad
- Resolución rápida de problemas

Una buena práctica es separando las clases en archivos diferentes.

**Proceso de POO**

1. Identificar el problema.
2. Identificar los objetos.
3. Definir las clases.
4. Diagramar.

**UML**

| Nombre de la clase | Identidad |
| --- | --- |
| Atributo 1, Atributo 2, Atributo 3 | Estado |
| Operación 1, Operación 2, Operación 3 | Comportamiento |

**Ejemplo**

| Person |
| --- |
| name |
| walk() |

```python
class Person:
     name = “”;
     def walk ( ):
```

**¿Qué es la herencia?**

**Don’t repeat yourself (DRY)** es una filosofía que promueve la reducción de duplicación en programación, esto nos va a inculcar que no tengamos líneas de código duplicadas.

Toda pieza de información nunca debería ser duplicada debido a que incrementa la dificultad en los cambios y evolución

La **herencia** nos permite crear nuevas clases a partir de otras, se basa en modelos y conceptos de la vida real. También tenemos una jerarquía de **padre e hijo**.

Existe la **Superclase** que es la clase padre de las **Subclases**. Estas últimas heredan atributos y comportamientos de la **Superclase**.

**Objetos, método constructor y su sintaxis en código**

Los **objetos** nos ayudan a crear instancia de una clase, el objeto es el resultado de lo que modelamos, de los parámetros declarados y usaremos los objetos para que nuestras clases cobren vida.

Los **métodos constructores** dan un estado inicial al objeto y podemos añadirle algunos datos al objeto mediante estos métodos. Los atributos o elementos que pasemos a través del constructor serán los datos mínimos que necesita el objeto para que pueda vivir.

**En código:**

```python
person = Person ()
```

**Método constructor**

- Da un estado inicial al objeto.
- Tiene el mismo nombre de la clase
- Son los parámetros mínimos que necesita el objeto para que pueda vivir.

**En código:**

```python
def_init_(self, name):
	self.name = name
```

```python
class Student (Person):
```

**Encapsulamiento**

El **Encapsulamiento** es hacer que un dato sea inviolable, inalterable cuando se le asigne un modificador de acceso.

public (Todas las clases)

protected (Clases, paquetes y subclases)

default (Clases y paquetes)

private (Clase a la que pertenece)

**Polimorfismo**

**Polimorfismo →** Muchas formas. Poli = muchas, morfismo = formas.

Es construir métodos con el mismo nombre pero con comportamiento diferente.