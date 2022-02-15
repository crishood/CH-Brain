# Curso de Manipulación del DOM

Created: February 10, 2022 4:38 PM
Minded: No
Tag: Platzi, code, computer science, web

# ****¿Qué es el DOM?****

**Critical Rendering Path** Es el proceso que se encarga de convertir en pixeles el HTML, CSS y JS.

El **DOM** es un árbol modificable que representa el HTML. 

El **CSSOM** es el árbol para el CSS.

![Untitled](Curso%20de%20Manipulacio%CC%81n%20del%20DOM%208b59be9419b84d8c978e7d0bedab66a4/Untitled.png)

# ****Web APIs modernas****

Combinar el DOM + JS = Web API.

Una API es un puente que comunica dos pedazos de software.

![Untitled](Curso%20de%20Manipulacio%CC%81n%20del%20DOM%208b59be9419b84d8c978e7d0bedab66a4/Untitled%201.png)

# ****Leer nodos****

Los reyes de internet. 

```jsx
document.getElementById()
parent.getElementByTagName()
parent.getElementByClassName()
```

Lo mejor para leer nodos en producción es

```jsx
parentElement.querySelector()
parentElement.querySelectorAll()
```

El query selector nos permite seleccionar cualquier cosas

Ejemplo

```jsx
document.querySelector('#address')
```

# Nodelist vs Array

Al usar `document.querySelectorAll()` JS nos retorna un NodeList en lugar de un array.

El nodelist carece de operaciones que tienen los arrays como `.map`, `.filter`, `.reduce`

```jsx
// De esta forma pasamos todos los elementos en el NodeList a un arreglo al cual si podremos usar los métodos filter, map, reduce entre otros. 
const nodeList = document.querySelectorAll("selector css");
const elementList = [...nodeList];
```

Recomendación importante cada vez que obtengamos un NodeList pásemelo a Array ya que los motores de javascript como el motor V8 de google están mas optimizados para Arrays que para NodeList.

# Crear y agregar nodos

```jsx
document.createElement('h4')
document.createTextNode('Texto')
```

```jsx
document.appendChild()
document.append()
document.insertBefore()
document.insertAdjacentElement()
```

```jsx
const container = document.querySelector('div.py-5')
const h3 = document.createElement('h3')
container.appendChild(h3)
const text = document.createTextNode('Verde')
h3.appendChild(text)
```

appendChild agrega nodos al final.

## node.append

Es la evolución de appendChild.

1. Puedes agregar más de un nodo.
2. Puedes agregar texto.
3. IE 11: No soportado.

```jsx
container.append('Dímelo...', document.createElement('div'))
```

## insertBefore

```jsx
const titulo = document.createElement('h1')
const referencia = document.querySelector('h2')
container.insertBefore(titulo, referencia)
```

## insertAdjacentElement

```jsx
referencia.insertAdjacentElement('beforebegin',NUEVO_NODO)
referencia.insertAdjacentElement('afterbegin',NUEVO_NODO)
referencia.insertAdjacentElement('beforeend',NUEVO_NODO)
referencia.insertAdjacentElement('afterend',NUEVO_NODO)
```

# Otras formas de agregar nodos

Existen otras formas de agregar nodos:.

- `node.outerHTML`: Sirve para leer HTML para leer HTML
- `node.innerHTML:` Sirve para escribir HTML

.PEEEEEEERO, tienen un problema de seguridad 👀☝️ **hack:** Cuando en el inspector de elementos seleccionas un elemento y en la consola escribes `$0`, este te devolverá el elemento tal como si lo hubieses seleccionado con `document.querySelector()`

El problema con estas formas de inserciones es que permiten la inserción XSS, es decir, código maligno, y cualquier usuario programador malicioso podría meter scripts molestos, imagina que cada que un usuario llegue a tu página le salga un alert… ¡Sería catastrófico! Siempre sanitiza (remover caracteres especiales) los inputs de tus usuarios.

# Atributos y propiedades

Los atributos son valores adicionales a las etiquetas HTML que ajustan su comportamiento a las necesidades del usuario.

