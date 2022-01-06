# Entorno de Trabajo para Ciencia de Datos con Jupyter Notebooks y Anaconda

Created: January 6, 2022 3:05 PM
Minded: Yes
Tag: #computerscience, #datascience, #Platzi

## Introducción

El sistema operativo no importa. Puedes usar el que gustes. Aunque los científicos de datos prefieren usar un sistema Linux. Además, si eres de Windows, existe WSL.

Existen muchas herramientas para programar, pero todas estas tienen algo en común, los Notebooks.

Antes lo habitual para trabajar con Python era escribir un archivo de código, ejecutarlo desde la terminal y si no funcionaba como queríamos, cambiamos el código y lo ejecutamos otra vez (desde el principio).

Un sujeto llamado Fernando Perez comenzó a trabajar en un proyecto llamado IPython. Esta herramienta ampliaba la funcionalidad por defecto del REPL de Python.

El REPL es un componente de Python que significa Read, Evaluate, Print, Loop. IPython añadía otras características adicionales. Con esto el desarrollo de código se convirtió en algo más dinámico.

Este proyecto creció hasta convertirse en los Jupyter Notebooks, que nos permite tener además poder escribir notas en nuestros Notebooks, para documentar de mejor manera. Con Jupyter Notebooks podemos crear reportes de código ejecutables, y no solo están disponibles para Python sino para otros lenguajes, como R o Julia.

**Notebooks VS Scripts**

- Ambos son útiles
- Organización. En un script solo podrás escribir código (máximo podrás usar comentarios). En un Notebook podrás usar texto enriquecido.
- Experimentación y prototipado. Podemos escribir el código primero en un Notebook, probarlo, y si esta bueno, pasarlo a un Script.
- Objetivo

## ¿En qué lugares programar para ciencia de datos?

Google Colab (o simplemente Colab) es una herramienta para crear Notebooks que funciona en el navegador. Para usarla basta con tener una cuenta de Google.

**Notebooks en la nube VS locales**

- Ambos son útiles
- Configuración de entorno. En la nube ya esta todo configurado. En local, la configuración la tiene que hacer tu mismo (aunque no es difícil).
- Tiempos de ejecución. En la nube hay más capacidad de computación.
- Escalabilidad

## Utilizar Deepnote

Deepnote es un servicio en la nube, basado en Jupyter Notebooks, el cuál no requiere configuración y, a diferencia de Colab, trabaja a nivel de proyecto.

Deepnote provee colaboración en tiempo real, integración con múltiples Apps y acceso a una terminal o línea de comandos. También permite almacenar variables de entorno y publicar proyectos (esto te puede servir para construir un portafolio).

