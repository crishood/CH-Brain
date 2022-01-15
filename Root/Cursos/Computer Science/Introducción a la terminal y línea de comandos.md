# Introducción a la terminal y línea de comandos

Created: January 6, 2022 10:07 AM
Minded: Si
Tag: #computerscience

## 01. Introducción

La terminal es una herramienta indispensable para ser un desarrollador. Esta ventana nos brinda varios beneficios.

### ¿Por qué debo aprender a manejar la terminal?

- Flexibilidad
- Control
- El sistema operativo del internet se basa en unix / linux, así que para muchas cosas avanzadas no hay interfaz.
- Procesos eficaces y rápidos
- Automatizar cosas

## 02. Aprendiendo a caminar en la terminal

Todo empieza en un `/` así se le denomina  a la raíz.

### ¿Qué es un comando?

> *Un comando es una acción escrita, generalmente, a través de una terminal y emulada por una shell para ser ejecutada por nuestro sistema operativo.*
> 

### **Anatomía de un comando**

Todos los comandos se componen de:

- Un **nombre** con el que se invoca el comando.
- **Opciones** que modifican el comportamiento del comando. Son opcionales.
- **Argumentos** sobre los que actúa el comando. También opcionales.

![Untitled](Root/Cursos/Computer%20Science/Introducción%20a%20la%20terminal%20y%20línea%20de%20comandos/Untitled.png)

Anatomía del comando `ls` que lista las carpetas y archivos (en este caso de la carpeta `/usr/local`). La opción `a` muestra los archivos ocultos y `l` muestra los detalles de cada carpeta/archivo.

Para ver las opciones y los argumentos que soporta un comando incluido en el sistema operativo (al menos en Linux/Mac) se usa el comando `man <nombre_del_comando>`. Para comandos hechos por terceros (p.e. `git`, `rails`, etc.), se usa `<nombre_del_comando> --help` o `<nombre_del_comando> -h`.

### Comandos básicos

```bash
# Listar archivos
ls

# Listar archivos con peso
ls -lh

# Listar archivos ocultos
ls -a

# Identificar la ruta
pwd

# Movernos entre directorios 
cd

# Movernos con una ruta desde el directorio actual
cd ./ruta/relativa/

# Movernos un directorio arriba en la jerarquía
cd ../

# Crear un directorio
mkdir

# Copiar un archivo
cp

# Borrar un archivo
rm

# Mover un archivo
mv

# Borrar un directorio
rmdir

#Limpiar la terminal
clear
```

## 03. **Manipulando archivos y directorios**

```bash
# Ordenar por tamaño
ls -lS

# Ordenar en reversa
ls -lr

# Desplegar árbol
tree

# Desplegar árbol de 2 niveles 
tree -L 2

# Crear directorio
mkdir directorio1 directorio2 directorio3

#Crear archivo
touch file1 file2 file3

# Copiar archivo
cp file1 file_copia

# Mover archivo o renombrarlo
mv file1 file2

# Borrar archivos con mensaje de confirmación
rm -i file1

# Borrar directorios
rm -r dir1

```

## 04. **Explorando el contenido de nuestros archivos**

```bash
# Para ver las primeras o últimas n líneas
head file1 -n 10
tail file1 -n 20

# Para ver el texto de un archivo
less file1.md

# Para abrir una carpeta en linux
nautilus

# Para abrir una aplicación
open

```

## 05. Qué es un comando

Un comando puede ser 4 cosas:

- Un programa ejecutable
- Un comando de utilidad de la shell
- Una función de shell
- Un alias

```bash
# Para crear un alias
alias l="ls -lS"

# Para pedir ayuda sobre un comando
help ls

man ls

info ls

whatis ls
```

¿Pero qué es shell?

Shell es un intérprete de órdenes para el computador.

Dependiendo del tipo de interfaz que empleen, los *shells* pueden ser:

