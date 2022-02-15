# Curso de Asincronismo con JavaScript

Created: February 12, 2022 6:00 AM
Minded: No
Tag: Platzi, code, computer science, web

# ****Introducción al asincronismo****

JS es un lenguaje de programación asíncrono y no bloqueante con un manejador de eventos conocido como el event loop, implementado en un único hilo para sus interfaces de entrada y de salida.

## ¿Qué es asincronismo?

Es la acción que no ocurre al mismo tiempo. 

Asincronismo es cuando nos asignan una tarea pero no nos dan los materiales para ejecutarla. Podríamos quedarnos esperando el material, pero como somo asíncronos nos ponemos a hacer otras cosas mientras llega lo que necesitamos.

Ejemplo del aeropuerto:

La pista es el hilo.

Tenemos una entrada de aterrizaje y una salida de despegue.

El Event Loop es la torre de control.

## Conceptos importantes

1. **Memory Heap:** Región de memoria libre, normalmente de gran tamaño, dedicada al alojamiento dinámico de objetos. Es compartida por todo el programa y controlada por un recolector de basura que se encarga de liberar aquello que no se necesita.
2. **Pila de ejecución (Call Stack):** La pila de llamadas, se encarga de albergar las instrucciones que deben ejecutarse. Nos indica en que punto del programa estamos, por donde vamos.
3. **Cola de tareas:** Cada vez que nuestro programa recibe una notificación del exterior o de otro contexto distinto al de la aplicación, el mensaje se inserta en una cola de mensajes pendientes y se registra su callback correspondiente.
4. **Eventloop o Loop de eventos:** Cuando la pila de llamadas (call stack) se vacía, es decir, no hay nada más que ejecutar, se procesan los mensajes de la cola. Con cada ‘tick’ del bucle de eventos, se procesa un nuevo mensaje.

![Untitled](Curso%20de%20Asincronismo%20con%20JavaScript%201c0164626b1441a0bbc2cc72a5249f23/Untitled.png)

1. **API:** Interfaz de programación de aplicaciones (Application Programming Interface). Es un conjunto de rutinas que provee acceso a funciones de un determinado software.
2. **Concurrencia:** Cuando dos o más tareas progresan simultáneamente.
3. **Paralelismo:** Cuando dos o más tareas se ejecutan, literalmente, a la vez, en el mismo instante de tiempo.
4. **Bloqueante:** Una llamada u operación bloqueante no devuelve el control a nuestra aplicación hasta que se ha completado. Por tanto el thread queda bloqueado en estado de espera.

# ****Definición Estructura Callback****

Un callback es una función que al crearla le pasamos como parámetro una función.

# Promise

Es mejor hacer promises que hacer un callback hell de condiciones anidadas.

# ****Conociendo Async/await****

Con async y await logramos hacer promesas que se comportan como código síncrono.

Async/await es como **Syntax Sugar**. Es una manera mas *bonita* de hacer lo mismo que estábamos haciendo con .then(). La clave es recordar que si una función regresa un promesa, podemos usar el keyword **await**, que le indicia al navagador: “Espera a que la promesa se resuelva y almacena su resultado en esta variable”. Todo esto toma lugar dentro de una función asíncrona, así que usamos **async** para lograr esto.

# Ventajas y desventajas

**Callbacks:**  

- Ventajas: Simple(una función que recibe otra función). Son universales, corren en cualquier navegador.
- Desventajas: Composición tediosa, anidando cada vez más elementos. Caer en Callback Hell.

**Promesas:** 

- Ventajas: Facilmente enlazables .Then( return… ).Then - Fácil e intuitivo de leer.
- Desventajas: Posible error si no se retorna el siguiente llamado. No corre en todos los navegadores.

**Async-Await:** 

- Ventajas: Se puede usar try-catch . Código más ordenado e intuitivo.
- Desventajas: No corre en todos los navegadores (se requiere un transpilador).