Para trabajar con Deepnote nos dirigimos a [deepnote.com](http://deepnote.com). Tendremos que iniciar sesión y lo podremos hacer con Google o con Github. Una vez iniciada sesión veremos nuestro Dashboard.

Deepnote trabaja a nivel de proyectos. Para crear un proyecto hacemos clic en el botón `+ New Project`. Esto creará el proyecto con nuestro primer Notebook.

Para ejecutar los bloques de código de un Notebook hacemos clic en `> Run notebook` en la parte superior.

Para subir archivos simplemente los arrastramos desde nuestro equipo al panel izquierdo donde se encuentra el árbol de archivos (Files).

En la barra lateral, en `Integrations` (ícono de 4 cuadrados), podemos seleccionar las integraciones con otras apps que queramos, haciendo clic en `Add` en la integración. Dependiendo de la integración se deben seguir algunos pasos. Por ejemplo, para integrar con Google Drive debemos autorizar a Drive y luego darle un nombre a la integración. Después de esto, la integración aparecerá arriba en la parte de Active Integrations.

Algunas integraciones nos proveen de un botón `How to use` para saber como usarlas. Por ejemplo, para acceder a nuestro drive usamos la ruta `/datasets/drive`

Al igual que Google Colab (y otras herramientas), Deepnote provee a los proyectos librerías de comunes de ciencias de datos.

Una diferencia importante con Colab, es que en Colab podemos agregar solo bloques de código o de texto cuando nos posicionamos entre dos bloques. En Deepnote, tenemos las opciones Block y Code, donde en Block se nos muestra una lista extensa con más tipos de bloque.

Un bloque especial es el de Graph, el cuál nos permite visualizar una gráfica de un dataframe de forma interactiva, con un menú de opciones al lado.

Deepnote también tiene una barra de comandos. Para abrirla usamos el atajo `Ctrl + P` (nota que es diferente al de Colab).

Podemos publicar nuestro proyecto. Para ello en la barra de navegación hacemos clic en Share y activamos la opción Share Project. Una vez publicado, cualquiera que tenga el link del proyecto podrá abrirlo y verlo. También podemos especificar que pueden hacer con el Notebook (si pueden solo verlo o también pueden editarlo).

En este mismo menú también podemos administrar los colaboradores del proyecto. La sección Publishing sirve para publicar el proyecto pero como si fuese una página web, la cuál podremos compartir en redes sociales.

En la barra lateral, en la opción `Terminal` (ícono de terminal) podemos ver las terminales de nuestro proyecto. Al principio no habrá ninguna, pero una vez agregada una podremos usar una terminal en nuestro proyecto.

# Entorno de desarrollo con Anaconda

## ¿Qué son los ambientes virtuales?

¡Es muy probable que, en tu día a día, no solo te encuentres trabajando en un único proyecto, sino en varios!

Cada proyecto en el que trabajemos va a requerir sus propias dependencias (con sus respectivas versiones) o su propia versión de Python. Para que los proyectos no se pisen entre sí, y que podamos trabajarlos todos en el mismo equipo, podemos usar ambientes virtuales.

Un ambiente virtual es un lugar donde un proyecto puede tener sus propias dependencias, independientemente de las dependencias que tengan los demás proyectos.

## Instalar Conda a través de la terminal

Conda es una herramienta para crear y manipular ambientes virtuales de Python. De hecho, es un programa para la gestión de paquetes, dependencias y entornos para cualquier lenguaje: Python, R, Ruby, Lua, Scala, Java, JavaScript, C, C++, Fortran y más.

Conda es multiplataforma, es decir, funciona en cualquier sistema operativo.

Para instalar Conda debemos instalar primero Miniconda, la cuál es una versión minificada de Conda, pero que trae consigo una versión de Python.

Anaconda es una dependencia más grande, dentro de la cuál Miniconda está incluida, y que incluye una serie de paquetes de uso común en Ciencias de Datos (como las que se tienen inicialmente al crear un Notebook en Colab o Deepnote).

**Instalación de Conda**

Anaconda se puede instalar de dos formas: mediante un instalador gráfico (descarga [aquí](https://www.anaconda.com/products/individual-d)) o desde la terminal.

Una vez dentro de la [página](https://www.anaconda.com/products/individual-d), hacemos clic en Get Additional Installers. Esto nos llevará a unos enlaces para descargar el instalador acorde a nuestro sistema operativo. No haremos clic directamente en ninguno sino que haremos clic derecho y Copiar link al que nos corresponde (dependiendo de nuestro sistema operativo).

Ahora en la terminal descargamos el instalador con el siguiente comando:

```bash
wget -O anaconda.sh <link_copiado>

# para linux (el link puede haberse actualizado)
wget -O anaconda.sh https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
```

Una vez descargado el instalador lo ejecutamos:

```bash
bash anaconda.sh
```

Seguimos las instrucciones que se nos indiquen. Cuando se nos muestren los términos de licencia tendremos que ir presionando `Enter` para seguir leyendo hasta llegar a la pregunta de aceptación, la cuál responderemos escribiendo `yes`

Finalmente, después de hacerse la instalación se nos preguntará si queremos que conda inicie, y respondemos `yes`. Con esto, conda se iniciará y te posicionará en un ambiente virtual llamado `base` (cuyo nombre verás al lado del cursor de tu terminal, entre paréntesis, y si no, reinicia tu terminal).

Con `conda info` podes obtener información actual de tu conda, como el ambiente en el que te encuentras actualmente.

Conda ya trae Jupyter Notebook instalado. Para usarlo ejecutamos `jupyter-notebook`. Esto crea un servidor web con Jupyter, y (no siempre) abrirá una nueva ventana en el navegador con jupyter listo para usar (si no hace esto, puedes abrir jupyter manualmente usando los links que aparecen en la terminal, de preferencia el que empieza con localhost:8888). Al principio veremos un explorador de archivos mostrándonos los archivos de la carpeta donde ejecutaste el comando anterior.

En el navegador tendremos una interfaz base para trabajar con Notebooks.

La terminal quedará en un proceso al ejecutar `jupyter-notebok` ya que está ejecutando un servidor web. Para terminar el proceso presionamos `Ctrl + C` y confirmamos con `y` (no te tardes mucho).

## Conda: crear y actualizar ambientes

Cuando instalamos anaconda, este crea un ambiente virtual llamado `base` al cuál entramos cada vez que abrimos la terminal.

Para ver todos los ambientes creados en el equipo: `conda env list`

Para crear un ambiente: `conda create --name <nombre> python=<version> <dep1≥=<ver1> <dep2>=<ver2> ...`

- Se puede omitir la versión de Python, haciendo que se instale la más reciente.
- Cada `dep` es una dependencia y podemos especificar o no la versión de cada una de esta a instalar.

Para activar un ambiente: `conda activate <nombre>`

Para ver las dependencias de un ambiente: `conda list`

- `conda list <nombre>`: muestra información del paquete con el nombre indicado. Para ver la información de Python se usa `python`

Para actualizar una dependencia a la versión más reciente: `conda update <nombre>`

Para instalar una dependencia: `conda install <nombre>=<version>`

- La versión puede omitirse.
- Si se indica la versión, esta debe ser válida para la versión de python en el ambiente.

Para actualizar Python en el ambiente se usa `python` como `nombre`, tanto en `coda update` como en `conda install`

Para crear un ambiente a partir de otro: `conda create --name <nombre_ambiente_nuevo> --copy <nombre_ambiente_anterior>`

## Conda: eliminar ambientes y librerías

Para desinstalar un paquete: `conda remove <nombre>`

Para eliminar un ambiente: `conda env remove --name <nombre>`

- No puedes eliminar un ambiente si estas en el mismo. Para hacer esto primero debes desactivarlo.

Para desactivar el ambiente actual: `conda deactivate`

- Esto nos mueve del ambiente actual al `base`

## Conda: comandos avanzados

Cuando instalamos un paquete en un ambiente, conda busca en repositorios o canales suyos y los descarga. Estos canales no tienen todos los paquetes que realmente existen, por lo que por defecto algunos paquetes (como `boltons`) no estarán disponibles. Si tratamos de instalar un paquete así, conda nos dirá que no lo encontró y nos mostrará la lista de canales donde buscó el paquete (cada canal es una URL).

Para resolver esto debemos agregar más canales. Para saber que canal agregar nos dirigimos a [https://anaconda.org/](https://anaconda.org/) y en la barra de búsqueda buscamos nuestro paquete.

Los resultados de esta búsqueda serán el paquete anterior pero prefijado con distintos nombres de canales (por ejemplo para boltons tendremos conda-forge, lightsource2-tag, entre otros). Debemos seleccionar el canal adecuado para nuestra plataforma.

Para instalar un paquete desde un canal específico: `conda install --channel <nombre_canal> <nombre_paquete>`

Podemos hacer seguimiento a los diferentes estados o versiones de un ambiente, los cuáles reciben formalmente el nombre de revisiones.

Para listar las revisiones de un ambiente: `conda list --revision`

Para volver a una revisión anterior: `conda install --revision <n>`

- `n` es el número de la revisión, el cuál se obtiene con `conda list --revision`

Para exportar un ambiente: `conda env export`

- Esto imprime la información en terminal.
- `conda env export --no-builds` exporta sin mostrar los builds de los paquetes (que muchas veces no importan mucho).
- `conda env export --from-history` exporta solo mostrando las dependencias que se instalaron manualmente, es decir, no muestra las subdependencias.
- `conda env export --file <nombre>` exporta a un archivo indicado (mayormente llamado ***environment.yml***).

Para crear un ambiente a partir de un archivo ***.yml***: `conda env create --file <nombre>`

## Acelerar la creación de ambientes virtuales con Mamba

Mamba es una re implementación de Conda para crear ambientes virtuales.

Mamba permite resolver (descargar) dependencias en paralelo.

Mamba se instala a través de Conda con `conda install --channel conda-forge mamba`

- Este comando lo debemos ejecutar mientras estamos en el ambiente `base`

Para obtener la ayuda de mamba: `mamba --help`

Los comandos de conda para instalar o crear ambientes a partir de un archivo que aprendimos anteriormente también sirven en mamba, simplemente usamos `mamba` en lugar de `conda`