- [De líneas texto](https://es.wikipedia.org/wiki/L%C3%ADnea_de_comandos) (**CLI**, *Command-Line Interface*, interfaz de línea de comandos),
- [Gráficos](https://es.wikipedia.org/wiki/Interfaz_gr%C3%A1fica_de_usuario) (**GUI**, *Graphical User Interface*, interfaz gráfica de usuario),
- [De lenguaje natural](https://es.wikipedia.org/wiki/Interfaz_natural_de_usuario) (**NUI**, *Natural User Interface*, interfaz natural de usuario).

Los *shell* son necesarios para invocar o ejecutar los distintos programas disponibles en la [computadora](https://es.wikipedia.org/wiki/Computadora). Un ejemplo de Shell en Windows es [Power Shell](https://es.wikipedia.org/wiki/PowerShell)

## 06. **Wildcards**

Son condiciones para explorar y filtrar archivos

```bash
#Ver todos los archivos que terminen en .txt
ls *.txt

# Ver todos los archivos que empeicen por data
ls data*

# Ver todos los archivos con un caracter después de data
ls data?

#Ver todos los archivos con tres caracteres después de data
ls data???
```

## 07. **Redirecciones: cómo funciona la shell**

> tdin (0): Entrada estándar. stdout (1): Salida estándar. stderr (2): Salida de errores.
> 

```bash
comando < archivo
```

```bash
comando > archivo
```

```bash
comando >> archivo
```

```bash
comando 2> archivo
```

```bash
comando > archivo 2>&1
```

## 08. **Redirecciones: pipe operator**

Pipe operator `|`

💡Los ***filtros*** son el procesos de tomar una entrada de flujo y, realizando una conversión, es mandado a la salida de otro stream..**Definición**

> Un pipeline sirve en la construcción de comandos para generar filtros.
> 

.**Pipeline stdout a stdin**

Usamos el operado pipe `|` entre dos comando para direccionar el `stdout` del primero con el `stdin` del segundo. Cualquier comando, entre pipes, puede tener opciones o argumentos para construir filtros complejos.

Una de las ventajas de los pipes, en Linux y UNIX, es de que pueden variar y generar salidas intermedias de diferentes procesos, generando todo un trace de flujo de información.

```bash
# Comando para imprimir 
echo 'Mensaje de texto'

# Comando para concatenar
cat file1.txt file2.txt

# Pipe Operator
ls -lh | less
```

## 09. Encadenado comandos: operadores de control

```bash
# Comandos encadenados de manera síncrona
ls; mkdir folder1; cal

# Comandos encadenados de manera asíncrona
ls & cal & date

# Comandos condicionados
mkdir folder1 && cd folder1

# Comandos con or
cd folder_que_no_existe || touch archivo1.txt
```

## 10. Cómo se manejan los permisos

### Tipos de archivo

| Atributo | Tipo de archivo |
| --- | --- |
| - | Un archivo normal |
| d | Directorio |
| l | Link simbólico |
| b | Un archivo de bloque especial. Guarda información de dispositivos |

### Modos de archivos

r = read

w = write

x = execute

Modo octal

| Dueño | Grupo | World |
| --- | --- | --- |
| rwx | r-x | r-x |
| 1    1    1 | 1    0    1 | 1    0    1 |
| 7 | 5 | 5 |

### Modo simbólico

| Símbolo | Significado |
| --- | --- |
| u | Solo para el usuario. |
| g | Solo para el grupo. |
| o | Solo para otros. |
| a | Aplica para todos. |

```bash
# Comando para cambiar permisos
chmod 755 miarchivo.txt
```

## 12. Variables de entorno

```bash
printenv

# Imprimir variables de entorno
echo $HOME

# Imprimir todas las rutas de binarios de nuestro sistem
echo $Path
```

```bash
# Crear links simbólicos
ln -s Ruta/ nombre_del_link

```

### Manejadores de paquetes

Son colecciones de herramientas que descargan e instalan herramientas específicas.

### Variables de entorno

- Algunas variables son:
    - `HOME` es nuestro HOME de usuario 😆.
    - `PATH` tiene todas las rutas donde se encuentran los binarios en los que se ejecuta nuestro sistema. 🛣️ Hay varios manejadores de paquetes para binarios, pero no todas las veces se agregan a PATH, y se deben agregar a mano.
- En HOME, existe un archivo que se llama `.bashrc` que es donde está nuestra configuración de Bash. Lo podemos abrir con VS Code para modificarlo. En este archivo podemos crear alias.
- `alias <nombre>="comando"` para crear un alias útil 👀.
- `code <archivo>` para abrir un archivo de texto en VS Code desde la terminal.
- Para modificar o **crear una variable de entorno**, se hace, por ejemplo `PLATZI_MESSAGE='Hola amigos"`.
- Para agregar una ruta a la variable PATH ponemos en .bashrc `PATH=$PATH:<ruta>`, guardamos, cargamos bash en la terminal, y listo 😄.

### ¿Qué es un binario?

Un programa que se va a ejecutar

## 13. Búsquedas

```bash
# Para buscar rutas de binarios
which code
which node
which pip

# Buscar archivos que tengan algunas palabras en el nombre
find ./ -name nombre_del_archivo

#Buscar en disco S todos los archivos que tengan extensión .flp
find /mnt/s *.flp
```

**Banderas básicas**:

- **name**: Realiza una búsqueda por nombre de archivo.
- **iname**: Realiza una búsqueda por nombre de archivo sin tomar en cuenta las mayúsculas o minúsculas.
- **type**: Realiza una búsqueda por tipo de archivo, f(files) y d(directories) que son los más comunes.
- **size**: Realiza una búsqueda por el tamaño de archivo y/o directorio.

## 14. grep

Grep es un comando súper poderoso para buscar cadenas de caracteres específicas dentro de archivos de texto.

```bash
# Buscar la palabra "Tower" dentro del archivo movies.csv
grep Towers movies.csv

# Contar la cantidad de veces que aparece la palabra "the" ignorando las mayúsculas y minúsculas 
grep -ci the movies.csv
```

```bash
# Contar número de palabras
wc movies.csv
```

## 15. Comandos de red

```bash
# Para ver la máscara de red, puerto de transmisión
ifconfig 

# Con este comando podemos ver si una ip está activa
ping www.crishood.com

# Traer el html de una página
curl www.crishood.com

# Descargar el html de una página
wget crishood.github.io

# Trazar la ruta de computadoras que tenemos que seguir para llegar a una página
traceroute www.crishood.com

# Mostrar dispositivos de red
netstat –i
```

## 16. Comprimir

```bash
#Para comprimir en tar
tar -cvf [nombre archivo].tar [dir documento]

#Para descomprimir
tar -xvf [Nombre del archivo que queremos desempaquetar.tar]

# Para comprimir en zip
zip -r [Nombre del archivo comprimido].zip [Nombre del archivo que queremos comprimir]

# Para descomprimir en zip
unzip [Nombre del archivo que queremos descomprimir].zip

```

c: create
v: verbose list files processed
f: files (regular file)

## 17. Procesos

Todo proceso tiene un id que se llama PID

```bash
# Para ver procesos en ejecución
ps

# Para detener un proceso
kill [PID]

# Ver procesos más pesados
top 
```

`ctrl + c` termina un proceso

`ctrl + z` pausa un proceso

```bash
# Para mover procesos al foreground
fg [PID]

# Para mover procesos al background
bg [PID]
```