`<h1 id=”main-title”></h1>`

En este caso id es un atributo de la etiqueta h1.

La propiedad es la variable que podemos cambiar por medio de JS.

# Eliminar Nodos

Hay tres maneras de eliminar nodos:

```jsx
parentElement.removeChild()
document.remove() //No es soportado por IE, no depende del padre
document.replaceChild(nuevoNodo, aRemplazar)
```

Utiliza el método `parentElement()` para obtener el padre del elemento seleccionado.

# Operaciones en lote

Crear o eliminar nodos al DOM es una operación costosa. Hay que tratar de ejecutarla la menor cantidad de veces dentro de nuestro código.

Por ejemplo si queremos agregar 100 elementos al DOM podemos hacer de entrada lo siguiente:

```jsx
for(let i = 0; i<100; i++){
	const node = document.createElement('p')
	document.body.appendChild(node)
} 
```

```jsx
const nodos = []
for(let i = 0; i<100; i++){
	const node = document.createElement('p')
	nodos.push(node)// Tenemos los 100 elementos en la memoria de JS
} 
document.body.append(...nodos)// Usamos el spread operator para que muestre todos los elementos del vector
```

# ****Reaccionar a lo que sucede en el DOM****

La magia de JS está en la interacción, y esta sucede gracias a los eventos.

Los eventos necesitan de estos dos métodos:

```jsx
//Para añadir un evento usamos el método con la siguiente estructura
node.addEventListener('click', () => {...funcion})

//Para eliminar un elemento es necesario que este tenga un nombre por lo cual
//es recomendable no usar funciones anónimas cuando tengamos la intención
//de borrarlas.
node.removeEventListener('click', accion)
```

```jsx
// Ejemplo de listener para inputs de HTML
// Al recibir una entrada de texto se va a ejecutar una función anónima
// que recibe como parametro los datos del evento en la variable event
input.addEventListener('input', (event) => {
	console.log(event)	
	})
```

# Propagación de eventos

Los eventos suceden desde el elemento más pequeño hacia afuera. Si doy click en un botón que tiene un listener, el evento se va a propagar a cada uno de los padres que estén afuera.

![Untitled](Curso%20de%20Manipulacio%CC%81n%20del%20DOM%208b59be9419b84d8c978e7d0bedab66a4/Untitled%202.png)

Este fenómeno se le conoce como *“bubbling”*.

Para detener la propagación de eventos agregamos el siguiente método:

 

```jsx
div3.addEventListener("click", (event) => {

    event.stopPropagation()

});
```

# Delegación de eventos

La delegación de eventos es básicamente un contenedor padre que le pasa el evento a todos sus hijos (en realidad no se los está pasando, sino que el contenedor padre sigue estando presente en todos los hijos, es por eso que cuando clicamos a un hijo el evento es disparado).

Entendiendo esto, cuando obtenemos el target podemos saber cuál elemento hijo del padre fue clicado, por tanto, con una simple condicional puede ver si el elemento clicado es el que yo quiero.

**Ojo:**

Eso no significa que el evento se quite de los demás elementos hijos, si tu clicas cualquier otro elemento hijo el evento se va a disparar sí o sí, pero lo que sucede es que la condición del target no se cumple, por eso no hace nada.

Y sabiendo esto, puedes hacer cosas chulas como crear funciones que escuchen eventos dinámicamente, una característica de los eventos es que solo se le aplican a los elementos que están desde el inicio, pero si tu agregas otro nodo desde JavaScript **los eventos no se van a escuchar para ese nuevo nodo.**

Entonces, una técnica que se suele usar es escuchar al padre (o en ocasiones a todo el document) y cada vez que el evento ocurra buscar a todos sus hijos que coincidan con el selector al que queremos aplicarle el evento, de esta forma no importa si los nodos se añaden posteriormente desde JavaScript, el evento será escuchado pues JavaScript directamente irá a buscar todos los nodos hijos que cumplan con dicho selector.

# **Intersection Observer API**

El intersection observer es una API para observar los objetos que están en pantalla. Observamos cuando un objeto se intersecta con el viewport que es la pantalla visible.